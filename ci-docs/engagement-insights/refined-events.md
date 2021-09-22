---
title: Geänderte Ereignisse erstellen und ändern
description: Soe erstellen und ändern Sie verfeinerte Ereignisse.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034773"
---
# <a name="create-and-modify-refined-events"></a>Geänderte Ereignisse erstellen und ändern

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Ein Ereignis sind Daten, die das Benutzerverhalten repräsenteiren, z. B. die Aktivität auf einer Website.

- Ein *Basisereignis* zeichnet auf, wann ein Benutzer eine Seite anzeigt (Anzeigeereignis) oder mit Inhalten interagiert (Aktionsereignis).
- Ein *verfeinertes* Ereignis ist eine virtuelle Ansicht eines Basisereignisses. Sie definieren verfeinerte Ereignisse, indem Sie Eigenschaften entfernen und hinzufügen oder Ereignisse basierend auf Eigenschaftswerten filtern.

Verwenden Sie verfeinerte Ereignisse, um den Umfang eines Basisereignisses für den [Export](export-events.md) zu verkleinern oder um Eigenschaften zu entfernen, die für die Exposition oder den Export nicht erforderlich sind.

## <a name="create-refined-events"></a>Erzeugen von verfeinerten Ereignissen

Es gibt drei Möglichkeiten, um aus einem Basisereignis ein verfeinertes Ereignis zu erstellen. 

1. Wechseln Sie zu **Daten**> **Ereignisse** und wählen Sie eine der folgenden Optionen aus:
    - Wählen Sie **Neue Ereignisse** aus und wählen Sie dann **Verfeinerte Ereignisse erstellen** aus.
    - Wählen Sie ein Basisereignis aus, um eine Detailansicht zu öffnen, und wählen Sie dann **Verfeinerte Ereignisse erstellen** im oberen Menü aus.
    - Wählen Sie **Mehr [...]** aus, um das Kontextmenü für ein Basisereignis zu öffnen. Wählen Sie dann **Verfeinerte Ereignisse erstellen** aus.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Optionen zum Erstellen verfeinerter Ereignisse.":::

1. Geben Sie im Dialog **Verfeinerte Ereignisse erstellen** die folgenden Informationen ein:

- Wählen Sie im Dropdown **Basisereignisse** ein Ereignis aus, wenn Sie ein neues Ereignis erstellen.
- Geben Sie einen Namen in das Feld **Anzeigename des verfeinerten Ereignisses** ein.
- Aktualisieren Sie optional den vorgeschlagenen Namen unter **Tatsächlicher Name**, ohne Leerzeichen zu verwenden.

3. Wählen Sie **Erstellen** aus, um Ihre Einstellungen zu übernehmen.

1. Wählen Sie in der Detailansicht Ihres verfeinerten Ereignisses **Eigenschaften hinzufügen und entfernen** aus, um den Bereich **Eigenschaften bearbeiten** zu öffnen. 

1. Verwenden Sie die Kontrollkästchen, um die Eigenschaften auszuwählen, die Sie anzeigen oder ausblenden möchten. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Bearbeiten von Eigenschaften für verfeinerte Ereignisse.":::

1. Wählen Sie **Bestätigen** aus, um Ihre Auswahl zu übernehmen.

1. Wählen Sie **Speichern** aus, um die Konfiguration zu speichern.

## <a name="edit-refined-events"></a>Bearbeiten verfeinerter Ereignisse

Sie können den Namen und die Eigenschaften eines verfeinerten Ereignisses ändern.

### <a name="edit-event-name"></a>Bearbeiten des Ereignisnamens

1. Wechseln Sie zu **Daten** > **Ereignisse**. 
1. Wählen Sie für ein Ereignis **Mehr [...]** aus und wählen Sie dann **Name bearbeiten** aus.
1. Aktualisieren Sie den Ereignisnamen und wählen Sie **Umbenennen** aus.

### <a name="edit-selected-properties"></a>Bearbeiten ausgewählter Eigenschaften

1. Wechseln Sie zu **Daten** > **Ereignisse** und wählen Sie die verfeinerten Ereignisse aus, um die Detailansicht zu öffnen.
1. Wählen Sie **Eigenschaften hinzufügen und entfernen** aus. 
1. Bearbeiten Sie die Auswahl der Kontrollkästchen.
1. Wählen Sie **Bestätigen** und dann **Speichern** aus, um die Änderungen zu übernehmen.

Weitere Informationen zum Exportieren von Ereignissen finden Sie unter [Exportieren von Ereignissen](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
