---
title: Anzeigen von Kundenprofilen
description: Erhalten Sie eine kombinierte Ansicht Ihrer vereinheitlichten Kundendaten.
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a5d928ae518f3cb1afbf8e2b197e51b27665f6e0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269743"
---
# <a name="customer-profiles"></a><span data-ttu-id="92844-103">Kundenprofile</span><span class="sxs-lookup"><span data-stu-id="92844-103">Customer profiles</span></span>

<span data-ttu-id="92844-104">Die Seite **Kunden** zeigt eine kombinierte Ansicht Ihrer Kunden, basierend auf Profildaten, die aus [allen Datenquellen](data-sources.md) gesammelt wurden.</span><span class="sxs-lookup"><span data-stu-id="92844-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="92844-105">Kundenprofile sind verfügbar, sobald Sie [die einheitliche Kundenentität erstellen](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="92844-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="92844-106">Vergewissern Sie sich, dass Sie den Datenvereinheitlichungsprozess abgeschlossen haben, um eine bessere Sicht auf Ihre Kunden zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="92844-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="92844-107">Auf der Seite können Sie auch nach Kunden suchen.</span><span class="sxs-lookup"><span data-stu-id="92844-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="92844-108">Kunden können Einzelpersonen oder Organisationen sein (Vorschau).</span><span class="sxs-lookup"><span data-stu-id="92844-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="92844-109">Jedes Kunden- oder Organisationsprofil wird durch eine Kachel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="92844-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="92844-110">Wählen Sie eine Kachel aus, um zusätzliche Informationen über diesen speziellen Kunden oder diese Organisation anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="92844-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="92844-111">Verwenden Sie die Paginierungssteuerungselement am unteren Rand der Seite, um zusätzliche Datensätze anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="92844-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="92844-112">![B2C-Kundenprofile](media/profiles-customers.png "B2C-Kundenprofile")</span><span class="sxs-lookup"><span data-stu-id="92844-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="92844-113">Organisationen (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="92844-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="92844-114">![B2B-Kundenprofile](media/profile-customers-b2b.png "B2B-Kundenprofile")</span><span class="sxs-lookup"><span data-stu-id="92844-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="92844-115">Wenn Sie die Kacheln bei der Auswahl von **Kunden** in der Navigation nicht sehen können, muss Ihr Administrator [mindestens ein durchsuchbares Attribut](search-filter-index.md) im **Such- und Filterindex** definieren.</span><span class="sxs-lookup"><span data-stu-id="92844-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="92844-116">Suche nach Kunden</span><span class="sxs-lookup"><span data-stu-id="92844-116">Search for customers</span></span>

<span data-ttu-id="92844-117">Suchen Sie nach Kunden, indem Sie einen Namen oder ein anderes Attribut in das Suchfeld eingeben.</span><span class="sxs-lookup"><span data-stu-id="92844-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="92844-118">Die Suche funktioniert nur innerhalb der Entität Kundenprofil, die während des Datenvereinheitlichungsprozesses erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="92844-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="92844-119">Als Admin können Sie die durchsuchbaren Attribute über die Seite **Such- und Filterindex** konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="92844-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="92844-120">Weitere Informationen finden Sie unter [Such- und Filterindex verwalten](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="92844-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="92844-121">Kunden filtern</span><span class="sxs-lookup"><span data-stu-id="92844-121">Filter customers</span></span>

<span data-ttu-id="92844-122">Sie können Kunden nach den Entitätsfeldern des Kundenprofils filtern.</span><span class="sxs-lookup"><span data-stu-id="92844-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="92844-123">Ähnlich wie bei der Suche muss Ihr Admin zunächst die Felder mit Hilfe der Seite **Such- und Filterindex** als filterbar definieren.</span><span class="sxs-lookup"><span data-stu-id="92844-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="92844-124">Wählen Sie **Filter** auf der Seite **Kunden**.</span><span class="sxs-lookup"><span data-stu-id="92844-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="92844-125">Markieren Sie die Kästchen neben den Attributen, nach denen Sie Kunden filtern möchten.</span><span class="sxs-lookup"><span data-stu-id="92844-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="92844-126">![Kundenprofile](media/profiles-customers3.png "Kundenprofile")</span><span class="sxs-lookup"><span data-stu-id="92844-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="92844-127">Entfernen Sie Ihre Filter, indem Sie **Filter löschen** auf der Seite **Kunden** wählen.</span><span class="sxs-lookup"><span data-stu-id="92844-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="92844-128">Seite mit Kundendetails</span><span class="sxs-lookup"><span data-stu-id="92844-128">Customer details page</span></span>

<span data-ttu-id="92844-129">Wählen Sie eine der Kundenkacheln, um die **Kundendetailseite** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="92844-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="92844-130">Diese Ansicht enthält vereinheitlichte Informationen für den ausgewählten Kunden.</span><span class="sxs-lookup"><span data-stu-id="92844-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="92844-131">Kundendetails enthalten:</span><span class="sxs-lookup"><span data-stu-id="92844-131">Customer details include:</span></span>

-   <span data-ttu-id="92844-132">**Kundenprofil-Kachel:** Diese Kachel zeigt die verschiedenen Werte der vereinheitlichten Entität „Kundenprofil“ an.</span><span class="sxs-lookup"><span data-stu-id="92844-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="92844-133">Diese Angaben können z. B. E-Mail-Adresse, Name, Stadt und so weiter sein.</span><span class="sxs-lookup"><span data-stu-id="92844-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="92844-134">**Potenzielle Interessen, potenzielle Marken:** Zeigt an, ob Sie eine Erstanbieter-Anreicherung konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="92844-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="92844-135">Es stellt potenzielle Interessen und Affinitäten für Marken dar, die ein Kunde mit einem ähnlichen Profil wie dieser Kunde haben könnte.</span><span class="sxs-lookup"><span data-stu-id="92844-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="92844-136">Weitere Informationen finden Sie unter [Anreichern von Kundenprofilen mit Marken- und Interessenaffinitäten](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="92844-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="92844-137">**Kennzahlen:** Zeigt an, ob Sie eine oder mehrere Kennzahlen eines bestimmten Typs konfiguriert haben: Kundenattributkennzahlen.</span><span class="sxs-lookup"><span data-stu-id="92844-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="92844-138">Sie enthalten berechnete KPIs rund um Ihre Kunden auf der Ebene des einzelnen Kunden.</span><span class="sxs-lookup"><span data-stu-id="92844-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="92844-139">Weitere Informationen finden Sie unter [Definieren und Verwalten von Kennzahlen](measures.md).</span><span class="sxs-lookup"><span data-stu-id="92844-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="92844-140">**Aktivitäts-Zeitleiste:** Zeigt an, ob Sie Aktivitäten konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="92844-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="92844-141">Die Zeitleistenansicht enthält chronologisch sortierte Aktivitäten dieses Kunden, beginnend mit der jüngsten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="92844-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="92844-142">Weitere Informationen finden Sie unter [Kundenaktivitäten](activities.md).</span><span class="sxs-lookup"><span data-stu-id="92844-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="92844-143">Wählen Sie **Zurück zu Kunden**, um zur Kundensuchseite zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="92844-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="92844-144">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="92844-144">Next steps</span></span>

<span data-ttu-id="92844-145">[Fügen Sie weitere Datenquellen hinzu](data-sources.md) oder [erstellen Sie Kundensegmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="92844-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]