---
title: Kennzahlenübersicht
description: Erfahren Sie, wie Kennzahlen dabei helfen, die Leistung Ihres Unternehmens zu analysieren und widerzuspiegeln.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 99368a7ab2e8d7b3e53c04fbf25bb23bd2e550a9
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245372"
---
# <a name="measures-overview"></a>Kennzahlenübersicht

Mithilfe von Kennzahlen können Sie das Kundenverhalten und die Geschäftsleistung besser verstehen. Sie betrachten relevante Werte aus [einheitlichen Profilen](data-unification.md). Ein Unternehmen möchte beispielsweise die *Gesamtausgaben pro Kunde* ermitteln, um den Kaufverlauf oder -messung eines einzelnen Kunden oder den *Gesamtumsatz des Unternehmens* zu verstehen, um den aggregierten Gesamtumsatz des gesamten Unternehmens zu verstehen.

Erstellen Sie Kennzahlen, um Geschäftsaktivitäten zu planen, indem Sie Kundendaten abfragen und Erkenntnisse extrahieren. Erstellen Sie beispielsweise eine Kennzahl für *Gesamtausgaben pro Kunde* und *Gesamtrendite pro Kunde* hilft bei der Identifizierung einer Gruppe von Kunden mit hohen Ausgaben und hoher Rendite. Dann [ein Segment erstellen](segments.md), um die nächstbesten Maßnahmen voranzutreiben.

## <a name="create-a-measure"></a>Eine Kennzahl erstellen

Wählen Sie aus, wie eine Kennzahl basierend auf Ihrem Ziel Publikum erstellt werden soll.

# <a name="individual-consumers-b-to-c"></a>[Einzelne Verbraucher (B2C)](#tab/b2c)

- Von Grund auf neu mit Kennzahlen-Builder: [Eine eigene erstellen](measure-builder.md).
- Von üblicherweise gebrauchten: [Vordefinierte Vorlagen verwenden](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Unternehmenskonten (B2B)](#tab/b2b)

Von Grund auf neu mit Kennzahlen-Builder: [Eine eigene erstellen](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Vorhandene Kennzahlen verwalten

Gehen Sie zur **Kennzahlen** Seite, um die von Ihnen erstellten Kennzahlen, deren Status, Kennzahlentyp und den Zeitpunkt der letzten Aktualisierung der Daten anzuzeigen. Sie können die Liste der Kennzahlen nach einer beliebigen Spalte sortieren oder das Suchfeld verwenden, um die Kennzahl zu finden, die Sie verwalten möchten.

Wählen Weiter für eine Kennzahl aus, um verfügbare Aktionen anzuzeigen. Wählen Sie eine Kennzahlennamen aus, um eine Vorschau der Ausgabe anzeigen und eine CSV-Datei herunterladen.

:::image type="content" source="media/measures-actions.png" alt-text="Maßnahmen zur Verwaltung einzelner Kennzahlen."lightbox="media/measures-actions.png":::

- **Bearbeiten** der Kennzahl, um seine Eigenschaften zu ändern.
- **Aktualisieren** der Kennzahl, um die neuesten Daten einzuschließen.
- **Umbenennen** der Kennzahl.
- **Aktivieren** oder **Deaktivieren** der Kennzahl. Bei einer [geplanten Aktualisierung](schedule-refresh.md) werden inaktive Kennzahlen nicht aktualisiert und sie haben den **Status** aufgelistet als **Übersprungen**. Dies zeigt an, dass nicht einmal eine Aktualisierung versucht wurde.
- **Tag** zu [Tags verwalten](work-with-tags-columns.md#manage-tags) für die Kennzahl.
- **Löschen** der Kennzahl.
- **Spalten** zu [Passen Sie die Spalten an](work-with-tags-columns.md#customize-columns) diese Anzeige.
- **Filter** zu [nach Tags filtern](work-with-tags-columns.md#filter-on-tags).
- **Suchname**, um nach Kennzahlennamen zu suchen.

## <a name="refresh-measures"></a>Kennzahlen aktualisieren

Kennzahlen können nach einem automatischen Zeitplan oder manuell bei Bedarf aufgefrischt werden. Um eine oder mehrere Kennzahlen manuell zu aktualisieren, wählen Sie sie aus und wählen Sie **Aktualisieren**. Zum [Planen einer automatischen Aktualisierung](schedule-refresh.md) wechseln Sie zu **Administrator** > **System** > **Zeitplan**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
