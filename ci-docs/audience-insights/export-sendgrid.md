---
title: Exportieren von Customer Insights-Daten zu SendGrid
description: Lernen Sie, wie Sie die Verbindung zu SendGrid konfigurieren.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597280"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="6c613-103">Konnektor für SendGrid (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="6c613-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="6c613-104">Exportieren Sie Segmente einheitlicher Kundenprofile in SendGrid-Kontaktlisten und verwenden Sie sie für Kampagnen und E-Mail-Marketing in SendGrid.</span><span class="sxs-lookup"><span data-stu-id="6c613-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="6c613-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6c613-105">Prerequisites</span></span>

-   <span data-ttu-id="6c613-106">Sie haben ein [SendGrid-Konto](https://sendgrid.com/) und die entsprechenden Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="6c613-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6c613-107">Es gibt bestehende Kontaktlisten in SendGrid und die entsprechenden IDs.</span><span class="sxs-lookup"><span data-stu-id="6c613-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="6c613-108">Weitere Informationen finden Sie unter [SendGrid – Kontakte verwalten](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="6c613-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="6c613-109">Sie haben [Konfigurierte Segmente](segments.md) in Zielgruppen-Insights.</span><span class="sxs-lookup"><span data-stu-id="6c613-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="6c613-110">Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.</span><span class="sxs-lookup"><span data-stu-id="6c613-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="6c613-111">Herstellen einer Verbindung mit SendGrid</span><span class="sxs-lookup"><span data-stu-id="6c613-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="6c613-112">Gehen Sie zu **Administrator** > **Exportziele**.</span><span class="sxs-lookup"><span data-stu-id="6c613-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6c613-113">Unter **SendGrid** wählen Sie **Einrichten**.</span><span class="sxs-lookup"><span data-stu-id="6c613-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="6c613-114">Geben Sie Ihrem Exportziel einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="6c613-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGrid-Exportkonfigurationsbereich.":::

1. <span data-ttu-id="6c613-116">Geben Sie Ihren **SendGrid-API-Schlüssel** [SendGrid-API-Schlüssel](https://sendgrid.com/docs/ui/account-and-settings/api-keys/) ein.</span><span class="sxs-lookup"><span data-stu-id="6c613-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="6c613-117">Geben Sie Ihre **[SendGrid-Listen-ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** ein.</span><span class="sxs-lookup"><span data-stu-id="6c613-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="6c613-118">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="6c613-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6c613-119">Wählen Sie **Verbinden**, um die Verbindung zu SendGrid zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="6c613-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="6c613-120">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="6c613-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="6c613-121">Wählen Sie **Weiter**, um die Konfiguration des Exports zu starten.</span><span class="sxs-lookup"><span data-stu-id="6c613-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="6c613-122">Konfigurieren Sie den Konnektor</span><span class="sxs-lookup"><span data-stu-id="6c613-122">Configure the connector</span></span>

1. <span data-ttu-id="6c613-123">Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="6c613-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="6c613-124">Wiederholen Sie die gleichen Schritte für andere optionale Felder wie **Vorname**, **Nachname**, **Land/Region**, **Bundesland/Kanton**, **Stadt** und **Postleitzahl**.</span><span class="sxs-lookup"><span data-stu-id="6c613-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="6c613-125">Wählen Sie die Segemente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6c613-125">Select the segments you want to export.</span></span> <span data-ttu-id="6c613-126">Es wird dringend **empfohlen, nicht mehr als 100.000 Kundenprofile insgesamt** an SendGrid zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="6c613-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="6c613-127">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="6c613-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="6c613-128">Exportieren der Daten</span><span class="sxs-lookup"><span data-stu-id="6c613-128">Export the data</span></span>

<span data-ttu-id="6c613-129">Sie könenn [Daten nach Bedarf exportieren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="6c613-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="6c613-130">Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="6c613-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6c613-131">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="6c613-131">Known limitations</span></span>

- <span data-ttu-id="6c613-132">Insgesamt bis zu 100.000 Profile an SendGrid.</span><span class="sxs-lookup"><span data-stu-id="6c613-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="6c613-133">Der Export zu SendGrid ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="6c613-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="6c613-134">Das Exportieren von bis zu 100.000 Profilen an SendGrid kann bis zu einigen Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="6c613-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="6c613-135">Die Anzahl der Profile, die Sie zu SendGrid exportieren können, hängt von Ihrem Vertrag mit SendGrid ab und ist dort begrenzt.</span><span class="sxs-lookup"><span data-stu-id="6c613-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6c613-136">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="6c613-136">Data privacy and compliance</span></span>

<span data-ttu-id="6c613-137">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an SendGrid aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="6c613-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6c613-138">Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass SendGrid alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="6c613-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="6c613-139">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6c613-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6c613-140">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="6c613-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]