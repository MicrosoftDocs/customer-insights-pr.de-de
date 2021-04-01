---
title: Customer Insights-Daten zu AdRoll exportieren
description: Lernen Sie, wie Sie die Verbindung zu AdRoll konfigurieren.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697073"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="2ac7a-103">Konnektor für AdRoll (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="2ac7a-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="2ac7a-104">Exportieren Sie Segmente einheitlicher Kundenprofile nach AdRoll und verwenden Sie sie für Werbezwecke.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="2ac7a-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2ac7a-105">Prerequisites</span></span>

-   <span data-ttu-id="2ac7a-106">Sie haben ein [AdRoll-Konto](https://www.adroll.com/) und die entsprechenden Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2ac7a-107">Sie haben [Konfigurierte Segmente](segments.md) in Zielgruppen-Insights.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="2ac7a-108">Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="2ac7a-109">Mit AdRoll verbinden</span><span class="sxs-lookup"><span data-stu-id="2ac7a-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="2ac7a-110">Gehen Sie zu **Administrator** > **Exportziele**.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="2ac7a-111">Unter **AdRollo**, wählen Sie **Einrichten**.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="2ac7a-112">Geben Sie Ihrem Exportziel einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Konfigurationsbereich für die AdRoll-Verbindung.":::

1. <span data-ttu-id="2ac7a-114">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2ac7a-115">Wählen Sie **Verbinden**, um die Verbindung zu AdRoll zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="2ac7a-116">Wählen Sie **Mit AdRoll authentifizieren** und geben Sie Ihre AdRoll Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="2ac7a-117">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="2ac7a-118">Geben Sie Ihre **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="2ac7a-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="2ac7a-119">Wählen Sie **Weiter**, um die Konfiguration des Exports zu starten.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="2ac7a-120">Konfigurieren Sie den Konnektor</span><span class="sxs-lookup"><span data-stu-id="2ac7a-120">Configure the connector</span></span>

1. <span data-ttu-id="2ac7a-121">Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="2ac7a-122">Es ist erforderlich, Segmente nach AdRoll zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="2ac7a-123">Wählen Sie die Segemente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-123">Select the segments you want to export.</span></span> <span data-ttu-id="2ac7a-124">Wählen Sie ein Segment mit mindestens 100 Mitgliedern aus.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="2ac7a-125">Sie können keine kleineren Segmente exportieren.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-125">You can't export smaller segments.</span></span> <span data-ttu-id="2ac7a-126">Zusätzlich beträgt die maximale Größe eines zu exportierenden Segments 250.000 Mitglieder pro Export.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="2ac7a-127">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="2ac7a-128">Exportieren der Daten</span><span class="sxs-lookup"><span data-stu-id="2ac7a-128">Export the data</span></span>

<span data-ttu-id="2ac7a-129">Sie könenn [Daten nach Bedarf exportieren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="2ac7a-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="2ac7a-130">Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2ac7a-131">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="2ac7a-131">Known limitations</span></span>

- <span data-ttu-id="2ac7a-132">Sie können pro Export bis zu 250.000 Profile zu AdRoll exportieren.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="2ac7a-133">Sie können keine Segmente mit weniger als 100 Profilen nach AdRoll exportieren.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="2ac7a-134">Der Export zu AdRoll ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="2ac7a-135">Das Exportieren von bis zu 250.000 Profilen nach AdRoll kann bis zu 10 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="2ac7a-136">Die Anzahl der Profile, die Sie zu AdRoll exportieren können, hängt von Ihrem Vertrag mit AdRoll ab und ist dort begrenzt.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2ac7a-137">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="2ac7a-137">Data privacy and compliance</span></span>

<span data-ttu-id="2ac7a-138">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an AdRoll aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2ac7a-139">Microsoft wird diese Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, sicherzustellen, dass AdRoll alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2ac7a-140">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2ac7a-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="2ac7a-141">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="2ac7a-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
