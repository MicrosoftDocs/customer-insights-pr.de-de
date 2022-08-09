---
title: Export von Segmenten zu Adobe Experience Platform (Vorschauversion)
description: Erfahren Sie, wie Sie Customer Insights Segmente in Adobe Experience Platform verwenden können.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195289"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Export von Segmenten zu Adobe Experience Platform (Vorschauversion)

Exportieren Sie Segmente, die auf relevante Zielgruppen zu Adobe Experience Platform abzielen.

:::image type="content" source="media/AEP-flow.png" alt-text="Prozessdiagramm der in diesem Artikel beschriebenen Schritte.":::

## <a name="prerequisites"></a>Anforderungen

- Eine Adobe Experience Platform-Lizenz
- Eine Adobe Campaign Standard Linzenz.
- Ein [Azure Blob Storage-Konto](/azure/storage/blobs/create-data-lake-storage-account) Name und Kontoschlüssel. Zum Ermitteln des Namens und des Schlüssels finden Sie unter [Verwalten Sie die Speicherkontoeinstellungen im Azure-Portal](/azure/storage/common/storage-account-manage).
- Ein [Azure Blob Storage Container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)

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

Wir konfigurieren den Export von Customer Insights in ein Azure Blob Storage-Konto.

### <a name="set-up-connection-to-azure-blob-storage"></a>Richten Sie die Verbindung mit Azure Blob Storage ein

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Azure Blob Storage**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie die **Kontobezeichnung**, **Kontoschlüssel** und **Container** für Ihr Blob Storage-Konto ein, in das Sie das Segment exportieren möchten.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot der Speicherkontokonfiguration. ":::

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

### <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Azure Blob Storage-Abschnitt aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. Wählen Sie die Segmente aus, die Sie exportieren möchten. In diesem Beispiel ist es **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot der Benutzeroberfläche für die Segmentauswahl mit ausgewähltem ChurnProneCustomers-Segment.":::

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Stellen Sie sicher, dass die Anzahl der Datensätze im exportierten Segment innerhalb des zulässigen Grenzwerts Ihrer Adobe Campaign Standard-Lizenz liegen.

Exportierte Daten werden in dem von Ihnen konfigurierten Azure Blob Storage gespeichert. Die folgenden Ordnerpfade werden automatisch in Ihrem Container erstellt:

- Für Quell-Entitäten und vom System generierte Entitäten: 

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Beispiel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- Das *model.json* für die exportierten Entitäten befindet sich auf der *%ExportDestinationName%*-Ebene.

  Beispiel Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Experience Data Model (XDM) definieren in Adobe Experience Platform

Bevor die exportierten Daten aus Customer Insights innerhalb von Adobe Experience Platform verwendet werden können, definieren wir das Schema für das Experience Data Model und [die Daten für das Echtzeit-Kundenprofil konfigurieren](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Lernen Sie, [was XDM ist](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) und verstehen Sie die [Grundlagen der Schemakomposition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Daten importieren in Adobe Experience Platform

Importieren Sie die vorbereiteten Publikum-Daten aus Customer Insights in Adobe Experience Platform.

1. [Erstellen Sie eine Azure Blob Storage-Quellverbindung](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Konfigurieren Sie einen Datenflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) für eine Cloud Storage Batch Verbindung, um die Segmente aus Customer Insights in Adobe Experience Platform zu importieren.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Erstellen Sie eine Zielgruppe in Adobe Campaign Standard

Zum Senden der E-Mail für diese Kampagne verwenden wir Adobe Campaign Standard.

1. [Erstellen Sie eine Zielgruppe](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard unter Verwendung der Daten in Adobe Experience Platform.

1. [Segment-Builder verwenden](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard zum Definieren einer Zielgruppe basierend auf den Daten in der Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Erstellen und senden Sie die E-Mail mit Adobe Campaign Standard

Erstellen Sie den E-Mail-Inhalt und dann [testen und senden](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) Sie Ihre E-Mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Beispiel-E-Mail mit Verlängerungsangebot von Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
