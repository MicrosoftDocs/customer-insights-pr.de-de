---
title: Power Apps-Connector (Vorschauversion)
description: Verbinden Sie sich mit Power Apps und Power Automate.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 8807e82e65ea20d1a7f7dc07552229f377927eed
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196899"
---
# <a name="power-apps-connector-preview"></a>Power Apps-Connector (Vorschauversion)

Bringen Sie einheitliche Kundenprofile in Ihre personalisierten Apps mit Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Verbinden von Power Apps mit Dynamics 365 Customer Insights

Customer Insights ist eine von vielen [verfügbaren Datenquellen in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Siehe Power Apps-Dokumentation für weitere Informationen zu [Hinzufügen einer Datenverbindung zu einer App](/powerapps/maker/canvas-apps/add-data-connection). Wir empfehlen, dass Sie auch überprüfen, [wie Power Apps die Delegierung verwendet, um große Datenmengen in Canvas-Apps zu verarbeiten](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Verfügbare Entitäten

Nach dem Hinzufügen von Customer Insights als Datenverbindung wählen Sie die folgenden Entitäten in Power Apps aus:

- **Kunde**: Zur Verwendung von Daten aus dem [Vereinheitlichtes Kund*innenprofil](customer-profiles.md).
- **UnifiedActivity**: Um die [Aktivitätszeitachse](activities.md) in der App anzuzeigen.
- **ContactProfile**: Um die Kontakte eines Kunden anzuzeigen. Diese Entität ist nur in Customer Insights Umgebungen für Geschäftskonten verfügbar.

## <a name="limitations"></a>Einschränkungen

### <a name="retrievable-entities"></a>Abrufbare Entitäten

Sie können nur die Entitäten **Kunde**, **UnifiedActivity**, **Segmente** und **Kontaktprofil** durch die Power Apps Konnektoren abrufen. ContactProfile ist nur in Customer Insights Umgebungen für Geschäftskonten verfügbar. Andere Entitäten werden angezeigt, da der zugrunde liegende Konnektor sie durch Trigger in Power Automate unterstützt.

Sie können maximal 100 Anrufe pro 60 Sekunden tätigen. Sie können die API Endpunkt mehrmals aufrufen, indem Sie den $skip-Parameter verwenden. [Erfahren Sie mehr über den $skip-Parameter](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Stellvertretung

Die Delegierung funktioniert für die **Kundenentität** und die **UnifiedActivity**-Entität.

- Delegation für die Entität **Kunde**: Um die Delegation für diese Entität zu verwenden, müssen die Felder in [Such- & Filterindex](search-filter-index.md) indiziert sein.  
- Delegierung für **UnifiedActivity**: Die Delegierung für diese Entität funktioniert nur für die Felder **ActivityId** und **CustomerId**.  
- Delegation für **KontaktProfil**: Delegation für diese Entität funktioniert nur für die Felder **Kontakt-ID** und **Kunden-ID**. ContactProfile ist nur in Customer Insights Umgebungen für Geschäftskonten verfügbar.

Weitere Informationen zur Delegation finden Sie unter [Power Apps delegierbare Funktionen und Operationen](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="example-gallery-control"></a>Beispiel für Galeriesteuerelement

Sie können optional Kundenprofile zu einer [Katalogsteuerelement](/powerapps/maker/canvas-apps/add-gallery) hinzufügen.

1. Fügen Sie ein Steuerelement **Katalog** zu einer App hinzu, die Sie erstellen.
  
   :::image type="content" source="media/connector-powerapps9.png" alt-text="Ein Galerie-Element hinzufügen.":::

1. Wählen Sie **Kunde** als Datenquelle für Artikel.

   :::image type="content" source="media/choose-datasource-powerapps.png" alt-text="Datenquelle auswählen.":::

1. Ändern Sie das Datenfeld auf der rechten Seite, um auszuwählen, welches Feld für die Kundeneinheit in der Galerie angezeigt werden soll.

1. Wenn Sie ein beliebiges Feld des ausgewählten Kunden im Katalog anzeigen möchten, füllen Sie die Eigenschaft **Text** einer Beschriftung mithilfe von **{Name_of_the_gallery}.Ausgewählt.{property_name}** hinzu.  
    - Beispiel: _Gallery1.Selected.address1_city_

1. Um die einheitliche Zeitskala für einen Kunden anzuzeigen, fügen Sie ein Katalog-Element und die Eigenschaft **Elemente** mithilfe von **Filter (UnifiedActivity, CustomerID = {Customer_Id})** hinzu  
    - Beispiel: _Filter('Unified Activity', CustomerId = Gallery1.Selected.CustomerId)_

[!INCLUDE [footer-include](includes/footer-banner.md)]
