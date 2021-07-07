---
title: Exportieren Sie Customer Insights-Daten in die Salesforce Marketing Cloud
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und in die Salesforce Marketing Cloud exportieren.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314612"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="3295e-103">Exportieren von Segmenten und anderen Daten in die Salesforce Marketing Cloud (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="3295e-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="3295e-104">Verwenden Sie Ihre Kundendaten in Salesforce Marketing Cloud, indem Sie sie über einen SFTP-Speicherort (Secure File Transfer Protocol) exportieren.</span><span class="sxs-lookup"><span data-stu-id="3295e-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="3295e-105">Voraussetzungen für die Verbindung</span><span class="sxs-lookup"><span data-stu-id="3295e-105">Prerequisites for connection</span></span>

- <span data-ttu-id="3295e-106">Verfügbarkeit eines SFTP-Hosts und entsprechender Admin-Zugangsdaten.</span><span class="sxs-lookup"><span data-stu-id="3295e-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="3295e-107">So richten Sie SFTP-Standorte für Salesforce Marketing Cloud ein</span><span class="sxs-lookup"><span data-stu-id="3295e-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="3295e-108">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="3295e-108">Known limitations</span></span>

- <span data-ttu-id="3295e-109">Die Laufzeit eines Exports hängt von Ihrer Systemleistung ab.</span><span class="sxs-lookup"><span data-stu-id="3295e-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="3295e-110">Wir empfehlen zwei CPU-Kerne und 1 GB Speicher als minimale Konfiguration Ihres Servers.</span><span class="sxs-lookup"><span data-stu-id="3295e-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="3295e-111">Das Exportieren von Entitäten mit bis zu 100 Millionen Kundenprofilen kann bei Verwendung der empfohlenen Mindestkonfiguration 90 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="3295e-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="3295e-112">Verbindung zur Salesforce Marketing Cloud einrichten</span><span class="sxs-lookup"><span data-stu-id="3295e-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="3295e-113">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="3295e-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="3295e-114">Wählen Sie **Verbindung hinzufügen** und wählen Sie **Salesforce Marketing Cloud**, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3295e-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="3295e-115">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="3295e-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="3295e-116">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="3295e-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="3295e-117">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="3295e-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="3295e-118">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="3295e-118">Choose who can use this connection.</span></span> <span data-ttu-id="3295e-119">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="3295e-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="3295e-120">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="3295e-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="3295e-121">Geben Sie **Benutzername**, **Kennwort** und **Hostname** und **Exportordner** für Ihr SFTP-Konto an.</span><span class="sxs-lookup"><span data-stu-id="3295e-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="3295e-122">Wählen Sie die **üerprüfen**, um die Verbindung zu testen.</span><span class="sxs-lookup"><span data-stu-id="3295e-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="3295e-123">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="3295e-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3295e-124">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="3295e-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="3295e-125">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="3295e-125">Configure an export</span></span>

<span data-ttu-id="3295e-126">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="3295e-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="3295e-127">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="3295e-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3295e-128">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="3295e-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3295e-129">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3295e-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="3295e-130">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem SFTP-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="3295e-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="3295e-131">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3295e-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="3295e-132">Wählen Sie, ob Sie Ihre Daten **Gzipped** oder **Entpackt** exportieren möchten, und das **Feldtrennzeichen** für die exportierten Dateien.</span><span class="sxs-lookup"><span data-stu-id="3295e-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="3295e-133">Wählen Sie die Entitäten für die zu exportierenden Beispielsegmente.</span><span class="sxs-lookup"><span data-stu-id="3295e-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3295e-134">Jede ausgewählte Entität wird beim Export in bis zu fünf Ausgabedateien aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="3295e-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="3295e-135">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="3295e-135">Select **Save**.</span></span>

<span data-ttu-id="3295e-136">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3295e-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="3295e-137">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3295e-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3295e-138">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="3295e-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="3295e-139">Importieren Sie Customer Insights-Daten vom SFTP Standort in die Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="3295e-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="3295e-140">Erstellen der [Datenerweiterungen in der Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5), um die Customer Insights-Datendatei vom SFTP-Speicherort zu importieren.</span><span class="sxs-lookup"><span data-stu-id="3295e-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="3295e-141">[Importieren Sie die Daten vom SFTP-Speicherort](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) in die Salesforce Marketing Cloud-Datenerweiterung.</span><span class="sxs-lookup"><span data-stu-id="3295e-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="3295e-142">Richten Sie die Automatisierung ein, um die Daten in die Data Extensions zu importieren.</span><span class="sxs-lookup"><span data-stu-id="3295e-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="3295e-143">Mehr erfahren über [Dateiablageautomatisierungen und geplante Automatisierungen](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="3295e-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="3295e-144">Definieren einer [Dateiablageautomatisierung](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) oder einer [geplante Automatisierung](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="3295e-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="3295e-145">Hier ist ein Beispiel für [eine Automatisierung mit SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="3295e-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3295e-146">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="3295e-146">Data privacy and compliance</span></span>

<span data-ttu-id="3295e-147">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten über SFTP aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="3295e-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3295e-148">Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass das Exportziel alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="3295e-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3295e-149">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3295e-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3295e-150">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="3295e-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
