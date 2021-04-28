---
title: Exportieren Sie Customer Insights-Daten in Campaign Monitor
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zum Campaign Monitor exportieren.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7fd6af37b40e21d030a1ace0cd5f8fcc7861c3fa
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760532"
---
# <a name="export-segment-lists-to-campaign-monitor-preview"></a><span data-ttu-id="1c339-103">Segmentlisten in Campaign Monitor exportieren (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="1c339-103">Export segment lists to Campaign Monitor (preview)</span></span>

<span data-ttu-id="1c339-104">Exportieren Sie Segmente einheitlicher Kundenprofile in Campaign Monitor und verwenden Sie sie für Marketingaktivitäten.</span><span class="sxs-lookup"><span data-stu-id="1c339-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1c339-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1c339-105">Prerequisites</span></span>

-   <span data-ttu-id="1c339-106">Sie haben ein [Campaign Monitor-Konto](https://www.campaignmonitor.com/) und entsprechende Administrator-Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="1c339-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1c339-107">Sie haben [Konfigurierte Segmente](segments.md) in Zielgruppen-Insights.</span><span class="sxs-lookup"><span data-stu-id="1c339-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="1c339-108">Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.</span><span class="sxs-lookup"><span data-stu-id="1c339-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1c339-109">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1c339-109">Known limitations</span></span>

- <span data-ttu-id="1c339-110">Sie können bis zu 1 Million Profile pro Export in Campaign Monitor exportieren.</span><span class="sxs-lookup"><span data-stu-id="1c339-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="1c339-111">Der Export nach Campaign Monitor ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="1c339-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="1c339-112">Das Exportieren von bis zu 1 Million Profilen nach Campaign Monitor kann bis zu 20 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="1c339-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="1c339-113">Die Anzahl der Profile, die Sie in Campaign Monitor exportieren können, hängt von Ihrem Vertrag mit Campaign Monitor ab.</span><span class="sxs-lookup"><span data-stu-id="1c339-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="1c339-114">Verbindung mit Campaign Monitor einrichten</span><span class="sxs-lookup"><span data-stu-id="1c339-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="1c339-115">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="1c339-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1c339-116">Wählen Sie **Verbindung hinzufügen** und dann **Campaign Monitor** aus, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1c339-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="1c339-117">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="1c339-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1c339-118">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="1c339-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1c339-119">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="1c339-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1c339-120">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="1c339-120">Choose who can use this connection.</span></span> <span data-ttu-id="1c339-121">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="1c339-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1c339-122">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1c339-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1c339-123">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="1c339-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1c339-124">Wählen Sie **Verbinden** aus, um die Verbindung zu Campaign Monitor zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="1c339-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="1c339-125">Wählen Sie **Mit Campaign Monitor authentifizieren** aus, und geben Sie Ihre Administratoranmeldeinformationen für Campaign Monitor an.</span><span class="sxs-lookup"><span data-stu-id="1c339-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="1c339-126">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="1c339-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1c339-127">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="1c339-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1c339-128">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="1c339-128">Configure an export</span></span>

<span data-ttu-id="1c339-129">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="1c339-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1c339-130">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1c339-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1c339-131">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="1c339-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1c339-132">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1c339-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1c339-133">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Campaign Monitor-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="1c339-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="1c339-134">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1c339-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1c339-135">Geben Sie Ihre [**Campaign Monitor-Listen-ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id) ein.</span><span class="sxs-lookup"><span data-stu-id="1c339-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="1c339-136">[Generieren Sie den API-Schlüssel](https://www.campaignmonitor.com/api/getting-started/) über die **Kontoeinstellungen** in Campaign Monitor zuerst, um die API-Listen-ID anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1c339-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="1c339-137">Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="1c339-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="1c339-138">Der Export nach Campaign Monitor ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="1c339-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="1c339-139">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="1c339-139">Select **Save**.</span></span>

<span data-ttu-id="1c339-140">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1c339-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1c339-141">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1c339-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1c339-142">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1c339-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1c339-143">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="1c339-143">Data privacy and compliance</span></span>

<span data-ttu-id="1c339-144">Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten an Campaign Monitor zu übertragen, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="1c339-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1c339-145">Microsoft überträgt diese Daten auf Ihre Anweisung. Sie sind jedoch dafür verantwortlich, dass Campaign Monitor alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="1c339-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1c339-146">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1c339-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="1c339-147">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="1c339-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
