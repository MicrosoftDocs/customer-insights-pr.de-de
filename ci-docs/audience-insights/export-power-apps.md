---
title: Power Apps-Konnektor
description: Verbinden Sie sich mit Power Apps und Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 2ab5a9059991611a2959a19cc688d232ec782e1e
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554112"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps-Connector (Vorschau)

Bringen Sie einheitliche Kundenprofile in Ihre personalisierten Apps mit Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Verbinden von Power Apps mit Dynamics 365 Customer Insights

Customer Insights ist eine von vielen [verfügbaren Datenquellen in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Siehe Power Apps-Dokumentation für weitere Informationen zu [Hinzufügen einer Datenverbindung zu einer App](/powerapps/maker/canvas-apps/add-data-connection). Wir empfehlen, dass Sie auch überprüfen, [wie Power Apps die Delegierung verwendet, um große Datenmengen in Canvas-Apps zu verarbeiten](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Verfügbare Entitäten

Nach dem Hinzufügen von Customer Insights als Datenverbindung können Sie die folgenden Entitäten in Power Apps auswählen:

- Kunde: zur Verwendung von Daten aus dem [einheitlichen Kundenprofil](customer-profiles.md).
- UnifiedActivity: um die [Aktivitätszeitskala](activities.md) in der App anzuzeigen.

## <a name="limitations"></a>Einschränkungen

### <a name="retrievable-entities"></a>Abrufbare Entitäten

Sie können nur die Entitäten **Kunde**, **UnifiedActivity** und **Segmente** durch den Power Apps-Konnektor aufrufen. Andere Entitäten werden angezeigt, da der zugrunde liegende Konnektor sie durch Trigger in Power Automate unterstützt.  

### <a name="delegation"></a>Stellvertretung

Die Delegierung funktioniert für die Kundenentität und die UnifiedActivity-Entität. 

- Delegation für die Entität **Kunde**: Um die Delegation für diese Entität zu verwenden, müssen die Felder in [Such- & Filterindex](search-filter-index.md) indiziert sein.  

- Delegierung für **UnifiedActivity**: Die Delegierung für diese Entität funktioniert nur für die Felder **ActivityId** und **CustomerId**.  

- Weitere Informationen zur Delegierung finden Sie unter [Power Apps delegierbare Funktionen und Vorgänge](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Beispiel für Galeriesteuerelement

Beispiel: Sie fügen Kundenprofile zu einem [Galerie-Steuerelement](/powerapps/maker/canvas-apps/add-gallery) hinzu.

1. Fügen Sie ein Steuerelement **Galerie** zu einer App hinzu, die Sie erstellen.

> [!div class="mx-imgBorder"]
> ![Ein Galerie-Element hinzufügen.](media/connector-powerapps9.png "Ein Galerie-Element hinzufügen")

1. Wählen Sie **Kunde** als Datenquelle für Artikel.

    > [!div class="mx-imgBorder"]
    > ![Datenquelle auswählen.](media/choose-datasource-powerapps.png "Wählen Sie eine Datenquelle")

1. Sie können das Datenfeld auf der rechten Seite ändern, um auszuwählen, welches Feld für die Kundeneinheit in der Galerie angezeigt werden soll.

1. Wenn Sie ein beliebiges Feld des ausgewählten Kunden in der Galerie anzeigen möchten, füllen Sie die Eigenschaft Text eines Etiketts aus: **{Name_of_the_gallery}.Selected.{property_name}**

    Beispiel: Gallery1.Selected.address1_city

1. Um die einheitliche Zeitachse für einen Kunden anzuzeigen, fügen Sie ein Gallery-Element und die Eigenschaft Items hinzu: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Beispiel: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]