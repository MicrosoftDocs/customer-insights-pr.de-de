---
title: Exportieren von Customer Insights-Daten zu Mailchimp
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu Mailchimp exportieren.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b94a8e8b6bb867ca04a64007d592b22fbd700618
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759877"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="020ca-103">Segmentlisten in Mailchimp exportieren (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="020ca-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="020ca-104">Exportieren Sie Segmente von vereinheitlichten Kundenprofilen nach Mailchimp, um Newsletter und E-Mail-Kampagnen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="020ca-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="020ca-105">Voraussetzungen für die Verbindung</span><span class="sxs-lookup"><span data-stu-id="020ca-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="020ca-106">Sie haben ein [Mailchimp-Konto](https://mailchimp.com/) und die entsprechenden Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="020ca-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="020ca-107">Es gibt bestehende Zielgruppen in Mailchimp und die dazugehörigen IDs.</span><span class="sxs-lookup"><span data-stu-id="020ca-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="020ca-108">Weitere Informationen finden Sie unter [Mailchimp-Zielgruppen](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="020ca-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="020ca-109">Sie haben [Konfigurierte Segmente](segments.md)</span><span class="sxs-lookup"><span data-stu-id="020ca-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="020ca-110">Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.</span><span class="sxs-lookup"><span data-stu-id="020ca-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="020ca-111">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="020ca-111">Known limitations</span></span>

- <span data-ttu-id="020ca-112">Bis zu 1 Million Profile pro Export zu Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="020ca-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="020ca-113">Der Export zu Mailchimp ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="020ca-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="020ca-114">Das Exportieren von Segmenten mit 1 Million Profilen kann bis zu drei Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="020ca-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="020ca-115">Die Anzahl der Profile, die Sie zu Mailchimp exportieren können, hängt von Ihrem Vertrag mit Mailchimp ab und ist dort begrenzt.</span><span class="sxs-lookup"><span data-stu-id="020ca-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="020ca-116">Verbindung mit Mailchimp einrichten</span><span class="sxs-lookup"><span data-stu-id="020ca-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="020ca-117">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="020ca-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="020ca-118">Wählen Sie **Verbindung hinzufügen** und dann **Autopilot** aus, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="020ca-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="020ca-119">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="020ca-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="020ca-120">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="020ca-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="020ca-121">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="020ca-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="020ca-122">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="020ca-122">Choose who can use this connection.</span></span> <span data-ttu-id="020ca-123">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="020ca-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="020ca-124">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="020ca-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="020ca-125">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="020ca-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="020ca-126">Wählen Sie **Verbinden** aus, um die Verbindung zu Mailchimp zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="020ca-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="020ca-127">Wählen Sie **Mit Mailchimp authentifizieren** und geben Sie Ihre Mailchimp Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="020ca-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="020ca-128">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="020ca-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="020ca-129">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="020ca-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="020ca-130">Den Konnektor konfigurieren</span><span class="sxs-lookup"><span data-stu-id="020ca-130">Configure the connector</span></span>

<span data-ttu-id="020ca-131">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="020ca-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="020ca-132">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="020ca-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="020ca-133">Gehen Sie zu **Daten**> **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="020ca-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="020ca-134">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="020ca-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="020ca-135">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Mailchimp-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="020ca-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="020ca-136">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="020ca-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="020ca-137">Geben Sie Ihre **[Mailchimp-Zielgruppen-ID](https://mailchimp.com/help/find-audience-id/)** ein</span><span class="sxs-lookup"><span data-stu-id="020ca-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="020ca-138">Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="020ca-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="020ca-139">Optional können Sie **Vorname** und **Nachname** exportieren, um personalisiertere E-Mails zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="020ca-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="020ca-140">Wählen Sie **Attribut hinzufügen**, um diese Felder zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="020ca-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="020ca-141">Wählen Sie die Segemente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="020ca-141">Select the segments you want to export.</span></span> <span data-ttu-id="020ca-142">Sie können insgesamt bis zu 1 Mio. Kundenprofile zu Mailchimp exportieren.</span><span class="sxs-lookup"><span data-stu-id="020ca-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="020ca-143">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="020ca-143">Select **Save**.</span></span>

<span data-ttu-id="020ca-144">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="020ca-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="020ca-145">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="020ca-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="020ca-146">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="020ca-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="020ca-147">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="020ca-147">Data privacy and compliance</span></span>

<span data-ttu-id="020ca-148">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Mailchimp aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="020ca-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="020ca-149">Microsoft wird diese Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Mailchimp alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können.</span><span class="sxs-lookup"><span data-stu-id="020ca-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="020ca-150">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="020ca-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="020ca-151">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="020ca-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
