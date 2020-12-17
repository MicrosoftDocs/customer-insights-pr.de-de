---
title: Customer Insights-Daten zu SFTP-Hosts exportieren
description: Erfahren Sie, wie Sie die Verbindung zu einem SFTP-Host konfigurieren.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643502"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="52dd6-103">Connector für SFTP (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="52dd6-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="52dd6-104">Verwenden Sie Ihre Kundendaten in Anwendungen von Drittanbietern, indem Sie sie auf einen Secure File Transfer Protocol(SFTP)-Host exportieren.</span><span class="sxs-lookup"><span data-stu-id="52dd6-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="52dd6-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="52dd6-105">Prerequisites</span></span>

- <span data-ttu-id="52dd6-106">Verfügbarkeit eines SFTP-Hosts und entsprechender Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="52dd6-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="52dd6-107">Verbindung mit SFTP herstellen</span><span class="sxs-lookup"><span data-stu-id="52dd6-107">Connect to SFTP</span></span>

1. <span data-ttu-id="52dd6-108">Gehen Sie zu **Administrator** > **Exportziele**.</span><span class="sxs-lookup"><span data-stu-id="52dd6-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="52dd6-109">Wählen Sie **SFTP** und **einrichten** aus.</span><span class="sxs-lookup"><span data-stu-id="52dd6-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="52dd6-110">Geben Sie Ihrem Ziel einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="52dd6-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="52dd6-111">Geben Sie einen **Benutzername**, **Kennwort** und **Hostname** für Ihr SFTP-Konto an.</span><span class="sxs-lookup"><span data-stu-id="52dd6-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="52dd6-112">Beispiel: Wenn der Stammordner Ihres SFTP-Servers /root/folder ist und Sie möchten, dass die Daten nach /root/folder/ci_export_destination_folder exportiert werden, sollte der Host sftp://<server_address>/ci_export_destination_folder“ sein.</span><span class="sxs-lookup"><span data-stu-id="52dd6-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="52dd6-113">Wählen Sie die **üerprüfen**, um die Verbindung zu testen.</span><span class="sxs-lookup"><span data-stu-id="52dd6-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="52dd6-114">Wählen Sie nach erfolgreicher Überprüfung aus, ob Sie Ihre Daten **gezippt** oder **entpackt** exportieren möchten und wählen Sie die **Feldtrennzeichen** für die exportierten Dateien.</span><span class="sxs-lookup"><span data-stu-id="52dd6-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="52dd6-115">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="52dd6-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="52dd6-116">Wählen Sie **Weiter**, um die Konfiguration des Exports zu starten.</span><span class="sxs-lookup"><span data-stu-id="52dd6-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="52dd6-117">Verbindung konfigurieren</span><span class="sxs-lookup"><span data-stu-id="52dd6-117">Configure the connection</span></span>

1. <span data-ttu-id="52dd6-118">Wählen Sie das **Kundenattribut**, das Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="52dd6-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="52dd6-119">Sie können ein oder mehrere Attribute exportieren.</span><span class="sxs-lookup"><span data-stu-id="52dd6-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="52dd6-120">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="52dd6-120">Select **Next**.</span></span>

1. <span data-ttu-id="52dd6-121">Wählen Sie die Segemente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="52dd6-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="52dd6-122">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="52dd6-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="52dd6-123">Exportieren der Daten</span><span class="sxs-lookup"><span data-stu-id="52dd6-123">Export the data</span></span>

<span data-ttu-id="52dd6-124">Sie könenn [Daten nach Bedarf exportieren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="52dd6-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="52dd6-125">Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="52dd6-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="52dd6-126">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="52dd6-126">Data privacy and compliance</span></span>

<span data-ttu-id="52dd6-127">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten über SFTP aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="52dd6-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="52dd6-128">Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass das Exportziel alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="52dd6-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="52dd6-129">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="52dd6-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="52dd6-130">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="52dd6-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
