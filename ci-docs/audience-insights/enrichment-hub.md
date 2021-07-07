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
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305247"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="4e7b0-103">Anreicherung für Kundenprofile (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="4e7b0-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="4e7b0-104">Nutzen Sie Daten aus Quellen wie Microsoft und anderen Partnern zur Anreicherung Ihrer Kundendaten.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Enrichment Hub-Seite":::

<span data-ttu-id="4e7b0-106">Gehen Sie in Zielgruppen-Insights zu **Daten** > **Anreicherung**, um mit Anreicherungsoptionen zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>  

<span data-ttu-id="4e7b0-107">Um Anreicherungen erstellen oder bearbeiten zu können, benötigen Sie die Berechtigungen eines Teilnehmers oder Administrators.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="4e7b0-108">Weitere Informationen finden Sie unter [Berechtigungen](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="4e7b0-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="4e7b0-109">Auf der Registerkarte **Entdecken** finden Sie die folgenden Anreicherungen:</span><span class="sxs-lookup"><span data-stu-id="4e7b0-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="4e7b0-110">[Marken](enrichment-microsoft.md) bereitgestellt von Microsoft</span><span class="sxs-lookup"><span data-stu-id="4e7b0-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="4e7b0-111">[Interessen](enrichment-microsoft.md) bereitgestellt von Microsoft</span><span class="sxs-lookup"><span data-stu-id="4e7b0-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="4e7b0-112">[Erweiterte Adressen](enrichment-enhanced-addresses.md) bereitgestellt von Microsoft</span><span class="sxs-lookup"><span data-stu-id="4e7b0-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="4e7b0-113">[Unternehmensdaten](enrichment-leadspace.md) werden von Leadspace bereitgestellt</span><span class="sxs-lookup"><span data-stu-id="4e7b0-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="4e7b0-114">[Demografiedaten](enrichment-experian.md) von Experian bereitgestellt</span><span class="sxs-lookup"><span data-stu-id="4e7b0-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="4e7b0-115">[Standortdaten](enrichment-here.md), bereitgestellt von HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="4e7b0-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="4e7b0-116">[Kundendaten](enrichment-SFTP-custom-import.md) über Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="4e7b0-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="4e7b0-117">Auf der Registerkarte **Meine Anreicherungen** können Sie die von Ihnen konfigurierten Anreicherungen sehen und ihre Eigenschaften bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="4e7b0-118">Vorhandene Anreicherungen verwalten</span><span class="sxs-lookup"><span data-stu-id="4e7b0-118">Manage existing enrichments</span></span>

<span data-ttu-id="4e7b0-119">Gehen Sie zur Registerkarte **Meine Anreicherungen**, um alle konfigurierten Anreicherungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-119">Go to the **My enrichments** tab to see all configured enrichments.</span></span> <span data-ttu-id="4e7b0-120">Jede Anreicherung wird als Zeile dargestellt, die zusätzliche Informationen zur Anreicherung enthält.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="4e7b0-121">Wählen Sie eine Anreicherung aus, um die verfügbaren Optionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="4e7b0-122">Sie können auch die Auslassungspunkte (...) in einem Listenelement auswählen, um die Optionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Optionen zum Verwalten von Anreicherungen in der Liste der Anreicherungen":::

- <span data-ttu-id="4e7b0-124">**Anzeige** von Anreicherungsdetails mit der Anzahl der angereicherten Kundenprofile.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="4e7b0-125">**Bearbeiten** der Anreicherungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="4e7b0-126">**Ausführen** der Bereicherung, um Kundenprofile mit den neuesten Daten zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="4e7b0-127">**Deaktivieren** einer vorhandenen Anreicherung, um zu verhindern, dass sie bei jeder geplanten Aktualisierung automatisch aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="4e7b0-128">Die Daten der letzten erfolgreichen Aktualisierung sind weiterhin verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="4e7b0-129">**Aktivieren** eine inaktiven Anreicherung, um die automatische Aktualisierung bei jeder geplanten Aktualisierung neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="4e7b0-130">**Löschen** einer Anreicherung.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="4e7b0-131">Sie können mehrere Anreicherungen gleichzeitig ausführen oder deaktivieren, indem Sie sie in der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="4e7b0-132">Anzeige- und Bearbeitungsoptionen sind nicht als Massenaktion verfügbar und funktionieren jeweils nur für eine Anreicherung.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="4e7b0-133">Anreicherungen und Verbindungen</span><span class="sxs-lookup"><span data-stu-id="4e7b0-133">Enrichments and connections</span></span>

<span data-ttu-id="4e7b0-134">Anreicherungen von Drittanbietern werden mithilfe von [Verbindungen](connections.md) konfiguriert, die ein Administrator mit Anmeldeinformationen einrichtet und die Zustimmung zur Datenübertragung erteilt.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="4e7b0-135">Die Verbindung kann dann von Administratoren und Mitwirkenden zur Anreicherungskonfiguration verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="4e7b0-136">Mehrfachanreicherungen des gleichen Typs</span><span class="sxs-lookup"><span data-stu-id="4e7b0-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="4e7b0-137">Die zu bereichernde Entität wird während der Anreicherungskonfiguration angegeben, sodass Sie nur eine Teilmenge Ihrer Profile anreichern können.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="4e7b0-138">Anreichern von Daten beispielsweise nur für ein bestimmtes Segment.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-138">For example, enrich data only for a specific segment.</span></span> <span data-ttu-id="4e7b0-139">Sie können mehrere Anreicherungen desselben Typs konfigurieren und dieselbe Verbindung wiederverwenden.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="4e7b0-140">Bei einigen Anreicherungen ist die Anzahl der Anreicherungen desselben Typs, die erstellt werden können, begrenzt.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="4e7b0-141">Die Grenzwerte und die aktuelle Verwendung sind auf der Seite **Anreicherung** zu sehen.</span><span class="sxs-lookup"><span data-stu-id="4e7b0-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
