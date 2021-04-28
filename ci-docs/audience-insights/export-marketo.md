---
title: Customer Insights Daten nach Marketo exportieren
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu Marketo exportieren.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759820"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="4702c-103">Segmente nach Marketo exportieren (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="4702c-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="4702c-104">Exportieren Sie Segmente von vereinheitlichten Kundenprofilen, um Kampagnen zu erstellen, E-Mail-Marketing zu betreiben und bestimmte Kundengruppen mit Marketo zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="4702c-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="4702c-105">Voraussetzungen für die Verbindung</span><span class="sxs-lookup"><span data-stu-id="4702c-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="4702c-106">Sie haben ein [Marketo-Konto](https://login.marketo.com/) und die entsprechenden Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="4702c-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="4702c-107">Es gibt bestehende Listen in Marketo und die entsprechenden IDs.</span><span class="sxs-lookup"><span data-stu-id="4702c-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="4702c-108">Weitere Informationen finden Sie unter [Marketo-Listen](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="4702c-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="4702c-109">Sie haben [Konfigurierte Segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="4702c-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="4702c-110">Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.</span><span class="sxs-lookup"><span data-stu-id="4702c-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="4702c-111">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4702c-111">Known limitations</span></span>

- <span data-ttu-id="4702c-112">Bis zu 1 Million Profile pro Export zu Marketo.</span><span class="sxs-lookup"><span data-stu-id="4702c-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="4702c-113">Der Export zu Marketo ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="4702c-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="4702c-114">Das Exportieren von Segmenten mit insgesamt 1 Million Profilen kann bis zu 3 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="4702c-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="4702c-115">Die Anzahl der Profile, die Sie zu Marketo exportieren können, hängt von Ihrem Vertrag mit Marketo ab und ist dort begrenzt.</span><span class="sxs-lookup"><span data-stu-id="4702c-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="4702c-116">Richten Sie die Verbindung mit Marketo ein</span><span class="sxs-lookup"><span data-stu-id="4702c-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="4702c-117">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="4702c-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4702c-118">Wählen Sie **Verbindung hinzufügen** und dann **Marketo** aus, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4702c-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="4702c-119">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="4702c-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4702c-120">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="4702c-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4702c-121">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="4702c-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4702c-122">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="4702c-122">Choose who can use this connection.</span></span> <span data-ttu-id="4702c-123">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="4702c-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="4702c-124">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="4702c-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="4702c-125">Geben Sie Ihre **[Marketo Client ID, Client secret und REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)** ein.</span><span class="sxs-lookup"><span data-stu-id="4702c-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="4702c-126">Wählen Sie **Ich stimme zu**, um die **Datenschutz und Compliance** zu bestätigen und wählen Sie **Verbinden**, um die Verbindung zu Marketo zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="4702c-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="4702c-127">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="4702c-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="4702c-128">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="4702c-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="4702c-129">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="4702c-129">Configure an export</span></span>

<span data-ttu-id="4702c-130">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="4702c-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4702c-131">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="4702c-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4702c-132">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="4702c-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4702c-133">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4702c-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="4702c-134">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Marketo-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="4702c-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="4702c-135">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="4702c-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="4702c-136">Geben Sie Ihre **[Marketo-Listen-ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** ein.</span><span class="sxs-lookup"><span data-stu-id="4702c-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="4702c-137">Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="4702c-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="4702c-138">Optional können Sie **Vorname**, **Nachname**, **Stadt**, **Bundesland** und **Land/Region** exportieren, um personalisiertere E-Mails zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4702c-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="4702c-139">Wählen Sie **Attribut hinzufügen**, um diese Felder zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="4702c-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="4702c-140">Wählen Sie die Segemente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4702c-140">Select the segments you want to export.</span></span> <span data-ttu-id="4702c-141">Sie können insgesamt bis zu 1 Mio. Kundenprofile zu Marketo exportieren.</span><span class="sxs-lookup"><span data-stu-id="4702c-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="4702c-142">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="4702c-142">Select **Save**.</span></span>

<span data-ttu-id="4702c-143">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4702c-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="4702c-144">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4702c-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4702c-145">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="4702c-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="4702c-146">In Marketo finden Sie Ihre Segmente jetzt unter [Marketo-Listen](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="4702c-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4702c-147">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="4702c-147">Data privacy and compliance</span></span>

<span data-ttu-id="4702c-148">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Marketo aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="4702c-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4702c-149">Microsoft wird diese Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Marketo alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können.</span><span class="sxs-lookup"><span data-stu-id="4702c-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4702c-150">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4702c-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4702c-151">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="4702c-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]