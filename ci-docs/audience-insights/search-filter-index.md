---
title: Kundenprofile suchen und filtern
description: Schnelles Auffinden von Informationen über einheitliche Kundenprofile und Filter für bestimmte Attribute.
ms.date: 01/19/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d675738c43cbdb5f9b478d53d6124db38ba3004d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270065"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="b50c1-103">Kundenprofile: Such- und Filterindex</span><span class="sxs-lookup"><span data-stu-id="b50c1-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="b50c1-104">Das Ergebnis der Vereinheitlichung Ihrer Kundendaten ist eine Kundenprofileinheit, die eine einheitliche Sicht auf Ihren gesamten Kundenstamm bietet.</span><span class="sxs-lookup"><span data-stu-id="b50c1-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="b50c1-105">Um schnell [Informationen über einen bestimmten Kunden oder eine bestimmte Kundengruppe zu finden](customer-profiles.md), können Sie die Funktionen **Suchen** und **Filter** auf der Seite **Kunden** konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b50c1-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="b50c1-106">Lesen Sie weiter, um zu erfahren, wie Admins die Attribute auf der Seite **Such- und Filterindex** bearbeiten können, die den Benutzern zum Suchen und Filtern zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="b50c1-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b50c1-107">![Suchfilter](media/search-filter.png "Suchfilter")</span><span class="sxs-lookup"><span data-stu-id="b50c1-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="b50c1-108">Felder hinzufügen und Attribute angeben</span><span class="sxs-lookup"><span data-stu-id="b50c1-108">Add fields and specify attributes</span></span>

<span data-ttu-id="b50c1-109">Wenn Sie als Administrator zum ersten Mal durchsuchbare Attribute definieren, müssen Sie zunächst indizierte Felder definieren.</span><span class="sxs-lookup"><span data-stu-id="b50c1-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="b50c1-110">Wir empfehlen Ihnen, alle Attribute auszuwählen, nach denen Benutzer Kunden auf der Seite **Kunden** suchen und filtern können.</span><span class="sxs-lookup"><span data-stu-id="b50c1-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="b50c1-111">Sie können nur Attribute angeben, die in der Entität Kundenprofil vorhanden sind, die Sie während des Datenvereinheitlichungsprozesses angelegt haben.</span><span class="sxs-lookup"><span data-stu-id="b50c1-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="b50c1-112">Öffnen Sie die Seite **Kunden** und wählen Sie **Such- & Filterindex**.</span><span class="sxs-lookup"><span data-stu-id="b50c1-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="b50c1-113">Wählen Sie **+ Hinzufügen**, um die indizierten Felder anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b50c1-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="b50c1-114">Wählen Sie die Attribute in der Liste aus, die Sie als indizierte Felder hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="b50c1-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="b50c1-115">Sie können jederzeit weitere Attribute hinzufügen, indem Sie **Hinzufügen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="b50c1-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="b50c1-116">Sie können auch alle ausgewählten Attribute entfernen, indem Sie das Symbol **Entfernen** wählen.</span><span class="sxs-lookup"><span data-stu-id="b50c1-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="b50c1-117">Durchsuchen Sie die Tabelle Indizierte Kundenfelder</span><span class="sxs-lookup"><span data-stu-id="b50c1-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="b50c1-118">Die folgenden Informationen werden in der Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b50c1-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="b50c1-119">**Name**: Stellt den Namen des Attributs so dar, wie er in der Entität Kundenprofil erscheint.</span><span class="sxs-lookup"><span data-stu-id="b50c1-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="b50c1-120">**Datentyp**: Gibt an, ob der Datentyp eine Zeichenfolge, eine Zahl oder ein Datum ist.</span><span class="sxs-lookup"><span data-stu-id="b50c1-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="b50c1-121">**In die Suche einbeziehen**: Gibt an, ob dieses Attribut für die Suche nach Kunden auf der Seite **Kunden** über das Feld **Suche** verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b50c1-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="b50c1-122">**Filter hinzufügen**: Steuerelement, um festzulegen, wie dieses Attribut für die Filterung auf der Seite **Kunden** verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b50c1-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="b50c1-123">Bearbeitung von Filteroptionen für ein bestimmtes Attribut</span><span class="sxs-lookup"><span data-stu-id="b50c1-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="b50c1-124">Das Menü **Filter** auf der Seite **Kunden** kann eine unterschiedliche Anzahl von Attribut-Ebenen enthalten (z. B. verschiedene Altersgruppen, nach denen Kunden gefiltert werden können).</span><span class="sxs-lookup"><span data-stu-id="b50c1-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="b50c1-125">Wählen Sie **Filter hinzufügen** für ein bestimmtes Attribut auf der Seite **Such- und Filterindex**.</span><span class="sxs-lookup"><span data-stu-id="b50c1-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="b50c1-126">Sie können die Anzahl der Ergebnisse und die Reihenfolge, in der sie organisiert werden, definieren.</span><span class="sxs-lookup"><span data-stu-id="b50c1-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="b50c1-127">Abhängig vom Datentyp des Attributs erscheint einer der folgenden Bereiche.</span><span class="sxs-lookup"><span data-stu-id="b50c1-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="b50c1-128">Zeichenfolgentypattribute: Geben Sie die Anzahl der gewünschten Ergebnisse auf dem **Zeichenfolgenfilteroptionen** Bereich und die Bestellrichtlinie an, nach der sie organisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b50c1-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="b50c1-129">Numerische Zeichenfolgenattribute: Geben Sie die Intervalle auf dem **Nummernfilteroptionen** Bereich und die Bestellrichtlinie an, nach der sie organisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b50c1-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="b50c1-130">Datenattribute: Geben Sie die Intervalle auf dem **Datenfilteroptionen** Bereich und die Bestellrichtlinie an, nach der sie organisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b50c1-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="b50c1-131">Wählen Sie **Speichern**, um Ihre Änderungen zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="b50c1-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="b50c1-132">Wählen Sie **Ausführen**, sobald Sie bereit sind, Ihre Einstellungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="b50c1-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b50c1-133">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b50c1-133">Next steps</span></span>

<span data-ttu-id="b50c1-134">Gehen Sie zu Seite **Kunden**, um nach Kundenprofilen zu suchen, oder verwenden Sie die indizierten Felder, um eine Teilmenge aller Kundenprofile anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b50c1-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]