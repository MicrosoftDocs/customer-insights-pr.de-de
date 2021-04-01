---
title: Customer Insights-Daten zu Google Ads exportieren
description: Lernen Sie, wie Sie die Verbindung zu Google Ads konfigurieren.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598246"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="94102-103">Konnektor für Google Ads (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="94102-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="94102-104">Exportieren Sie Segmente von vereinheitlichten Kundenprofilen in die Google Ads Zielgruppenliste und nutzen Sie diese für Werbung in der Google Suche, Gmail, YouTube und im Google Display-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="94102-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="94102-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="94102-105">Prerequisites</span></span>

-   <span data-ttu-id="94102-106">Sie haben ein [Google Ads-Konto](https://ads.google.com/) und die entsprechenden Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="94102-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="94102-107">Es gibt bestehende Zielgruppen in Google Ads und die dazugehörigen IDs.</span><span class="sxs-lookup"><span data-stu-id="94102-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="94102-108">Weitere Informationen finden Sie unter [Google Ads-Zielgruppen](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="94102-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="94102-109">Sie haben [Konfigurierte Segmente](segments.md)</span><span class="sxs-lookup"><span data-stu-id="94102-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="94102-110">Vereinheitlichte Kundenprofile in den exportierten Segmenten enthalten Felder, die eine E-Mail-Adresse, einen Vornamen und einen Nachnamen darstellen</span><span class="sxs-lookup"><span data-stu-id="94102-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="94102-111">Mit Google Ads verbinden</span><span class="sxs-lookup"><span data-stu-id="94102-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="94102-112">Gehen Sie zu **Administrator** > **Exportziele**.</span><span class="sxs-lookup"><span data-stu-id="94102-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="94102-113">Unter **Google Ads**, wählen Sie **Einrichten**.</span><span class="sxs-lookup"><span data-stu-id="94102-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="94102-114">Geben Sie Ihrem Exportziel einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="94102-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="94102-115">Geben Sie Ihre **[Google Ads Kunden-ID](https://support.google.com/google-ads/answer/1704344)** ein.</span><span class="sxs-lookup"><span data-stu-id="94102-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="94102-116">Geben Sie Ihr **[Google Ads genehmigtes Entwickler-Token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** ein.</span><span class="sxs-lookup"><span data-stu-id="94102-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="94102-117">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="94102-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="94102-118">Geben Sie Ihre **[Google Ads Zielgruppen-ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** ein und wählen Sie **Verbinden**, um die Verbindung zu Google Ads zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="94102-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="94102-119">Wählen Sie **Mit Google Ads authentifizieren** und geben Sie Ihre Google Ads Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="94102-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="94102-120">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="94102-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Bildschirmfoto exportieren für Google Ads-Verbindung":::

1. <span data-ttu-id="94102-122">Wählen Sie **Weiter**, um die Konfiguration des Exports zu starten.</span><span class="sxs-lookup"><span data-stu-id="94102-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="94102-123">Konfigurieren Sie den Konnektor</span><span class="sxs-lookup"><span data-stu-id="94102-123">Configure the connector</span></span>

1. <span data-ttu-id="94102-124">Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="94102-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="94102-125">Wiederholen Sie die gleichen Schritte für die Felder **Vorname** und **Nachname**.</span><span class="sxs-lookup"><span data-stu-id="94102-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="94102-126">Wählen Sie die Segemente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="94102-126">Select the segments you want to export.</span></span> <span data-ttu-id="94102-127">Sie können insgesamt bis zu 1 Million Kundenprofile zu Google Ads exportieren.</span><span class="sxs-lookup"><span data-stu-id="94102-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="94102-128">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="94102-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="94102-129">Exportieren der Daten</span><span class="sxs-lookup"><span data-stu-id="94102-129">Export the data</span></span>

<span data-ttu-id="94102-130">Sie könenn [Daten nach Bedarf exportieren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="94102-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="94102-131">Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="94102-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="94102-132">In Google Ads finden Sie Ihre Segmente jetzt unter [Google Ads Zielgruppen](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="94102-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="94102-133">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="94102-133">Known limitations</span></span>

- <span data-ttu-id="94102-134">Bis zu 1 Million Profile pro Export zu Google Ads.</span><span class="sxs-lookup"><span data-stu-id="94102-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="94102-135">Der Export zu Google Ads ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="94102-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="94102-136">Das Exportieren von Segmenten mit insgesamt 1 Million Profilen kann aufgrund von Beschränkungen auf der Anbieterseite bis zu 5 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="94102-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="94102-137">Der Abgleich in Google Ads kann bis zu 48 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="94102-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="94102-138">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="94102-138">Data privacy and compliance</span></span>

<span data-ttu-id="94102-139">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Google Ads aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="94102-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="94102-140">Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Google Ads alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können.</span><span class="sxs-lookup"><span data-stu-id="94102-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="94102-141">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="94102-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="94102-142">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="94102-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]