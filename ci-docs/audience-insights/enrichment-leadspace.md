---
title: Anreicherung von Firmenprofilen mit der Drittanbieter-Anreicherung Leadspace
description: Allgemeine Informationen über die Drittanbieter-Anreicherung von Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668722"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="4bc06-103">Anreicherung von Firmenprofilen mit Leadspace (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="4bc06-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="4bc06-104">Leadspace ist ein datenwissenschaftliches Unternehmen, das eine B2B-Kundendatenplattform anbietet.</span><span class="sxs-lookup"><span data-stu-id="4bc06-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="4bc06-105">Sie ermöglicht es Kunden mit einheitlichen Kundenprofilen für Unternehmen, ihre Daten anzureichern.</span><span class="sxs-lookup"><span data-stu-id="4bc06-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="4bc06-106">Die Anreicherung umfasst zusätzliche Attribute wie Unternehmensgröße, Standort, Branche und mehr.</span><span class="sxs-lookup"><span data-stu-id="4bc06-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4bc06-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4bc06-107">Prerequisites</span></span>

<span data-ttu-id="4bc06-108">Um Leadspace zu konfigurieren, müssen die folgenden Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="4bc06-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="4bc06-109">Sie haben eine aktive Leadspace-Lizenz und den „dauerhaften Schlüssel“ (bezeichnet als **Leadspace-Token**).</span><span class="sxs-lookup"><span data-stu-id="4bc06-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="4bc06-110">Gehen Sie direkt zu [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) für Details über ihr Produkt.</span><span class="sxs-lookup"><span data-stu-id="4bc06-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="4bc06-111">Sie haben [Administrator](permissions.md#administrator) Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="4bc06-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="4bc06-112">Sie haben [Einheitliche Kundenprofile](customer-profiles.md) für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="4bc06-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="4bc06-113">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="4bc06-113">Configuration</span></span>

1. <span data-ttu-id="4bc06-114">Gehen Sie in Zielgruppen-Insights zu **Daten** > **Anreicherung**.</span><span class="sxs-lookup"><span data-stu-id="4bc06-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="4bc06-115">Wählen Sie **Meine Daten anreichern** auf der Leadspace-Kachel.</span><span class="sxs-lookup"><span data-stu-id="4bc06-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Screenshot der Leadspace-Kachel.":::

1. <span data-ttu-id="4bc06-117">Wählen Sie **Starten** und geben Sie einen aktiven **Leadspace-Token** (unbefristeter Schlüssel) ein.</span><span class="sxs-lookup"><span data-stu-id="4bc06-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="4bc06-118">Prüfen und geben Sie Ihre Zustimmung zum **Datenschutz und Einhaltung von Vorschriften**, indem Sie das Kontrollkästchen **Ich stimme zu** markieren.</span><span class="sxs-lookup"><span data-stu-id="4bc06-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="4bc06-119">Bestätigen Sie beide Eingaben, indem Sie **Verbinden mit Leadspace** wählen.</span><span class="sxs-lookup"><span data-stu-id="4bc06-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="4bc06-120">Wählen Sie **Daten zuordnen** und legen Sie fest, welche Felder aus Ihren Unified Profiles verwendet werden sollen, um nach passenden Firmendaten von Leadspace zu suchen.</span><span class="sxs-lookup"><span data-stu-id="4bc06-120">Select **Map data** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="4bc06-121">Das Feld **Firmenname** ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4bc06-121">The **Name of company** field is required.</span></span> <span data-ttu-id="4bc06-122">Für eine höhere Abgleichsgenauigkeit können bis zu zwei weitere Felder, **Firmen-Website** und **Firmenstandort**, hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="4bc06-122">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace-Feld-Zuordnungsbereich.":::
   
1. <span data-ttu-id="4bc06-124">Wählen Sie **Anwenden**, um die Zuordnung der Felder abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4bc06-124">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="4bc06-125">Wählen Sie **Ausführen**, um die Firmenprofile anzureichern.</span><span class="sxs-lookup"><span data-stu-id="4bc06-125">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="4bc06-126">Wie lange eine Anreicherung dauert, hängt von der Anzahl der vereinheitlichten Kundenprofile ab.</span><span class="sxs-lookup"><span data-stu-id="4bc06-126">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="4bc06-127">Anreicherungsergebnisse</span><span class="sxs-lookup"><span data-stu-id="4bc06-127">Enrichment results</span></span>

<span data-ttu-id="4bc06-128">Nach dem Aktualisieren der Anreicherung können Sie die neu angereicherten Unternehmensdaten unter[Meine Bereicherung](enrichment-hub.md) überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4bc06-128">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="4bc06-129">Den Zeitpunkt der letzten Aktualisierung und die Anzahl der angereicherten Profile können Sie anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4bc06-129">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="4bc06-130">Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.</span><span class="sxs-lookup"><span data-stu-id="4bc06-130">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="4bc06-131">Weitere Informationen finden Sie unter [Leadspace-APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="4bc06-131">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4bc06-132">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4bc06-132">Next steps</span></span>

<span data-ttu-id="4bc06-133">Bauen Sie auf Ihren angereicherten Kundendaten auf.</span><span class="sxs-lookup"><span data-stu-id="4bc06-133">Build on top of your enriched customer data.</span></span> <span data-ttu-id="4bc06-134">Erstellen Sie [Segmente](segments.md), [Maße](measures.md), und selbst [Exportdaten](export-destinations.md), um Ihren Kunden personalisierte Erlebnisse zu bieten.</span><span class="sxs-lookup"><span data-stu-id="4bc06-134">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4bc06-135">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="4bc06-135">Data privacy and compliance</span></span>

<span data-ttu-id="4bc06-136">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Leadspace aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="4bc06-136">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4bc06-137">Microsoft wird diese Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Leadspace alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können.</span><span class="sxs-lookup"><span data-stu-id="4bc06-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4bc06-138">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4bc06-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4bc06-139">Ihr Dynamics 365 Customer Insights-Administrator kann diese Anreicherung jederzeit entfernen, um die Nutzung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="4bc06-139">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>