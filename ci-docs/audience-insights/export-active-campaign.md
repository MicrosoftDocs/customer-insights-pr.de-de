---
title: Exportieren Sie Customer Insights-Daten nach ActiveCampaign
description: Erfahren Sie, wie Sie die Verbindung und den Export zu ActiveCampaign konfigurieren.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314614"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="b5741-103">Segmente nach ActiveCampaign exportieren (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="b5741-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="b5741-104">Exportieren Sie Segmente von einheitlichen Kundenprofilen nach ActiveCampaign und verwenden Sie sie für Marketingaktivitäten.</span><span class="sxs-lookup"><span data-stu-id="b5741-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b5741-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b5741-105">Prerequisites</span></span>

-   <span data-ttu-id="b5741-106">Sie haben ein [ActiveCampaign-Konto](https://www.activecampaign.com/) und entsprechende Administrator-Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="b5741-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b5741-107">Sie haben [Konfigurierte Segmente](segments.md) in Zielgruppen-Insights.</span><span class="sxs-lookup"><span data-stu-id="b5741-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="b5741-108">Vereinheitlichte Kundenprofile in den exportierten Segmenten enthalten ein Feld mit einer E-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="b5741-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b5741-109">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b5741-109">Known limitations</span></span>

- <span data-ttu-id="b5741-110">Sie können bis zu 1 Million Profile pro Export zu ActiveCampaign exportieren und die Fertigstellung kann bis zu 90 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="b5741-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="b5741-111">Der Export nach ActiveCampaign ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="b5741-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="b5741-112">Die Anzahl der Profile, die Sie zu ActiveCampaign exportieren können, hängt von Ihrem Vertrag mit ActiveCampaign ab.</span><span class="sxs-lookup"><span data-stu-id="b5741-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="b5741-113">Richten Sie die Verbindung mit ActiveCampaign ein.</span><span class="sxs-lookup"><span data-stu-id="b5741-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="b5741-114">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="b5741-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b5741-115">Wählen Sie **Verbindung hinzufügen** und wählen Sie **ActiveCampaign**, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b5741-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="b5741-116">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="b5741-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b5741-117">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="b5741-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b5741-118">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="b5741-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b5741-119">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="b5741-119">Choose who can use this connection.</span></span> <span data-ttu-id="b5741-120">Standardmäßig sind es nur Administratoren.</span><span class="sxs-lookup"><span data-stu-id="b5741-120">By default, it's only administrators.</span></span> <span data-ttu-id="b5741-121">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b5741-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b5741-122">Geben Sie Ihren [ActiveCampaign API-Schlüssel und REST Endpunkt Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) ein.</span><span class="sxs-lookup"><span data-stu-id="b5741-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="b5741-123">Der REST Endpunkt Hostname ist nur der Hostname ohne https://.</span><span class="sxs-lookup"><span data-stu-id="b5741-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="b5741-124">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="b5741-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b5741-125">Wählen Sie **Verbinden**, um die Verbindungsauswahl zu ActiveCampaign zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="b5741-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="b5741-126">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="b5741-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b5741-127">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="b5741-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b5741-128">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="b5741-128">Configure an export</span></span>

<span data-ttu-id="b5741-129">Sie können einen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="b5741-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="b5741-130">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b5741-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b5741-131">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="b5741-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b5741-132">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b5741-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b5741-133">In dem Feld **Anschluss für Export** wählen Sie im Bereich ActiveCampaign eine Verbindung aus.</span><span class="sxs-lookup"><span data-stu-id="b5741-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="b5741-134">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="b5741-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b5741-135">Geben Sie Ihre [**ActiveCampaign Listen-ID ein**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="b5741-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="b5741-136">Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="b5741-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b5741-137">Es ist erforderlcih, Segmente nach ActiveCampaign zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="b5741-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="b5741-138">Optional können Sie Vorname, Nachname, und Telefon exportieren, um personalisiertere E-Mails zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b5741-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="b5741-139">Wählen Sie Attribut hinzufügen, um diese Felder zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="b5741-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="b5741-140">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="b5741-140">Select **Save**.</span></span>

<span data-ttu-id="b5741-141">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b5741-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b5741-142">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b5741-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b5741-143">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b5741-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b5741-144">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="b5741-144">Data privacy and compliance</span></span>

<span data-ttu-id="b5741-145">Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten an ActiveCampaign zu übermitteln , erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogene Daten.</span><span class="sxs-lookup"><span data-stu-id="b5741-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b5741-146">Microsoft überträgt solche Daten auf Ihre Anweisung, aber Sie sind dafür verantwortlich, dass ActiveCampaign alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="b5741-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b5741-147">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b5741-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="b5741-148">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="b5741-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
