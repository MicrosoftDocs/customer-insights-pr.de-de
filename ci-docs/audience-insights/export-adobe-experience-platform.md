---
title: Customer Insights-Daten in Adobe Experience Platform exportieren
description: Erfahren Sie, wie Sie Zielgruppen-Insights-Segmente in Adobe Experience Platform verwenden.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596268"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Customer Insights-Segmente in Adobe Experience Platform verwenden (Verwenden)

Als Benutzer von Zielgruppen-Insights für Dynamics 365 Customer Insights haben Sie möglicherweise Segmente erstellt, um Ihre Marketingkampagnen effizienter zu gestalten, indem Sie relevante Zielgruppen ansprechen. Um ein Segment aus Zielgruppen-Insights in Adobe Experience Platform und Anwendungen wie Adobe Campaign Standard zu verwenden, müssen Sie einige in diesem Artikel beschriebene Schritte ausführen.

:::image type="content" source="media/AEP-flow.png" alt-text="Prozessdiagramm der in diesem Artikel beschriebenen Schritte.":::

## <a name="prerequisites"></a>Anforderungen

-   Dynamics 365 Customer Insights-Lizenz
-   Adobe Experience Platform-Lizenz
-   Adobe Campaign Standard-Lizenz
-   Azure Blob Storage-Konto

## <a name="campaign-overview"></a>Kampagnenübersicht

Schauen wir uns eine fiktive Beispielkampagne an, um besser zu verstehen, wie Sie Segmente aus Zielgruppen-Insights in Adobe Experience Platform verwenden können.

Nehmen wir an, Ihr Unternehmen bietet Ihren Kunden in den USA einen monatlichen, abonnementbasierten Service an. Sie möchten Kunden identifizieren, deren Abonnements in den Nächsten acht Tagen erneuert werden sollen, deren Abonnement jedoch noch nicht verlängert wurde. Um diese Kunden zu halten, möchten Sie ihnen mithilfe von Adobe Experience Platform ein Werbeangebot per E-Mail senden.

In diesem Beispiel möchten wir die Werbe-E-Mail-Kampagne einmal ausführen. Dieser Artikel behandelt nicht den Anwendungsfall, die Kampagne mehr als einmal auszuführen.

## <a name="identify-your-target-audience"></a>Identifizieren Sie Ihre Zielgruppe

In unserem Szenario gehen wir davon aus, dass die E-Mail-Adressen der Kunden in Zielgruppen-Insights verfügbar sind und ihre Werbepräferenzen analysiert wurden, um Mitglieder des Segments zu identifizieren.

Das [Segment, das Sie in Zielgruppen-Insights definiert haben](segments.md) wird **ChurnProneCustomers** genannt und Sie planen, diesen Kunden die E-Mail-Aktion zu senden.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot der Segmentseite mit dem erstellten ChurnProneCustomers-Segment.":::

Die Angebots-E-Mail, die Sie versenden möchten, enthält das Vorname, Nachname, und das Abonnement-Enddatum des Kunden. Es informiert die Kunden über den Rabatt, den sie erhalten, wenn sie ihr Abonnement vor Ablauf verlängern.

## <a name="export-your-target-audience"></a>Exportieren Sie Ihre Zielgruppe

Nachdem unsere Zielgruppe identifiziert wurde, können wir den Export von Zielgruppen-Insights in ein Azure Blob-Speicherkonto konfigurieren.

1. Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Ziele exportieren**.

1. Wählen Sie in der Kachel **Azure Blob-Speicher** **Einrichten** aus.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfigurationskachel für Azure Blob-Speicher.":::

1. Geben Sie einen **Anzeigename** für dieses neue Exportziel ein und geben Sie dann **Kontoname**, **Kontoschlüssel**, und **Container** des Azure Blob-Speicherkontos ein, in das Sie das Segment exportieren möchten.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot der Speicherkontokonfiguration. "::: 

   - Weitere Informationen zum Suchen des Azure-Blobspeicherkontonamens und des Kontoschlüssels finden Sie unter [Verwalten von Speicherkontoeinstellungen im Azure-Portal](/azure/storage/common/storage-account-manage).

   - Informationen zum Erstellen eines Containers finden Sie unter [Erstellen eines Containers](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Klicken Sie auf **Weiter**.

1. Wählen Sie die Segmente aus, die Sie exportieren möchten. In diesem Beispiel ist es **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot der Benutzeroberfläche für die Segmentauswahl mit ausgewähltem ChurnProneCustomers-Segment.":::

1. Wählen Sie **Speichern** aus.

Nachdem Sie das Exportziel gespeichert haben, finden Sie es auf **Administrator** > **Exporte** > **Meine Exportziele**.

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Screenshot mit hervorgehobener Exportliste und Beispielsegment.":::

Sie können jetzt [das Segment nach Bedarf exportieren](export-destinations.md#export-data-on-demand). Der Export wird auch bei jeder [geplanten Aktualisierung](system.md) durchgeführt.

> [!NOTE]
> Stellen Sie sicher, dass die Anzahl der Datensätze im exportierten Segment innerhalb des zulässigen Grenzwerts Ihrer Adobe Campaign Standard-Lizenz liegt.

Exportierte Daten werden in dem oben konfigurierten Azure Blob-Speichercontainer gespeichert. Der folgende Ordnerpfad wird automatisch in Ihrem Container erstellt:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Beispiel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Das *model.json* für die exportierten Entitäten befindet sich auf der *%ExportDestinationName%*-Ebene.

Beispiel Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definieren Sie das Experience Data Model (XDM) in Adobe Experience Platform

Bevor die aus Zielgruppe-Insights exportierten Daten in Adobe Experience Platform verwendet werden können, müssen Sie das Experience Data Model-Schema definieren und [die Daten für das Echtzeit-Kundenprofil konfigurieren](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Lernen Sie, [was XDM ist](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) und verstehen Sie die [Grundlagen der Schemakomposition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importieren Sie Daten in die Adobe Experience Platform

Nachdem alles vorhanden ist, müssen wir die vorbereiteten Zielgruppen-Daten aus Zielgruppen-Insights in Adobe Experience Platform importieren, um Profile zu erstellen.

Zuerst, [erstellen Sie eine Azure Blob Storage-Quellverbindung](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Nachdem Sie die Quellverbindung definiert haben, [konfigurieren Sie einen Dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) für eine Cloud-Speicher-Batch-Verbindung zum Importieren der Segmentausgabe von Zielgruppen-Insights in Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Erstellen Sie eine Zielgruppe in Adobe Campaign Standard

Um die E-Mail für diese Kampagne zu senden, verwenden wir Adobe Campaign Standard. Nach dem Importieren der Daten in Adobe Experience Platform müssen wir [eine Zielgruppe erstellen](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard unter Verwendung der Daten in Adobe Experience Platform.

Lernen wie man, [den Segment Builder verwendet](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard, um ein Publikum basierend auf den Daten in Adobe Experience Platform zu definieren.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Erstellen und senden Sie die E-Mail mit Adobe Campaign Standard

Erstellen Sie den E-Mail-Inhalt und dann [testen und senden](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) Sie Ihre E-Mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Beispiel-E-Mail mit Verlängerungsangebot von Adobe Campaign Standard.":::