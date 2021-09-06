---
title: Anzeigen von Kundenprofilen
description: Erhalten Sie eine kombinierte Ansicht Ihrer vereinheitlichten Kundendaten.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 87323d15c44ef82ae8bc3cc971be6c36356121571cb9a9630be699ac2d157bf6
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032803"
---
# <a name="customer-profiles"></a>Kundenprofile

Die Seite **Kunden** zeigt eine kombinierte Ansicht Ihrer Kunden, basierend auf Profildaten, die aus [allen Datenquellen](data-sources.md) gesammelt wurden. Kundenprofile sind verfügbar, sobald Sie [die einheitliche Kundenentität erstellen](data-unification.md). Vergewissern Sie sich, dass Sie den Datenvereinheitlichungsprozess abgeschlossen haben, um eine bessere Sicht auf Ihre Kunden zu erhalten. Auf der Seite können Sie auch nach Kunden suchen.

Kunden können Einzelpersonen oder Organisationen sein (Vorschau). Jedes Kunden- oder Organisationsprofil wird durch eine Kachel dargestellt. Wählen Sie eine Kachel aus, um zusätzliche Informationen über diesen speziellen Kunden oder diese Organisation anzuzeigen. Verwenden Sie die Paginierungssteuerungselement am unteren Rand der Seite, um zusätzliche Datensätze anzuzeigen.

> [!div class="mx-imgBorder"] 
> ![B2C-Kundenprofile.](media/profiles-customers.png "B2C-Kundenprofile")

Organisationen (Vorschau)
> [!div class="mx-imgBorder"] 
> ![B2B-Kundenprofile.](media/profile-customers-b2b.png "B2B-Kundenprofile")

> [!NOTE]
> Wenn Sie die Kacheln bei der Auswahl von **Kunden** in der Navigation nicht sehen können, muss Ihr Administrator [mindestens ein durchsuchbares Attribut](search-filter-index.md) im **Such- und Filterindex** definieren.

## <a name="search-for-customers"></a>Suche nach Kunden

Suchen Sie nach Kunden, indem Sie einen Namen oder ein anderes Attribut in das Suchfeld eingeben. Die Suche funktioniert nur innerhalb der Entität Kundenprofil, die während des Datenvereinheitlichungsprozesses erstellt wurde.

Als Admin können Sie die durchsuchbaren Attribute über die Seite **Such- und Filterindex** konfigurieren. Weitere Informationen finden Sie unter [Such- und Filterindex verwalten](search-filter-index.md).

## <a name="filter-customers"></a>Kunden filtern

Sie können Kunden nach den Entitätsfeldern des Kundenprofils filtern. Ähnlich wie bei der Suche muss Ihr Admin zunächst die Felder mit Hilfe der Seite **Such- und Filterindex** als filterbar definieren.

1. Wählen Sie **Filter** auf der Seite **Kunden**.

2. Markieren Sie die Kästchen neben den Attributen, nach denen Sie Kunden filtern möchten.

   > [!div class="mx-imgBorder"] 
   > ![Kundenprofile.](media/profiles-customers3.png "Kundenprofile")

3. Entfernen Sie Ihre Filter, indem Sie **Filter löschen** auf der Seite **Kunden** wählen.

##  <a name="customer-details-page"></a>Seite mit Kundendetails

Wählen Sie eine der Kundenkacheln, um die **Kundendetailseite** zu öffnen. Diese Ansicht enthält vereinheitlichte Informationen für den ausgewählten Kunden.

Kundendetails enthalten:

-   **Kundenprofil-Kachel**: Diese Kachel zeigt die verschiedenen Werte der vereinheitlichten Entität „Kundenprofil“ an. Diese Angaben können z. B. E-Mail-Adresse, Name, Stadt und so weiter sein. 

-   **Potenzielle Interessen, potenzielle Marken**: Zeigt an, ob Sie eine Erstanbieter-Anreicherung konfiguriert haben. Es stellt potenzielle Interessen und Affinitäten für Marken dar, die ein Kunde mit einem ähnlichen Profil wie dieser Kunde haben könnte. Weitere Informationen finden Sie unter [Anreichern von Kundenprofilen mit Marken- und Interessenaffinitäten](enrichment-microsoft.md).

-   **Kennzahlen**: Zeigt an, ob Sie eine oder mehrere Kennzahlen eines bestimmten Typs konfiguriert haben: Kundenattributkennzahlen. Sie enthalten berechnete KPIs rund um Ihre Kunden auf der Ebene des einzelnen Kunden. Weitere Informationen finden Sie unter [Definieren und Verwalten von Kennzahlen](measures.md).

-   **Aktivitäts-Zeitleiste**: Zeigt an, ob Sie Aktivitäten konfiguriert haben. Die Zeitleistenansicht enthält chronologisch sortierte Aktivitäten dieses Kunden, beginnend mit der jüngsten Aktivität. Weitere Informationen finden Sie unter [Kundenaktivitäten](activities.md).

Wählen Sie **Zurück zu Kunden**, um zur Kundensuchseite zurückzukehren.

## <a name="next-steps"></a>Nächste Schritte,

[Weitere Datenquellen hinzufügen](data-sources.md), [Vereinheitlichte Profile qnreichern](enrichment-hub.md), oder [Segmente erstellen](segments.md), um mit einheitlichen Profilen in anderen Anwendungen zu arbeiten.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
