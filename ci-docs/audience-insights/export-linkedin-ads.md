---
title: Exportieren von Customer Insights-Daten nach LinkedIn Ads
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und einen Export nach LinkedIn Ads durchführen.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124491"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="1085f-103">Exportieren von Segmenten nach LinkedIn Ads (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="1085f-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="1085f-104">Exportieren Sie Segmente einheitlicher Kundenprofilen nach LinkedIn Ads, um passende Zielgruppen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1085f-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="1085f-105">Verwenden Sie die passenden Zielgruppen für das Unternehmens- und das Kontakt-Targeting.</span><span class="sxs-lookup"><span data-stu-id="1085f-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1085f-106">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1085f-106">Prerequisites</span></span>

-   <span data-ttu-id="1085f-107">Sie verfügen über ein [LinkedIn Campaign Manager-Konto](https://business.linkedin.com/marketing-solutions/ads) und entsprechende Administrator-Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="1085f-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1085f-108">Sie haben [Konfigurierte Segmente](segments.md) in Zielgruppen-Insights.</span><span class="sxs-lookup"><span data-stu-id="1085f-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="1085f-109">Kundenprofile in den exportierten Segmenten enthalten ein Feld mit einer E-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="1085f-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1085f-110">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1085f-110">Known limitations</span></span>

- <span data-ttu-id="1085f-111">Sie können bis zu 100.000 Profile pro Export nach LinkedIn Ads exportieren.</span><span class="sxs-lookup"><span data-stu-id="1085f-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="1085f-112">Der Export nach LinkedIn Ads ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="1085f-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="1085f-113">Das Exportieren von bis zu 100.000 Profilen nach LinkedIn Ads kann bis zu 10 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="1085f-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="1085f-114">Einrichten der Verbindung mit LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="1085f-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="1085f-115">Gehen Sie in Zielgruppenerkenntnissen zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="1085f-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1085f-116">Wählen Sie **Verbindung hinzufügen** und dann **LinkedIn Ads** aus, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1085f-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="1085f-117">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="1085f-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1085f-118">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="1085f-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1085f-119">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="1085f-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1085f-120">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="1085f-120">Choose who can use this connection.</span></span> <span data-ttu-id="1085f-121">Wenn Sie keine Aktion ausführen, sind als Standard Administratoren ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="1085f-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="1085f-122">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1085f-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1085f-123">Geben Sie Ihre [LinkedIn Campaign Manager-Konto-ID](https://www.linkedin.com/help/lms/answer/a424270) an.</span><span class="sxs-lookup"><span data-stu-id="1085f-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="1085f-124">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="1085f-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1085f-125">Wählen Sie **Verbinden** aus, um die Verbindung zu Campaign Monitor zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="1085f-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="1085f-126">Wählen Sie **Mit LinkedIn authentifizieren** aus und geben Sie Ihre Administrator-Anmeldeinformationen für LinkedIn Campaign Manager an.</span><span class="sxs-lookup"><span data-stu-id="1085f-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="1085f-127">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="1085f-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1085f-128">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="1085f-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1085f-129">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="1085f-129">Configure an export</span></span>

<span data-ttu-id="1085f-130">Sie können einen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="1085f-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="1085f-131">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1085f-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1085f-132">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="1085f-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1085f-133">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1085f-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1085f-134">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem LinkedIn Ads-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="1085f-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="1085f-135">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1085f-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1085f-136">Wählen Sie aus, ob Sie Daten für [Kontakt-Targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) oder [Unternehmens-Targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) auf LinkedIn exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1085f-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="1085f-137">Wählen Sie im Bereich **Datenabgleich** in Ihrem vereinheitlichten Kundenprofil das Feld aus, das die E-Mail-Adresse eines Kunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="1085f-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="1085f-138">Der Export nach LinkedIn Ads ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="1085f-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="1085f-139">Wählen Sie die Segemente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1085f-139">Select the segments you want to export.</span></span> <span data-ttu-id="1085f-140">Die passenden Zielgruppen in LinkedIn Campaign Manager werden automatisch mit dem Namen der Segmente erstellt, die Sie zum Exportieren ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="1085f-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="1085f-141">Jedes Segment führt zu einer separaten passenden Zielgruppe.</span><span class="sxs-lookup"><span data-stu-id="1085f-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="1085f-142">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="1085f-142">Select **Save**.</span></span>

<span data-ttu-id="1085f-143">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1085f-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1085f-144">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1085f-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1085f-145">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1085f-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1085f-146">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="1085f-146">Data privacy and compliance</span></span>

<span data-ttu-id="1085f-147">Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten an LinkedIn Ads zu übertragen, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="1085f-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1085f-148">Microsoft überträgt diese Daten auf Ihre Anweisung. Sie sind jedoch dafür verantwortlich, dass LinkedIn Ads alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="1085f-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="1085f-149">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1085f-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="1085f-150">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktion zu beenden.</span><span class="sxs-lookup"><span data-stu-id="1085f-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
