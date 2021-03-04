---
title: Customer Insights-Daten zu SFTP-Hosts exportieren
description: Erfahren Sie, wie Sie die Verbindung zu einem SFTP-Host konfigurieren.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267997"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="c5f27-103">Connector für SFTP (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="c5f27-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="c5f27-104">Verwenden Sie Ihre Kundendaten in Anwendungen von Drittanbietern, indem Sie sie auf einen Secure File Transfer Protocol(SFTP)-Host exportieren.</span><span class="sxs-lookup"><span data-stu-id="c5f27-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c5f27-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c5f27-105">Prerequisites</span></span>

- <span data-ttu-id="c5f27-106">Verfügbarkeit eines SFTP-Hosts und entsprechender Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="c5f27-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="c5f27-107">Mit SFTP verbinden</span><span class="sxs-lookup"><span data-stu-id="c5f27-107">Connect to SFTP</span></span>

1. <span data-ttu-id="c5f27-108">Gehen Sie zu **Administrator** > **Exportziele**.</span><span class="sxs-lookup"><span data-stu-id="c5f27-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c5f27-109">Wählen Sie **SFTP** und **einrichten** aus.</span><span class="sxs-lookup"><span data-stu-id="c5f27-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="c5f27-110">Geben Sie Ihrem Ziel einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="c5f27-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c5f27-111">Geben Sie **Benutzername**, **Kennwort** und **Hostname** und **Exportordner** für Ihr SFTP-Konto an.</span><span class="sxs-lookup"><span data-stu-id="c5f27-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="c5f27-112">Wählen Sie die **üerprüfen**, um die Verbindung zu testen.</span><span class="sxs-lookup"><span data-stu-id="c5f27-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="c5f27-113">Wählen Sie nach erfolgreicher Überprüfung aus, ob Sie Ihre Daten als **Gzipped** oder **Entpackt** exportieren möchten, und wählen Sie die **Feldtrennzeichen** für die exportierten Dateien aus.</span><span class="sxs-lookup"><span data-stu-id="c5f27-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="c5f27-114">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="c5f27-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c5f27-115">Wählen Sie **Weiter**, um die Konfiguration des Exports zu starten.</span><span class="sxs-lookup"><span data-stu-id="c5f27-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="c5f27-116">Export konfigurieren</span><span class="sxs-lookup"><span data-stu-id="c5f27-116">Configure the export</span></span>

1. <span data-ttu-id="c5f27-117">Wählen Sie die Entitäten für die zu exportierenden Beispielsegmente.</span><span class="sxs-lookup"><span data-stu-id="c5f27-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c5f27-118">Jede ausgewählte Entität besteht beim Export aus bis zu fünf Ausgabedateien.</span><span class="sxs-lookup"><span data-stu-id="c5f27-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="c5f27-119">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="c5f27-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c5f27-120">Exportieren der Daten</span><span class="sxs-lookup"><span data-stu-id="c5f27-120">Export the data</span></span>

<span data-ttu-id="c5f27-121">Sie könenn [Daten nach Bedarf exportieren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c5f27-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c5f27-122">Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="c5f27-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c5f27-123">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="c5f27-123">Known limitations</span></span>

- <span data-ttu-id="c5f27-124">Die Laufzeit eines Exports hängt von Ihrer Systemleistung ab.</span><span class="sxs-lookup"><span data-stu-id="c5f27-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="c5f27-125">Wir empfehlen zwei CPU-Kerne und 1 GB Speicher als minimale Konfiguration Ihres Servers.</span><span class="sxs-lookup"><span data-stu-id="c5f27-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="c5f27-126">Das Exportieren von Entitäten mit bis zu 100 Millionen Kundenprofilen kann 90 Minuten dauern, wenn die empfohlene Mindestkonfiguration von zwei CPU-Kernen und 1 GB Speicher verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c5f27-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c5f27-127">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="c5f27-127">Data privacy and compliance</span></span>

<span data-ttu-id="c5f27-128">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten über SFTP aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="c5f27-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c5f27-129">Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass das Exportziel alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="c5f27-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c5f27-130">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c5f27-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c5f27-131">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="c5f27-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]