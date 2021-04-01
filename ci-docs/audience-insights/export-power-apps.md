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
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598154"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="5cc52-103">Microsoft Power Apps-Connector (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="5cc52-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="5cc52-104">Bringen Sie einheitliche Kundenprofile in Ihre personalisierten Apps mit Power Apps.</span><span class="sxs-lookup"><span data-stu-id="5cc52-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="5cc52-105">Verbinden von Power Apps mit Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="5cc52-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="5cc52-106">Customer Insights ist eine von vielen [verfügbaren Datenquellen in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="5cc52-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="5cc52-107">Siehe Power Apps-Dokumentation für weitere Informationen zu [Hinzufügen einer Datenverbindung zu einer App](/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="5cc52-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="5cc52-108">Wir empfehlen, dass Sie auch überprüfen, [wie Power Apps die Delegierung verwendet, um große Datenmengen in Canvas-Apps zu verarbeiten](/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="5cc52-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="5cc52-109">Verfügbare Entitäten</span><span class="sxs-lookup"><span data-stu-id="5cc52-109">Available entities</span></span>

<span data-ttu-id="5cc52-110">Nach dem Hinzufügen von Customer Insights als Datenverbindung können Sie die folgenden Entitäten in Power Apps auswählen:</span><span class="sxs-lookup"><span data-stu-id="5cc52-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="5cc52-111">Kunde: zur Verwendung von Daten aus dem [einheitlichen Kundenprofil](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="5cc52-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="5cc52-112">UnifiedActivity: um die [Aktivitätszeitskala](activities.md) in der App anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5cc52-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="5cc52-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="5cc52-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="5cc52-114">Abrufbare Entitäten</span><span class="sxs-lookup"><span data-stu-id="5cc52-114">Retrievable entities</span></span>

<span data-ttu-id="5cc52-115">Sie können nur die Entitäten **Kunde**, **UnifiedActivity** und **Segmente** durch den Power Apps-Konnektor aufrufen.</span><span class="sxs-lookup"><span data-stu-id="5cc52-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="5cc52-116">Andere Entitäten werden angezeigt, da der zugrunde liegende Konnektor sie durch Trigger in Power Automate unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5cc52-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="5cc52-117">Stellvertretung</span><span class="sxs-lookup"><span data-stu-id="5cc52-117">Delegation</span></span>

<span data-ttu-id="5cc52-118">Die Delegierung funktioniert für die Kundenentität und die UnifiedActivity-Entität.</span><span class="sxs-lookup"><span data-stu-id="5cc52-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="5cc52-119">Delegation für die Entität **Kunde**: Um die Delegation für diese Entität zu verwenden, müssen die Felder in [Such- & Filterindex](search-filter-index.md) indiziert sein.</span><span class="sxs-lookup"><span data-stu-id="5cc52-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="5cc52-120">Delegierung für **UnifiedActivity**: Die Delegierung für diese Entität funktioniert nur für die Felder **ActivityId** und **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="5cc52-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="5cc52-121">Weitere Informationen zur Delegierung finden Sie unter [Power Apps delegierbare Funktionen und Vorgänge](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="5cc52-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="5cc52-122">Beispiel für Galeriesteuerelement</span><span class="sxs-lookup"><span data-stu-id="5cc52-122">Example gallery control</span></span>

<span data-ttu-id="5cc52-123">Beispiel: Sie fügen Kundenprofile zu einem [Galerie-Steuerelement](/powerapps/maker/canvas-apps/add-gallery) hinzu.</span><span class="sxs-lookup"><span data-stu-id="5cc52-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="5cc52-124">Fügen Sie ein Steuerelement **Galerie** zu einer App hinzu, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="5cc52-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5cc52-125">![Ein Galerie-Element hinzufügen](media/connector-powerapps9.png "Ein Galerie-Element hinzufügen")</span><span class="sxs-lookup"><span data-stu-id="5cc52-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="5cc52-126">Wählen Sie **Kunde** als Datenquelle für Artikel.</span><span class="sxs-lookup"><span data-stu-id="5cc52-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5cc52-127">![Datenquelle auswählen](media/choose-datasource-powerapps.png "Wählen Sie eine Datenquelle")</span><span class="sxs-lookup"><span data-stu-id="5cc52-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="5cc52-128">Sie können das Datenfeld auf der rechten Seite ändern, um auszuwählen, welches Feld für die Kundeneinheit in der Galerie angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5cc52-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="5cc52-129">Wenn Sie ein beliebiges Feld des ausgewählten Kunden in der Galerie anzeigen möchten, füllen Sie die Eigenschaft Text eines Etiketts aus: **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="5cc52-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="5cc52-130">Beispiel: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="5cc52-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="5cc52-131">Um die einheitliche Zeitachse für einen Kunden anzuzeigen, fügen Sie ein Gallery-Element und die Eigenschaft Items hinzu: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="5cc52-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="5cc52-132">Beispiel: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="5cc52-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]