---
title: Exportieren Sie Customer Insights-Daten nach Sendinblue
description: Erfahren Sie, wie Sie die Verbindung und den Export zu Sendinblue konfigurieren.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314613"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="ed545-103">Segmente nach Sendinblue exportieren (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="ed545-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="ed545-104">Segmente von einheitlichen Kundenprofilen exportieren, um Kampagnen zu generieren, E-Mail-Marketing bereitzustellen und spezifische Kundengruppen mit Sendinblue zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="ed545-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="ed545-105">Voraussetzungen für die Verbindung</span><span class="sxs-lookup"><span data-stu-id="ed545-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="ed545-106">Sie haben ein [Sendinblue-Konto](https://www.sendinblue.com/) und entsprechende Administrator-Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="ed545-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ed545-107">Es gibt existierende Listen in Sendinblue und die entsprechenden IDs.</span><span class="sxs-lookup"><span data-stu-id="ed545-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="ed545-108">Sie haben [Konfigurierte Segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ed545-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="ed545-109">Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.</span><span class="sxs-lookup"><span data-stu-id="ed545-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ed545-110">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="ed545-110">Known limitations</span></span>

- <span data-ttu-id="ed545-111">Bis zu 1 Million Profile pro Export an Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="ed545-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="ed545-112">Der Export nach Sendinblue ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="ed545-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="ed545-113">Der Export von Segmenten mit insgesamt 1 Million Profilen kann bis zu 90 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="ed545-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="ed545-114">Die Anzahl der Profile, die Sie zu Sendinblue exportieren können, hängt von Ihrem Vertrag mit Sendinblue ab.</span><span class="sxs-lookup"><span data-stu-id="ed545-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="ed545-115">Verbindung zu Sendinblue einrichten</span><span class="sxs-lookup"><span data-stu-id="ed545-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="ed545-116">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="ed545-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ed545-117">Wählen Sie **Verbindung hinzufügen** und wählen Sie **Sendinblue**, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ed545-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="ed545-118">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="ed545-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ed545-119">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="ed545-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ed545-120">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="ed545-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ed545-121">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="ed545-121">Choose who can use this connection.</span></span> <span data-ttu-id="ed545-122">Standardmäßig sind es nur Administratoren.</span><span class="sxs-lookup"><span data-stu-id="ed545-122">By default it's only administrators.</span></span> <span data-ttu-id="ed545-123">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ed545-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ed545-124">Geben Sie Ihren **[SendinbBlue API-Schlüssel ein](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="ed545-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="ed545-125">Wählen Sie **Ich stimme zu**, um die **Privacy- und Datenschutzgesetze und Einhaltung** zu bestätigen und wählen Sie **Verbinden**, um die Verbindung zu Sendinblue zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="ed545-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="ed545-126">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="ed545-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ed545-127">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="ed545-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ed545-128">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="ed545-128">Configure an export</span></span>

<span data-ttu-id="ed545-129">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="ed545-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ed545-130">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ed545-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ed545-131">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="ed545-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ed545-132">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ed545-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ed545-133">In dem Feld **Anschluss für Export** wählen Sie im Bereich Sendinblue eine Verbindung aus.</span><span class="sxs-lookup"><span data-stu-id="ed545-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="ed545-134">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ed545-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ed545-135">Geben Sie Ihre **SendinbBlue Listen-ID** ein</span><span class="sxs-lookup"><span data-stu-id="ed545-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="ed545-136">Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="ed545-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="ed545-137">Optional können Sie **Vorname**, **Nachname**, und **Telefon** exportieren, um personalisiertere E-Mails zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ed545-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="ed545-138">Wählen Sie **Attribut hinzufügen**, um diese Felder zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="ed545-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="ed545-139">Wählen Sie die Segemente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ed545-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="ed545-140">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="ed545-140">Select **Save**.</span></span>

<span data-ttu-id="ed545-141">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ed545-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ed545-142">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ed545-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ed545-143">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ed545-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ed545-144">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="ed545-144">Data privacy and compliance</span></span>

<span data-ttu-id="ed545-145">Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten an Sendinblue zu übermitteln , erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogene Daten.</span><span class="sxs-lookup"><span data-stu-id="ed545-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ed545-146">Microsoft überträgt solche Daten auf Ihre Anweisung, aber Sie sind dafür verantwortlich, dass Sendinblue alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="ed545-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ed545-147">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ed545-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ed545-148">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="ed545-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
