---
title: Exportieren von Customer Insights-Daten nach Microsoft Advertising
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und nach Microsoft Advertising exportieren.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124489"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="5f24c-103">Exportieren von Segmenten nach Microsoft Advertising (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="5f24c-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="5f24c-104">Exportieren Sie Customer Insights-Segmente nach Microsoft Advertising, um Zielgruppen für Customer Match zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5f24c-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="5f24c-105">Verwenden Sie diese Zielgruppen für Ihre Werbekampagnen.</span><span class="sxs-lookup"><span data-stu-id="5f24c-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5f24c-106">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5f24c-106">Prerequisites</span></span>

-   <span data-ttu-id="5f24c-107">Ein [Microsoft Advertising-Konto](https://ads.microsoft.com/) und entsprechende Administrator-Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="5f24c-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5f24c-108">Sie haben die Nutzungsbedingungen für Customer Match akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="5f24c-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="5f24c-109">[Konfigurierte Segmente](segments.md) in Zielgruppenerkenntnissen.</span><span class="sxs-lookup"><span data-stu-id="5f24c-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="5f24c-110">Vereinheitlichte Kundenprofile in den exportierten Segmenten enthalten ein Feld mit einer E-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="5f24c-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5f24c-111">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="5f24c-111">Known limitations</span></span>

- <span data-ttu-id="5f24c-112">Sie können bis zu 500.000 Profile pro Export nach Microsoft Advertising exportieren.</span><span class="sxs-lookup"><span data-stu-id="5f24c-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="5f24c-113">Der Export nach Microsoft Advertising ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="5f24c-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="5f24c-114">Das Exportieren von bis zu 500.000 Profilen nach Microsoft Advertising kann bis zu 10 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="5f24c-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="5f24c-115">Einrichten der Verbindung mit Microsoft Advertising (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="5f24c-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="5f24c-116">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="5f24c-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5f24c-117">Wählen Sie **Verbindung hinzufügen** und dann **Microsoft Advertising** aus, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5f24c-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="5f24c-118">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="5f24c-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5f24c-119">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="5f24c-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5f24c-120">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="5f24c-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5f24c-121">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="5f24c-121">Choose who can use this connection.</span></span> <span data-ttu-id="5f24c-122">Als Standard sind Administratoren ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="5f24c-122">The default is administrators.</span></span> <span data-ttu-id="5f24c-123">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="5f24c-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="5f24c-124">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="5f24c-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5f24c-125">Wählen Sie **Verbinden** aus, um die Verbindung zu Microsoft Advertising zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="5f24c-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="5f24c-126">Wählen Sie **Mit Microsoft Advertising authentifizieren** aus, und geben Sie Ihre Administratoranmeldeinformationen für Microsoft Advertising an.</span><span class="sxs-lookup"><span data-stu-id="5f24c-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="5f24c-127">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="5f24c-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5f24c-128">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="5f24c-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="5f24c-129">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="5f24c-129">Configure an export</span></span>

<span data-ttu-id="5f24c-130">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="5f24c-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5f24c-131">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="5f24c-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5f24c-132">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="5f24c-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5f24c-133">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5f24c-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="5f24c-134">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Microsoft Advertising-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="5f24c-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="5f24c-135">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="5f24c-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="5f24c-136">Wählen Sie die zu exportierenden Segmente aus.</span><span class="sxs-lookup"><span data-stu-id="5f24c-136">Select the segments to export.</span></span> <span data-ttu-id="5f24c-137">Die Zielgruppen für Customer Match in Microsoft Advertising werden automatisch mit dem Namen der für den Export ausgewählten Segmente erstellt.</span><span class="sxs-lookup"><span data-stu-id="5f24c-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="5f24c-138">Jedes Segment führt zu einer separaten Zielgruppe für Customer Match.</span><span class="sxs-lookup"><span data-stu-id="5f24c-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="5f24c-139">Geben Sie Ihre **Kunden- und Konto-ID für Microsoft Advertising** ein.</span><span class="sxs-lookup"><span data-stu-id="5f24c-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="5f24c-140">Sie finden die Kunden-ID (`cid`) und die Konto-ID (`aid`) in den Parametern der URL, wenn Sie bei Microsoft Advertising angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="5f24c-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="5f24c-141">Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** in Ihrem vereinheitlichten Kundenprofil das Feld mit einer E-Mail-Adresse eines Kunden aus.</span><span class="sxs-lookup"><span data-stu-id="5f24c-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="5f24c-142">Der Export nach Microsoft Advertising ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="5f24c-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="5f24c-143">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="5f24c-143">Select **Save**.</span></span>

<span data-ttu-id="5f24c-144">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5f24c-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="5f24c-145">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5f24c-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5f24c-146">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="5f24c-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5f24c-147">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="5f24c-147">Data privacy and compliance</span></span>

<span data-ttu-id="5f24c-148">Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten an Microsoft Advertising zu übertragen, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="5f24c-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5f24c-149">Microsoft überträgt diese Daten auf Ihre Anweisung. Sie sind jedoch dafür verantwortlich, dass Microsoft Advertising alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="5f24c-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5f24c-150">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5f24c-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="5f24c-151">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktion zu beenden.</span><span class="sxs-lookup"><span data-stu-id="5f24c-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
