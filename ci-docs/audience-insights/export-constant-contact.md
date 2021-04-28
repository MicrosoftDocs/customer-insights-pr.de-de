---
title: Exportieren Sie Customer Insights-Daten in Constant Contact
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zum Constant Contact exportieren.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760531"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a><span data-ttu-id="855be-103">Segmentlisten in Constant Contact exportieren (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="855be-103">Export segment lists to Constant Contact (preview)</span></span>

<span data-ttu-id="855be-104">Exportieren Sie Segmente einheitlicher Kundenprofile in Constant Contact und verwenden Sie sie für Marketingaktivitäten.</span><span class="sxs-lookup"><span data-stu-id="855be-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="855be-105">Voraussetzungen für die Verbindung</span><span class="sxs-lookup"><span data-stu-id="855be-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="855be-106">Sie haben ein [Constant Contact-Konto](https://www.constantcontact.com/account-home) und entsprechende Administrator-Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="855be-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="855be-107">Sie haben [Konfigurierte Segmente](segments.md) in Zielgruppen-Insights.</span><span class="sxs-lookup"><span data-stu-id="855be-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="855be-108">Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.</span><span class="sxs-lookup"><span data-stu-id="855be-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="855be-109">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="855be-109">Known limitations</span></span>

- <span data-ttu-id="855be-110">Sie können bis zu 1 Million Profile pro Export in Constant Contact exportieren.</span><span class="sxs-lookup"><span data-stu-id="855be-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="855be-111">Der Export nach Constant Contact ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="855be-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="855be-112">Das Exportieren von bis zu 1 Million Profilen nach Constant Contact kann bis zu 1 Stunde dauern.</span><span class="sxs-lookup"><span data-stu-id="855be-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="855be-113">Die Anzahl der Profile, die Sie in Constant Contact exportieren können, hängt von Ihrem Vertrag mit Constant Contact ab.</span><span class="sxs-lookup"><span data-stu-id="855be-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="855be-114">Verbindung mit Constant Contact einrichten</span><span class="sxs-lookup"><span data-stu-id="855be-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="855be-115">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="855be-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="855be-116">Wählen Sie **Verbindung hinzufügen** und dann **Constant Contact** aus, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="855be-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="855be-117">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="855be-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="855be-118">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="855be-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="855be-119">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="855be-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="855be-120">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="855be-120">Choose who can use this connection.</span></span> <span data-ttu-id="855be-121">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="855be-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="855be-122">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="855be-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="855be-123">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="855be-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="855be-124">Wählen Sie **Verbinden** aus, um die Verbindung zu Constant Contact zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="855be-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="855be-125">Wählen Sie **Mit AdRoll authentifizieren** aus, und geben Sie Ihre Administratoranmeldeinformationen für Constant Contact an.</span><span class="sxs-lookup"><span data-stu-id="855be-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="855be-126">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="855be-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="855be-127">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="855be-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="855be-128">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="855be-128">Configure an export</span></span>

<span data-ttu-id="855be-129">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="855be-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="855be-130">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="855be-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="855be-131">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="855be-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="855be-132">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="855be-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="855be-133">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Constant Contact-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="855be-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="855be-134">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="855be-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="855be-135">Geben Sie die [**ID der Constant Contact-Liste**](https://app.constantcontact.com/pages/contacts/ui#lists) ein.</span><span class="sxs-lookup"><span data-stu-id="855be-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="855be-136">Öffnen Sie eine Liste in Constant Contact, um die Listen-ID in der URL zu finden.</span><span class="sxs-lookup"><span data-stu-id="855be-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="855be-137">Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="855be-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="855be-138">Der Export nach Constant Contact ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="855be-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="855be-139">Optional können Sie Vorname und Nachname als zusätzliche Felder exportieren, um mehr personalisierte E-Mails zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="855be-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="855be-140">Wählen Sie **Attribut hinzufügen**, um diese Felder zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="855be-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="855be-141">Wählen Sie die Segemente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="855be-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="855be-142">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="855be-142">Select **Save**.</span></span>

<span data-ttu-id="855be-143">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="855be-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="855be-144">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="855be-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="855be-145">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="855be-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="855be-146">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="855be-146">Data privacy and compliance</span></span>

<span data-ttu-id="855be-147">Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten an Constant Contact zu übertragen, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="855be-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="855be-148">Microsoft überträgt diese Daten auf Ihre Anweisung. Sie sind jedoch dafür verantwortlich, dass Constant Contact alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="855be-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="855be-149">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="855be-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="855be-150">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="855be-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
