---
title: Customer Insights-Daten zu Google Ads exportieren
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu Google Ads exportieren.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976317"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="b7dc7-103">Segmente in Google Ads exportieren (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="b7dc7-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="b7dc7-104">Exportieren Sie Segmente von vereinheitlichten Kundenprofilen in die Google Ads Zielgruppenliste und nutzen Sie diese für Werbung in der Google Suche, Gmail, YouTube und im Google Display-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="b7dc7-105">Voraussetzungen für die Verbindung</span><span class="sxs-lookup"><span data-stu-id="b7dc7-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="b7dc7-106">Sie haben ein [Google Ads-Konto](https://ads.google.com/) und die entsprechenden Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b7dc7-107">Sie haben [genehmigtes Google Ads Developer-Token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="b7dc7-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="b7dc7-108">Sie erfüllen die Anforderungen der [Kunden-Übereinstimmungs-Richtlinie](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="b7dc7-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="b7dc7-109">Sie erfüllen die Anforderungen der [Remarketing-Listengrößen](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="b7dc7-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="b7dc7-110">Es gibt bestehende Zielgruppen in Google Ads und die dazugehörigen IDs.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="b7dc7-111">Weitere Informationen finden Sie unter [Google Ads-Zielgruppen](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="b7dc7-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="b7dc7-112">Sie haben [Konfigurierte Segmente](segments.md)</span><span class="sxs-lookup"><span data-stu-id="b7dc7-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="b7dc7-113">Vereinheitlichte Kundenprofile in den exportierten Segmenten enthalten Felder, die eine E-Mail-Adresse, einen Vornamen und einen Nachnamen darstellen</span><span class="sxs-lookup"><span data-stu-id="b7dc7-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b7dc7-114">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b7dc7-114">Known limitations</span></span>

- <span data-ttu-id="b7dc7-115">Bis zu 1 Million Profile pro Export zu Google Ads.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="b7dc7-116">Der Export zu Google Ads ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="b7dc7-117">Das Exportieren von Segmenten mit insgesamt 1 Million Profilen kann aufgrund von Beschränkungen auf der Anbieterseite bis zu 5 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="b7dc7-118">Der Abgleich in Google Ads kann bis zu 48 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="b7dc7-119">Verbindung mit Google Ads einrichten</span><span class="sxs-lookup"><span data-stu-id="b7dc7-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="b7dc7-120">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b7dc7-121">Wählen Sie **Verbindung hinzufügen** und dann **Google Ads** aus, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="b7dc7-122">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b7dc7-123">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b7dc7-124">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b7dc7-125">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-125">Choose who can use this connection.</span></span> <span data-ttu-id="b7dc7-126">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b7dc7-127">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b7dc7-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b7dc7-128">Geben Sie Ihre **[Google Ads Kunden-ID](https://support.google.com/google-ads/answer/1704344)** ein.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="b7dc7-129">Geben Sie Ihr **[Google Ads genehmigtes Entwickler-Token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** ein.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="b7dc7-130">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b7dc7-131">Wählen Sie **Mit Google Ads authentifizieren** und geben Sie Ihre Google Ads Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="b7dc7-132">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b7dc7-133">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="b7dc7-134">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="b7dc7-134">Configure an export</span></span>

<span data-ttu-id="b7dc7-135">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b7dc7-136">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b7dc7-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b7dc7-137">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b7dc7-138">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b7dc7-139">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Google Ads-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="b7dc7-140">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b7dc7-141">Geben Sie Ihre **[Google Ads Zielgruppen-ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** ein und wählen Sie **Verbinden**, um die Verbindung zu Google Ads zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="b7dc7-142">Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b7dc7-143">Wiederholen Sie die gleichen Schritte für die Felder **Vorname** und **Nachname**.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="b7dc7-144">Wählen Sie die Segemente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-144">Select the segments you want to export.</span></span> <span data-ttu-id="b7dc7-145">Sie können insgesamt bis zu 1 Million Kundenprofile zu Google Ads exportieren.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="b7dc7-146">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b7dc7-147">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b7dc7-148">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b7dc7-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b7dc7-149">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="b7dc7-149">Data privacy and compliance</span></span>

<span data-ttu-id="b7dc7-150">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Google Ads aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b7dc7-151">Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Google Ads alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="b7dc7-152">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b7dc7-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b7dc7-153">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
