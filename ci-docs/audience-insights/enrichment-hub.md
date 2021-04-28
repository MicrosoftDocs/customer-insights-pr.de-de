---
title: Anreichern von vereinheitlichten Kundenprofilen
description: Verwenden Sie Funktionalitäten, um Ihre Kundendaten anzureichern.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896004"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="a77d4-103">Anreicherung für Kundenprofile (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="a77d4-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="a77d4-104">Nutzen Sie Daten aus Quellen wie Microsoft und anderen Partnern zur Anreicherung Ihrer Kundendaten.</span><span class="sxs-lookup"><span data-stu-id="a77d4-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Enrichment Hub-Seite":::

<span data-ttu-id="a77d4-106">Gehen Sie in Zielgruppen-Insights zu **Daten** > **Anreicherung**, um mit Anreicherungsoptionen zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="a77d4-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="a77d4-107">Um Anreicherungen erstellen oder bearbeiten zu können, benötigen Sie die Berechtigungen eines Teilnehmers oder Administrators.</span><span class="sxs-lookup"><span data-stu-id="a77d4-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="a77d4-108">Weitere Informationen finden Sie unter [Berechtigungen](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a77d4-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="a77d4-109">Auf der Registerkarte **Entdecken** finden Sie die folgenden Anreicherungen:</span><span class="sxs-lookup"><span data-stu-id="a77d4-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="a77d4-110">[Marken](enrichment-microsoft.md) bereitgestellt von Microsoft</span><span class="sxs-lookup"><span data-stu-id="a77d4-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="a77d4-111">[Interessen](enrichment-microsoft.md) bereitgestellt von Microsoft</span><span class="sxs-lookup"><span data-stu-id="a77d4-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="a77d4-112">[Unternehmensdaten](enrichment-leadspace.md) werden von Leadspace bereitgestellt</span><span class="sxs-lookup"><span data-stu-id="a77d4-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="a77d4-113">[Demografische Daten](enrichment-experian.md) bereitgestellt von Experian</span><span class="sxs-lookup"><span data-stu-id="a77d4-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="a77d4-114">[Standortdaten](enrichment-here.md), bereitgestellt von HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="a77d4-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="a77d4-115">[Kundendaten](enrichment-SFTP-custom-import.md) über Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="a77d4-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="a77d4-116">Auf der Registerkarte **Meine Anreicherungen** können Sie die von Ihnen konfigurierten Anreicherungen sehen und ihre Eigenschaften bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="a77d4-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="a77d4-117">Vorhandene Anreicherungen verwalten</span><span class="sxs-lookup"><span data-stu-id="a77d4-117">Manage existing enrichments</span></span>

<span data-ttu-id="a77d4-118">Gehen Sie zu **Meine Anreicherungen**, um alle konfigurierten Anreicherungen zu sehen.</span><span class="sxs-lookup"><span data-stu-id="a77d4-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="a77d4-119">Jede Anreicherung wird als Zeile dargestellt, die zusätzliche Informationen zur Anreicherung enthält.</span><span class="sxs-lookup"><span data-stu-id="a77d4-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="a77d4-120">Wählen Sie eine Anreicherung aus, um die verfügbaren Optionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a77d4-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="a77d4-121">Sie können auch die Auslassungspunkte (...) in einem Listenelement auswählen, um die Optionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a77d4-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Optionen zum Verwalten von Anreicherungen in der Liste der Anreicherungen":::

- <span data-ttu-id="a77d4-123">**Anzeige** von Anreicherungsdetails mit der Anzahl der angereicherten Kundenprofile.</span><span class="sxs-lookup"><span data-stu-id="a77d4-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="a77d4-124">**Bearbeiten** der Anreicherungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="a77d4-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="a77d4-125">**Ausführen** der Bereicherung, um Kundenprofile mit den neuesten Daten zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a77d4-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="a77d4-126">**Deaktivieren** einer vorhandenen Anreicherung, um zu verhindern, dass sie bei jeder geplanten Aktualisierung automatisch aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="a77d4-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="a77d4-127">Die Daten der letzten erfolgreichen Aktualisierung sind weiterhin verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a77d4-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="a77d4-128">**Aktivieren** eine inaktiven Anreicherung, um die automatische Aktualisierung bei jeder geplanten Aktualisierung neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="a77d4-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="a77d4-129">**Löschen** einer Anreicherung.</span><span class="sxs-lookup"><span data-stu-id="a77d4-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="a77d4-130">Sie können mehrere Anreicherungen gleichzeitig ausführen oder deaktivieren, indem Sie sie in der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="a77d4-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="a77d4-131">Anzeige- und Bearbeitungsoptionen sind nicht als Massenaktion verfügbar und funktionieren jeweils nur für eine Anreicherung.</span><span class="sxs-lookup"><span data-stu-id="a77d4-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="a77d4-132">Anreicherungen und Verbindungen</span><span class="sxs-lookup"><span data-stu-id="a77d4-132">Enrichments and connections</span></span>

<span data-ttu-id="a77d4-133">Anreicherungen von Drittanbietern werden mithilfe von [Verbindungen](connections.md) konfiguriert, die ein Administrator mit Anmeldeinformationen einrichtet und die Zustimmung zur Datenübertragung erteilt.</span><span class="sxs-lookup"><span data-stu-id="a77d4-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="a77d4-134">Die Verbindung kann dann von Administratoren und Mitwirkenden zur Anreicherungskonfiguration verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a77d4-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="a77d4-135">Mehrfachanreicherungen des gleichen Typs</span><span class="sxs-lookup"><span data-stu-id="a77d4-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="a77d4-136">Die zu bereichernde Entität wird während der Anreicherungskonfiguration angegeben, sodass Sie nur eine Teilmenge Ihrer Profile anreichern können.</span><span class="sxs-lookup"><span data-stu-id="a77d4-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="a77d4-137">Reichern Sie beispielsweise Daten nur für ein bestimmtes Segment an.</span><span class="sxs-lookup"><span data-stu-id="a77d4-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="a77d4-138">Sie können mehrere Anreicherungen desselben Typs konfigurieren und dieselbe Verbindung wiederverwenden.</span><span class="sxs-lookup"><span data-stu-id="a77d4-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="a77d4-139">Bei einigen Anreicherungen ist die Anzahl der Anreicherungen desselben Typs, die erstellt werden können, begrenzt.</span><span class="sxs-lookup"><span data-stu-id="a77d4-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="a77d4-140">Die Grenzwerte und die aktuelle Verwendung sind auf der Seite **Anreicherung** zu sehen.</span><span class="sxs-lookup"><span data-stu-id="a77d4-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
