---
title: Exportieren von Customer Insights-Daten nach Omnisend
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und nach Omnisend exportieren.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124490"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="77a28-103">Exportieren von Segmenten nach Omnisend (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="77a28-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="77a28-104">Exportieren Sie Segmente einheitlicher Kundenprofile nach Omnisend und verwenden Sie sie für Marketingaktivitäten.</span><span class="sxs-lookup"><span data-stu-id="77a28-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="77a28-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="77a28-105">Prerequisites</span></span>

-   <span data-ttu-id="77a28-106">Sie haben ein [Omnisend-Konto](https://www.omnisend.com/) und entsprechende Administrator-Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="77a28-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="77a28-107">Sie haben [Konfigurierte Segmente](segments.md) in Zielgruppen-Insights.</span><span class="sxs-lookup"><span data-stu-id="77a28-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="77a28-108">Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.</span><span class="sxs-lookup"><span data-stu-id="77a28-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="77a28-109">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="77a28-109">Known limitations</span></span>

- <span data-ttu-id="77a28-110">Sie können bis zu 1 Million Profile pro Export nach Omnisend exportieren. Dieser Vorgang kann bis zu 4 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="77a28-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="77a28-111">Der Export nach Omnisend ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="77a28-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="77a28-112">Die Anzahl der Profile, die Sie nach Omnisend exportieren können, hängt von Ihrem Vertrag mit Omnisend ab.</span><span class="sxs-lookup"><span data-stu-id="77a28-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="77a28-113">Einrichten einer Verbindung mit Omnisend</span><span class="sxs-lookup"><span data-stu-id="77a28-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="77a28-114">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="77a28-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="77a28-115">Wählen Sie **Verbindung hinzufügen** und dann **Omnisend** aus, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="77a28-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="77a28-116">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="77a28-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="77a28-117">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="77a28-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="77a28-118">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="77a28-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="77a28-119">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="77a28-119">Choose who can use this connection.</span></span> <span data-ttu-id="77a28-120">Standardmäßig sind es nur Administratoren.</span><span class="sxs-lookup"><span data-stu-id="77a28-120">By default it's only administrators.</span></span> <span data-ttu-id="77a28-121">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="77a28-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="77a28-122">Geben Sie Ihren [Omnisend-API-Schlüssel](https://support.omnisend.com/en/articles/1061890-generating-api-key) ein.</span><span class="sxs-lookup"><span data-stu-id="77a28-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="77a28-123">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="77a28-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="77a28-124">Wählen Sie **Verbinden** aus, um die Verbindung zu Omnisend zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="77a28-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="77a28-125">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="77a28-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="77a28-126">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="77a28-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="77a28-127">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="77a28-127">Configure an export</span></span>

<span data-ttu-id="77a28-128">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="77a28-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="77a28-129">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="77a28-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="77a28-130">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="77a28-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="77a28-131">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="77a28-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="77a28-132">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Omnisend-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="77a28-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="77a28-133">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="77a28-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="77a28-134">Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="77a28-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="77a28-135">Der Export nach Omnisend ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="77a28-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="77a28-136">Optional können Sie Vorname, Nachname, Adresse, Bundesland und Land/Region, Stadt und Postleitzahl exportieren, um personalisiertere E-Mails zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="77a28-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="77a28-137">Wählen Sie **Attribut hinzufügen**, um diese Felder zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="77a28-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="77a28-138">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="77a28-138">Select **Save**.</span></span>

<span data-ttu-id="77a28-139">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="77a28-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="77a28-140">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="77a28-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="77a28-141">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="77a28-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="77a28-142">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="77a28-142">Data privacy and compliance</span></span>

<span data-ttu-id="77a28-143">Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten an Omnisend zu übertragen, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="77a28-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="77a28-144">Microsoft überträgt diese Daten auf Ihre Anweisung. Sie sind jedoch dafür verantwortlich, dass Omnisend alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="77a28-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="77a28-145">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="77a28-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="77a28-146">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="77a28-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
