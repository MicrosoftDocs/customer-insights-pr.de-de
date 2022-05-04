---
title: Segmente in Customer Insights
description: Übersicht über Segmente und wie man sie erstellt und verwaltet.
ms.date: 03/30/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: 9791e971387eb7db91ed7c4e4fe76552656013ba
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647063"
---
# <a name="segments-overview"></a>Übersicht über Segmente

Mit Segmenten können Sie Ihre Kunden anhand von demografischen, transaktionalen oder verhaltensbezogenen Attributen gruppieren. Sie können Segmente verwenden, um Werbekampagnen, Vertriebsaktivitäten und Kundensupportaktionen gezielt auf die Erreichung Ihrer Geschäftsziele auszurichten.

Kundenprofile, die den Filtern einer Segmentdefinition entsprechen, werden als *Mitglieder* eines Segments bezeichnet. Es gelten einige [Serviceeinschränkungen](/dynamics365/customer-insights/service-limits).

## <a name="create-a-new-segment"></a>Ein neues Segment erstellen

Es gibt mehrere Wege, ein neues Segment zu erstellen: 

# <a name="individual-consumers-b-to-c"></a>[Einzelne Verbraucher (B2C)](#tab/b2c)

- Komplexes Segment mit Segmentbuilder: [Unsere eigenen erstellen](segment-builder.md#create-a-new-segment) 
- Einfache Segmente mit einem Operator: [Schnelles Segment](segment-builder.md#quick-segments) 
- KI-gestützter Weg, um ähnliche Kunden zu finden: [Ähnliche Kunden](find-similar-customer-segments.md) 
- KI-gestützte Vorschläge basierend auf Maßnahmen oder Attributen: [Vorgeschlagene Segmente zur Verbesserung der Maßnahmen](suggested-segments.md) 
- Vorschläge basierend auf Aktivitäten: [Vorgeschlagene Segmente basierend auf der Kundenaktivität](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Unternehmenskonten (B2B)](#tab/b2b)

- Komplexes Segment mit Segmentbuilder: [Unsere eigenen erstellen](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Vorhandene Segmente verwalten

Gehen Sie zur Seite **Segmente**, um alle Ihre gespeicherten Segmente anzuzeigen und zu verwalten.

Jedes Segment wird durch eine Zeile dargestellt, die zusätzliche Informationen über das Segment enthält.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Ausgewähltes Segment mit Optionen-Dropdown-Liste und verfügbaren Optionen." lightbox="media/segments-selected-segment.png":::

Die folgenden Aktionen sind verfügbar, wenn Sie ein Segment auswählen:

- **Anzeigen** der Segmentdetails, einschließlich Trend der Anzahl der Mitglieder, Vorschau der Segmentmitglieder.
- **Download** die Liste der Mitglieder als .CSV-Datei herunterladen.
- **Bearbeiten** des Segments, um seine Eigenschaften zu ändern.
- **Duplikat erstellen** eines Segments. Sie können die Eigenschaften sofort bearbeiten oder das Duplikat einfach speichern.
- **Aktualisieren** des Segments, um die neuesten Daten einzuschließen.
- **Aktivieren** oder **Deaktivieren** des Segments. Für inaktive Segmente ist die Segmentdefinition vorhanden, enthält jedoch noch keine Kunden. Ein aktives Segment sucht nach Kunden, die der Segmentdefinition entsprechen. Wenn eine [geplante Aktualisierung](system.md#schedule-tab) konfiguriert ist, haben inaktive Segmente den **Status** aufgelistet als **Übersprungen**. Dies zeigt an, dass nicht einmal eine Aktualisierung versucht wurde. Wenn ein inaktives Segment aktiviert wird, wird es aktualisiert und in geplante Aktualisierungen einbezogen.
  Alternativ können Sie die Funktionalität **Planen Sie später** im Auswahlmenü unter **Aktivieren/Deaktivieren** zur Angabe eines zukünftigen Datums und einer zukünftigen Uhrzeit für die Aktivierung und Deaktivierung eines bestimmten Segments verwenden.
- **[Finden Sie ähnliche Kunden](find-similar-customer-segments.md)** aus dem Segment.
- **Umbenennen** des Segments.
- **Tag** zu [Tags verwalten](work-with-tags-columns.md#manage-tags) für das Segment.
- **Download** die Liste der Mitglieder als .CSV-Datei herunterladen.
- **Exporte verwalten**, um exportbezogene Segmente anzuzeigen und zu verwalten. [Weitere Informationen zu Exporten.](export-destinations.md)
- **Löschen** des Segments.
- **Spalten** zu [Passen Sie die Spalten an](work-with-tags-columns.md#customize-columns) diese Anzeige.
- **Filter** zu [nach Tags filtern](work-with-tags-columns.md#filter-on-tags).
- **Suchname**, um nach Segmentnamen zu suchen.

## <a name="refresh-segments"></a>Aktualisieren von Segmenten

Sie können alle Segmente auf einmal aktualisieren, indem Sie **Alles aktualisieren** auf der Seite **Segmente** wählen, oder Sie können ein oder mehrere Segmente aktualisieren, wenn Sie sie auswählen und **Aktualisieren** aus den Optionen wählen. Alternativ können Sie eine laufende Aktualisierung unter **Administrator** > **System** > **Zeitplan** konfigurieren. Wenn eine wiederkehrende Aktualisierung konfiguriert ist, gelten die folgenden Regeln:
- Alle Segmente mit dem Typ **Dynamisch** oder **Erweiterung** werden automatisch mit der eingestellten Kadenz aktualisiert. Wenn die Aktualisierung abgeschlossen ist, zeigt der **Status** an, ob beim Aktualisieren des Segments Probleme aufgetreten sind. **Zuletzt aktualisiert** zeigt einen Zeitstempel der letzten erfolgreichen Aktualisierung an. Wenn ein Fehler auftritt, wählen Sie den Fehler aus, um die Details dazu anzuzeigen.
- Segmente mit dem Typ **Statisch** werden *nicht* automatisch aktualisiert werden. **Zuletzt aktualisiert** zeigt einen Zeitstempel der letzten Ausführung oder manuellen Aktualisierung der statischen Segmente an.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Segmente exportieren

Sie können ein Segment von der Segmentseite oder der [Exportseite](export-destinations.md) exportieren. 

1. Gehen Sie zur Seite **Segmente**.

1. Wählen Sie für das Segment, das Sie exportieren möchten, **Mehr anzeigen [...]** aus.

1. Wählen Sie **Exporte verwalten** aus der Dropdown-Liste Aktionen.

1. Die Seite **Exporte (Vorschau) für Segment** wird angezeigt. Sie sehen alle konfigurierten Exporte gruppiert danach, ob sie das aktuelle Segment enthalten oder nicht.

   1. Um das ausgewählte Segment zu einem Export hinzuzufügen, **bearbeiten** Sie den jeweiligen Export, um das entsprechende Segment auszuwählen, speichern Sie dann. In Umgebungen für einzelne Kunden können Sie stattdessen den Export in der Liste auswählen und **Segment hinzufügen** auswählen, um das gleiche Ergebnis zu erzielen.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]
