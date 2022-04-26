---
title: Kennzahlen verstehen und steuern
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
ms.openlocfilehash: ef10f480086ccac4fa5c6c58818e35ecae67532c
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529676"
---
# <a name="measures-overview"></a>Kennzahlenübersicht

Mithilfe von Kennzahlen können Sie das Kundenverhalten und die Geschäftsleistung besser verstehen. Sie betrachten relevante Werte aus [einheitlichen Profilen](data-unification.md). Ein Unternehmen möchte beispielsweise die *Gesamtausgaben pro Kunde* ermitteln, um den Kaufverlauf oder -messung eines einzelnen Kunden oder den *Gesamtumsatz des Unternehmens* zu verstehen, um den aggregierten Gesamtumsatz des gesamten Unternehmens zu verstehen.  

Kennzahlen werden mit dem [Kennzahlen-Builder](measure-builder.md) erstellt, einer Datenabfrageplattform mit verschiedenen Operatoren und einfachen Zuordnungsoptionen. Sie können die Daten filtern, Ergebnisse gruppieren und [Entitätsbeziehungspfade](relationships.md) erkennen und zeigen eine Vorschau der Ausgabe anzeigen. Sie können [vordefinierte Vorlagen](measure-templates.md) verwenden, um häufig verwendete Kennzahlen effizient zu konfigurieren.

Verwenden Sie die Kennzahlenerstellung, um Geschäftsaktivitäten zu planen, indem Sie Kundendaten abfragen und Erkenntnisse extrahieren. Erstellen Sie beispielsweise eine Kennzahl für *Gesamtausgaben pro Kunde* und *Gesamtrendite pro Kunde* hilft bei der Identifizierung einer Gruppe von Kunden mit hohen Ausgaben und hoher Rendite. Sie können basierend auf diesen Kennzahlen [ein Segment erstellen](segments.md), um die nächstbesten Maßnahmen voranzutreiben.

## <a name="manage-your-measures"></a>Verwalten von Kennzahlen

Die Liste der Kennzahlen finden Sie auf der Seite **Kennzahlen**.

Sie finden Informationen zu Kennzahlentyp, Ersteller, Erstellungsdatum, Status und Zustand. Wenn Sie eine Kennzahl aus der Liste auswählen, können Sie eine Vorschau der Ausgabe anzeigen und eine CSV-Datei herunterladen.

:::image type="content" source="media/measures-actions.png" alt-text="Maßnahmen zur Verwaltung einzelner Kennzahlen."lightbox="media/measures-actions.png":::

Die folgenden Aktionen sind verfügbar, wenn Sie eine Kennzahl auswählen:

- **Bearbeiten** der Konfiguration der Kennzahl.
- **Duplizieren** einer Messung. Sie können die Eigenschaften sofort bearbeiten oder das Duplikat einfach speichern.
- **Aktualisieren** Sie die Maßnahme basierend auf den neuesten Daten. Um alle Ihre Kennzahlen gleichzeitig zu aktualisieren, wählen Sie alle Kennzahlen und dann **Aktualisieren** aus.
- **Umbenennen** der Kennzahl.
- **Aktivieren** oder **Deaktivieren**. Inaktive Maßnahmen werden während einer [geplanten Aktualisierung](system.md#schedule-tab) nicht aktualisiert.
- **Tag** zu [Tags verwalten](work-with-tags-columns.md#manage-tags) für das Segment.
- **Löschen** der Kennzahl.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Nächster Schritt

Sie können vorhandene Maßnahmen verwenden, um [ein Kundensegment](segments.md) zu erstellen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
