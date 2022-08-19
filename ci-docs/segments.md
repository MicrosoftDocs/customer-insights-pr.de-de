---
title: Übersicht über Segmente
description: Übersicht über Segmente und wie man sie erstellt und verwaltet.
ms.date: 05/20/2022
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
ms.openlocfilehash: 195a7c733f047c24f9f47a151c1cb623fe34d055
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246292"
---
# <a name="segments-overview"></a>Übersicht über Segmente

Mit Segmenten können Sie Ihre Kunden anhand von demografischen, transaktionalen oder verhaltensbezogenen Attributen gruppieren. Sie können Segmente verwenden, um Werbekampagnen, Vertriebsaktivitäten und Kundensupportaktionen gezielt auf die Erreichung Ihrer Geschäftsziele auszurichten.

Kundenprofile, die den Filtern einer Segmentdefinition entsprechen, werden als *Mitglieder* eines Segments bezeichnet. Es gelten einige [Serviceeinschränkungen](/dynamics365/customer-insights/service-limits).

## <a name="create-a-segment"></a>Segment erstellen

Wählen Sie aus, wie ein Segment basierend auf Ihrem Ziel Publikum erstellt werden soll.

# <a name="individual-consumers-b-to-c"></a>[Einzelne Verbraucher (B2C)](#tab/b2c)

- Komplexe Segmente mit Segmentbuilder: [Ihre eigenen erstellen](segment-builder.md)
- Einfache Segmente mit einem Operator: [Schnelles Segment](segment-quick.md)
- KI-gestützter Weg, um ähnliche Kunden zu finden: [Ähnliche Kunden](find-similar-customer-segments.md)
- KI-gestützte Vorschläge basierend auf Maßnahmen oder Attributen: [Vorgeschlagene Segmente basierend auf Maßnahmen](suggested-segments.md)
- Vorschläge basierend auf Aktivitäten: [Vorgeschlagene Segmente basierend auf der Kundenaktivität](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Unternehmenskonten (B2B)](#tab/b2b)

- Simple oder komplexe Segmente mit Segmentbuilder: [Ihre eigenen erstellen](segment-builder.md)

---

## <a name="manage-existing-segments"></a>Vorhandene Segmente verwalten

Gehen Sie zur **Segmente** Seite, um die von Ihnen erstellten Segmente, deren Status und Status, die Anzahl der Mitglieder und den Zeitpunkt der letzten Aktualisierung der Daten anzuzeigen. Sie können die Liste der Segmente nach einer beliebigen Spalte sortieren oder das Suchfeld verwenden, um das Segment zu finden, das Sie verwalten möchten.

Wählen Sie das Segment aus, um verfügbare Aktionen anzuzeigen.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Ausgewähltes Segment mit Optionen-Dropdown-Liste und verfügbaren Optionen." lightbox="media/segments-selected-segment.png":::

- [**Anzeigen**](#view-segment-details) der Segmentdetails, einschließlich Trend der Anzahl der Mitglieder, Vorschau der Segmentmitglieder.
- **Download** die Liste der Mitglieder als .CSV-Datei herunterladen.
- **Bearbeiten** des Segments, um seine Eigenschaften zu ändern.
- **Duplikat erstellen** eines Segments. Sie können die Eigenschaften sofort bearbeiten oder das Duplikat speichern.
- [**Aktualisieren**](#refresh-segments) des Segments, um die neuesten Daten einzuschließen.
- **Aktivieren** oder **Deaktivieren** des Segments. Bei einer [geplanten Aktualisierung](schedule-refresh.md) werden inaktive Segmente nicht aktualisiert und sie haben den **Status** aufgelistet als **Übersprungen**. Dies zeigt an, dass nicht einmal eine Aktualisierung versucht wurde. Aktive Segmente werden basierend auf ihrem Typ aktualisiert: statisch oder dynamisch.
- **Statisch machen** oder **Dynamisch machen** den Segmenttyp. Statische Segmente müssen manuell aktualisiert werden. Dynamische Segmente werden während einer Systemaktualisierung automatisch aktualisiert.
- [**Finden Sie ähnliche Kunden**](find-similar-customer-segments.md) aus dem Segment.
- **Umbenennen** des Segments.
- **Tag** zu [Tags verwalten](work-with-tags-columns.md#manage-tags) für das Segment.
- [**Exporte verwalten**](#export-segments), um exportbezogene Segmente anzuzeigen und zu verwalten. [Weitere Informationen zu Exporten.](export-destinations.md)
- **Löschen** des Segments.
- **Spalten** zu [Passen Sie die Spalten an](work-with-tags-columns.md#customize-columns) diese Anzeige.
- **Filter** zu [nach Tags filtern](work-with-tags-columns.md#filter-on-tags).
- **Suchname**, um nach Segmentnamen zu suchen.

## <a name="view-segment-details"></a>Details zu einem Segment anzeigen

Auf der **Segmente** Seite wählen Sie ein Segment aus, um den Verarbeitungsverlauf und die Segmentmitglieder anzuzeigen.

Der obere Teil der Seite enthält ein Trenddiagramm, das Änderungen in der Mitgliederzahl visualisiert. Bewegen Sie die Maus über Datenpunkte, um die Mitgliederzahl an einem bestimmten Datum zu sehen. Ändern Sie den Zeitrahmen der Visualisierung.

:::image type="content" source="media/segment-time-range.png" alt-text="Segmentzeitbereich.":::

Der untere Teil enthält eine Liste der Segmentmitglieder.

> [!NOTE]
> Felder, die in dieser Liste erscheinen, basieren auf den Attributen der Entitäten Ihres Segments.
>
>Die Liste ist eine Vorschau der passenden Segmentmitglieder und zeigt die ersten 100 Datensätze Ihres Segments an, so dass Sie es schnell auswerten und seine Definitionen bei Bedarf überprüfen können. Um alle übereinstimmenden Datensätze zu sehen, müssen Sie [Segment](export-destinations.md) exportieren.

## <a name="refresh-segments"></a>Aktualisieren von Segmenten

Segmente können nach einem automatischen Zeitplan oder manuell bei Bedarf aufgefrischt werden. Um eine oder mehrere Segmente manuell zu aktualisieren, wählen Sie sie aus und wählen Sie **Aktualisieren**.

Zum [Planen einer automatischen Aktualisierung](schedule-refresh.md) wechseln Sie zu **Administrator** > **System** > **Zeitplan**. Es gelten die folgenden Regeln:

- Alle Segmente mit dem Typ **Dynamisch** oder **Erweiterung** werden automatisch mit der eingestellten Kadenz aktualisiert. Sobald die Aktualisierung abgeschlossen ist, zeigt der **Status** an, ob beim Aktualisieren des Segments Probleme aufgetreten sind. **Zuletzt aktualisiert** zeigt einen Zeitstempel der letzten erfolgreichen Aktualisierung an. Wenn ein Fehler auftritt, wählen Sie den Fehler aus, um die Details dazu anzuzeigen.
- Segmente mit dem Typ **Statisch** werden *nicht* automatisch aktualisiert werden. **Zuletzt aktualisiert** zeigt einen Zeitstempel der letzten Ausführung oder manuellen Aktualisierung der statischen Segmente an.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Segmente exportieren

Exportieren Sie Segmente in andere Apps, um die Daten weiter zu verwenden. Exportieren Sie ein Segment von der Segmentseite oder der [Exportseite](export-destinations.md).

1. Wählen Sie auf der Seite **Segmente** das Segment aus, das Sie exportieren möchten.

1. Wählen Sie **Exporte verwalten** aus. Die Seite **Exporte (Vorschauversion) für Segment** wird angezeigt. Sie sehen alle konfigurierten Exporte gruppiert danach, ob sie das aktuelle Segment enthalten oder nicht.

   1. Um das ausgewählte Segment zu einem Export hinzuzufügen, **bearbeiten** Sie den jeweiligen Export, um das entsprechende Segment auszuwählen, speichern Sie dann. In Umgebungen für einzelne Kunden können Sie den Export in der Liste auswählen und **Segment hinzufügen** auswählen, um das gleiche Ergebnis zu erzielen.

   1. Um einen neuen Export mit dem ausgewählten Segment zu erstellen, wählen Sie **Export hinzufügen** aus. Weitere Informationen zum Erstellen von Exporten finden Sie unter [Einrichten eines neuen Exports](export-destinations.md#set-up-a-new-export).

1. Wählen Sie **Zurück** aus, um zur Hauptseite für Segmente zurückzukehren.

## <a name="track-usage-of-a-segment"></a>Verfolgen Sie die Nutzung eines Segments

Wenn Sie Segmente in Apps verwenden, die auf derselben Microsoft Dataverse Organisation basieren, die mit Customer Insights verbunden ist, können Sie die Nutzung eines Segments verfolgen. Für [Customer Insights-Segmente, die in Kundenkontaktverläufe von Dynamics 365 Marketing verwendet werden](/dynamics365/marketing/real-time-marketing-ci-profile) informiert Sie das System über die Nutzung dieses Segments.

Beim Bearbeiten eines Segments, das in der Customer Insights-Umgebung oder in einem Kundenkontaktverlauf in Marketing verwendet wird, informiert ein Banner in der [Segment-Generator](segment-builder.md) Sie über die Abhängigkeiten. Sehen Sie die Abhängigkeitsdetails direkt über das Banner oder durch Auswählen von **Verwendungszweck** im Segment-Generator.

Der **Segmentnutzung**-Bereich zeigt die Details zur Verwendung dieses Segments in Dataverse-basierten Apps an. Für Segmente, die in Kundenkontaktverläufen verwendet werden, finden Sie einen Link, um den Verlauf in Marketing zu überprüfen, in der dieses Segment verwendet wird. Wenn Sie über Berechtigungen zum Zugriff auf die Marketing-App verfügen, können Sie dort auf weitere Details zugreifen.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Seitenbereich mit Details zur Segmentnutzung im Segment-Generator.":::

Das System informiert Sie über die Nutzung eines verfolgten Segments, wenn Sie versuchen, es zu löschen. Wenn das Segment, das Sie löschen möchten, in einem Kundenkontaktverlauf in Marketing verwendet wird, wird diese Reise für alle Benutzer im Segment beendet. Wenn der Verlauf Teil einer Marketingkampagne ist, betrifft die Löschung diese Kampagne selbst. Sie können das Segment jedoch trotz der Warnungen immer noch löschen.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Dialogfeld zur Bestätigung der Segmentlöschung, wenn ein Segment in einer Dataverse Anwendung verwendet wird.":::

### <a name="supported-apps"></a>Unterstützte Apps

Die Nutzung wird derzeit in den folgenden Dataverse-basierten Apps verfolgt:

- [Kundenkontaktverläufe in Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
