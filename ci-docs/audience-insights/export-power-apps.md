---
title: Power Apps-Konnektor
description: Verbinden Sie sich mit Power Apps und Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 985e6c85795fba8ca3063cdffc7f9012e798856a
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623222"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps-Connector (Vorschau)

Bringen Sie einheitliche Kundenprofile in Ihre personalisierten Apps mit Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Verbinden von Power Apps mit Dynamics 365 Customer Insights

Customer Insights ist eine von vielen [verfügbaren Datenquellen in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Siehe Power Apps-Dokumentation für weitere Informationen zu [Hinzufügen einer Datenverbindung zu einer App](/powerapps/maker/canvas-apps/add-data-connection). Wir empfehlen, dass Sie auch überprüfen, [wie Power Apps die Delegierung verwendet, um große Datenmengen in Canvas-Apps zu verarbeiten](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Verfügbare Entitäten

Nach dem Hinzufügen von Customer Insights als Datenverbindung können Sie die folgenden Entitäten in Power Apps auswählen:

- **Kunde**: Zur Verwendung von Daten aus dem [Vereinheitlichtes Kund*innenprofil](customer-profiles.md).
- **UnifiedActivity**: Um die [Aktivitätszeitachse](activities.md) in der App anzuzeigen.
- **ContactProfile**: Um die Kontakte eines Kunden anzuzeigen. Diese Entität ist derzeit nur mit Zielgruppenerkenntnis-Umgebungen für Geschäftskonten verfügbar.

## <a name="limitations"></a>Einschränkungen

### <a name="retrievable-entities"></a>Abrufbare Entitäten

Sie können nur die Entitäten **Kunde**, **UnifiedActivity**, **Segmente** und **Kontaktprofil** durch die Power Apps Konnektoren abrufen. Kontaktprofil ist derzeit nur mit Zielgruppenerkenntnis-Instanzen Geschäftskonten verfügbar. Andere Entitäten werden angezeigt, da der zugrunde liegende Konnektor sie durch Trigger in Power Automate unterstützt.

### <a name="delegation"></a>Stellvertretung

Die Delegierung funktioniert für die **Kundenentität** und die **UnifiedActivity**-Entität. 

- Delegation für die Entität **Kunde**: Um die Delegation für diese Entität zu verwenden, müssen die Felder in [Such- & Filterindex](search-filter-index.md) indiziert sein.  
- Delegierung für **UnifiedActivity**: Die Delegierung für diese Entität funktioniert nur für die Felder **ActivityId** und **CustomerId**.  
- Delegation für **KontaktProfil**: Delegation für diese Entität funktioniert nur für die Felder **Kontakt-ID** und **Kunden-ID**. KontaktProfil ist derzeit nur mit Zielgruppenerkenntnis-Umgebungen für Geschäftskonten verfügbar.

Weitere Informationen zur Delegation finden Sie unter [Power Apps delegierbare Funktionen und Operationen](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Beispiel für Galeriesteuerelement

Sie können Kundenprofile zu einer [Katalogsteuerelement](/powerapps/maker/canvas-apps/add-gallery) hinzufügen.

1. Fügen Sie ein Steuerelement **Katalog** zu einer App hinzu, die Sie erstellen.

    > [!div class="mx-imgBorder"]
    > ![Ein Galerie-Element hinzufügen.](media/connector-powerapps9.png "Ein Katalog-Element hinzufügen.")

2. Wählen Sie **Kunde** als Datenquelle für Artikel.

    > [!div class="mx-imgBorder"]
    > ![Datenquelle auswählen.](media/choose-datasource-powerapps.png "Wählen Sie eine Datenquelle.")

3. Sie können das Datenfeld auf der rechten Seite ändern, um auszuwählen, welches Feld für die Kundeneinheit in der Galerie angezeigt werden soll.

4. Wenn Sie ein beliebiges Feld des ausgewählten Kunden im Katalog anzeigen möchten, füllen Sie die Eigenschaft **Text** einer Beschriftung mithilfe von **{Name_of_the_gallery}.Ausgewählt.{property_name}** hinzu.  
    - Beispiel: _Gallery1.Selected.address1_city_

5. Um die einheitliche Zeitskala für einen Kunden anzuzeigen, fügen Sie ein Katalog-Element und die Eigenschaft **Elemente** mithilfe von **Filter (UnifiedActivity, CustomerID = {Customer_Id})** hinzu  
    - Beispiel: _Filter('Unified Activity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE[footer-include](../includes/footer-banner.md)]
