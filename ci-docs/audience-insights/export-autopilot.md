---
title: Exportieren von Customer Insights-Daten zu Autopilot
description: Lernen Sie, wie Sie die Verbindung zu Autopilot konfigurieren.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596129"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="1bf6d-103">Konnektor für Autopilot (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="1bf6d-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="1bf6d-104">Exportieren Sie Segmente einheitlicher Kundenprofile in Autopilot und verwenden Sie sie für E-Mail-Marketing in Autopilot.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="1bf6d-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1bf6d-105">Prerequisites</span></span>

-   <span data-ttu-id="1bf6d-106">Sie haben ein [Autopilot-Konto](https://www.autopilothq.com/) und entsprechende Anmeldeinformationen für den Administrator.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1bf6d-107">Sie haben [Konfigurierte Segmente](segments.md) in Zielgruppen-Insights.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="1bf6d-108">Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="1bf6d-109">Mit AutoPilot verbinden</span><span class="sxs-lookup"><span data-stu-id="1bf6d-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="1bf6d-110">Gehen Sie zu **Administrator** > **Exportziele**.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1bf6d-111">Unter **Autopilot**, wählen Sie **Einrichten**.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="1bf6d-112">Geben Sie Ihrem Exportziel einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Konfigurationsbereich für die Autopilot-Verbindung.":::

1. <span data-ttu-id="1bf6d-114">Geben Sie Ihren **Autopilot-API-Schlüssel** [Autopilot-API-Schlüssel](https://autopilot.docs.apiary.io/#) ein.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="1bf6d-115">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1bf6d-116">Wählen Sie **Verbinden**, um die Verbindung zu Autopilot zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="1bf6d-117">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1bf6d-118">Wählen Sie **Weiter**, um die Konfiguration des Exports zu starten.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="1bf6d-119">Konfigurieren Sie den Konnektor</span><span class="sxs-lookup"><span data-stu-id="1bf6d-119">Configure the connector</span></span>

1. <span data-ttu-id="1bf6d-120">Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="1bf6d-121">Wiederholen Sie die gleichen Schritte für andere optionale Felder wie **Vorname**, **Nachname**.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="1bf6d-122">Wählen Sie die Segemente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-122">Select the segments you want to export.</span></span> <span data-ttu-id="1bf6d-123">Es wird dringend **empfohlen, nicht mehr als 100.000 Kundenprofile insgesamt** an Autopilot zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="1bf6d-124">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="1bf6d-125">Exportieren der Daten</span><span class="sxs-lookup"><span data-stu-id="1bf6d-125">Export the data</span></span>

<span data-ttu-id="1bf6d-126">Sie könenn [Daten nach Bedarf exportieren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="1bf6d-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="1bf6d-127">Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1bf6d-128">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1bf6d-128">Known limitations</span></span>

- <span data-ttu-id="1bf6d-129">Sie können insgesamt bis zu 100.000 Profile zu Autopilot exportieren.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="1bf6d-130">Der Export zu Autopilot ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="1bf6d-131">Das Exportieren von bis zu 100.000 Profilen an Autopilot kann bis zu einigen Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="1bf6d-132">Die Anzahl der Profile, die Sie zu Autopilot exportieren können, hängt von Ihrem Vertrag mit Autopilot ab und ist dort begrenzt.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1bf6d-133">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="1bf6d-133">Data privacy and compliance</span></span>

<span data-ttu-id="1bf6d-134">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Autopilot aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1bf6d-135">Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Autopilot alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="1bf6d-136">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1bf6d-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1bf6d-137">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="1bf6d-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]