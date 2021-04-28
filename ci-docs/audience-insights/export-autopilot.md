---
title: Exportieren von Customer Insights-Daten zu Autopilot
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu Autopilot exportieren.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760142"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="6fcf6-103">Segmente nach Autopilot exportieren (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="6fcf6-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="6fcf6-104">Exportieren Sie Segmente einheitlicher Kundenprofile in Autopilot und verwenden Sie sie für E-Mail-Marketing in Autopilot.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="6fcf6-105">Voraussetzungen für die Verbindung</span><span class="sxs-lookup"><span data-stu-id="6fcf6-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="6fcf6-106">Sie haben ein [Autopilot-Konto](https://www.autopilothq.com/) und entsprechende Anmeldeinformationen für den Administrator.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6fcf6-107">Sie haben [Konfigurierte Segmente](segments.md) in Zielgruppen-Insights.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="6fcf6-108">Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6fcf6-109">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="6fcf6-109">Known limitations</span></span>

- <span data-ttu-id="6fcf6-110">Sie können insgesamt bis zu 100.000 Profile zu Autopilot exportieren.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="6fcf6-111">Der Export zu Autopilot ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="6fcf6-112">Das Exportieren von bis zu 100.000 Profilen an Autopilot kann bis zu einigen Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="6fcf6-113">Die Anzahl der Profile, die Sie zu Autopilot exportieren können, hängt von Ihrem Vertrag mit Autopilot ab und ist dort begrenzt.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="6fcf6-114">Richten Sie die Verbindung mit Autopilot ein</span><span class="sxs-lookup"><span data-stu-id="6fcf6-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="6fcf6-115">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6fcf6-116">Wählen Sie **Verbindung hinzufügen** und dann **Autopilot** aus, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="6fcf6-117">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="6fcf6-118">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="6fcf6-119">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6fcf6-120">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-120">Choose who can use this connection.</span></span> <span data-ttu-id="6fcf6-121">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="6fcf6-122">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6fcf6-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="6fcf6-123">Geben Sie Ihren [Autopilot-API-Schlüssel](https://autopilot.docs.apiary.io/#) ein.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="6fcf6-124">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6fcf6-125">Wählen Sie **Verbinden**, um die Verbindung zu Autopilot zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="6fcf6-126">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="6fcf6-127">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="6fcf6-128">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="6fcf6-128">Configure an export</span></span>

<span data-ttu-id="6fcf6-129">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="6fcf6-130">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6fcf6-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6fcf6-131">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6fcf6-132">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="6fcf6-133">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Autopilot-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="6fcf6-134">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="6fcf6-135">Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="6fcf6-136">Wiederholen Sie die gleichen Schritte für andere optionale Felder wie **Vorname**, **Nachname**.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="6fcf6-137">Wählen Sie die Segemente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-137">Select the segments you want to export.</span></span> <span data-ttu-id="6fcf6-138">Es wird dringend **empfohlen, nicht mehr als 100.000 Kundenprofile insgesamt** an Autopilot zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="6fcf6-139">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-139">Select **Save**.</span></span>

<span data-ttu-id="6fcf6-140">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6fcf6-141">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6fcf6-142">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="6fcf6-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6fcf6-143">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="6fcf6-143">Data privacy and compliance</span></span>

<span data-ttu-id="6fcf6-144">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Autopilot aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6fcf6-145">Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Autopilot alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="6fcf6-146">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6fcf6-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6fcf6-147">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="6fcf6-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
