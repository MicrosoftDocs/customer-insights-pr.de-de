---
title: Exportieren von Customer Insights-Daten zu Mailchimp
description: Lernen Sie, wie Sie die Verbindung zu Mailchimp konfigurieren.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598200"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="43b2c-103">Konnektor für Mailchimp (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="43b2c-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="43b2c-104">Exportieren Sie Segmente von vereinheitlichten Kundenprofilen nach Mailchimp, um Newsletter und E-Mail-Kampagnen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="43b2c-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="43b2c-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="43b2c-105">Prerequisites</span></span>

-   <span data-ttu-id="43b2c-106">Sie haben ein [Mailchimp-Konto](https://mailchimp.com/) und die entsprechenden Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="43b2c-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="43b2c-107">Es gibt bestehende Zielgruppen in Mailchimp und die dazugehörigen IDs.</span><span class="sxs-lookup"><span data-stu-id="43b2c-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="43b2c-108">Weitere Informationen finden Sie unter [Mailchimp-Zielgruppen](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="43b2c-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="43b2c-109">Sie haben [Konfigurierte Segmente](segments.md)</span><span class="sxs-lookup"><span data-stu-id="43b2c-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="43b2c-110">Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.</span><span class="sxs-lookup"><span data-stu-id="43b2c-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="43b2c-111">Mit Mailchimp verbinden</span><span class="sxs-lookup"><span data-stu-id="43b2c-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="43b2c-112">Gehen Sie zu **Administrator** > **Exportziele**.</span><span class="sxs-lookup"><span data-stu-id="43b2c-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="43b2c-113">Unter **Mailchimp**, wählen Sie **Einrichten**.</span><span class="sxs-lookup"><span data-stu-id="43b2c-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="43b2c-114">Geben Sie Ihrem Exportziel einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="43b2c-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="43b2c-115">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="43b2c-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="43b2c-116">Geben Sie Ihre **[Mailchimp Zielgruppen-ID](https://mailchimp.com/help/find-audience-id/)** ein und wählen Sie **Verbinden**, um die Verbindung zu Mailchimp zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="43b2c-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="43b2c-117">Wählen Sie **Mit Mailchimp authentifizieren** und geben Sie Ihre Mailchimp Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="43b2c-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="43b2c-118">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="43b2c-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Export-Screenshot für Mailchimp-Verbindung":::

1. <span data-ttu-id="43b2c-120">Wählen Sie **Weiter**, um die Konfiguration des Exports zu starten.</span><span class="sxs-lookup"><span data-stu-id="43b2c-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="43b2c-121">Konfigurieren Sie den Konnektor</span><span class="sxs-lookup"><span data-stu-id="43b2c-121">Configure the connector</span></span>

1. <span data-ttu-id="43b2c-122">Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="43b2c-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="43b2c-123">Optional können Sie **Vorname** und **Nachname** als zusätzliche Felder exportieren, um mehr personalisierte E-Mails zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="43b2c-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="43b2c-124">Wählen Sie **Attribut hinzufügen**, um diese Felder zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="43b2c-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="43b2c-125">Wählen Sie die Segemente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="43b2c-125">Select the segments you want to export.</span></span> <span data-ttu-id="43b2c-126">Sie können insgesamt bis zu 1 Mio. Kundenprofile zu Mailchimp exportieren.</span><span class="sxs-lookup"><span data-stu-id="43b2c-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Wählen Sie Felder und Segmente für den Export nach Mailchimp":::

1. <span data-ttu-id="43b2c-128">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="43b2c-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="43b2c-129">Exportieren der Daten</span><span class="sxs-lookup"><span data-stu-id="43b2c-129">Export the data</span></span>

<span data-ttu-id="43b2c-130">Sie könenn [Daten nach Bedarf exportieren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="43b2c-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="43b2c-131">Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="43b2c-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="43b2c-132">In Mailchimp finden Sie Ihre Segmente jetzt unter [Mailchimp Zielgruppen](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="43b2c-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="43b2c-133">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="43b2c-133">Known limitations</span></span>

- <span data-ttu-id="43b2c-134">Bis zu 1 Million Profile pro Export zu Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="43b2c-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="43b2c-135">Der Export zu Mailchimp ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="43b2c-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="43b2c-136">Der Export von Segmenten mit insgesamt 1 Million Profilen kann aufgrund von Beschränkungen auf der Anbieterseite bis zu drei Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="43b2c-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="43b2c-137">Die Anzahl der Profile, die Sie zu Mailchimp exportieren können, hängt von Ihrem Vertrag mit Mailchimp ab und ist dort begrenzt.</span><span class="sxs-lookup"><span data-stu-id="43b2c-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="43b2c-138">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="43b2c-138">Data privacy and compliance</span></span>

<span data-ttu-id="43b2c-139">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Mailchimp aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="43b2c-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="43b2c-140">Microsoft wird diese Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Mailchimp alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können.</span><span class="sxs-lookup"><span data-stu-id="43b2c-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="43b2c-141">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="43b2c-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="43b2c-142">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="43b2c-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]