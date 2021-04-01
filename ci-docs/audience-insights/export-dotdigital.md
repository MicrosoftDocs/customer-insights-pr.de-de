---
title: Customer Insights-Daten nach DotDigital exportieren
description: Lernen Sie, wie Sie die Verbindung zu DotDigital konfigurieren.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598016"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="654fb-103">Konnektor für DotDigital (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="654fb-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="654fb-104">Exportieren Sie Segmente von vereinheitlichten Kundenprofilen in DotDigital-Adressbücher und verwenden Sie diese für Kampagnen, E-Mail-Marketing und zum Aufbau von Kundensegmenten mit DotDigital.</span><span class="sxs-lookup"><span data-stu-id="654fb-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="654fb-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="654fb-105">Prerequisites</span></span>

-   <span data-ttu-id="654fb-106">Sie haben ein [DotDigital-Konto](https://dotdigital.com/) und entsprechende Anmeldeinformationen für den Administrator.</span><span class="sxs-lookup"><span data-stu-id="654fb-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="654fb-107">Es gibt bestehende Adressbücher in DotDigital und die entsprechenden IDs.</span><span class="sxs-lookup"><span data-stu-id="654fb-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="654fb-108">Die ID ist in der URL zu finden, wenn Sie ein Adressbuch auswählen und öffnen.</span><span class="sxs-lookup"><span data-stu-id="654fb-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="654fb-109">Weitere Informationen finden Sie unter [DotDigital Adressbücher](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="654fb-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="654fb-110">Sie haben [Konfigurierte Segmente](segments.md) in Zielgruppen-Insights.</span><span class="sxs-lookup"><span data-stu-id="654fb-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="654fb-111">Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.</span><span class="sxs-lookup"><span data-stu-id="654fb-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="654fb-112">Verbinden mit DotDigital</span><span class="sxs-lookup"><span data-stu-id="654fb-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="654fb-113">Gehen Sie zu **Administrator** > **Exportziele**.</span><span class="sxs-lookup"><span data-stu-id="654fb-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="654fb-114">Wählen Sie unter **DotDigital** **Einrichten**.</span><span class="sxs-lookup"><span data-stu-id="654fb-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="654fb-115">Geben Sie Ihrem Exportziel einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="654fb-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Konfigurationsbereich für DotDigital-Export.":::

1. <span data-ttu-id="654fb-117">Geben Sie Ihren **DotDigital-Benutzernamen und Ihr Kennwort** ein.</span><span class="sxs-lookup"><span data-stu-id="654fb-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="654fb-118">Geben Sie Ihre **[DotDigital-Adressbuch-ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** ein.</span><span class="sxs-lookup"><span data-stu-id="654fb-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="654fb-119">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="654fb-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="654fb-120">Wählen Sie **Verbinden**, um die Verbindung zu DotDigital zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="654fb-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="654fb-121">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="654fb-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="654fb-122">Wählen Sie **Weiter**, um die Konfiguration des Exports zu starten.</span><span class="sxs-lookup"><span data-stu-id="654fb-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="654fb-123">Konfigurieren Sie den Konnektor</span><span class="sxs-lookup"><span data-stu-id="654fb-123">Configure the connector</span></span>

1. <span data-ttu-id="654fb-124">Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="654fb-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="654fb-125">Wiederholen Sie die gleichen Schritte für andere optionale Felder wie **Vorname**, **Nachname**, **Voller Name**, **Geschlecht** und **Postleitzahl**.</span><span class="sxs-lookup"><span data-stu-id="654fb-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="654fb-126">Wählen Sie die Segemente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="654fb-126">Select the segments you want to export.</span></span> <span data-ttu-id="654fb-127">Sie können insgesamt bis zu 1 Million Kundenprofile zu DotDigital exportieren.</span><span class="sxs-lookup"><span data-stu-id="654fb-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="654fb-128">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="654fb-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="654fb-129">Exportieren der Daten</span><span class="sxs-lookup"><span data-stu-id="654fb-129">Export the data</span></span>

<span data-ttu-id="654fb-130">Sie könenn [Daten nach Bedarf exportieren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="654fb-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="654fb-131">Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="654fb-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="654fb-132">In DotDigital können Sie jetzt Ihre Segmente in [DotDigital Adressbüchern](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) finden.</span><span class="sxs-lookup"><span data-stu-id="654fb-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="654fb-133">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="654fb-133">Known limitations</span></span>

- <span data-ttu-id="654fb-134">Bis zu 1 Million Profile pro Export zu DotDigital.</span><span class="sxs-lookup"><span data-stu-id="654fb-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="654fb-135">Das Exportieren zu DotDigital ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="654fb-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="654fb-136">Das Exportieren von Segmenten mit insgesamt 1 Million Profilen kann aufgrund von Beschränkungen auf der Provider-Seite bis zu 3 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="654fb-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="654fb-137">Die Anzahl der Profile, die Sie zu DotDigital exportieren können, ist abhängig und begrenzt von Ihrem Vertrag mit DotDigital.</span><span class="sxs-lookup"><span data-stu-id="654fb-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="654fb-138">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="654fb-138">Data privacy and compliance</span></span>

<span data-ttu-id="654fb-139">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an DotDigital aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="654fb-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="654fb-140">Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass DotDigital alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="654fb-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="654fb-141">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="654fb-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="654fb-142">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="654fb-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]