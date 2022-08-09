---
title: Anzeigen von Kundenprofilen
description: Zeigen Sie Ihre einheitlichen Kundendaten an, einschließlich der Verwendung von Suche und Filter
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 6cdf47e6997f230811dcb0f2cf5542f3a6db2367
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188092"
---
# <a name="view-customer-profiles"></a>Anzeigen von Kundenprofilen

Kundenprofile sind verfügbar, sobald Sie die [die einheitliche *Kunden* Entität erstellen](data-unification.md). Die **Kunden**-Seite zeigt eine kombinierte Ansicht Ihrer Vereinheitlichtes Kundenprofile. Bei den Kunden kann es sich um Einzelpersonen oder Unternehmen handeln.

Gehen Sie zum **Kunden** Seite, um Ihre Kunden und ihre Profile anzuzeigen. Jedes Kundenprofil wird durch eine Kachel dargestellt. Verwenden Sie die Paginierungssteuerelemente, um mehr Datensätze zu erhalten. Die Karte zeigt Felder aus der Entität *Kunde* im Sinne des **Such- und Filterindex** an. Die Reihenfolge der Felder innerhalb jeder Karte wird vom System ausgewählt.

> [!NOTE]
> Wenn Sie die Kacheln bei der Auswahl von **Kunden** nicht sehen können, muss Ihr Administrator [mindestens ein durchsuchbares Attribut](search-filter-index.md) in dem **Such- und Filterindex** definieren.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Kundenseite mit Ergebniskacheln":::

Wählen Sie eine der folgenden Aktionen aus:
- [Kundendetails anzeigen](#view-customer-details)
- [Den Such‑ und Filterindex verwalten](search-filter-index.md) (nur Administratoren)
- [Kunden filtern](#filter-customers)
- **Karten erweitern** oder **Karten reduzieren** um die auf der Kundenkachel angezeigten Informationen zu erweitern oder zu reduzieren
- **Sortieren nach** ein bestimmtes Attribut
- [Suche nach Kunden](#search-for-customers)

  > [!NOTE]
  > Um Suche und Filter zu verwenden, muss ein Administrator die durchsuchbaren Attribute konfigurieren und die filterbaren Felder mithilfe des Such- und Filterindex definieren.

## <a name="search-for-customers"></a>Suche nach Kunden

Suchen Sie nach Kunden, indem Sie einen Namen oder ein anderes Attribut in das **Kunden suchen** eingeben. Die durchsuchbaren Attribute werden vom Administrator definiert und stammen aus dem Vereinheitliche *Kunde* Entität.

> [!NOTE]
> **Zeichenfolge** ist der einzige Datentyp, der in die Suche einbezogen wird. Verwenden Sie es im Feld **Kunden suchen** auf der Seite Kunden, um nach Kunden zu suchen.

## <a name="filter-customers"></a>Kunden filtern

Filtern Sie Kunden nach den *Kunden* Entitätsfeldern. Filterbare Felder werden vom Administrator definiert.

1. Wählen Sie **Filter anzeigen** auf der Seite **Kunden** aus. Der Filterbereich wird angezeigt.

1. Markieren Sie die Kästchen neben den Attributen, nach denen Sie Kunden filtern möchten.

1. Entfernen Sie alle Filter, indem Sie auswählen **Filter löschen** oder deaktivieren Sie ein Kontrollkästchen neben einem ausgewählten Attribut.

1. Wählen Sie **Filter ausblenden** aus, um den Filter zu schließen.

1. Um die Filterergebnisse als [Segment](segments.md) zu speichern, wählen Sie **Filter als Segment speichern** aus.
   1. Geben Sie einen Namen für das Segment ein.
   1. Wählen Sie **Speichern** aus, um das Segment zu speichern.
   1. Wählen Sie aus, ob Sie das Segment jetzt ausführen möchten, indem Sie **Aktivieren** oder führe es aus **Später** auswählen.

## <a name="view-customer-details"></a>Kundendetails anzeigen

Wählen Sie auf der Seite **Kunden** eine Kundenkachel aus, um Details für den ausgewählten Kunden anzuzeigen.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Seite mit Kundendetails":::

Kundendetails enthalten:

**Kachel Kundenprofil**: Zeigt die verschiedenen Werte aus der vereinheitlichten Entität *Kunde* an. Wenn ein Feld keinen Wert für das ausgewählte Kundenprofil hat, wird es nicht angezeigt, ausgenommen für das Adressfeld. Die Kachel ist in Abschnitte gegliedert:

- Der erste Abschnitt zeigt einen vordefinierten Satz von Feldern, gefolgt von allen Feldern, die Teil des Such- und Filterindex sind. Alle adressbezogenen Felder werden in einer Zeile zusammengefasst, wenn das Profil solche Felder enthält, selbst wenn das Profil keine Adressinformationen enthält.
- **Kontakte für diesen Kunden** Anzeige in Umgebungen für Geschäftskonten. Jeder Kontakt wird mit seinen Feldern angezeigt. Leere Felder werden ausgeblendet.
- **Weitere Felder** zeigt die restlichen Felder des ausgewählten Kunden an, außer IDs.
- **IDs** listet alle IDs unter ihrem entsprechenden Entitätsnamen auf. Felder werden anhand ihrer Semantik als IDs identifiziert.

**Aktivitätszeitachse** zeigt Daten an, wenn Sie [Aktivitäten](activities.md) konfiguriert haben. Die Zeitskalaansicht enthält chronologisch sortierte Aktivitäten des ausgewählten Kunden, beginnend mit der letzten Aktivität.

**Erkenntnisse**:

- **Kennzahlen** wird angezeigt, wenn Sie [Kundenattributkennzahlen](measures.md) konfiguriert haben. Sie enthalten berechnete KPIs rund um Ihre Kunden auf der Ebene des einzelnen Kunden.

- **Potenzielle Interessen, potenzielle Marken** zeigt an, ob Sie ein [Anreicherung mit Marken- oder Interessenaffinität](enrichment-microsoft.md) konfiguriert haben. Es repräsentiert potenzielle Interessen und Affinitäten zu Marken anhand anderer Kunden, deren Profil dem ausgewählten Kundenprofil ähnlich ist.

Wählen Sie **Zurück zu Kunden**, um zur Seite **Kunden** zurückzukehren.

## <a name="next-steps"></a>Nächste Schritte,

[Weitere Datenquellen hinzufügen](data-sources.md), [Vereinheitlichte Profile bereichern](enrichment-hub.md), oder [Segmente erstellen](segments.md), um mit einheitlichen Kundenprofilen in anderen Anwendungen zu arbeiten.

[!INCLUDE [footer-include](includes/footer-banner.md)]
