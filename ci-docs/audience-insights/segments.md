---
title: Segmente in Zielgruppenerkenntnissen
description: Übersicht über Segmente und wie man sie erstellt und verwaltet.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6e2080b4ad19f6f57f60da591345e80ce9083e8a
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554066"
---
# <a name="segments-overview"></a>Übersicht über Segmente

Mit Segmenten können Sie Ihre Kunden anhand von demografischen, transaktionalen oder verhaltensbezogenen Attributen gruppieren. Sie können Segmente verwenden, um Werbekampagnen, Vertriebsaktivitäten und Kundensupportaktionen gezielt auf die Erreichung Ihrer Geschäftsziele auszurichten.

Kundenprofile, die den Filtern einer Segmentdefinition entsprechen, werden als *Mitglieder* eines Segments bezeichnet. Es gelten einige [Serviceeinschränkungen](service-limits.md).

## <a name="create-a-new-segment"></a>Ein neues Segment erstellen

Es gibt mehrere Wege, ein neues Segment zu erstellen: 

- Komplexes Segment mit Segment Builder: [Leeres Segment](segment-builder.md#create-a-new-segment)
- Einfache Segmente mit einem Operator: [Schnelles Segment](segment-builder.md#quick-segments)
- KI-gestützter Weg, um ähnliche Kunden zu finden: [Ähnliche Kunden](find-similar-customer-segments.md)
- KI-gestützte Vorschläge basierend auf Maßnahmen oder Attributen: [Vorgeschlagene Segmente zur Verbesserung der Maßnahmen](suggested-segments.md)
- Vorschläge basierend auf Aktivitäten: [Vorgeschlagene Segmente basierend auf der Kundenaktivität](suggested-segments-activity.md)

## <a name="manage-existing-segments"></a>Vorhandene Segmente verwalten

Gehen Sie zur Seite **Segmente**, um alle Ihre gespeicherten Segmente anzuzeigen und zu verwalten.

Jedes Segment wird durch eine Zeile dargestellt, die zusätzliche Informationen über das Segment enthält.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Ausgewähltes Segment mit Optionen-Dropdown-Liste und verfügbaren Optionen.":::

Die folgende Aktion ist verfügbar, wenn Sie ein Segment auswählen:

- **Anzeigen** der Segmentdetails, einschließlich Trend der Anzahl der Mitglieder, Vorschau der Segmentmitglieder.
- **Bearbeiten** des Segments, um seine Eigenschaften zu ändern.
- **Duplikat erstellen** eines Segments. Sie können die Eigenschaften sofort bearbeiten oder das Duplikat einfach speichern.
- **Aktualisieren** des Segments, um die neuesten Daten einzuschließen.
- **Aktivieren** oder **Deaktivieren** des Segments. Segmente haben zwei mögliche Status – aktiv oder inaktiv. Diese Status sind nützlich, wenn Sie ein Segment bearbeiten. Für inaktive Segmente ist die Segmentdefinition vorhanden, enthält jedoch noch keine Kunden. Wenn Sie ein Segment aktivieren, ändert sich sein Status von inaktiv in aktiv und es wird nach Kunden gesucht, die der Segmentdefinition entsprechen. Wenn eine [geplante Aktualisierung](system.md#schedule-tab) konfiguriert ist, haben inaktive Segmente den **Status** aufgelistet als **Übersprungen**. Dies zeigt an, dass nicht einmal eine Aktualisierung versucht wurde. Wenn ein inaktives Segment aktiviert wird, wird es aktualisiert und in geplante Aktualisierungen einbezogen.
  Alternativ können Sie die Funktionalität **Planen Sie später** im Auswahlmenü unter **Aktivieren/Deaktivieren** zur Angabe eines zukünftigen Datums und einer zukünftigen Uhrzeit für die Aktivierung und Deaktivierung eines bestimmten Segments verwenden.
- **Umbenennen** des Segments.
- **Download** die Liste der Mitglieder als .CSV-Datei herunterladen.
- **Exporte verwalten**, um exportbezogene Segmente anzuzeigen und zu verwalten. [Weitere Informationen zu Exporten.](export-destinations.md)
- **Löschen** des Segments.

## <a name="refresh-segments"></a>Aktualisieren von Segmenten

Sie können alle Segmente auf einmal aktualisieren, indem Sie **Alles aktualisieren** auf der Seite **Segmente** wählen, oder Sie können ein oder mehrere Segmente aktualisieren, wenn Sie sie auswählen und **Aktualisieren** aus den Optionen wählen. Alternativ können Sie eine laufende Aktualisierung unter **Administrator** > **System** > **Zeitplan** konfigurieren.

> [!TIP]
> Es gibt [sechs Arten von Status](system.md#status-types) für Aufgaben/Prozesse. Darüber hinaus [hängen die meisten Prozesse von anderen nachfolgenden Prozessen ab](system.md#refresh-policies). Sie können den Status eines Prozesses auswählen, um Details zum Fortschritt des gesamten Auftrags anzuzeigen. Nach der Auswahl von **Siehe Details** für eine der Aufgaben des Auftrags finden Sie zusätzliche Informationen: Verarbeitungszeit, das letzte Verarbeitungsdatum sowie alle mit der Aufgabe verbundenen Fehler und Warnungen.

## <a name="export-segments"></a>Segmente exportieren

Sie können ein Segment von der Segmentseite oder der [Exportseite](export-destinations.md) exportieren. 

1. Gehen Sie zur Seite **Segmente**.

1. Wählen Sie für das Segment, das Sie exportieren möchten, **Mehr anzeigen [...]** aus.

1. Wählen Sie **Exporte verwalten** aus der Dropdown-Liste Aktionen.

1. Die Seite **Exporte (Vorschau) für Segment** wird angezeigt. Sie können alle konfigurierten Exporte gruppiert nach Exporten anzeigen, die das aktuelle Segment enthalten oder nicht enthalten.

   1. Um das ausgewählte Segment zu einem Export hinzuzufügen, wählen Sie den Export in der Liste aus und wählen Sie dann **Segment hinzufügen** aus.

   1. Um einen neuen Export mit dem ausgewählten Segment zu erstellen, wählen Sie **Export hinzufügen** aus. Weitere Informationen zum Erstellen von Exporten finden Sie unter [Einrichten eines neuen Exports](export-destinations.md#set-up-a-new-export).

1. Wählen Sie **Zurück** aus, um zur Hauptseite für Segmente zurückzukehren.

## <a name="view-processing-history-and-segment-members"></a>Anzeigen der Verarbeitungsgeschichte und der Segmentmitglieder

Sie können konsolidierte Daten zu einem Segment anzeigen, indem Sie die Details des Segments überprüfen.

Wählen Sie auf der Seite **Segmente** das Segment aus, das Sie überprüfen möchten.

Der obere Teil der Seite enthält ein Trenddiagramm, das Änderungen in der Mitgliederzahl visualisiert. Bewegen Sie die Maus über Datenpunkte, um die Mitgliederzahl an einem bestimmten Datum zu sehen.

Sie können den Zeitrahmen der Visualisierung aktualisieren.

> [!div class="mx-imgBorder"]
> ![Segmentzeitbereich.](media/segment-time-range.png "Segmentzeitbereich")

Der untere Teil enthält eine Liste der Segmentmitglieder.

> [!NOTE]
> Felder, die in dieser Liste erscheinen, basieren auf den Attributen der Entitäten Ihres Segments.
>
>Die Liste ist eine Vorschau der passenden Segmentmitglieder und zeigt die ersten 100 Datensätze Ihres Segments an, so dass Sie es schnell auswerten und seine Definitionen bei Bedarf überprüfen können. Um alle übereinstimmenden Datensätze zu sehen, müssen Sie [Segment](export-destinations.md) exportieren.

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
