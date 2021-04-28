---
title: Exportieren Sie Customer Insights-Daten in Snapchat
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu Snapchat exportieren.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760530"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="24433-103">Segmentlisten in Snapchat exportieren (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="24433-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="24433-104">Exportieren Sie Segmente einheitlicher Kundenprofile in Snapchat und verwenden Sie sie für Marketingaktivitäten.</span><span class="sxs-lookup"><span data-stu-id="24433-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="24433-105">Voraussetzungen für die Verbindung</span><span class="sxs-lookup"><span data-stu-id="24433-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="24433-106">Sie haben ein [Snapchat Business-Konto](https://business.snapchat.com/), ein [Snapchat Ads-Konto](https://ads.snapchat.com/) und entsprechende Administrator-Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="24433-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="24433-107">Sie haben [Konfigurierte Segmente](segments.md) in Zielgruppen-Insights.</span><span class="sxs-lookup"><span data-stu-id="24433-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="24433-108">Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.</span><span class="sxs-lookup"><span data-stu-id="24433-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="24433-109">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="24433-109">Known limitations</span></span>

- <span data-ttu-id="24433-110">Der Export nach Snapchat ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="24433-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="24433-111">Das Exportieren von bis zu 1 Million Profilen nach Snapchat kann bis zu 15 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="24433-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="24433-112">Verbindung mit Snapchat einrichten</span><span class="sxs-lookup"><span data-stu-id="24433-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="24433-113">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="24433-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="24433-114">Wählen Sie **Verbindung hinzufügen** und dann **Snapchat** aus, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="24433-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="24433-115">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="24433-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="24433-116">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="24433-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="24433-117">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="24433-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="24433-118">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="24433-118">Choose who can use this connection.</span></span> <span data-ttu-id="24433-119">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="24433-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="24433-120">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="24433-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="24433-121">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="24433-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="24433-122">Wählen Sie **Verbinden** aus, um die Verbindung zu Snapchat zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="24433-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="24433-123">Wählen Sie **Mit Snapchat authentifizieren** aus, und geben Sie Ihre Administratoranmeldeinformationen für Snapchat an.</span><span class="sxs-lookup"><span data-stu-id="24433-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="24433-124">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="24433-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="24433-125">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="24433-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="24433-126">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="24433-126">Configure an export</span></span>

<span data-ttu-id="24433-127">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="24433-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="24433-128">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="24433-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="24433-129">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="24433-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="24433-130">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="24433-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="24433-131">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Snapchat-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="24433-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="24433-132">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="24433-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="24433-133">Geben Sie die [**Snapchat-Zielgruppen-ID**](https://businesshelp.snapchat.com/s/article/custom-audiences) ein.</span><span class="sxs-lookup"><span data-stu-id="24433-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="24433-134">Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="24433-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="24433-135">Der Export nach Snapchat ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="24433-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="24433-136">Wählen Sie die Segemente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="24433-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="24433-137">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="24433-137">Select **Save**.</span></span>

<span data-ttu-id="24433-138">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="24433-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="24433-139">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="24433-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="24433-140">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="24433-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="24433-141">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="24433-141">Data privacy and compliance</span></span>

<span data-ttu-id="24433-142">Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten an Snapchat zu übertragen, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="24433-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="24433-143">Microsoft überträgt diese Daten auf Ihre Anweisung. Sie sind jedoch dafür verantwortlich, dass Snapchat alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="24433-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="24433-144">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="24433-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="24433-145">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="24433-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
