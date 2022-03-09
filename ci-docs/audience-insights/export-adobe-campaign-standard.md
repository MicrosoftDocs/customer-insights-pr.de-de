---
title: Exportieren Sie Customer Insights-Daten nach Adobe Campaign Standard
description: Erfahren Sie, wie Sie Zielgruppenerkenntnis-Segmente in Adobe Campaign Standard verwenden.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 6b90ee53236fdd601ecdfd8e6117a15269a08084
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227757"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Customer Insights Segmente in Adobe Campaign Standard (Vorschau)

Als Nutzer von Zielgruppeneinblicken in Dynamics 365 Customer Insights haben Sie möglicherweise Segmente erstellt, um Ihre Marketingkampagnen durch die Ausrichtung auf relevante Zielgruppen effizienter zu gestalten. So verwenden Sie ein Segment aus Zielgruppenerkenntnissen in Adobe Experience Platform und Anwendungen wie Adobe Campaign Standard, Sie müssen einige der in diesem Artikel beschriebenen Schritte ausführen.

:::image type="content" source="media/ACS-flow.png" alt-text="Prozessdiagramm der in diesem Artikel beschriebenen Schritte.":::

## <a name="prerequisites"></a>Anforderungen

-   Dynamics 365 Customer Insights-Lizenz
-   Adobe Campaign Standard Linzenz
-   Azure Blob Storage-Konto

## <a name="campaign-overview"></a>Kampagnenübersicht

Um besser zu verstehen, wie Sie Segmente aus Zielgruppenerkenntnissen in Adobe Experience Platform verwenden können, schauen wir uns eine fiktive Beispielkampagne an.

Nehmen wir an, Ihr Unternehmen bietet Ihren Kunden in den USA einen monatlichen, abonnementbasierten Service an. Sie möchten Kunden identifizieren, deren Abonnements in den Nächsten acht Tagen erneuert werden sollen, deren Abonnement jedoch noch nicht verlängert wurde. Um diese Kunden zu halten, möchten Sie ihnen ein Werbeangebot per E-Mail senden, indem Sie Adobe Campaign Standard verwenden.

In diesem Beispiel möchten wir die Werbe-E-Mail-Kampagne einmal ausführen. Dieser Artikel behandelt nicht den Anwendungsfall, die Kampagne mehr als einmal auszuführen. Zielgruppenerkenntnis und Adobe Campaign Standard kann auch für ein wiederkehrendes Kampagnenszenario konfiguriert werden.

## <a name="identify-your-target-audience"></a>Identifizieren Sie Ihre Zielgruppe

In unserem Szenario gehen wir davon aus, dass die E-Mail-Adressen der Kunden in Zielgruppen-Insights verfügbar sind und ihre Werbepräferenzen analysiert wurden, um Mitglieder des Segments zu identifizieren.

Das [Segment, das Sie in Zielgruppen-Insights definiert haben](segments.md) wird **ChurnProneCustomers** genannt und Sie planen, diesen Kunden die E-Mail-Aktion zu senden.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot der Segmentseite mit dem erstellten ChurnProneCustomers-Segment.":::

Die Angebots-E-Mail, die Sie versenden möchten, enthält das Vorname, Nachname, und das Abonnement-Enddatum des Kunden. Es informiert die Kunden über den Rabatt, den sie erhalten, wenn sie ihr Abonnement vor Ablauf verlängern.

## <a name="export-your-target-audience"></a>Exportieren Sie Ihre Zielgruppe

### <a name="configure-a-connection"></a>Verbindung konfigurieren

Nachdem unsere Zielgruppe identifiziert wurde, können wir den Export von Zielgruppen-Insights in ein Azure Blob-Speicherkonto konfigurieren.

1. Gehen Sie in Zielgruppenerkenntnissen zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und dann **Adobe Campaign** aus, um die Verbindung zu konfigurieren, oder wählen Sie **Einrichten** in der Kachel **Adobe Campaign** aus.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigurationskachel für Adobe Campaign Standard.":::

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Geben Sie die **Kontobezeichnung**, **Kontoschlüssel** und **Container** des Azure Blob Storage-Kontos ein, in das Sie das Segment exportieren möchten.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot der Speicherkontokonfiguration. "::: 

   - Weitere Informationen zum Suchen des Azure-Blob Storage Kontonamen und des Kontoschlüssels finden Sie unter [Verwalten von Speicherkontoeinstellungen im Azure-Portal](/azure/storage/common/storage-account-manage).

   - Informationen zum Erstellen eines Containers finden Sie unter [Erstellen eines Containers](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

### <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Um einen neuen Export zu erstellen, wählen Sie **Export hinzufügen** aus.

1. In dem Feld **Verbindung für Export** wählen Sie eine Verbindung im Bereich Adobe Campaign aus. Wenn dieser Abschnittsname nicht angezeigt wird, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. Wählen Sie die Segmente aus, die Sie exportieren möchten. In diesem Beispiel ist es **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot der Benutzeroberfläche für die Segmentauswahl mit ausgewähltem ChurnProneCustomers-Segment.":::

1. Klicken Sie auf **Weiter**.

1. Jetzt ordnen wir das Feld **Quelle** aus dem Zielgruppenerkenntnis-Segment dem Feld **Ziel** im Adobe Campaign Standard-Profilschema hinzu.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Feldzuordnung für den Adobe Campaign Standard Connector.":::

   Wenn Sie weitere Attribute hinzufügen möchten, wählen Sie **Attribut hinzufügen**. Der Zielname kann sich vom Quellfeldnamen unterscheiden, sodass Sie weiterhin die Segmentausgabe von Zielgruppenerkenntnis in Adobe Campaign Standard zuordnen können, wenn die Felder in beiden Systemen nicht denselben Namen haben.

   > [!NOTE]
   > Die E-Mail-Adresse wird als Identitätsfeld verwendet, aber Sie können jede andere Kennung aus Ihrem Zielgruppenerkenntnis-Kundenprofil verwenden, um Daten in Adobe Campaign Standard zuzuordnen.

1. Wählen Sie **Speichern** aus.

Nachdem Sie das Exportziel gespeichert haben, finden Sie in **Daten** > **Exporte**.

Sie können jetzt [das Segment nach Bedarf exportieren](export-destinations.md#run-exports-on-demand). Der Export wird auch bei jeder [geplanten Aktualisierung](system.md) durchgeführt.

> [!NOTE]
> Stellen Sie sicher, dass die Anzahl der Datensätze im exportierten Segment innerhalb des zulässigen Grenzwerts Ihrer Adobe Campaign Standard-Lizenz liegen.

Exportierte Daten werden in dem oben konfigurierten Azure Blob Storage Container gespeichert. Der folgende Ordnerpfad wird automatisch in Ihrem Container erstellt:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Beispiel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurieren von Adobe Campaign Standard

Wenn ein Segment aus Zielgruppen-Insights exportiert wird, enthält es die Spalten, die Sie beim Definieren des Exportziels im vorherigen Schritt ausgewählt haben. Diese Daten können verwendet werden, um Profile im [Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles) zu erstellen.

Um das Segment in Adobe Campaign Standard zu verwenden, müssen wir das Profilschema in Adobe Campaign Standard erweitern, um zwei zusätzliche Felder einzuschließen. Lernen wie man [die Profilressource erweitert](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) mithilfe von neuen Feldern in Adobe Campaign Standard.

In unserem Beispiel sind diese Felder *Segmentname und Segmentdatum (optional)*.

Wir verwenden diese Felder, um die Profile in Adobe Campaign Standard zu erweitern, auf den wir diese Kampagne ausrichten möchten.

Wenn keine anderen Datensätze in Adobe Campaign Standard vorhanden sind, können Sie diesen Schritt überspringen.

## <a name="import-data-into-adobe-campaign-standard"></a>Daten importieren in Adobe Campaign Standard

Nun, da alles an seinem Platz ist, müssen wir die vorbereiteten Zielgruppendaten aus den Zielgruppenerkenntnissen nach Adobe Campaign Standard importieren, um Profile zu erstellen. Erfahren, [wie Profile in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) mithilfe eines Workflows importiert werden.

Der Importworkflow in der Abbildung unten wurde so konfiguriert, dass er alle acht Stunden ausgeführt wird und nach exportierten Zielgruppenerkenntnis-Segmenten (.csv-Datei in Azure Blob Storage) sucht. Der Workflow extrahiert den Inhalt der CSV-Datei in einer angegebenen Spaltenreihenfolge. Dieser Workflow wurde entwickelt, um eine grundlegende Fehlerbehandlung durchzuführen und sicherzustellen, dass jeder Datensatz eine E-Mail-Adresse hat, bevor die Daten in Adobe Campaign Standard hydriert werden. Der Workflow extrahiert außerdem den Segmentnamen aus dem Dateinamen, bevor er in die Profildaten von Adobe Campaign Standard übertragen wird.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Screenshot eines Import-Workflows in der Adobe Campaign Standard-Benutzeroberfläche.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Eine Zielgruppe in Adobe Campaign Standard abrufen

Sobald die Daten in Adobe Campaign Standard importiert wurden, können Sie [einen Workflow erstellen](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) Kunden [abfragen](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) auf der Grundlage vond *Segmentname* und *Segmentdatum*, um Profile auszuwählen, die für unsere Beispielkampagne identifiziert wurden.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Erstellen und senden Sie die E-Mail mit Adobe Campaign Standard

Erstellen Sie den E-Mail-Inhalt und dann [testen und senden](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) Sie Ihre E-Mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Beispiel-E-Mail mit Verlängerungsangebot von Adobe Campaign Standard.":::
