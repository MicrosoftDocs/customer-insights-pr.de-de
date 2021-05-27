---
title: Exportieren von Customer Insights-Daten zu SendGrid
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu SendGrid exportieren.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d3d61d2b5b68079c7717e41dee5a2f698f2b62c
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976915"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="e84a1-103">Segmente nach SendGrid exportieren (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="e84a1-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="e84a1-104">Exportieren Sie Segmente einheitlicher Kundenprofile in SendGrid-Kontaktlisten und verwenden Sie sie für Kampagnen und E-Mail-Marketing in SendGrid.</span><span class="sxs-lookup"><span data-stu-id="e84a1-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="e84a1-105">Voraussetzungen für die Verbindung</span><span class="sxs-lookup"><span data-stu-id="e84a1-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="e84a1-106">Sie haben ein [SendGrid-Konto](https://sendgrid.com/) und die entsprechenden Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="e84a1-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e84a1-107">Es gibt bestehende Kontaktlisten in SendGrid und die entsprechenden IDs.</span><span class="sxs-lookup"><span data-stu-id="e84a1-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="e84a1-108">Weitere Informationen finden Sie unter [SendGrid – Kontakte verwalten](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="e84a1-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="e84a1-109">Sie haben [Konfigurierte Segmente](segments.md) in Zielgruppen-Insights.</span><span class="sxs-lookup"><span data-stu-id="e84a1-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e84a1-110">Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.</span><span class="sxs-lookup"><span data-stu-id="e84a1-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e84a1-111">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e84a1-111">Known limitations</span></span>

- <span data-ttu-id="e84a1-112">Insgesamt bis zu 100.000 Profile an SendGrid.</span><span class="sxs-lookup"><span data-stu-id="e84a1-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="e84a1-113">Der Export zu SendGrid ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="e84a1-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="e84a1-114">Das Exportieren von bis zu 100.000 Profilen an SendGrid kann bis zu einigen Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="e84a1-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="e84a1-115">Die Anzahl der Profile, die Sie zu SendGrid exportieren können, hängt von Ihrem Vertrag mit SendGrid ab und ist dort begrenzt.</span><span class="sxs-lookup"><span data-stu-id="e84a1-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="e84a1-116">Verbindung mit SendGrid einrichten</span><span class="sxs-lookup"><span data-stu-id="e84a1-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="e84a1-117">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="e84a1-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e84a1-118">Wählen Sie **Verbindung hinzufügen** und dann **SendGrid** aus, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e84a1-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="e84a1-119">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="e84a1-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e84a1-120">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="e84a1-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e84a1-121">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="e84a1-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e84a1-122">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="e84a1-122">Choose who can use this connection.</span></span> <span data-ttu-id="e84a1-123">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="e84a1-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e84a1-124">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e84a1-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e84a1-125">Geben Sie Ihren **SendGrid-API-Schlüssel** [SendGrid-API-Schlüssel](https://sendgrid.com/docs/ui/account-and-settings/api-keys/) ein.</span><span class="sxs-lookup"><span data-stu-id="e84a1-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="e84a1-126">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="e84a1-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e84a1-127">Wählen Sie **Verbinden**, um die Verbindung zu SendGrid zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="e84a1-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="e84a1-128">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="e84a1-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e84a1-129">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="e84a1-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e84a1-130">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="e84a1-130">Configure an export</span></span>

<span data-ttu-id="e84a1-131">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="e84a1-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e84a1-132">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e84a1-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e84a1-133">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="e84a1-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e84a1-134">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e84a1-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e84a1-135">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem SendGrid-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="e84a1-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="e84a1-136">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e84a1-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e84a1-137">Geben Sie Ihre **[SendGrid-Listen-ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** ein.</span><span class="sxs-lookup"><span data-stu-id="e84a1-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="e84a1-138">Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="e84a1-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e84a1-139">Wiederholen Sie die gleichen Schritte für andere optionale Felder wie **Vorname**, **Nachname**, **Land/Region**, **Bundesland/Kanton**, **Stadt** und **Postleitzahl**.</span><span class="sxs-lookup"><span data-stu-id="e84a1-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="e84a1-140">Wählen Sie die Segemente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e84a1-140">Select the segments you want to export.</span></span> <span data-ttu-id="e84a1-141">Es wird dringend **empfohlen, nicht mehr als 100.000 Kundenprofile insgesamt** an SendGrid zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="e84a1-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="e84a1-142">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="e84a1-142">Select **Save**.</span></span>

<span data-ttu-id="e84a1-143">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e84a1-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e84a1-144">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e84a1-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e84a1-145">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e84a1-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e84a1-146">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="e84a1-146">Data privacy and compliance</span></span>

<span data-ttu-id="e84a1-147">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an SendGrid aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="e84a1-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e84a1-148">Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass SendGrid alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="e84a1-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="e84a1-149">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e84a1-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e84a1-150">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="e84a1-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]