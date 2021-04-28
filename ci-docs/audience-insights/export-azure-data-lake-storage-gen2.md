---
title: Customer Insights-Daten zu Azure Data Lake Storage Gen2 exportieren
description: Lernen Sie, wie Sie die Verbindung zu Azure Data Lake Storage Gen2 konfigurieren.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760050"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="842c2-103">Richten Sie die Verbindung mit Azure Data Lake Storage Gen2 ein (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="842c2-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="842c2-104">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="842c2-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="842c2-105">Wählen Sie **Verbindung hinzufügen** und dann **Azure Data Lake Gen 2** aus, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="842c2-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="842c2-106">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="842c2-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="842c2-107">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="842c2-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="842c2-108">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="842c2-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="842c2-109">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="842c2-109">Choose who can use this connection.</span></span> <span data-ttu-id="842c2-110">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="842c2-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="842c2-111">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="842c2-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="842c2-112">Geben Sie **Kontobezeichnung**, **Kontoschlüssel** und **Container** für den Azure Data Lake Storage Gen2 ein.</span><span class="sxs-lookup"><span data-stu-id="842c2-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="842c2-113">Erfahren Sie, wie Sie ein Speicherkonto erstellen, das Sie mit Azure Data Lake Storage Gen2 verwenden können, unter [Speicherkonto erstellen](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="842c2-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="842c2-114">Weitere Informationen zum Azure Data Lake Gen 2-Kontonamen und Kontoschlüssel finden Sie unter [Verwalten Sie die Speicherkontoeinstellungen im Azure-Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="842c2-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="842c2-115">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="842c2-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="842c2-116">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="842c2-116">Configure an export</span></span>

<span data-ttu-id="842c2-117">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="842c2-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="842c2-118">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="842c2-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="842c2-119">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="842c2-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="842c2-120">Um einen neuen Export zu erstellen, wählen Sie **Export hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="842c2-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="842c2-121">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem **Azure Data Lake**-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="842c2-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="842c2-122">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="842c2-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="842c2-123">Aktivieren Sie das Kontrollkästchen neben jeder der Entitäten, die Sie an dieses Ziel exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="842c2-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="842c2-124">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="842c2-124">Select **Save**.</span></span>

<span data-ttu-id="842c2-125">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="842c2-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="842c2-126">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="842c2-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="842c2-127">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="842c2-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="842c2-128">Exportierte Daten werden in dem von Ihnen konfigurierten Azure Data Lake Gen 2-Speichercontainer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="842c2-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
