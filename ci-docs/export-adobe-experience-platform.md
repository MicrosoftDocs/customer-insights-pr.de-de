---
title: Exportieren Sie Customer Insights-Daten nach Adobe Experience Platform
description: Erfahren Sie, wie Sie Customer Insights Segmente in Adobe Experience Platform verwenden können.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 42a4e0c6bce67a63b449a541299620ef2f4a3259
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647260"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Customer Insights Segmente in Adobe Experience Platform nutzen (Vorschau)

Als Benutzer von Dynamics 365 Customer Insights haben Sie vielleicht Segmente erstellt, um Ihre Marketingkampagnen effizienter zu gestalten, indem Sie relevante Zielgruppen ansprechen. Um ein Segment aus Customer Insights in Adobe Experience Platform und Anwendungen wie Adobe Campaign Standard zu verwenden, müssen Sie ein paar Schritte befolgen, die in diesem Artikel beschrieben werden.

:::image type="content" source="media/AEP-flow.png" alt-text="Prozessdiagramm der in diesem Artikel beschriebenen Schritte.":::

## <a name="prerequisites"></a>Anforderungen

-   Dynamics 365 Customer Insights-Lizenz
-   Adobe Experience Platform-Lizenz
-   Adobe Campaign Standard Linzenz
-   Azure Blob Storage-Konto

## <a name="campaign-overview"></a>Kampagnenübersicht

Um besser zu verstehen, wie Sie Segmente aus Customer Insights in Adobe Experience Platform verwenden können, lassen Sie uns eine fiktive Beispielkampagne betrachten.

Nehmen wir an, Ihr Unternehmen bietet Ihren Kunden in den USA einen monatlichen, abonnementbasierten Service an. Sie möchten Kunden identifizieren, deren Abonnements in den Nächsten acht Tagen erneuert werden sollen, deren Abonnement jedoch noch nicht verlängert wurde. Um diese Kunden zu halten, möchten Sie ihnen ein Werbeangebot per E-Mail senden, indem Sie Adobe Experience Platform verwenden.

In diesem Beispiel möchten wir die Werbe-E-Mail-Kampagne einmal ausführen. Dieser Artikel behandelt nicht den Anwendungsfall, die Kampagne mehr als einmal auszuführen.

## <a name="identify-your-target-audience"></a>Identifizieren Sie Ihre Zielgruppe

In unserem Szenario gehen wir davon aus, dass die E-Mail-Adressen der Kunden in Customer Insights verfügbar sind und ihre Werbepräferenzen analysiert wurden, um Mitglieder des Segments zu identifizieren.

Das [Segment, das Sie in Customer Insights](segments.md) definiert haben, heißt **ChurnProneCustomers** und Sie planen, diesen Kunden die E-Mail-Werbung zu schicken.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot der Segmentseite mit dem erstellten ChurnProneCustomers-Segment.":::

Die Angebots-E-Mail, die Sie versenden möchten, enthält das Vorname, Nachname, und das Abonnement-Enddatum des Kunden. Es informiert die Kunden über den Rabatt, den sie erhalten, wenn sie ihr Abonnement vor Ablauf verlängern.

## <a name="export-your-target-audience"></a>Exportieren Sie Ihre Zielgruppe

Nachdem wir unsere Zielgruppe identifiziert haben, können wir den Export aus Customer Insights in ein Azure Blob-Storage-Konto konfigurieren.

### <a name="configure-a-connection"></a>Verbindung konfigurieren

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Azure Blob Storage** oder wählen Sie **Einrichten** in der Kachel **Azure Blob Storage**, um die Verbindung zu konfigurieren.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfigurationskachel für Azure Blob-Speicher."::: 

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie die **Kontobezeichnung**, **Kontoschlüssel** und **Container** für Ihr Blob Storage-Konto ein, in das Sie das Segment exportieren möchten.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot der Speicherkontokonfiguration. "::: 
   
    - Weitere Informationen zum Ermitteln des Blob Storage Kontonamens und des Kontoschlüssels finden Sie unter [Verwalten Sie die Speicherkontoeinstellungen im Azure-Portal](/azure/storage/common/storage-account-manage).
    - Informationen zum Erstellen eines Containers finden Sie unter [Erstellen eines Containers](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus. 

### <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Um einen neuen Export zu erstellen, wählen Sie **Export hinzufügen** aus.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Azure Blob Storage-Abschnitt aus. Wenn dieser Abschnittsname nicht angezeigt wird, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. Wählen Sie die Segmente aus, die Sie exportieren möchten. In diesem Beispiel ist es **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot der Benutzeroberfläche für die Segmentauswahl mit ausgewähltem ChurnProneCustomers-Segment.":::

1. Wählen Sie **Speichern** aus.

Nachdem Sie das Exportziel gespeichert haben, finden Sie in **Daten** > **Exporte**.

Sie können jetzt [das Segment nach Bedarf exportieren](export-destinations.md#run-exports-on-demand). Der Export wird auch bei jeder [geplanten Aktualisierung](system.md) durchgeführt.

> [!NOTE]
> Stellen Sie sicher, dass die Anzahl der Datensätze im exportierten Segment innerhalb des zulässigen Grenzwerts Ihrer Adobe Campaign Standard-Lizenz liegen.

Exportierte Daten werden in dem oben konfigurierten Azure Blob Storage Container gespeichert. Der folgende Ordnerpfad wird automatisch in Ihrem Container erstellt:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Beispiel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Das *model.json* für die exportierten Entitäten befindet sich auf der *%ExportDestinationName%*-Ebene.

Beispiel Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Experience Data Model (XDM) definieren in Adobe Experience Platform

Bevor die exportierten Daten aus Customer Insights innerhalb von Adobe Experience Platform verwendet werden können, müssen wir das Schema für das Experience Data Model definieren und [die Daten für das Echtzeit-Kundenprofil konfigurieren](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Lernen Sie, [was XDM ist](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) und verstehen Sie die [Grundlagen der Schemakomposition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Daten importieren in Adobe Experience Platform

Jetzt, wo alles an Ort und Stelle ist, müssen wir die vorbereiteten Zielgruppen-Daten von Customer Insights in Adobe Experience Platform importieren.

Zuerst, [erstellen Sie eine Azure Blob Storage-Quellverbindung](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Nachdem Sie die Quellverbindung definiert haben, [konfigurieren Sie einen Datenflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) für eine Cloud Storage Batch Verbindung, um die Segmente aus Customer Insights in Adobe Experience Platform zu importieren.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Erstellen Sie eine Zielgruppe in Adobe Campaign Standard

Zum Senden der E-Mail für diese Kampagne verwenden wir Adobe Campaign Standard. Nach dem Importieren der Daten in Adobe Experience Platform müssen wir [eine Zielgruppe erstellen](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard mit den Daten in Adobe Experience Platform.


Lernen wie man [den Segment-Builder nutzt](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard zum Definieren einer Zielgruppe basierend auf den Daten in der Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Erstellen und senden Sie die E-Mail mit Adobe Campaign Standard

Erstellen Sie den E-Mail-Inhalt und dann [testen und senden](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) Sie Ihre E-Mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Beispiel-E-Mail mit Verlängerungsangebot von Adobe Campaign Standard.":::
