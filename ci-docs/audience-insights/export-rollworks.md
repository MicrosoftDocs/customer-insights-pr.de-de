---
title: Exportieren Sie Customer Insights-Daten in RollWorks
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu RollWorks exportieren.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760533"
---
# <a name="export-segment-lists-to-rollworks-preview"></a><span data-ttu-id="11697-103">Segmentlisten in RollWorks exportieren (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="11697-103">Export segment lists to RollWorks (preview)</span></span>

<span data-ttu-id="11697-104">Exportieren Sie Segmente einheitlicher Kundenprofile in RollWorks und verwenden Sie sie für Marketingaktivitäten.</span><span class="sxs-lookup"><span data-stu-id="11697-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="11697-105">Voraussetzungen für die Verbindung</span><span class="sxs-lookup"><span data-stu-id="11697-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="11697-106">Sie haben ein [RollWorks-Konto](https://www.rollworks.com/) und entsprechende Administrator-Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="11697-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="11697-107">Sie haben [Konfigurierte Segmente](segments.md) in Zielgruppen-Insights.</span><span class="sxs-lookup"><span data-stu-id="11697-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="11697-108">Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.</span><span class="sxs-lookup"><span data-stu-id="11697-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="11697-109">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="11697-109">Known limitations</span></span>

- <span data-ttu-id="11697-110">Sie können bis zu 250.000 Profile pro Export in RollWorks exportieren.</span><span class="sxs-lookup"><span data-stu-id="11697-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="11697-111">Sie können keine Segmente mit weniger als 100 Profilen nach RollWorks exportieren.</span><span class="sxs-lookup"><span data-stu-id="11697-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="11697-112">Der Export nach RollWorks ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="11697-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="11697-113">Das Exportieren von bis zu 250.000 Profilen nach RollWorks kann bis zu 10 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="11697-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="11697-114">Die Anzahl der Profile, die Sie in RollWorks exportieren können, hängt von Ihrem Vertrag mit RollWorks ab.</span><span class="sxs-lookup"><span data-stu-id="11697-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="11697-115">Verbindung mit RollWorks einrichten</span><span class="sxs-lookup"><span data-stu-id="11697-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="11697-116">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="11697-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="11697-117">Wählen Sie **Verbindung hinzufügen** und dann **RollWorks** aus, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="11697-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="11697-118">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="11697-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="11697-119">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="11697-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="11697-120">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="11697-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="11697-121">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="11697-121">Choose who can use this connection.</span></span> <span data-ttu-id="11697-122">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="11697-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="11697-123">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="11697-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="11697-124">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="11697-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="11697-125">Wählen Sie **Verbinden** aus, um die Verbindung zu RollWorks zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="11697-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="11697-126">Wählen Sie **Mit RollWorks authentifizieren** aus, und geben Sie Ihre Administratoranmeldeinformationen für RollWorks an.</span><span class="sxs-lookup"><span data-stu-id="11697-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="11697-127">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="11697-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="11697-128">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="11697-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="11697-129">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="11697-129">Configure an export</span></span>

<span data-ttu-id="11697-130">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="11697-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="11697-131">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="11697-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="11697-132">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="11697-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="11697-133">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="11697-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="11697-134">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem RollWorks-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="11697-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="11697-135">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="11697-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="11697-136">Geben Sie Ihre **RollWorks-Werbe-ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles) ein.</span><span class="sxs-lookup"><span data-stu-id="11697-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="11697-137">Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="11697-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="11697-138">Der Export nach RollWorks ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="11697-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="11697-139">Wählen Sie die Segemente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="11697-139">Select the segments you want to export.</span></span> <span data-ttu-id="11697-140">Wählen Sie ein Segment mit mindestens 100 Mitgliedern aus.</span><span class="sxs-lookup"><span data-stu-id="11697-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="11697-141">Sie können keine kleineren Segmente exportieren.</span><span class="sxs-lookup"><span data-stu-id="11697-141">You can't export smaller segments.</span></span> <span data-ttu-id="11697-142">Zusätzlich beträgt die maximale Größe eines zu exportierenden Segments 250.000 Mitglieder pro Export.</span><span class="sxs-lookup"><span data-stu-id="11697-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="11697-143">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="11697-143">Select **Save**.</span></span>

<span data-ttu-id="11697-144">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="11697-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="11697-145">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="11697-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="11697-146">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="11697-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="11697-147">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="11697-147">Data privacy and compliance</span></span>

<span data-ttu-id="11697-148">Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten an RollWorks zu übertragen, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="11697-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="11697-149">Microsoft überträgt diese Daten auf Ihre Anweisung. Sie sind jedoch dafür verantwortlich, dass RollWorks alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="11697-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="11697-150">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="11697-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="11697-151">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="11697-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
