---
title: Verwenden Sie Datenquellen zur Datenerfassung
description: Erfahren Sie, wie Daten aus unterschiedlichen Quellen importiert werden.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887893"
---
# <a name="data-sources-overview"></a><span data-ttu-id="f39cb-103">Übersicht über Datenquellen</span><span class="sxs-lookup"><span data-stu-id="f39cb-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="f39cb-104">Die Funktionalität „Zielgruppen-Insights“ in Dynamics 365 Customer Insights verbindet sich mit Daten aus einer breiten Palette von Quellen.</span><span class="sxs-lookup"><span data-stu-id="f39cb-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="f39cb-105">Das Herstellen einer Verbindung zu einem Datenquelle wird häufig als Prozess von *Datenerfassung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f39cb-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="f39cb-106">Nach der Erfassung der Daten können Sie [vereinheitlichen](data-unification.md) und Aktionen durchführen.</span><span class="sxs-lookup"><span data-stu-id="f39cb-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="f39cb-107">Datenquelle hinzufügen</span><span class="sxs-lookup"><span data-stu-id="f39cb-107">Add a data source</span></span>

<span data-ttu-id="f39cb-108">In den ausführlichen Artikeln erfahren Sie, wie Sie ein Datenquelle hinzufügen, je nachdem, welche Option Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="f39cb-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="f39cb-109">Sie können ein Datenquelle auf drei Arten hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="f39cb-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="f39cb-110">Durch Dutzende von Power Query-Connectors</span><span class="sxs-lookup"><span data-stu-id="f39cb-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="f39cb-111">Aus einem Common Data Model-Ordner</span><span class="sxs-lookup"><span data-stu-id="f39cb-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="f39cb-112">Aus Ihrem eigenen Common Data Service-Lake</span><span class="sxs-lookup"><span data-stu-id="f39cb-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="f39cb-113">Fügen Sie Daten aus lokalen Datenquellen hinzu</span><span class="sxs-lookup"><span data-stu-id="f39cb-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="f39cb-114">Das Aufnehmen von Daten aus lokalen Datenquellen in Zielgruppenerkenntnissen wird basierend auf Power Platform Dataflows unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f39cb-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="f39cb-115">Dataflows können in Customer Insights durch [Bereitstellung der Microsoft Dataverse-Umgebungs-URL](manage-environments.md#create-an-environment-in-an-existing-organization) beim Einrichten der Umgebung aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f39cb-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="f39cb-116">Datenquellen, die nach dem Zuordnen einer Dataverse-Umgebung mit Customer Insights erstellt werden, verwenden [Power Platform Dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="f39cb-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="f39cb-117">Dataflows unterstützen die lokale Konnektivität mithilfe der Datengateways.</span><span class="sxs-lookup"><span data-stu-id="f39cb-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="f39cb-118">Entfernen Sie Datenquellen, die vor einer Dataverse-Umgebungszuordnung vorhanden waren, und erstellen Sie sie neu, um Datengateways lokal zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f39cb-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="f39cb-119">Datengateways einer vorhandenen Power BI- oder Power Apps-Umgebung werden sichtbar und Sie können sie in Customer Insights wiederverwenden.</span><span class="sxs-lookup"><span data-stu-id="f39cb-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="f39cb-120">Die Datenquellenseite enthält Links zur Power Platform-Umgebung, in der Sie lokale Datengateways anzeigen und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="f39cb-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Screenshot der Datenquellenseite mit Links, die auf die Power Platform-Umgebung verweisen.":::

## <a name="review-ingested-data"></a><span data-ttu-id="f39cb-122">Eingebundene Daten überprüfen</span><span class="sxs-lookup"><span data-stu-id="f39cb-122">Review ingested data</span></span>

<span data-ttu-id="f39cb-123">Sie sehen den Namen jeder aufgenommenen Datenquelle, ihren Status und das letzte Mal, dass die Daten für diese Quelle aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="f39cb-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="f39cb-124">Sie können die Liste der Datenquellen nach jeder Spalte sortieren.</span><span class="sxs-lookup"><span data-stu-id="f39cb-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f39cb-125">![Datenquelle hinzugefügt](media/configure-data-datasource-added.png "Datenquelle hinzugefügt")</span><span class="sxs-lookup"><span data-stu-id="f39cb-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="f39cb-126">Status</span><span class="sxs-lookup"><span data-stu-id="f39cb-126">Status</span></span>  |<span data-ttu-id="f39cb-127">Beschreibung des Dataflows</span><span class="sxs-lookup"><span data-stu-id="f39cb-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="f39cb-128">Erfolgreich</span><span class="sxs-lookup"><span data-stu-id="f39cb-128">Successful</span></span>   |<span data-ttu-id="f39cb-129">Die Datenquelle wurde erfolgreich aufgenommen, wenn in der Spalte **Aufgefrischt** ein Zeitpunkt genannt wird.</span><span class="sxs-lookup"><span data-stu-id="f39cb-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="f39cb-130">Nicht gestartet</span><span class="sxs-lookup"><span data-stu-id="f39cb-130">Not started</span></span>   |<span data-ttu-id="f39cb-131">Die Datenquelle hat noch keine Datenerfassung oder ist noch im Entwurfsmodus.</span><span class="sxs-lookup"><span data-stu-id="f39cb-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="f39cb-132">Wird aktualisiert</span><span class="sxs-lookup"><span data-stu-id="f39cb-132">Refreshing</span></span>    |<span data-ttu-id="f39cb-133">Die Datenaufnahme ist im Gange.</span><span class="sxs-lookup"><span data-stu-id="f39cb-133">Data ingestion is in progress.</span></span> <span data-ttu-id="f39cb-134">Sie können diesen Vorgang abbrechen, indem Sie **Aktualisierung beenden** in der Spalte **Aktionen** wählen.</span><span class="sxs-lookup"><span data-stu-id="f39cb-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="f39cb-135">Wenn Sie die Aktualisierung einer Datenquelle stoppen, wird der letzte Aktualisierungsstatus wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="f39cb-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="f39cb-136">Fehlerhaft</span><span class="sxs-lookup"><span data-stu-id="f39cb-136">Failed</span></span>     |<span data-ttu-id="f39cb-137">Bei der Dateneingabe sind Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f39cb-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="f39cb-138">Wählen Sie den Wert in der **Status**-Spalte einer beliebigen Datenquelle, um weitere Details zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f39cb-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="f39cb-139">Im **Fortschrittsdetails**-Bereich erweitern Sie **Datenquellen**.</span><span class="sxs-lookup"><span data-stu-id="f39cb-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="f39cb-140">Wählen Sie **Details anzeigen**, um weitere Informationen zum Auffrischungsstatus zu prüfen, einschließlich Fehlerdetails und nachgelagerte Prozessaktualisierungen.</span><span class="sxs-lookup"><span data-stu-id="f39cb-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="f39cb-141">Das Laden von Daten kann einige Zeit dauern.</span><span class="sxs-lookup"><span data-stu-id="f39cb-141">Loading data can take some time.</span></span> <span data-ttu-id="f39cb-142">Nach einer erfolgreichen Aktualisierung können die aufgenommenen Daten von der Seite **Entitäten** überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="f39cb-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="f39cb-143">Weitere Informationen finden Sie unter [Entitäten](entities.md).</span><span class="sxs-lookup"><span data-stu-id="f39cb-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="f39cb-144">Aktualisieren einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="f39cb-144">Refresh a data source</span></span>

<span data-ttu-id="f39cb-145">Datenquellen können nach einem automatischen Zeitplan oder manuell bei Bedarf aufgefrischt werden.</span><span class="sxs-lookup"><span data-stu-id="f39cb-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="f39cb-146">Gehen Sie zu **Admin** > **System** > [**Planen**](system.md#schedule-tab), um geplante Aktualisierungen aller Ihrer aufgenommenen Datenquellen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f39cb-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="f39cb-147">Um eine Datenquelle bei Bedarf zu aktualisieren, folgen Sie diesen Schritten:</span><span class="sxs-lookup"><span data-stu-id="f39cb-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="f39cb-148">Gehen Sie in Zielgruppen-Insights zu **Daten** > **Datenquellen**</span><span class="sxs-lookup"><span data-stu-id="f39cb-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="f39cb-149">Wählen Sie die vertikalen Auslassungspunkte neben der Datenquelle, die Sie aktualisieren möchten, und wählen Sie **Auffrischen** aus der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="f39cb-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="f39cb-150">Die Datenquelle wird jetzt für eine manuelle Aktualisierung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="f39cb-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="f39cb-151">Durch das Aktualisieren eines Datenquelle werden sowohl das Entitätsschema als auch die Daten für alle im Datenquelle angegebenen Entitäten aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="f39cb-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="f39cb-152">Wählen Sie **Auffrischung stoppen**, wenn Sie eine bestehende Auffrischung abbrechen wollen und die Datenquelle in ihren letzten Auffrischungsstatus zurückkehren soll.</span><span class="sxs-lookup"><span data-stu-id="f39cb-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="f39cb-153">Löschen einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="f39cb-153">Delete a data source</span></span>

1. <span data-ttu-id="f39cb-154">Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.</span><span class="sxs-lookup"><span data-stu-id="f39cb-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="f39cb-155">Wählen Sie die vertikalen Auslassungspunkte neben der Datenquelle aus, die Sie entfernen möchten, und wählen Sie **Löschen** aus dem Dropdownmenü aus.</span><span class="sxs-lookup"><span data-stu-id="f39cb-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="f39cb-156">Bestätigen Sie den Löschvorgang.</span><span class="sxs-lookup"><span data-stu-id="f39cb-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
