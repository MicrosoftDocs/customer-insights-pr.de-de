---
title: Customer Insights-Daten in Adobe Campaign Standard exportieren
description: Erfahren Sie, wie Sie Zielgruppen-Insights-Segmente in Adobe Campaign Standard verwenden.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596314"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Customer Insights-Segmente in Adobe Campaign Standard verwenden (Verwenden)

Als Benutzer von Zielgruppen-Insights für Dynamics 365 Customer Insights haben Sie möglicherweise Segmente erstellt, um Ihre Marketingkampagnen effizienter zu gestalten, indem Sie relevante Zielgruppen ansprechen. Um ein Segment aus Zielgruppen-Insights in Adobe Experience Platform und Anwendungen wie Adobe Campaign Standard zu verwenden, müssen Sie einige in diesem Artikel beschriebene Schritte ausführen.

:::image type="content" source="media/ACS-flow.png" alt-text="Prozessdiagramm der in diesem Artikel beschriebenen Schritte.":::

## <a name="prerequisites"></a>Anforderungen

-   Dynamics 365 Customer Insights-Lizenz
-   Adobe Campaign Standard-Lizenz
-   Azure Blob Storage-Konto

## <a name="campaign-overview"></a>Kampagnenübersicht

Schauen wir uns eine fiktive Beispielkampagne an, um besser zu verstehen, wie Sie Segmente aus Zielgruppen-Insights in Adobe Experience Platform verwenden können.

Nehmen wir an, Ihr Unternehmen bietet Ihren Kunden in den USA einen monatlichen, abonnementbasierten Service an. Sie möchten Kunden identifizieren, deren Abonnements in den Nächsten acht Tagen erneuert werden sollen, deren Abonnement jedoch noch nicht verlängert wurde. Um diese Kunden zu halten, möchten Sie ihnen mithilfe von Adobe Campaign Standard ein Werbeangebot per E-Mail senden.

In diesem Beispiel möchten wir die Werbe-E-Mail-Kampagne einmal ausführen. Dieser Artikel behandelt nicht den Anwendungsfall, die Kampagne mehr als einmal auszuführen. Zielgruppen-Insights und Adobe Campaign Standard können jedoch so konfiguriert werden, dass sie auch für ein wiederkehrendes Kampagnenszenario funktionieren.

## <a name="identify-your-target-audience"></a>Identifizieren Sie Ihre Zielgruppe

In unserem Szenario gehen wir davon aus, dass die E-Mail-Adressen der Kunden in Zielgruppen-Insights verfügbar sind und ihre Werbepräferenzen analysiert wurden, um Mitglieder des Segments zu identifizieren.

Das [Segment, das Sie in Zielgruppen-Insights definiert haben](segments.md) wird **ChurnProneCustomers** genannt und Sie planen, diesen Kunden die E-Mail-Aktion zu senden.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot der Segmentseite mit dem erstellten ChurnProneCustomers-Segment.":::

Die Angebots-E-Mail, die Sie versenden möchten, enthält das Vorname, Nachname, und das Abonnement-Enddatum des Kunden. Es informiert die Kunden über den Rabatt, den sie erhalten, wenn sie ihr Abonnement vor Ablauf verlängern.

## <a name="export-your-target-audience"></a>Exportieren Sie Ihre Zielgruppe

Nachdem unsere Zielgruppe identifiziert wurde, können wir den Export von Zielgruppen-Insights in ein Azure Blob-Speicherkonto konfigurieren.

1. Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Ziele exportieren**.

1. In der Kachel **Adobe Campaign** wählen Sie **Einrichten**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigurationskachel für Adobe Campaign Standard.":::

1. Geben Sie einen **Anzeigename** für dieses neue Exportziel ein und geben Sie dann **Kontoname**, **Kontoschlüssel**, und **Container** des Azure Blob-Speicherkontos ein, in das Sie das Segment exportieren möchten.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot der Speicherkontokonfiguration. "::: 

   - Weitere Informationen zum Suchen des Azure-Blobspeicherkontonamens und des Kontoschlüssels finden Sie unter [Verwalten von Speicherkontoeinstellungen im Azure-Portal](/azure/storage/common/storage-account-manage).

   - Informationen zum Erstellen eines Containers finden Sie unter [Erstellen eines Containers](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Klicken Sie auf **Weiter**.

1. Wählen Sie die Segmente aus, die Sie exportieren möchten. In diesem Beispiel ist es **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot der Benutzeroberfläche für die Segmentauswahl mit ausgewähltem ChurnProneCustomers-Segment.":::

1. Klicken Sie auf **Weiter**.

1. Jetzt kartieren wir die **Quelle**-Felder aus dem Segment Zielgruppen-Insights bis zu den **Ziel**-Feldnamen im Adobe Campaign Standard-Profilschema.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Feldzuordnung für den Adobe Campaign Standard-Connector.":::

   Wenn Sie weitere Attribute hinzufügen möchten, wählen Sie **Attribut hinzufügen**. Der Zielname kann sich vom Namen des Quellfelds unterscheiden, sodass Sie die Segmentausgabe von Zielgruppen-Insights weiterhin Adobe Campaign Standard zuordnen können, wenn die Felder in beiden Systemen nicht denselben Namen haben.

   > [!NOTE]
   > Die E-Mail-Adresse wird als Identitätsfeld verwendet. Sie können jedoch jede andere Kennung aus Ihrem Kundenprofil für Zielgruppen-Insights verwenden, um Daten Adobe Campaign Standard zuzuordnen.

1. Wählen Sie **Speichern** aus.

Nachdem Sie das Exportziel gespeichert haben, finden Sie es auf **Administrator** > **Exporte** > **Meine Exportziele**.

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Screenshot mit hervorgehobener Exportliste und Beispielsegment.":::

Sie können jetzt [das Segment nach Bedarf exportieren](export-destinations.md#export-data-on-demand). Der Export wird auch bei jeder [geplanten Aktualisierung](system.md) durchgeführt.

> [!NOTE]
> Stellen Sie sicher, dass die Anzahl der Datensätze im exportierten Segment innerhalb des zulässigen Grenzwerts Ihrer Adobe Campaign Standard-Lizenz liegt.

Exportierte Daten werden in dem oben konfigurierten Azure Blob-Speichercontainer gespeichert. Der folgende Ordnerpfad wird automatisch in Ihrem Container erstellt:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Beispiel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Adobe Campaign Standard konfigurieren

Wenn ein Segment aus Zielgruppen-Insights exportiert wird, enthält es die Spalten, die Sie beim Definieren des Exportziels im vorherigen Schritt ausgewählt haben. Diese Daten können verwendet werden, um [Profile in Adobe Campaign Standard zu erstellen](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Um das Segment in Adobe Campaign Standard zu verwenden, müssen Sie das Profilschema in Adobe Campaign Standard um zwei zusätzliche Felder erweitern. Lernen wie man [die Profilressource erweitert](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) mit neuen Feldern in Adobe Campaign Standard.

In unserem Beispiel sind diese Felder *Segmentname und Segmentdatum (optional).*

Wir werden diese Felder verwenden, um die Profile in Adobe Campaign Standard zu identifizieren, auf die wir für diese Kampagne abzielen möchten.

Wenn in Adobe Campaign Standard keine anderen Datensätze als die zu importierenden vorhanden sind, können Sie diesen Schritt überspringen.

## <a name="import-data-into-adobe-campaign-standard"></a>Daten in Adobe Campaign Standard importieren

Nachdem alles vorhanden ist, müssen wir die vorbereiteten Zielgruppen-Daten aus Zielgruppen-Insights in Adobe Campaign Standard importieren, um Profile zu erstellen. Lernen Sie, [wie Sie Profile in Adobe Campaign Standard importieren](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) mihilfe eines Workflows.

Der Import-Workflow in der Abbildung unten wurde so konfiguriert, dass er alle 8 Stunden ausgeführt wird. Er sucht nach exportierten Zielgruppen-Insights-Segmenten (CSV-Datei im Azure Blob-Speicher). Der Workflow extrahiert den Inhalt der CSV-Datei in einer angegebenen Spaltenreihenfolge. Dieser Workflow wurde entwickelt, um eine grundlegende Fehlerbehandlung durchzuführen und sicherzustellen, dass jeder Datensatz eine E-Mail-Adresse hat, bevor die Daten in Adobe Campaign Standard hydratisiert werden. Der Workflow extrahiert auch den Segmentnamen aus dem Dateinamen, bevor er in ACS-Profildaten aktualisiert wird.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Screenshot eines Import-Workflows in der Benutzeroberfläche von Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Rufen Sie die Zielgruppe in Adobe Campaign Standard ab

Sobald die Daten in Adobe Campaign Standard importiert wurden, [können Sie einen Workflow erstellen](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) und Kunden [abfragen](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) basierend auf dem *Segmentname* und *Segmentdatum* um Profile auszuwählen, die für unsere Beispielkampagne identifiziert wurden.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Erstellen und senden Sie die E-Mail mit Adobe Campaign Standard

Erstellen Sie den E-Mail-Inhalt und dann [testen und senden](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) Sie Ihre E-Mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Beispiel-E-Mail mit Verlängerungsangebot von Adobe Campaign Standard.":::