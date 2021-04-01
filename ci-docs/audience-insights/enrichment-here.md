---
title: Anreicherung von mit der Drittanbieter-Anreicherung HERE Technologies
description: Allgemeine Informationen über die Drittanbieter-Anreicherung von HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597740"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="edbab-103">Anreicherung von Kundenprofilen mit HERE Technologies (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="edbab-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="edbab-104">HERE Technologies ist ein Unternehmen für Standortplattformen, das ortsbezogene Daten und Dienste anbietet.</span><span class="sxs-lookup"><span data-stu-id="edbab-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="edbab-105">Mit den Datenanreicherungsdiensten von HERE Technologies können Sie durch Adressnormalisierung, Extraktion von Breiten- und Längengraden und mehr ein genaueres Standortverständnis Ihrer Kunden aufbauen.</span><span class="sxs-lookup"><span data-stu-id="edbab-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="edbab-106">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="edbab-106">Prerequisites</span></span>

<span data-ttu-id="edbab-107">Um HERE Technologies Enrichments zu konfigurieren, müssen die folgenden Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="edbab-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="edbab-108">Sie haben ein aktives HERE Technologies Abonnement.</span><span class="sxs-lookup"><span data-stu-id="edbab-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="edbab-109">Um ein Abonnement zu erhalten, können Sie sich [hier anmelden](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) oder [direkt mit HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) in Verbindung setzen.</span><span class="sxs-lookup"><span data-stu-id="edbab-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="edbab-110">Erfahren Sie mehr über HERE Technologies Location Enrichment.</span><span class="sxs-lookup"><span data-stu-id="edbab-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="edbab-111">Sie haben den HERE Technologies API-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="edbab-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="edbab-112">Sie haben [Administrator](permissions.md#administrator) Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="edbab-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="edbab-113">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="edbab-113">Configuration</span></span>

1. <span data-ttu-id="edbab-114">Gehen Sie zu **Daten** > **Anreicherung**.</span><span class="sxs-lookup"><span data-stu-id="edbab-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="edbab-115">Wählen Sie **Meine Daten anreichern** auf der Kachel HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="edbab-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="edbab-116">![HERE Technologies Kachel](media/HERE-tile.png "HERE Technologies Kachel")</span><span class="sxs-lookup"><span data-stu-id="edbab-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="edbab-117">Geben Sie einen aktiven **HERE Technologies API-Schlüssel** ein.</span><span class="sxs-lookup"><span data-stu-id="edbab-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="edbab-118">Prüfen und geben Sie Ihre Zustimmung zum **Datenschutz und Einhaltung von Vorschriften**, indem Sie das Kontrollkästchen **Ich stimme zu** markieren.</span><span class="sxs-lookup"><span data-stu-id="edbab-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="edbab-119">Bestätigen Sie beide Eingaben, indem Sie **Verbinden mit HERE** wählen.</span><span class="sxs-lookup"><span data-stu-id="edbab-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="edbab-120">Wählen Sie **Daten hinzufügen** und dann den **Kundendatensatz**, den Sie mit Standortdaten von HERE Technologies anreichern möchten.</span><span class="sxs-lookup"><span data-stu-id="edbab-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="edbab-121">Sie können die **Kundenentität** auswählen, um alle Ihre Kundenprofile anzureichern, oder eine Segmententität auswählen, um nur Kundenprofile anzureichern, die in diesem Segment enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="edbab-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Screenshot bei Auswahl des Kundendatensatzes.":::

1. <span data-ttu-id="edbab-123">Wählen Sie, ob Sie Felder der primären und/oder sekundären Adresse zuordnen wollen.</span><span class="sxs-lookup"><span data-stu-id="edbab-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="edbab-124">Sie können eine Feldzuordnung für beide Adressen angeben (z. B. eine Privat- und eine Geschäftsadresse) und die Profile für beide Adressen getrennt anreichern.</span><span class="sxs-lookup"><span data-stu-id="edbab-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="edbab-125">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="edbab-125">Select **Next**.</span></span>

1. <span data-ttu-id="edbab-126">Definieren Sie, welche Felder aus Ihren einheitlichen Profilen verwendet werden sollen, um nach übereinstimmenden Standortdaten von HERE Technologies zu suchen.</span><span class="sxs-lookup"><span data-stu-id="edbab-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="edbab-127">Die Felder **Straße 1** und **Postleitzahl** sind für die ausgewählte primäre und/oder sekundäre Adresse erforderlich.</span><span class="sxs-lookup"><span data-stu-id="edbab-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="edbab-128">Für eine höhere Abgleichsgenauigkeit können weitere Felder hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="edbab-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="edbab-129">![HERE Technologies Anreicherungs-Konfigurationsseite](media/enrichment-HERE-configuration.png "HERE Technologies Anreicherungs-Konfigurationsseite")</span><span class="sxs-lookup"><span data-stu-id="edbab-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="edbab-130">Wählen Sie **Anwenden**, um die Zuordnung der Felder abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="edbab-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="edbab-131">Anreicherungsergebnisse</span><span class="sxs-lookup"><span data-stu-id="edbab-131">Enrichment results</span></span>

<span data-ttu-id="edbab-132">Wählen Sie **Ausführen** aus der Befehlsleiste aus, um den Anreicherungsprozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="edbab-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="edbab-133">Sie können das System die Anreicherung auch automatisch als Teil von einer [geplante Aktualisierung](system.md#schedule-tab) ausführen lassen.</span><span class="sxs-lookup"><span data-stu-id="edbab-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="edbab-134">Die Verarbeitungszeit hängt von der Größe Ihrer Kundendaten und den API-Antwortzeiten von HERE Technologies ab.</span><span class="sxs-lookup"><span data-stu-id="edbab-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="edbab-135">Nach Abschluss des Anreicherungsprozesses können Sie die neu angereicherten Kundenprofildaten unter **Meine Anreicherungen** überprüfen.</span><span class="sxs-lookup"><span data-stu-id="edbab-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="edbab-136">Außerdem finden Sie den Zeitpunkt des letzten Updates und die Anzahl der angereicherten Profile.</span><span class="sxs-lookup"><span data-stu-id="edbab-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="edbab-137">Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.</span><span class="sxs-lookup"><span data-stu-id="edbab-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="edbab-138">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="edbab-138">Next steps</span></span>

<span data-ttu-id="edbab-139">Bauen Sie auf Ihren angereicherten Kundendaten auf.</span><span class="sxs-lookup"><span data-stu-id="edbab-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="edbab-140">Erstellen Sie [Segmente](segments.md), [Maße](measures.md), und selbst [Exportdaten](export-destinations.md), um Ihren Kunden personalisierte Erlebnisse zu bieten.</span><span class="sxs-lookup"><span data-stu-id="edbab-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="edbab-141">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="edbab-141">Data privacy and compliance</span></span>

<span data-ttu-id="edbab-142">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an HERE Technologies aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="edbab-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="edbab-143">Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass HERE Technologies alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können.</span><span class="sxs-lookup"><span data-stu-id="edbab-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="edbab-144">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="edbab-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="edbab-145">Ihr Dynamics 365 Customer Insights-Administrator kann diese Anreicherung jederzeit entfernen, um die Nutzung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="edbab-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]