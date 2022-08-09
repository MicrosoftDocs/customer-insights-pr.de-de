---
title: Customer Insights-Segmente in Adobe Campaign Standard exportieren (Vorschauversion)
description: Erfahren Sie, wie Sie Customer Insights Segmente in Adobe Campaign Standard verwenden.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195519"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Customer Insights-Segmente in Adobe Campaign Standard exportieren (Vorschauversion)

Exportieren Sie Segmente, die auf relevante Zielgruppen zu Adobe Campaign Standard abzielen.

:::image type="content" source="media/ACS-flow.png" alt-text="Prozessdiagramm der in diesem Artikel beschriebenen Schritte.":::

## <a name="prerequisites"></a>Anforderungen

- Eine Adobe Campaign Standard Linzenz.
- Ein [Azure Blob Storage-Konto](/azure/storage/blobs/create-data-lake-storage-account) Name und Kontoschlüssel. Zum Ermitteln des Namens und des Schlüssels finden Sie unter [Verwalten Sie die Speicherkontoeinstellungen im Azure-Portal](/azure/storage/common/storage-account-manage).
- Ein [Azure Blob Storage Container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)

## <a name="campaign-overview"></a>Kampagnenübersicht

Um besser zu verstehen, wie Sie Segmente aus Customer Insights in Adobe Experience Platform verwenden können, lassen Sie uns eine fiktive Beispielkampagne betrachten.

Nehmen wir an, Ihr Unternehmen bietet Ihren Kunden in den USA einen monatlichen, abonnementbasierten Service an. Sie möchten Kunden identifizieren, deren Abonnements in den Nächsten acht Tagen erneuert werden sollen, deren Abonnement jedoch noch nicht verlängert wurde. Um diese Kunden zu halten, möchten Sie ihnen ein Werbeangebot per E-Mail senden, indem Sie Adobe Campaign Standard verwenden.

In diesem Beispiel möchten wir die Werbe-E-Mail-Kampagne einmal ausführen. Dieser Artikel behandelt nicht den Anwendungsfall, die Kampagne mehr als einmal auszuführen. Customer Insights und Adobe Campaign Standard können jedoch auch für ein Szenario mit wiederkehrenden Kampagnen konfiguriert werden.

## <a name="identify-your-target-audience"></a>Identifizieren Sie Ihre Zielgruppe

In unserem Szenario gehen wir davon aus, dass die E-Mail-Adressen der Kunden in Customer Insights verfügbar sind und ihre Werbepräferenzen analysiert wurden, um Mitglieder des Segments zu identifizieren.

Das [Segment, das Sie in Customer Insights](segments.md) definiert haben, heißt **ChurnProneCustomers** und Sie planen, diesen Kunden die E-Mail-Werbung zu schicken.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot der Segmentseite mit dem erstellten ChurnProneCustomers-Segment.":::

Die Angebots-E-Mail, die Sie versenden möchten, enthält das Vorname, Nachname, und das Abonnement-Enddatum des Kunden. Es informiert die Kunden über den Rabatt, den sie erhalten, wenn sie ihr Abonnement vor Ablauf verlängern.

## <a name="export-your-target-audience"></a>Exportieren Sie Ihre Zielgruppe

### <a name="set-up-connection-to-adobe-campaign"></a>Verbindung mit Adobe Campaign einrichten

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Adobe Campaign** aus.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie die **Kontobezeichnung**, **Kontoschlüssel** und **Container** für Ihr Blob Storage-Konto ein.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot der Speicherkontokonfiguration. ":::

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

### <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. In dem Feld **Verbindung für Export** wählen Sie eine Verbindung im Bereich Adobe Campaign aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. Wählen Sie die Segmente aus, die Sie exportieren möchten. In diesem Beispiel ist es **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot der Benutzeroberfläche für die Segmentauswahl mit ausgewähltem ChurnProneCustomers-Segment.":::

1. Wählen Sie **Weiter** aus.

1. Ordnen Sie die **Quelle**-Felder aus dem Customer Insights-Segment den **Ziel**-Feldnamen im Profilschema Adobe Campaign Standard zu.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Feldzuordnung für den Adobe Campaign Standard Connector.":::

   Wenn Sie weitere Attribute hinzufügen möchten, wählen Sie **Attribut hinzufügen**. Der Zielname kann sich vom Namen des Quellfelds unterscheiden, so dass Sie die Segmentausgabe von Customer Insights trotzdem dem Adobe Campaign Standard zuordnen können, wenn die Felder in den beiden Systemen nicht den gleichen Namen haben.

   > [!NOTE]
   > Die E-Mail-Adresse wird als Identitätsfeld verwendet, aber Sie können auch jede andere Kennung aus dem Kundenprofil verwenden, um die Daten Adobe Campaign Standard zuzuordnen.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Stellen Sie sicher, dass die Anzahl der Datensätze im exportierten Segment innerhalb des zulässigen Grenzwerts Ihrer Adobe Campaign Standard-Lizenz liegen.

Exportierte Daten werden in dem oben konfigurierten Azure Blob Storage Container gespeichert. Der folgende Ordnerpfad wird automatisch in Ihrem Container erstellt: *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Beispiel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurieren von Adobe Campaign Standard

Die exportierten Segmente enthalten die Spalten, die Sie bei der Konfiguration des Exports ausgewählt haben. Diese Daten können verwendet werden, um Profile im [Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles) zu erstellen.

Um das Segment in Adobe Campaign Standard, zu verwenden, müssen wir das [Profilschema erweitern](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) in Adobe Campaign Standard, um zwei zusätzliche Felder einzuschließen.

In unserem Beispiel sind diese Felder Segmentname und Segmentdatum. Wir verwenden diese Felder, um die Profile in Adobe Campaign Standard zu erweitern, auf den wir diese Kampagne ausrichten möchten.

Wenn keine anderen Datensätze in Adobe Campaign Standard vorhanden sind, überspringen Sie diesen Schritt.

## <a name="import-data-into-adobe-campaign-standard"></a>Daten importieren in Adobe Campaign Standard

Importieren Sie die vorbereiteten Zielgruppendaten aus Customer Insights in Adobe Campaign Standard zu [Profile mit einem Workflow erstellen](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Der Import-Workflow in der Abbildung unten wurde so konfiguriert, dass er alle acht Stunden ausgeführt wird und nach exportierten Customer Insights Segmenten (.csv-Datei in Azure Blob Storage) sucht. Der Workflow extrahiert den Inhalt der CSV-Datei in einer angegebenen Spaltenreihenfolge. Dieser Workflow wurde entwickelt, um eine grundlegende Fehlerbehandlung durchzuführen und sicherzustellen, dass jeder Datensatz eine E-Mail-Adresse hat, bevor die Daten in Adobe Campaign Standard hydriert werden. Der Workflow extrahiert außerdem den Segmentnamen aus dem Dateinamen, bevor er in die Profildaten von Adobe Campaign Standard übertragen wird.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Screenshot eines Import-Workflows in der Adobe Campaign Standard-Benutzeroberfläche.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Eine Zielgruppe in Adobe Campaign Standard abrufen

Sobald die Daten in Adobe Campaign Standard, importiert wurden, können Sie [einen Workflow erstellen](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) und Kunden [abfragen](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) auf der Grundlage von Segmentname und Segmentdatum um Profile auszuwählen, die für unsere Beispielkampagne identifiziert wurden.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Erstellen und senden Sie die E-Mail mit Adobe Campaign Standard

Erstellen Sie den E-Mail-Inhalt und dann [testen und senden](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) Sie Ihre E-Mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Beispiel-E-Mail mit Verlängerungsangebot von Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
