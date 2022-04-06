---
title: Anzeigen von Kundenprofilen
description: Erhalten Sie eine kombinierte Ansicht Ihrer vereinheitlichten Kundendaten.
ms.date: 09/30/2021
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
---

# <a name="customer-profiles"></a>Kundenprofile

Die **Kunden**-Seite zeigt eine kombinierte Ansicht Ihrer Vereinheitlichtes Kund*innenprofile. Die Kundenprofile sind verfügbar, sobald Sie [die einheitliche Kundenentität erstellt haben](data-unification.md). Auf der Seite können Sie nach Kunden suchen und den Index für diese Suche definieren.

Bei den Kunden kann es sich um Einzelpersonen oder Unternehmen handeln. Jedes Kundenprofil wird durch eine Kachel dargestellt. Verwenden Sie die Paginierungssteuerelemente, um mehr Datensätze zu erhalten. Die Karte zeigt Felder aus der Entität *Kunde* im Sinne des **Such- und Filterindex** an. Die Reihenfolge der Felder innerhalb jeder Karte wird vom System ausgewählt.

Wählen Sie eine Kachel aus, um Daten für den ausgewählten Kunden auf einer speziellen Seite namens [Kundendetailseite](customer-profiles.md#customer-details-page) anzuzeigen.

> [!div class="mx-imgBorder"] 
> ![Kundenseite mit Ergebniskacheln](media/customers-page-result-tiles-B2C.png "Kundenseite mit Ergebniskacheln")

> [!NOTE]
> Wenn Sie die Kacheln bei der Auswahl von **Kunden** in der Navigation nicht sehen können, muss Ihr Administrator [mindestens ein durchsuchbares Attribut](search-filter-index.md) in dem **Such- und Filterindex** definieren.

## <a name="search-for-customers"></a>Suche nach Kunden

Suchen Sie nach Kunden, indem Sie einen Namen oder ein anderes Attribut in das Suchfeld eingeben. Die Suche funktioniert nur innerhalb der _Kunde_ Entität, die während des Datenvereinigungsprozesses erstellt wurde.

Als Admin können Sie die durchsuchbaren Attribute über die Seite **Such- und Filterindex** konfigurieren. Weitere Informationen finden Sie unter [Such- und Filterindex verwalten](search-filter-index.md).

## <a name="filter-customers"></a>Kunden filtern

Sie können Kunden nach den _Kunden_ Entitätsfeldern filtern. Ähnlich wie bei der Suche muss Ihr Admin zunächst die Felder mit Hilfe der Seite **Such- und Filterindex** als filterbar definieren.

1. Wählen Sie **Filter anzeigen** auf der Seite **Kunden** aus.

1. Markieren Sie die Kästchen neben den Attributen, nach denen Sie Kunden filtern möchten.

1. Entfernen Sie Ihre Filter, indem Sie **Filter löschen** auf der Seite **Kunden** wählen.

## <a name="customer-details-page"></a>Seite mit Kundendetails

Wählen Sie eine der Kundenkacheln, um die **Kundendetailseite** zu öffnen. Diese Ansicht enthält vereinheitlichte Informationen für den ausgewählten Kunden. Die Kundendaten umfassen die folgenden Inhalte:

**Kachel Kundenprofil**: Diese Kachel zeigt die verschiedenen Werte aus der vereinheitlichten Entität _Kunde_ an. Wenn ein Feld keinen Wert für das ausgewählte Kundenprofil hat, wird es nicht angezeigt. Die Kachel ist in Abschnitte gegliedert:  
  - Der erste Abschnitt zeigt einen vordefinierten Satz von Feldern, gefolgt von allen Feldern, die Teil des Such- und Filterindex sind. Alle adressbezogenen Felder werden in einer Zeile zusammengefasst, wenn das Profil solche Felder enthält. 
  - **Kontakte für diesen Kunden**: In Umgebungen für Geschäftskonten werden im zweiten Abschnitt alle zugehörigen Kontakte für diesen Kunden angezeigt. Jeder Kontakt wird mit seinen Feldern angezeigt. Leere Felder werden ausgeblendet.
  - **Weitere Felder**: Zeigt die restlichen Felder des ausgewählten Kunden an, außer IDs. 
  - **IDs**: Listet alle IDs unter ihrem entsprechenden Entitätsnamen auf. Felder werden durch ihre Semantik als IDs identifiziert, die sie als solche kategorisieren.

**Aktivitätszeitachse**: Zeigt Daten an, wenn Sie Aktivitäten konfiguriert haben. Die Zeitskalaansicht enthält chronologisch sortierte Aktivitäten des ausgewählten Kunden, beginnend mit der letzten Aktivität. Weitere Informationen finden Sie unter [Kundenaktivitäten](activities.md).

**Erkenntnisse**:  
  - **Kennzahlen**: Zeigt an, ob Sie eine oder mehrere Kennzahlen für Kundenattributkennzahlen konfiguriert haben. Sie enthalten berechnete KPIs rund um Ihre Kunden auf der Ebene des einzelnen Kunden. Weitere Informationen finden Sie unter [Kennzahlen definieren und verwalten](measures.md).

  - **Potenzielle Interessen, potenzielle Marken**: Zeigt an, ob Sie eine Anreicherung mit Marken- oder Interessenaffinität konfiguriert haben. Es repräsentiert potenzielle Interessen und Affinitäten zu Marken anhand anderer Kunden, deren Profil dem ausgewählten Kundenprofil ähnlich ist. Weitere Informationen finden Sie unter [Kundenprofile mit Marken- und Interessenaffinitäten anreichern](enrichment-microsoft.md).

Um zur Kundensuchseite zurückzukehren, wählen Sie **Zurück zu Kunden**.

## <a name="next-steps"></a>Nächste Schritte,

[Weitere Datenquellen hinzufügen](data-sources.md), [Vereinheitlichte Profile bereichern](enrichment-hub.md), oder [Segmente erstellen](segments.md), um mit einheitlichen Kundenprofilen in anderen Anwendungen zu arbeiten.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
