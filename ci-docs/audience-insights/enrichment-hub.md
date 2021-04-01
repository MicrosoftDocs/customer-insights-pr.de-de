---
title: Anreichern von vereinheitlichten Kundenprofilen
description: Verwenden Sie Funktionalitäten, um Ihre Kundendaten anzureichern.
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597694"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="08c29-103">Anreicherung für Kundenprofile (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="08c29-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="08c29-104">Nutzen Sie Daten aus Quellen wie Microsoft und anderen Partnern zur Anreicherung Ihrer Kundendaten.</span><span class="sxs-lookup"><span data-stu-id="08c29-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Enrichment Hub-Seite":::

<span data-ttu-id="08c29-106">Gehen Sie in Zielgruppen-Insights zu **Daten** > **Anreicherung**, um mit Anreicherungsoptionen zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="08c29-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="08c29-107">Um Anreicherungen erstellen oder bearbeiten zu können, benötigen Sie die Berechtigungen eines Teilnehmers oder Administrators.</span><span class="sxs-lookup"><span data-stu-id="08c29-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="08c29-108">Weitere Informationen finden Sie unter [Berechtigungen](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="08c29-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="08c29-109">Auf der Registerkarte **Entdecken** finden Sie die folgenden Anreicherungen:</span><span class="sxs-lookup"><span data-stu-id="08c29-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="08c29-110">[Marken](enrichment-microsoft-graph.md) bereitgestellt von Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="08c29-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="08c29-111">[Interessen](enrichment-microsoft-graph.md) bereitgestellt von Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="08c29-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="08c29-112">[Unternehmensdaten](enrichment-leadspace.md) werden von Leadspace bereitgestellt</span><span class="sxs-lookup"><span data-stu-id="08c29-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="08c29-113">[Demografische Daten](enrichment-experian.md) bereitgestellt von Experian</span><span class="sxs-lookup"><span data-stu-id="08c29-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="08c29-114">[Standortdaten](enrichment-here.md), bereitgestellt von HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="08c29-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="08c29-115">[Kundendaten](enrichment-SFTP-custom-import.md) über Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="08c29-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="08c29-116">Auf der Registerkarte **Meine Anreicherungen** können Sie die von Ihnen konfigurierten Anreicherungen sehen und ihre Eigenschaften bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="08c29-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="08c29-117">Vorhandene Anreicherungen verwalten</span><span class="sxs-lookup"><span data-stu-id="08c29-117">Manage existing enrichments</span></span>

<span data-ttu-id="08c29-118">Gehen Sie zu **Meine Anreicherungen**, um alle konfigurierten Anreicherungen zu sehen.</span><span class="sxs-lookup"><span data-stu-id="08c29-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="08c29-119">Jede Anreicherung wird als Zeile dargestellt, die zusätzliche Informationen zur Anreicherung enthält.</span><span class="sxs-lookup"><span data-stu-id="08c29-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="08c29-120">Wählen Sie eine Anreicherung aus, um die verfügbaren Optionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="08c29-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="08c29-121">Alternativ können Sie die Auslassungspunkte (...) in einem Listenelement auswählen, um die Optionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="08c29-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Optionen zum Verwalten von Anreicherungen in der Liste der Anreicherungen":::

- <span data-ttu-id="08c29-123">**Anzeige** von Anreicherungsdetails mit der Anzahl der angereicherten Kundenprofile.</span><span class="sxs-lookup"><span data-stu-id="08c29-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="08c29-124">**Bearbeiten** der Anreicherungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="08c29-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="08c29-125">**Ausführen** der Bereicherung, um Kundenprofile mit den neuesten Daten zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="08c29-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="08c29-126">**Deaktivieren** einer vorhandenen Anreicherung, um zu verhindern, dass sie bei jeder geplanten Aktualisierung automatisch aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="08c29-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="08c29-127">Die Daten der letzten erfolgreichen Aktualisierung sind weiterhin verfügbar.</span><span class="sxs-lookup"><span data-stu-id="08c29-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="08c29-128">**Aktivieren** eine inaktiven Anreicherung, um die automatische Aktualisierung bei jeder geplanten Aktualisierung neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="08c29-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="08c29-129">**Löschen** einer Anreicherung.</span><span class="sxs-lookup"><span data-stu-id="08c29-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="08c29-130">Sie können mehrere Anreicherungen gleichzeitig ausführen oder deaktivieren, indem Sie sie in der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="08c29-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="08c29-131">Anzeige- und Bearbeitungsoptionen sind nicht als Massenaktion verfügbar und funktionieren jeweils nur für eine Anreicherung.</span><span class="sxs-lookup"><span data-stu-id="08c29-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]