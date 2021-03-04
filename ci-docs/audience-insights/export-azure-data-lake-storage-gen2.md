---
title: Customer Insights-Daten zu Azure Data Lake Storage Gen2 exportieren
description: Lernen Sie, wie Sie die Verbindung zu Azure Data Lake Storage Gen2 konfigurieren.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477178"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="059b4-103">Konnektor für Azure Data Lake Storage Gen2 (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="059b4-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="059b4-104">Speichern Sie Ihre Customer Insights-Daten in Azure Data Lake Storage Gen2, oder verwenden Sie es, um Ihre Daten in andere Anwendungen zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="059b4-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="059b4-105">Konfigurieren Sie den Konnektor für Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="059b4-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="059b4-106">Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Ziele exportieren**.</span><span class="sxs-lookup"><span data-stu-id="059b4-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="059b4-107">Unter **Azure Data Lake Storage Gen2** wählen Sie **Einrichten**.</span><span class="sxs-lookup"><span data-stu-id="059b4-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="059b4-108">Geben Sie Ihrem Ziel einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="059b4-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="059b4-109">Geben Sie **Kontobezeichnung**, **Kontoschlüssel** und **Container** für den Azure Data Lake Storage Gen2 ein.</span><span class="sxs-lookup"><span data-stu-id="059b4-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="059b4-110">Erfahren Sie, wie Sie ein Speicherkonto erstellen, das Sie mit Azure Data Lake Storage Gen2 verwenden können, unter [Speicherkonto erstellen](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="059b4-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="059b4-111">Weitere Informationen zum Ermitteln des Azure Data Lake Gen2-Speicherkontonamens und des Kontoschlüssels finden Sie unter [Verwalten Sie die Speicherkontoeinstellungen im Azure-Portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="059b4-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="059b4-112">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="059b4-112">Select **Next**.</span></span>

1. <span data-ttu-id="059b4-113">Aktivieren Sie das Kontrollkästchen neben jeder der Entitäten, die Sie an dieses Ziel exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="059b4-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="059b4-114">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="059b4-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="059b4-115">Exportieren der Daten</span><span class="sxs-lookup"><span data-stu-id="059b4-115">Export the data</span></span>

<span data-ttu-id="059b4-116">Sie könenn [Daten nach Bedarf exportieren](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="059b4-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="059b4-117">Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="059b4-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
