---
title: Entitäten bei der Datenvereinheitlichung zusammenführen
description: Führen Sie Entitäten zusammen, um vereinheitlichte Kundenprofile zu erstellen.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 5d5ff4c6f091d1b50d0f6c8366bbe4f0e6428dac
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268501"
---
# <a name="merge-entities"></a>Entitäten zusammenführen

Die Zusammenführungsphase ist die letzte Phase des Datenvereinheitlichungsprozesses. Sein Zweck ist es, widersprüchliche Daten abzugleichen. Beispiele für widersprüchliche Daten könnten ein Kundenname sein, der in zwei Ihrer Datensätze gefunden wurde, der jedoch in jedem etwas anders angezeigt wird („Grant Marshall“ gegenüber "Grant Marshal"), oder eine Telefonnummer, die sich im Format (617-803-091X im Vergleich zu 617803091X unterscheidet). Die Zusammenführung dieser widersprüchlichen Datenpunkte erfolgt auf einer attributweisen Basis.

Nach Abschluss der [Match-Phase](match-entities.md) starten Sie die Zusammenführungsphase durch Auswahl der Kachel **zusammenführen** auf der Seite **Vereinheitlichen**.

## <a name="review-system-recommendations"></a>Empfehlungen für die Überprüfung des Systems

Auf der Seite **zusammenführen** wählen Sie Attribute aus, die in Ihrer einheitlichen Kundenprofilentität zusammengeführt werden sollen (das Ergebnis des Konfigurationsprozesses). Einige Attribute werden vom System automatisch zusammengeführt.

### <a name="view-merged-attributes"></a>Zusammengeführte Attribute anzeigen

Um die Attribute anzuzeigen, die in einem Ihrer automatisch abgemischten Attribute enthalten sind, markieren Sie das abgemischte Attribut. Die beiden Attribute, aus denen das zusammengeführte Attribut besteht, werden in zwei neuen Zeilen unterhalb des zusammengeführten Attributs angezeigt.

> [!div class="mx-imgBorder"]
> ![Gemischtes Attribut auswählen](media/configure-data-merge-profile-attributes.png "Zusammengeführtes Attribut auswählen")

### <a name="separate-merged-attributes"></a>Separate zusammengeführte Attribute

Um eines der automatisch zusammengefügten Attribute zu trennen oder aufzuheben, suchen Sie das Attribut in der Tabelle **Profilattribute**.

1. Aktivieren Sie die Schaltfläche Auslassungspunkte (...).
  
2. Wählen Sie in der Dropdown-Liste **Separate Felder** aus.

### <a name="remove-merged-attributes"></a>Zusammengeführte Attribute entfernen

Um ein Attribut aus der Endkundenprofil-Entität auszuschließen, finden Sie es in der Tabelle **Profilattribute**.

1. Aktivieren Sie die Schaltfläche Auslassungspunkte (...).
  
2. Wählen Sie in der Dropdownliste die Option **Nicht zusammenführen** aus.

   Das Attribut wird in den Abschnitt **Entfernt aus Kundendatensatz** verschoben.

## <a name="manually-add-a-merged-attribute"></a>Manuelles Hinzufügen eines zusammengeführten Attributs

Um ein zusammengeführtes Attribut hinzuzufügen, gehen Sie auf die Seite **Zusammenführen**.

1. Wählen Sie **Zusammengeführtes Attribut hinzufügen**.

2. Geben Sie einen **Name** ein, um sie später auf der Seite **Zusammenführen** zu identifizieren.

3. Optional können Sie einen **Anzeigenamen** in der einheitlichen Kundenprofilentität anzeigen.

4. Konfigurieren Sie **Duplizierte Attribute auswählen**, um die Attribute, die Sie aus den abgeglichenen Einheiten zusammenführen möchten, auszuwählen. Sie können auch nach Attributen suchen.

5. Setzen Sie den **Rang nach Wichtigkeit**, um ein Attribut über die anderen zu priorisieren. Wenn beispielsweise die Entität *WebAccountCSV* die genauesten Daten über das Attribut *Vollständige Namen* enthält, könnten Sie diese Entität gegenüber *ContactCSV* priorisieren, indem Sie *WebAccountCSV* auswählen. Infolgedessen wird *WebAccountCSV* auf die erste Priorität verschoben, während *ContactCSV* auf die zweite Priorität verschoben wird, wenn Werte für das Attribut *Vollständiger Name* gezogen werden.

## <a name="run-your-merge"></a>Führen Sie Ihre Zusammenführung durch

Unabhängig davon, ob Sie Attribute manuell zusammenführen oder vom System zusammenführen lassen, können Sie Ihre Zusammenführung immer durchführen. Wählen Sie **Ausführen** auf der Seite **Zusammenführen**, um den Prozess zu starten.

> [!div class="mx-imgBorder"]
> ![Datenzusammenführung Speichern und Ausführen](media/configure-data-merge-save-run.png "Datenzusammenführung Speichern und Ausführen")

Um weitere Änderungen vorzunehmen und den Schritt erneut auszuführen, können Sie eine laufende Zusammenführung abbrechen. Wählen Sie den Text **Wird aktualisiert ...** und **Auftrag abbrechen** im angezeigten Seitenbereich aus.

Nachdem der Text **Wird aktualisiert ...** zu **Erfolgreich** geändert wurde, ist die Zusammenführung abgeschlossen und hat Widersprüche in Ihren Daten gemäß den von Ihnen definierten Richtlinien behoben. Zusammengeführte und nicht zusammengeführte Attribute sind in der einheitlichen Profilentität enthalten. Ausgeschlossene Attribute sind nicht in der einheitlichen Profilentität enthalten.

Wenn Sie eine Zusammenführung nicht zum ersten Mal erfolgreich ausgeführt haben, werden alle nachfolgenden Prozesse, einschließlich Anreicherung, Segmentierung und Kennzahlen, automatisch erneut ausgeführt. Nachdem alle nachfolgenden Prozesse erneut ausgeführt wurden, spiegeln die Kundenprofile alle von Ihnen vorgenommenen Änderungen wider.

> [!TIP]
> Es gibt [sechs Arten von Status](system.md#status-types) für Aufgaben/Prozesse. Darüber hinaus [hängen die meisten Prozesse von anderen nachfolgenden Prozessen ab](system.md#refresh-policies). Sie können den Status eines Prozesses auswählen, um Details zum Fortschritt des gesamten Auftrags anzuzeigen. Nach der Auswahl von **Siehe Details** für eine der Aufgaben des Auftrags finden Sie zusätzliche Informationen: Verarbeitungszeit, das letzte Verarbeitungsdatum sowie alle mit der Aufgabe verbundenen Fehler und Warnungen.

## <a name="next-step"></a>Nächster Schritt

Konfigurieren von [Aktivitäten](activities.md), [Anreicherung](enrichment-microsoft-graph.md), oder [Beziehungen](relationships.md), um mehr Einblicke über Ihre Kunden zu gewinnen.

Wenn Sie bereits Aktivitäten, Anreicherungen oder Beziehungen konfiguriert haben oder Segmente definiert haben, werden diese automatisch verarbeitet, um die neuesten Kundendaten zu verwenden.




[!INCLUDE[footer-include](../includes/footer-banner.md)]