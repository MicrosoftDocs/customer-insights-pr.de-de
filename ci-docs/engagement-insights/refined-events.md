---
title: Erstellen und Bearbeiten von Ereignissen
description: Ereignisse erstellen und ändern.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 935dc4cd41218842e8406b747daef47de04e337a
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606208"
---
# <a name="create-and-modify-events"></a>Erstellen und Bearbeiten von Ereignissen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ein Ereignis sind Daten, die das Benutzerverhalten repräsenteiren, z. B. die Aktivität auf einer Website.

- Ein *Basisereignis* zeichnet auf, wann ein Benutzer eine Seite anzeigt (Anzeigeereignis) oder mit Inhalten interagiert (Aktionsereignis).
- Ein *verfeinertes* Ereignis ist eine virtuelle Ansicht eines Basisereignisses. Sie definieren verfeinerte Ereignisse, indem Sie Eigenschaften entfernen und hinzufügen oder Ereignisse basierend auf Eigenschaftswerten filtern.

## <a name="prerequisites"></a>Voraussetzungen

Verbinden Sie Ihre Websitedaten zuerst mit Kundenbindungserkenntnissen mithilfe eines einfachen Codeausschnitts, um Ereignisse zu sehen. Weitere Informationen finden Sie unter [Installieren Sie das Web-SDK auf einer Website](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Anrufdaten zuerst verbinden.":::

## <a name="create-refined-events"></a>Detailliertere Ereignisse erstellen

Verwenden Sie verfeinerte Ereignisse, um den Umfang eines Basisereignisses für den [Export](export-events.md) zu verkleinern oder um Eigenschaften zu entfernen, die für die Exposition oder den Export nicht erforderlich sind.

> [!NOTE]
> Nachdem Sie das Web-SDK zu Ihrer Website hinzugefügt haben, können Sie Ihre Basisereignisse anzeigen und verfeinerte Ereignisse erstellen. 

So zeigen Sie Ihre Basisereignisse an:

1. Wechseln Sie zu **Daten** im linken Navigationsbereich.

1. Wählen Sie **Ereignisse**, um eine Liste aller Ereignisse im Arbeitsbereich anzuzeigen.

    :::image type="content" source="media/data-events.png" alt-text="Neue Ereignisse.":::

So erstellen Sie ein verfeinertes Ereignis aus einem Basisereignis: 

1. Gehen Sie zu **Daten** > **Ereignisse** und wählen Sie **+ Neue Veranstaltungen** oben auf dem Bildschirm.

1. In dem Dialog **Neue Veranstaltungen** wählen Sie **Erstellen Sie verfeinerte Ereignisse** und wählen dann **Weiter**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Neuer Ereignisassistent.":::
     
1. Geben Sie die folgenden Informationen im Fenster **Neues Ereignis** ein:

   - Wählen Sie ein Ereignis aus der **Basisereignisse** Dropdown-Liste aus.
   - Geben Sie einen Namen in das Feld **Anzeigename des verfeinerten Ereignisses** ein.
   - Aktualisieren Sie optional den vorgeschlagenen Namen unter **Tatsächlicher Name**, ohne Leerzeichen zu verwenden.

1. Wählen Sie **Erstellen** aus, um Ihre Einstellungen zu übernehmen.

Das verfeinerte Ereignis erscheint jetzt in Ihrer Liste **Ereignisse**.

### <a name="edit-event-name"></a>Bearbeiten des Ereignisnamens

Sie können den Namen und die Eigenschaften eines Basis- oder verfeinerten Ereignisses ändern.

1. Wechseln Sie zu **Daten** > **Ereignisse**. 

1. Wählen Sie für ein Ereignis **Mehr [...]** aus und wählen Sie dann **Name bearbeiten** aus.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Optionen zum Erstellen verfeinerter Ereignisse.":::

3. Aktualisieren Sie den Ereignisnamen und wählen Sie **Umbenennen** aus.

### <a name="view-the-details-of-a-refined-event"></a>Details eines verfeinerten Ereignisses anzeigen:

1. In der Liste **Ereignis** wählen Sie Ihre Basis- oder verfeinerten Ereignisse aus. 

1. Wählen Sie **Eigenschaften hinzufügen und entfernen** oben auf der Anzeige aus, um den Bereich **Eigenschaften bearbeiten** zu öffnen. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Eigenschaften hinzufügen und entfernen.":::

1. Verwenden Sie die Kontrollkästchen, um die Eigenschaften auszuwählen, die Sie anzeigen oder ausblenden möchten. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Bearbeiten von Eigenschaften für verfeinerte Ereignisse.":::

1. Wählen Sie **Bestätigen**, um Ihre Auswahl zu übernehmen, und wählen Sie dann **Speichern**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Ausgewählte Eigenschaften für ein verfeinertes Ereignis bearbeiten

1. Wechseln Sie zu **Daten** > **Ereignisse** und wählen Sie die verfeinerten Ereignisse aus, um die Detailansicht zu öffnen.
1. Wählen Sie **Eigenschaften hinzufügen und entfernen** aus. 
1. Bearbeiten Sie die Auswahl der Kontrollkästchen.
1. Wählen Sie **Bestätigen** und dann **Speichern** aus, um die Änderungen zu übernehmen.

Weitere Informationen zum Exportieren von Ereignissen finden Sie unter [Exportieren von Ereignissen](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
