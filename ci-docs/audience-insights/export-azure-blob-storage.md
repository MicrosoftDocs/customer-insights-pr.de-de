---
title: Customer Insights-Daten in einen Azure Blob Storage exportieren
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zum Azure Blob Storage exportieren.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760188"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="6fee6-103">Exportieren Sie die Segmentliste und andere Daten in den Azure Blob Storage (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="6fee6-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="6fee6-104">Speichern Sie Ihre Customer Insights-Daten in einem Azure Blob Storage, oder verwenden Sie es, um Ihre Daten in andere Anwendungen zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="6fee6-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="6fee6-105">Richten Sie die Verbindung mit Azure Blob Storage ein</span><span class="sxs-lookup"><span data-stu-id="6fee6-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="6fee6-106">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="6fee6-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6fee6-107">Wählen Sie **Verbindung hinzufügen** und dann **Azure Blob Storage** aus, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6fee6-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="6fee6-108">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="6fee6-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="6fee6-109">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="6fee6-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="6fee6-110">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="6fee6-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6fee6-111">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="6fee6-111">Choose who can use this connection.</span></span> <span data-ttu-id="6fee6-112">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="6fee6-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="6fee6-113">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6fee6-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6fee6-114">Geben Sie **Kontobezeichnung**, **Kontoschlüssel** und **Container** für Ihr Blob Storage-Konto ein.</span><span class="sxs-lookup"><span data-stu-id="6fee6-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="6fee6-115">Weitere Informationen zum Ermitteln des Blob Storage-Kontonamens und des Kontoschlüssels finden Sie unter [Verwalten Sie die Speicherkontoeinstellungen im Azure-Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="6fee6-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="6fee6-116">Informationen zum Erstellen eines Containers finden Sie unter [Erstellen eines Containers](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="6fee6-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="6fee6-117">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="6fee6-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="6fee6-118">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="6fee6-118">Configure an export</span></span>

<span data-ttu-id="6fee6-119">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="6fee6-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="6fee6-120">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6fee6-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6fee6-121">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="6fee6-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6fee6-122">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6fee6-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="6fee6-123">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Azure Blob Storage-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="6fee6-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="6fee6-124">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="6fee6-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="6fee6-125">Aktivieren Sie das Kontrollkästchen neben jeder der Entitäten, die Sie an dieses Ziel exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6fee6-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="6fee6-126">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="6fee6-126">Select **Save**.</span></span>

<span data-ttu-id="6fee6-127">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6fee6-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6fee6-128">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6fee6-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="6fee6-129">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="6fee6-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="6fee6-130">Exportierte Daten werden in dem von Ihnen konfigurierten Blob Storage-Container gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6fee6-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="6fee6-131">Die folgenden Ordnerpfade werden automatisch in Ihrem Container erstellt:</span><span class="sxs-lookup"><span data-stu-id="6fee6-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="6fee6-132">Für Quell-Entitäten und vom System generierte Entitäten: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="6fee6-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="6fee6-133">Beispiel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="6fee6-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="6fee6-134">Die model.json-Datei für die exportierten Entitäten befindet sich auf der %ExportDestinationName%-Ebene</span><span class="sxs-lookup"><span data-stu-id="6fee6-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="6fee6-135">Beispiel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="6fee6-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
