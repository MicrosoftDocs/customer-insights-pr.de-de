---
title: Customer Insights-Daten nach DotDigital exportieren
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu DotDigital exportieren.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 235bcdfa4a7c4c1a382778bd4f66c1a9f5b7beb1
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759958"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="c0409-103">Segmentlisten in DotDigital exportieren (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="c0409-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="c0409-104">Exportieren Sie Segmente von vereinheitlichten Kundenprofilen in DotDigital-Adressbücher und verwenden Sie diese für Kampagnen, E-Mail-Marketing und zum Aufbau von Kundensegmenten mit DotDigital.</span><span class="sxs-lookup"><span data-stu-id="c0409-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="c0409-105">Voraussetzungen für die Verbindung</span><span class="sxs-lookup"><span data-stu-id="c0409-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="c0409-106">Sie haben ein [DotDigital-Konto](https://dotdigital.com/) und entsprechende Anmeldeinformationen für den Administrator.</span><span class="sxs-lookup"><span data-stu-id="c0409-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c0409-107">Es gibt bestehende Adressbücher in DotDigital und die entsprechenden IDs.</span><span class="sxs-lookup"><span data-stu-id="c0409-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="c0409-108">Die ID ist in der URL zu finden, wenn Sie ein Adressbuch auswählen und öffnen.</span><span class="sxs-lookup"><span data-stu-id="c0409-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="c0409-109">Weitere Informationen finden Sie unter [DotDigital Adressbücher](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="c0409-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="c0409-110">Sie haben [Konfigurierte Segmente](segments.md) in Zielgruppen-Insights.</span><span class="sxs-lookup"><span data-stu-id="c0409-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="c0409-111">Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.</span><span class="sxs-lookup"><span data-stu-id="c0409-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c0409-112">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="c0409-112">Known limitations</span></span>

- <span data-ttu-id="c0409-113">Bis zu 1 Million Profile pro Export zu DotDigital.</span><span class="sxs-lookup"><span data-stu-id="c0409-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="c0409-114">Das Exportieren zu DotDigital ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="c0409-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="c0409-115">Das Exportieren von Segmenten mit insgesamt 1 Million Profilen kann aufgrund von Beschränkungen auf der Provider-Seite bis zu 3 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="c0409-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="c0409-116">Die Anzahl der Profile, die Sie zu DotDigital exportieren können, ist abhängig und begrenzt von Ihrem Vertrag mit DotDigital.</span><span class="sxs-lookup"><span data-stu-id="c0409-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="c0409-117">Verbindung mit DotDigital einrichten</span><span class="sxs-lookup"><span data-stu-id="c0409-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="c0409-118">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="c0409-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c0409-119">Wählen Sie **Verbindung hinzufügen** und dann **DotDigital** aus, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c0409-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="c0409-120">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="c0409-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c0409-121">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="c0409-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c0409-122">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="c0409-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c0409-123">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="c0409-123">Choose who can use this connection.</span></span> <span data-ttu-id="c0409-124">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="c0409-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c0409-125">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c0409-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c0409-126">Geben Sie Ihren **DotDigital-Benutzernamen und Ihr Kennwort** ein.</span><span class="sxs-lookup"><span data-stu-id="c0409-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="c0409-127">Geben Sie Ihre **[DotDigital-Adressbuch-ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** ein.</span><span class="sxs-lookup"><span data-stu-id="c0409-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="c0409-128">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="c0409-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c0409-129">Wählen Sie **Verbinden**, um die Verbindung zu DotDigital zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="c0409-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="c0409-130">Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="c0409-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c0409-131">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="c0409-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="c0409-132">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="c0409-132">Configure an export</span></span>

<span data-ttu-id="c0409-133">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="c0409-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c0409-134">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c0409-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c0409-135">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="c0409-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c0409-136">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c0409-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="c0409-137">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem DotDigital-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="c0409-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="c0409-138">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c0409-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="c0409-139">Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="c0409-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="c0409-140">Wiederholen Sie die gleichen Schritte für andere optionale Felder wie **Vorname**, **Nachname**, **Voller Name**, **Geschlecht** und **Postleitzahl**.</span><span class="sxs-lookup"><span data-stu-id="c0409-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="c0409-141">Wählen Sie die Segemente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="c0409-141">Select the segments you want to export.</span></span> <span data-ttu-id="c0409-142">Sie können insgesamt bis zu 1 Million Kundenprofile zu DotDigital exportieren.</span><span class="sxs-lookup"><span data-stu-id="c0409-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="c0409-143">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="c0409-143">Select **Save**.</span></span>

<span data-ttu-id="c0409-144">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c0409-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c0409-145">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c0409-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c0409-146">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c0409-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="c0409-147">In DotDigital können Sie jetzt Ihre Segmente in [DotDigital Adressbüchern](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) finden.</span><span class="sxs-lookup"><span data-stu-id="c0409-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c0409-148">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="c0409-148">Data privacy and compliance</span></span>

<span data-ttu-id="c0409-149">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an DotDigital aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="c0409-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c0409-150">Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass DotDigital alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="c0409-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="c0409-151">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c0409-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c0409-152">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="c0409-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
