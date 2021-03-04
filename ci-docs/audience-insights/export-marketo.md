---
title: Customer Insights Daten nach Marketo exportieren
description: Lernen Sie, wie Sie die Verbindung zu Marketo konfigurieren.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267080"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="f4e52-103">Konnektor für Marketo (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="f4e52-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="f4e52-104">Exportieren Sie Segmente von vereinheitlichten Kundenprofilen, um Kampagnen zu erstellen, E-Mail-Marketing zu betreiben und bestimmte Kundengruppen mit Marketo zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="f4e52-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f4e52-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f4e52-105">Prerequisites</span></span>

-   <span data-ttu-id="f4e52-106">Sie haben ein [Marketo-Konto](https://login.marketo.com/) und die entsprechenden Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="f4e52-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f4e52-107">Es gibt bestehende Listen in Marketo und die entsprechenden IDs.</span><span class="sxs-lookup"><span data-stu-id="f4e52-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="f4e52-108">Weitere Informationen finden Sie unter [Marketo-Listen](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="f4e52-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="f4e52-109">Sie haben [Konfigurierte Segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="f4e52-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="f4e52-110">Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.</span><span class="sxs-lookup"><span data-stu-id="f4e52-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="f4e52-111">Verbinden mit Marketo</span><span class="sxs-lookup"><span data-stu-id="f4e52-111">Connect to Marketo</span></span>

1. <span data-ttu-id="f4e52-112">Gehen Sie zu **Administrator** > **Exportziele**.</span><span class="sxs-lookup"><span data-stu-id="f4e52-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f4e52-113">Unter **Marketo**, wählen Sie **Einrichten**.</span><span class="sxs-lookup"><span data-stu-id="f4e52-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="f4e52-114">Geben Sie Ihrem Exportziel einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="f4e52-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f4e52-115">Geben Sie Ihre **[Marketo Client ID, Client secret und REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)** ein.</span><span class="sxs-lookup"><span data-stu-id="f4e52-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="f4e52-116">Geben Sie Ihre **[Marketo-Listen-ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** ein.</span><span class="sxs-lookup"><span data-stu-id="f4e52-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="f4e52-117">Wählen Sie **Ich stimme zu**, um die **Datenschutz und Compliance** zu bestätigen und wählen Sie **Verbinden**, um die Verbindung zu Marketo zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="f4e52-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="f4e52-118">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="f4e52-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Bildschirmfoto für Marketo-Verbindung exportieren":::

1. <span data-ttu-id="f4e52-120">Wählen Sie **Weiter**, um die Konfiguration des Exports zu starten.</span><span class="sxs-lookup"><span data-stu-id="f4e52-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="f4e52-121">Konfigurieren Sie den Konnektor</span><span class="sxs-lookup"><span data-stu-id="f4e52-121">Configure the connector</span></span>

1. <span data-ttu-id="f4e52-122">Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="f4e52-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="f4e52-123">Optional können Sie **Vorname**, **Nachname**, **Stadt**, **Bundesland** und **Land/Region** als zusätzliche Felder exportieren, um stärker personalisierte E-Mails zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f4e52-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="f4e52-124">Wählen Sie **Attribut hinzufügen**, um diese Felder zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="f4e52-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="f4e52-125">Wählen Sie die Segemente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="f4e52-125">Select the segments you want to export.</span></span> <span data-ttu-id="f4e52-126">Sie können insgesamt bis zu 1 Mio. Kundenprofile zu Marketo exportieren.</span><span class="sxs-lookup"><span data-stu-id="f4e52-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Wählen Sie Felder und Segmente für den Export nach Marketo":::

1. <span data-ttu-id="f4e52-128">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="f4e52-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f4e52-129">Exportieren der Daten</span><span class="sxs-lookup"><span data-stu-id="f4e52-129">Export the data</span></span>

<span data-ttu-id="f4e52-130">Sie könenn [Daten nach Bedarf exportieren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f4e52-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="f4e52-131">Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="f4e52-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f4e52-132">In Marketo finden Sie Ihre Segmente jetzt unter [Marketo-Listen](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="f4e52-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f4e52-133">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f4e52-133">Known limitations</span></span>

- <span data-ttu-id="f4e52-134">Bis zu 1 Million Profile pro Export zu Marketo.</span><span class="sxs-lookup"><span data-stu-id="f4e52-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="f4e52-135">Der Export zu Marketo ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="f4e52-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="f4e52-136">Das Exportieren von Segmenten mit insgesamt 1 Million Profilen kann bis zu 3 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="f4e52-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="f4e52-137">Die Anzahl der Profile, die Sie zu Marketo exportieren können, hängt von Ihrem Vertrag mit Marketo ab und ist dort begrenzt.</span><span class="sxs-lookup"><span data-stu-id="f4e52-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f4e52-138">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="f4e52-138">Data privacy and compliance</span></span>

<span data-ttu-id="f4e52-139">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Marketo aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="f4e52-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f4e52-140">Microsoft wird diese Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Marketo alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können.</span><span class="sxs-lookup"><span data-stu-id="f4e52-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f4e52-141">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f4e52-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f4e52-142">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="f4e52-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]