---
title: Anreicherung von Firmenprofilen mit der Drittanbieter-Anreicherung Leadspace
description: Allgemeine Informationen über die Drittanbieter-Anreicherung von Leadspace.
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597648"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="23dbb-103">Anreicherung von Firmenprofilen mit Leadspace (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="23dbb-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="23dbb-104">Leadspace ist ein datenwissenschaftliches Unternehmen, das eine B2B-Kundendatenplattform anbietet.</span><span class="sxs-lookup"><span data-stu-id="23dbb-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="23dbb-105">Sie ermöglicht es Kunden mit einheitlichen Kundenprofilen für Unternehmen, ihre Daten anzureichern.</span><span class="sxs-lookup"><span data-stu-id="23dbb-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="23dbb-106">Die Anreicherung umfasst zusätzliche Attribute wie Unternehmensgröße, Standort, Branche und mehr.</span><span class="sxs-lookup"><span data-stu-id="23dbb-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="23dbb-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="23dbb-107">Prerequisites</span></span>

<span data-ttu-id="23dbb-108">Um Leadspace zu konfigurieren, müssen die folgenden Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="23dbb-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="23dbb-109">Sie haben eine aktive Leadspace-Lizenz und den „dauerhaften Schlüssel“ (bezeichnet als **Leadspace-Token**).</span><span class="sxs-lookup"><span data-stu-id="23dbb-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="23dbb-110">Gehen Sie direkt zu [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) für Details über ihr Produkt.</span><span class="sxs-lookup"><span data-stu-id="23dbb-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="23dbb-111">Sie haben [Administrator](permissions.md#administrator) Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="23dbb-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="23dbb-112">Sie haben [Einheitliche Kundenprofile](customer-profiles.md) für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="23dbb-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="23dbb-113">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="23dbb-113">Configuration</span></span>

1. <span data-ttu-id="23dbb-114">Gehen Sie in Zielgruppen-Insights zu **Daten** > **Anreicherung**.</span><span class="sxs-lookup"><span data-stu-id="23dbb-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="23dbb-115">Wählen Sie **Meine Daten anreichern** auf der Leadspace-Kachel.</span><span class="sxs-lookup"><span data-stu-id="23dbb-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Screenshot der Leadspace-Kachel.":::

1. <span data-ttu-id="23dbb-117">Wählen Sie **Starten** und geben Sie einen aktiven **Leadspace-Token** (unbefristeter Schlüssel) ein.</span><span class="sxs-lookup"><span data-stu-id="23dbb-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="23dbb-118">Prüfen und geben Sie Ihre Zustimmung zum **Datenschutz und Einhaltung von Vorschriften**, indem Sie das Kontrollkästchen **Ich stimme zu** markieren.</span><span class="sxs-lookup"><span data-stu-id="23dbb-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="23dbb-119">Bestätigen Sie beide Eingaben, indem Sie **Verbinden mit Leadspace** wählen.</span><span class="sxs-lookup"><span data-stu-id="23dbb-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="23dbb-120">Wählen Sie **Daten zuordnen** und dann den Datensatz, den Sie mit Unternehmensdaten von Leadspace anreichern möchten.</span><span class="sxs-lookup"><span data-stu-id="23dbb-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="23dbb-121">Sie können die *Kundenentität* auswählen, um alle Ihre Kundenprofile anzureichern, oder eine Segmententität auswählen, um nur Kundenprofile anzureichern, die in diesem Segment enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="23dbb-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Wählen Sie zwischen Kundenprofil und Segmentanreicherung.":::

1. <span data-ttu-id="23dbb-123">Wählen Sie **Weiter** und legen Sie fest, welche Felder aus Ihren Unified Profiles verwendet werden sollen, um nach passenden Firmendaten von Leadspace zu suchen.</span><span class="sxs-lookup"><span data-stu-id="23dbb-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="23dbb-124">Das Feld **Firmenname** ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="23dbb-124">The **Name of company** field is required.</span></span> <span data-ttu-id="23dbb-125">Für eine höhere Abgleichsgenauigkeit können bis zu zwei weitere Felder, **Firmen-Website** und **Firmenstandort**, hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="23dbb-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace-Feld-Zuordnungsbereich.":::
   
1. <span data-ttu-id="23dbb-127">Wählen Sie **Anwenden**, um die Zuordnung der Felder abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="23dbb-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="23dbb-128">Wählen Sie **Ausführen**, um die Firmenprofile anzureichern.</span><span class="sxs-lookup"><span data-stu-id="23dbb-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="23dbb-129">Wie lange eine Anreicherung dauert, hängt von der Anzahl der vereinheitlichten Kundenprofile ab.</span><span class="sxs-lookup"><span data-stu-id="23dbb-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="23dbb-130">Anreicherungsergebnisse</span><span class="sxs-lookup"><span data-stu-id="23dbb-130">Enrichment results</span></span>

<span data-ttu-id="23dbb-131">Nach dem Aktualisieren der Anreicherung können Sie die neu angereicherten Unternehmensdaten unter[Meine Bereicherung](enrichment-hub.md) überprüfen.</span><span class="sxs-lookup"><span data-stu-id="23dbb-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="23dbb-132">Den Zeitpunkt der letzten Aktualisierung und die Anzahl der angereicherten Profile können Sie anzeigen.</span><span class="sxs-lookup"><span data-stu-id="23dbb-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="23dbb-133">Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.</span><span class="sxs-lookup"><span data-stu-id="23dbb-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="23dbb-134">Weitere Informationen finden Sie unter [Leadspace-APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="23dbb-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="23dbb-135">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="23dbb-135">Next steps</span></span>

<span data-ttu-id="23dbb-136">Bauen Sie auf Ihren angereicherten Kundendaten auf.</span><span class="sxs-lookup"><span data-stu-id="23dbb-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="23dbb-137">Erstellen Sie [Segmente](segments.md), [Maße](measures.md), und selbst [Exportdaten](export-destinations.md), um Ihren Kunden personalisierte Erlebnisse zu bieten.</span><span class="sxs-lookup"><span data-stu-id="23dbb-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="23dbb-138">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="23dbb-138">Data privacy and compliance</span></span>

<span data-ttu-id="23dbb-139">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Leadspace aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="23dbb-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="23dbb-140">Microsoft wird diese Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Leadspace alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können.</span><span class="sxs-lookup"><span data-stu-id="23dbb-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="23dbb-141">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="23dbb-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="23dbb-142">Ihr Dynamics 365 Customer Insights-Administrator kann diese Anreicherung jederzeit entfernen, um die Nutzung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="23dbb-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]