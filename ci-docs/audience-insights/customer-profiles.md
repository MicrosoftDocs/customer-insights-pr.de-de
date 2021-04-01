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
ms.openlocfilehash: d6a9e7872a488b6d68afce35b547f93cc4a7c652
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596866"
---
# <a name="customer-profiles"></a>Kundenprofile

Die Seite **Kunden** zeigt eine kombinierte Ansicht Ihrer Kunden, basierend auf Profildaten, die aus [allen Datenquellen](data-sources.md) gesammelt wurden. Kundenprofile sind verfügbar, sobald Sie [die einheitliche Kundenentität erstellen](data-unification.md). Vergewissern Sie sich, dass Sie den Datenvereinheitlichungsprozess abgeschlossen haben, um eine bessere Sicht auf Ihre Kunden zu erhalten. Auf der Seite können Sie auch nach Kunden suchen.

Kunden können Einzelpersonen oder Organisationen sein (Vorschau). Jedes Kunden- oder Organisationsprofil wird durch eine Kachel dargestellt. Wählen Sie eine Kachel aus, um zusätzliche Informationen über diesen speziellen Kunden oder diese Organisation anzuzeigen. Verwenden Sie die Paginierungssteuerungselement am unteren Rand der Seite, um zusätzliche Datensätze anzuzeigen.

> [!div class="mx-imgBorder"] 
> ![B2C-Kundenprofile](media/profiles-customers.png "B2C-Kundenprofile")

Organisationen (Vorschau)
> [!div class="mx-imgBorder"] 
> ![B2B-Kundenprofile](media/profile-customers-b2b.png "B2B-Kundenprofile")

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
   > ![Kundenprofile](media/profiles-customers3.png "Kundenprofile")

3. Entfernen Sie Ihre Filter, indem Sie **Filter löschen** auf der Seite **Kunden** wählen.

##  <a name="customer-details-page"></a>Seite mit Kundendetails

Wählen Sie eine der Kundenkacheln, um die **Kundendetailseite** zu öffnen. Diese Ansicht enthält vereinheitlichte Informationen für den ausgewählten Kunden.

Kundendetails enthalten:

-   **Kundenprofil-Kachel:** Diese Kachel zeigt die verschiedenen Werte der vereinheitlichten Entität „Kundenprofil“ an. Diese Angaben können z. B. E-Mail-Adresse, Name, Stadt und so weiter sein. 

-   **Potenzielle Interessen, potenzielle Marken:** Zeigt an, ob Sie eine Erstanbieter-Anreicherung konfiguriert haben. Es stellt potenzielle Interessen und Affinitäten für Marken dar, die ein Kunde mit einem ähnlichen Profil wie dieser Kunde haben könnte. Weitere Informationen finden Sie unter [Anreichern von Kundenprofilen mit Marken- und Interessenaffinitäten](enrichment-microsoft-graph.md).

-   **Kennzahlen:** Zeigt an, ob Sie eine oder mehrere Kennzahlen eines bestimmten Typs konfiguriert haben: Kundenattributkennzahlen. Sie enthalten berechnete KPIs rund um Ihre Kunden auf der Ebene des einzelnen Kunden. Weitere Informationen finden Sie unter [Definieren und Verwalten von Kennzahlen](measures.md).

-   **Aktivitäts-Zeitleiste:** Zeigt an, ob Sie Aktivitäten konfiguriert haben. Die Zeitleistenansicht enthält chronologisch sortierte Aktivitäten dieses Kunden, beginnend mit der jüngsten Aktivität. Weitere Informationen finden Sie unter [Kundenaktivitäten](activities.md).

Wählen Sie **Zurück zu Kunden**, um zur Kundensuchseite zurückzukehren.

## <a name="next-steps"></a>Nächste Schritte

[Fügen Sie weitere Datenquellen hinzu](data-sources.md) oder [erstellen Sie Kundensegmente](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]