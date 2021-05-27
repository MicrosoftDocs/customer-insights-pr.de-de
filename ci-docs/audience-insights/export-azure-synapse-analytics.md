---
title: Exportieren Sie Customer Insights-Daten zu Azure Synapse Analyse
description: Erfahren Sie, wie Sie die Verbindung zu Outlook und Azure Synapse Analyse konfigurieren.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977376"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="c301c-103">Daten zu Azure Synapse Analyse (Vorschau) exportieren</span><span class="sxs-lookup"><span data-stu-id="c301c-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="c301c-104">Azure Synapse ist ein Analysedienst, der die Zeit für Einblicke in Data Warehouses und Big Data-Systeme verkürzt.</span><span class="sxs-lookup"><span data-stu-id="c301c-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="c301c-105">Sie können Ihre Customer Insights-Daten in [Azure Synapse](/azure/synapse-analytics/overview-what-is) erfassen und verwenden.</span><span class="sxs-lookup"><span data-stu-id="c301c-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c301c-106">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c301c-106">Prerequisites</span></span>

<span data-ttu-id="c301c-107">Die folgenden Voraussetzungen müssen erfüllt sein, um die Verbindung von Customer Insights zu Azure Synapse zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c301c-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="c301c-108">Stellen Sie sicher, dass Sie alle **Rollenzuweisungen** wie beschrieben festlegen.</span><span class="sxs-lookup"><span data-stu-id="c301c-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="c301c-109">Voraussetzungen in Customer Insights</span><span class="sxs-lookup"><span data-stu-id="c301c-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="c301c-110">Sie verfügen in Zielgruppenerkenntnissenn über die Benutzerrolle **Administrator**.</span><span class="sxs-lookup"><span data-stu-id="c301c-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="c301c-111">Erfahren Sie mehr über das [Festlegen von Benutzerberechtigungen in Zielgruppenerkenntnissen](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="c301c-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="c301c-112">In Azure:</span><span class="sxs-lookup"><span data-stu-id="c301c-112">In Azure:</span></span> 

- <span data-ttu-id="c301c-113">Ein aktives Azure-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="c301c-113">An active Azure subscription.</span></span>

- <span data-ttu-id="c301c-114">Bei Verwendung eines neuen Azure Data Lake Storage Gen2-Konto benötigt der *Dienstprinzipal für Kundenerkenntnisse* die Berechtigungen **Blob Datenmitwirkender**.</span><span class="sxs-lookup"><span data-stu-id="c301c-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="c301c-115">Erfahren Sie mehr über [Verbindung zu einem Azure Data Lake Storage Gen2-Konto mit Azure-Dienstprinzipal für Zielgruppenerkenntnisse](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="c301c-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="c301c-116">Im Data Lake Storage Gen2 **muss der** [hierarchischer Namespace](/azure/storage/blobs/data-lake-storage-namespace) aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="c301c-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="c301c-117">In der Ressourcengruppe, in der sich der Azure Synapse Arbeitsbereich befindet, muss dem *Dienstprinzipal* und der *Benutzer für Erkenntniseinblicke* mindestens **Leseberechtigungen** zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="c301c-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="c301c-118">Weitere Informationen finden Sie unter [Weisen Sie Azure-Rollen über das Azure-Portal zu](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="c301c-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="c301c-119">Der *Benutzer* braucht die Berechtigung **Speicher-Blob-Datenmitwirkender** im Azure Data Lake Storage Gen2-Konto, in dem sich die Daten befinden und die mit dem Azure Synapse Arbeitsplatz verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="c301c-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="c301c-120">Erfahren Sie mehr über [Verwenden des Azure-Portals zum Zuweisen einer Azure-Rolle für den Zugriff auf Blob- und Warteschlangendaten](/azure/storage/common/storage-auth-aad-rbac-portal) und [Berechtigungen für Speicher-Blob Datenmitwirkender](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="c301c-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="c301c-121">Die *[Azure Synapse vom Arbeitsbereich verwaltete Identität](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* benötigt die Berechtigung **Speicher-Blob Datenmitwirkender** im Azure Data Lake Storage Gen2-Konto, in dem sich die Daten befinden und die mit dem Azure Synapse Arbeitsplatz verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="c301c-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="c301c-122">Erfahren Sie mehr zur [Verwendung des Azure Portals zum Zuweisen einer Azure Rolle für den Zugriff auf Blob- und Warteschlangendaten](/azure/storage/common/storage-auth-aad-rbac-portal) und [Speichern von Blob-Daten Mitwirkender-Berechtigungen](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="c301c-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="c301c-123">Im Azure Synapse Arbeitsbereich benötigt der *Dienstprinzipal für Zielgruppenerkenntnisse* die zugewiesene Rolle **Synapse-Administrator**.</span><span class="sxs-lookup"><span data-stu-id="c301c-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="c301c-124">Weitere Informationen finden Sie unter [So richten Sie die Zugriffssteuerung für Ihren Synapse-Arbeitsbereich ein](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="c301c-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="c301c-125">Richten Sie die Verbindung ein und exportieren Sie diese zu Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="c301c-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="c301c-126">Verbindung konfigurieren</span><span class="sxs-lookup"><span data-stu-id="c301c-126">Configure a connection</span></span>

1. <span data-ttu-id="c301c-127">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="c301c-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c301c-128">Wählen Sie **Verbindung hinzufügen** und dann **Azure Synapse Analyse** oder wählen Sie **Einrichten** in der Kachel **Azure Synapse Analyse**, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c301c-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="c301c-129">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld Anzeigename.</span><span class="sxs-lookup"><span data-stu-id="c301c-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="c301c-130">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="c301c-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="c301c-131">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="c301c-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c301c-132">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="c301c-132">Choose who can use this connection.</span></span> <span data-ttu-id="c301c-133">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="c301c-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c301c-134">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c301c-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c301c-135">Wählen Sie das Abonnement aus oder suchen Sie danach, in dem Sie die Customer Insights-Daten verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c301c-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="c301c-136">Sobald ein Abonnement ausgewählt ist, können Sie auch **Arbeitsbereich**, **Speicherkonto**, und **Container** auswählen.</span><span class="sxs-lookup"><span data-stu-id="c301c-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="c301c-137">Klicken Sie auf **Speichern**, um die Verbindung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c301c-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="c301c-138">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="c301c-138">Configure an export</span></span>

<span data-ttu-id="c301c-139">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="c301c-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c301c-140">Weitere Informationen finden Sie unter [zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c301c-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c301c-141">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="c301c-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c301c-142">Um einen neuen Export zu erstellen, wählen Sie **Export hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="c301c-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="c301c-143">Wählen Sie im Feld **Verbindung für den Export** eine Verbindung aus dem Bereich **Azure Synapse Analyse** aus.</span><span class="sxs-lookup"><span data-stu-id="c301c-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="c301c-144">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine [Verbindungen](connections.md) dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c301c-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="c301c-145">Geben Sie einen erkennbaren **Anzeigename** für Ihren Export und einen **Datenbanknamen** ein.</span><span class="sxs-lookup"><span data-stu-id="c301c-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="c301c-146">Wählen Sie aus, in welche Entitäten Sie zu Azure Synapse Analyse exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="c301c-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="c301c-147">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="c301c-147">Select **Save**.</span></span>

<span data-ttu-id="c301c-148">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c301c-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c301c-149">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c301c-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c301c-150">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c301c-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="c301c-151">Aktualisieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="c301c-151">Update an export</span></span>

1. <span data-ttu-id="c301c-152">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="c301c-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c301c-153">Wählen Sie für den Export, den Sie aktualisieren möchten, **bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="c301c-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="c301c-154">**Hinzufügen** oder **Entfernen** von Entitäten aus der Auswahl.</span><span class="sxs-lookup"><span data-stu-id="c301c-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="c301c-155">Wenn Entitäten aus der Auswahl entfernt werden, werden sie nicht aus der Synapse-Analyse-Datenbank gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c301c-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="c301c-156">Zukünftige Datenaktualisierungen aktualisieren jedoch nicht die entfernten Entitäten in dieser Datenbank.</span><span class="sxs-lookup"><span data-stu-id="c301c-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="c301c-157">**Ändern des Datenbanknamens** erstellt eine neue Synapse-Analye-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="c301c-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="c301c-158">Die Datenbank mit dem zuvor konfigurierten Namen erhält bei zukünftigen Aktualisierungen keine Aktualisierungen.</span><span class="sxs-lookup"><span data-stu-id="c301c-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
