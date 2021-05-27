---
title: Customer Insights-Daten zu SFTP-Hosts exportieren
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu einem SFTP-Speicherort exportieren.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3663a48955f0b1db8a96e25403e5f8947bc6a220
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976892"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="06f86-103">Segmentlisten und anderen zu einem SFTP-Speicherort exportieren (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="06f86-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="06f86-104">Verwenden Sie Ihre Kundendaten in Anwendungen von Drittanbietern, indem Sie sie an einen SFTP-Speicherort (Secure File Transfer Protocol) exportieren.</span><span class="sxs-lookup"><span data-stu-id="06f86-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="06f86-105">Voraussetzungen für die Verbindung</span><span class="sxs-lookup"><span data-stu-id="06f86-105">Prerequisites for connection</span></span>

- <span data-ttu-id="06f86-106">Verfügbarkeit eines SFTP-Hosts und entsprechender Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="06f86-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="06f86-107">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="06f86-107">Known limitations</span></span>

- <span data-ttu-id="06f86-108">Die Laufzeit eines Exports hängt von Ihrer Systemleistung ab.</span><span class="sxs-lookup"><span data-stu-id="06f86-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="06f86-109">Wir empfehlen zwei CPU-Kerne und 1 GB Speicher als minimale Konfiguration Ihres Servers.</span><span class="sxs-lookup"><span data-stu-id="06f86-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="06f86-110">Das Exportieren von Entitäten mit bis zu 100 Millionen Kundenprofilen kann 90 Minuten dauern, wenn die empfohlene Mindestkonfiguration von zwei CPU-Kernen und 1 GB Speicher verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="06f86-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="06f86-111">Verbindungen mit SFTP einrichten</span><span class="sxs-lookup"><span data-stu-id="06f86-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="06f86-112">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="06f86-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="06f86-113">Wählen Sie **Verbindung hinzufügen** und dann **SFTP** aus, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="06f86-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="06f86-114">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="06f86-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="06f86-115">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="06f86-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="06f86-116">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="06f86-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="06f86-117">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="06f86-117">Choose who can use this connection.</span></span> <span data-ttu-id="06f86-118">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="06f86-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="06f86-119">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="06f86-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="06f86-120">Geben Sie **Benutzername**, **Kennwort** und **Hostname** und **Exportordner** für Ihr SFTP-Konto an.</span><span class="sxs-lookup"><span data-stu-id="06f86-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="06f86-121">Wählen Sie die **üerprüfen**, um die Verbindung zu testen.</span><span class="sxs-lookup"><span data-stu-id="06f86-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="06f86-122">Wählen Sie, ob Sie Ihre Daten **Gzipped** oder **Entpackt** exportieren möchten, und das **Feldtrennzeichen** für die exportierten Dateien.</span><span class="sxs-lookup"><span data-stu-id="06f86-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="06f86-123">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="06f86-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="06f86-124">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="06f86-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="06f86-125">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="06f86-125">Configure an export</span></span>

<span data-ttu-id="06f86-126">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="06f86-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="06f86-127">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="06f86-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="06f86-128">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="06f86-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="06f86-129">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="06f86-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="06f86-130">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem SFTP-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="06f86-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="06f86-131">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="06f86-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="06f86-132">Wählen Sie die Entitäten für die zu exportierenden Beispielsegmente.</span><span class="sxs-lookup"><span data-stu-id="06f86-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="06f86-133">Jede ausgewählte Entität wird beim Export in bis zu fünf Ausgabedateien aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="06f86-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="06f86-134">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="06f86-134">Select **Save**.</span></span>

<span data-ttu-id="06f86-135">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="06f86-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="06f86-136">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="06f86-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="06f86-137">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="06f86-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="06f86-138">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="06f86-138">Data privacy and compliance</span></span>

<span data-ttu-id="06f86-139">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten über SFTP aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="06f86-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="06f86-140">Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass das Exportziel alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="06f86-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="06f86-141">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="06f86-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="06f86-142">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="06f86-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
