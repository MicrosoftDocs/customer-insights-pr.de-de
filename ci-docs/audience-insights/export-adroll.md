---
title: Customer Insights-Daten zu AdRoll exportieren
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu AdRoll exportieren.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67bfa23d56b26ae592efa4d7197713664bb02623
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304820"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="52ddf-103">Exportieren von Segmenten nach AdRoll (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="52ddf-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="52ddf-104">Exportieren Sie Segmente einheitlicher Kundenprofile nach AdRoll und verwenden Sie sie für Werbezwecke.</span><span class="sxs-lookup"><span data-stu-id="52ddf-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="52ddf-105">Voraussetzungen für die Verbindung</span><span class="sxs-lookup"><span data-stu-id="52ddf-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="52ddf-106">Sie haben ein [AdRoll-Konto](https://www.adroll.com/) und die entsprechenden Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="52ddf-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="52ddf-107">Sie haben [Konfigurierte Segmente](segments.md) in Zielgruppen-Insights.</span><span class="sxs-lookup"><span data-stu-id="52ddf-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="52ddf-108">Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.</span><span class="sxs-lookup"><span data-stu-id="52ddf-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="52ddf-109">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="52ddf-109">Known limitations</span></span>

- <span data-ttu-id="52ddf-110">Sie können bis zu 250,000 Profile gleichzeitig zu AdRoll exportieren.</span><span class="sxs-lookup"><span data-stu-id="52ddf-110">You can export up to 250,000 profiles at a time to AdRoll.</span></span>
- <span data-ttu-id="52ddf-111">Sie können keine Segmente mit weniger als 100 Profilen nach AdRoll exportieren.</span><span class="sxs-lookup"><span data-stu-id="52ddf-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="52ddf-112">Der Export zu AdRoll ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="52ddf-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="52ddf-113">Das Exportieren von bis zu 250.000 Profilen nach AdRoll kann bis zu 10 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="52ddf-113">Exporting up to 250,000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="52ddf-114">Die Anzahl der Profile, die Sie zu AdRoll exportieren können, hängt von Ihrem Vertrag mit AdRoll ab.</span><span class="sxs-lookup"><span data-stu-id="52ddf-114">The number of profiles that you can export to AdRoll is dependent on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="52ddf-115">Richten Sie die Verbindung mit AdRoll ein</span><span class="sxs-lookup"><span data-stu-id="52ddf-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="52ddf-116">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="52ddf-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="52ddf-117">Wählen Sie **Verbindung hinzufügen** und dann **AdRoll** aus, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="52ddf-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="52ddf-118">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="52ddf-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="52ddf-119">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="52ddf-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="52ddf-120">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="52ddf-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="52ddf-121">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="52ddf-121">Choose who can use this connection.</span></span> <span data-ttu-id="52ddf-122">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="52ddf-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="52ddf-123">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="52ddf-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="52ddf-124">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="52ddf-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="52ddf-125">Wählen Sie **Verbinden**, um die Verbindung zu AdRoll zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="52ddf-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="52ddf-126">Wählen Sie **Mit AdRoll authentifizieren** und geben Sie Ihre AdRoll Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="52ddf-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="52ddf-127">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="52ddf-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="52ddf-128">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="52ddf-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="52ddf-129">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="52ddf-129">Configure an export</span></span>

<span data-ttu-id="52ddf-130">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="52ddf-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="52ddf-131">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="52ddf-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="52ddf-132">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="52ddf-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="52ddf-133">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="52ddf-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="52ddf-134">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem AdRoll-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="52ddf-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="52ddf-135">Wenn dieser Abschnittsname nicht angezeigt wird, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="52ddf-135">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="52ddf-136">Geben Sie Ihre **AdRoll-Werbetreibenden-ID** ein.</span><span class="sxs-lookup"><span data-stu-id="52ddf-136">Enter your **AdRoll Advertiser ID**.</span></span> <span data-ttu-id="52ddf-137">Weitere Informationen zu [AdRoll Werbeprofilen](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="52ddf-137">For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="52ddf-138">Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="52ddf-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="52ddf-139">Es ist erforderlich, Segmente nach AdRoll zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="52ddf-139">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="52ddf-140">Wählen Sie die Segemente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="52ddf-140">Select the segments you want to export.</span></span> <span data-ttu-id="52ddf-141">Wählen Sie ein Segment mit mindestens 100 Mitgliedern aus.</span><span class="sxs-lookup"><span data-stu-id="52ddf-141">Select a segment with a least 100 members.</span></span> <span data-ttu-id="52ddf-142">Sie können keine kleineren Segmente exportieren.</span><span class="sxs-lookup"><span data-stu-id="52ddf-142">You can't export smaller segments.</span></span> <span data-ttu-id="52ddf-143">Zusätzlich beträgt die maximale Größe eines zu exportierenden Segments 250.000 Mitglieder pro Export.</span><span class="sxs-lookup"><span data-stu-id="52ddf-143">Additionally the maximum size of a segment to export is 250,000 members per export.</span></span> 

1. <span data-ttu-id="52ddf-144">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="52ddf-144">Select **Save**.</span></span>

<span data-ttu-id="52ddf-145">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="52ddf-145">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="52ddf-146">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="52ddf-146">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="52ddf-147">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="52ddf-147">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="52ddf-148">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="52ddf-148">Data privacy and compliance</span></span>

<span data-ttu-id="52ddf-149">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an AdRoll aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="52ddf-149">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="52ddf-150">Microsoft wird diese Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, sicherzustellen, dass AdRoll alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="52ddf-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="52ddf-151">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="52ddf-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="52ddf-152">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="52ddf-152">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
