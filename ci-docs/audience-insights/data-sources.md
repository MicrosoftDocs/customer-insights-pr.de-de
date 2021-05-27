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
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085529"
---
# <a name="data-sources-overview"></a><span data-ttu-id="d0353-103">Übersicht über Datenquellen</span><span class="sxs-lookup"><span data-stu-id="d0353-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="d0353-104">Die Funktionalität „Zielgruppen-Insights“ in Dynamics 365 Customer Insights verbindet sich mit Daten aus einer breiten Palette von Quellen.</span><span class="sxs-lookup"><span data-stu-id="d0353-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="d0353-105">Das Herstellen einer Verbindung zu einem Datenquelle wird häufig als Prozess von *Datenerfassung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d0353-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="d0353-106">Nach der Erfassung der Daten können Sie [vereinheitlichen](data-unification.md) und Aktionen durchführen.</span><span class="sxs-lookup"><span data-stu-id="d0353-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="d0353-107">Datenquelle hinzufügen</span><span class="sxs-lookup"><span data-stu-id="d0353-107">Add a data source</span></span>

<span data-ttu-id="d0353-108">In den ausführlichen Artikeln erfahren Sie, wie Sie ein Datenquelle hinzufügen, je nachdem, welche Option Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="d0353-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="d0353-109">Sie können ein Datenquelle auf drei Arten hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="d0353-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="d0353-110">Durch Dutzende von Power Query-Connectors</span><span class="sxs-lookup"><span data-stu-id="d0353-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="d0353-111">Aus einem Common Data Model-Ordner</span><span class="sxs-lookup"><span data-stu-id="d0353-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="d0353-112">Aus Ihrem eigenen Common Data Service-Lake</span><span class="sxs-lookup"><span data-stu-id="d0353-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="d0353-113">Fügen Sie Daten aus lokalen Datenquellen hinzu</span><span class="sxs-lookup"><span data-stu-id="d0353-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="d0353-114">Das Aufnehmen von Daten aus lokalen Datenquellen in Zielgruppenerkenntnissen wird basierend auf Power Platform Dataflows unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d0353-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="d0353-115">Dataflows können in Customer Insights durch [Bereitstellung der Microsoft Dataverse-Umgebungs-URL](manage-environments.md#create-an-environment-in-an-existing-organization) beim Einrichten der Umgebung aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="d0353-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="d0353-116">Datenquellen, die nach dem Zuordnen einer Dataverse-Umgebung mit Customer Insights erstellt werden, verwenden [Power Platform Dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="d0353-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="d0353-117">Dataflows unterstützen die lokale Konnektivität mithilfe des Datengateways.</span><span class="sxs-lookup"><span data-stu-id="d0353-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="d0353-118">Entfernen Sie Datenquellen, die vor einer Dataverse Umgebungszuordnung vorhanden waren, und erstellen Sie sie neu, um [Datengateways lokal zu verwenden](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span><span class="sxs-lookup"><span data-stu-id="d0353-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span></span>

<span data-ttu-id="d0353-119">Datengateways einer vorhandenen Power BI- oder Power Apps-Umgebung werden sichtbar und Sie können sie in Customer Insights wiederverwenden.</span><span class="sxs-lookup"><span data-stu-id="d0353-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="d0353-120">Die Datenquellenseite enthält Links zur Power Platform-Umgebung, in der Sie lokale Datengateways anzeigen und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="d0353-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="d0353-121">Eingebundene Daten überprüfen</span><span class="sxs-lookup"><span data-stu-id="d0353-121">Review ingested data</span></span>

<span data-ttu-id="d0353-122">Sie sehen den Namen jeder aufgenommenen Datenquelle, ihren Status und das letzte Mal, dass die Daten für diese Quelle aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="d0353-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="d0353-123">Sie können die Liste der Datenquellen nach jeder Spalte sortieren.</span><span class="sxs-lookup"><span data-stu-id="d0353-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d0353-124">![Datenquelle hinzugefügt](media/configure-data-datasource-added.png "Datenquelle hinzugefügt")</span><span class="sxs-lookup"><span data-stu-id="d0353-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="d0353-125">Status</span><span class="sxs-lookup"><span data-stu-id="d0353-125">Status</span></span>  |<span data-ttu-id="d0353-126">Beschreibung des Dataflows</span><span class="sxs-lookup"><span data-stu-id="d0353-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="d0353-127">Erfolgreich</span><span class="sxs-lookup"><span data-stu-id="d0353-127">Successful</span></span>   |<span data-ttu-id="d0353-128">Die Datenquelle wurde erfolgreich aufgenommen, wenn in der Spalte **Aufgefrischt** ein Zeitpunkt genannt wird.</span><span class="sxs-lookup"><span data-stu-id="d0353-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="d0353-129">Nicht gestartet</span><span class="sxs-lookup"><span data-stu-id="d0353-129">Not started</span></span>   |<span data-ttu-id="d0353-130">Die Datenquelle hat noch keine Datenerfassung oder ist noch im Entwurfsmodus.</span><span class="sxs-lookup"><span data-stu-id="d0353-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="d0353-131">Wird aktualisiert</span><span class="sxs-lookup"><span data-stu-id="d0353-131">Refreshing</span></span>    |<span data-ttu-id="d0353-132">Die Datenaufnahme ist im Gange.</span><span class="sxs-lookup"><span data-stu-id="d0353-132">Data ingestion is in progress.</span></span> <span data-ttu-id="d0353-133">Sie können diesen Vorgang abbrechen, indem Sie **Aktualisierung beenden** in der Spalte **Aktionen** wählen.</span><span class="sxs-lookup"><span data-stu-id="d0353-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="d0353-134">Wenn Sie die Aktualisierung einer Datenquelle stoppen, wird der letzte Aktualisierungsstatus wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="d0353-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="d0353-135">Fehlerhaft</span><span class="sxs-lookup"><span data-stu-id="d0353-135">Failed</span></span>     |<span data-ttu-id="d0353-136">Bei der Dateneingabe sind Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d0353-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="d0353-137">Wählen Sie den Wert in der **Status**-Spalte einer beliebigen Datenquelle, um weitere Details zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d0353-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="d0353-138">Im **Fortschrittsdetails**-Bereich erweitern Sie **Datenquellen**.</span><span class="sxs-lookup"><span data-stu-id="d0353-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="d0353-139">Wählen Sie **Details anzeigen**, um weitere Informationen zum Auffrischungsstatus zu prüfen, einschließlich Fehlerdetails und nachgelagerte Prozessaktualisierungen.</span><span class="sxs-lookup"><span data-stu-id="d0353-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="d0353-140">Das Laden von Daten kann einige Zeit dauern.</span><span class="sxs-lookup"><span data-stu-id="d0353-140">Loading data can take some time.</span></span> <span data-ttu-id="d0353-141">Nach einer erfolgreichen Aktualisierung können die aufgenommenen Daten von der Seite **Entitäten** überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="d0353-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="d0353-142">Weitere Informationen finden Sie unter [Entitäten](entities.md).</span><span class="sxs-lookup"><span data-stu-id="d0353-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="d0353-143">Aktualisieren einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="d0353-143">Refresh a data source</span></span>

<span data-ttu-id="d0353-144">Datenquellen können nach einem automatischen Zeitplan oder manuell bei Bedarf aufgefrischt werden.</span><span class="sxs-lookup"><span data-stu-id="d0353-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="d0353-145">Gehen Sie zu **Admin** > **System** > [**Planen**](system.md#schedule-tab), um geplante Aktualisierungen aller Ihrer aufgenommenen Datenquellen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d0353-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="d0353-146">Um eine Datenquelle bei Bedarf zu aktualisieren, folgen Sie diesen Schritten:</span><span class="sxs-lookup"><span data-stu-id="d0353-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="d0353-147">Gehen Sie in Zielgruppen-Insights zu **Daten** > **Datenquellen**</span><span class="sxs-lookup"><span data-stu-id="d0353-147">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="d0353-148">Wählen Sie die vertikalen Auslassungspunkte neben der Datenquelle, die Sie aktualisieren möchten, und wählen Sie **Auffrischen** aus der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="d0353-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="d0353-149">Die Datenquelle wird jetzt für eine manuelle Aktualisierung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d0353-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="d0353-150">Durch das Aktualisieren eines Datenquelle werden sowohl das Entitätsschema als auch die Daten für alle im Datenquelle angegebenen Entitäten aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="d0353-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="d0353-151">Wählen Sie **Auffrischung stoppen**, wenn Sie eine bestehende Auffrischung abbrechen wollen und die Datenquelle in ihren letzten Auffrischungsstatus zurückkehren soll.</span><span class="sxs-lookup"><span data-stu-id="d0353-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="d0353-152">Löschen einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="d0353-152">Delete a data source</span></span>

1. <span data-ttu-id="d0353-153">Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.</span><span class="sxs-lookup"><span data-stu-id="d0353-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="d0353-154">Wählen Sie die vertikalen Auslassungspunkte neben der Datenquelle aus, die Sie entfernen möchten, und wählen Sie **Löschen** aus dem Dropdownmenü aus.</span><span class="sxs-lookup"><span data-stu-id="d0353-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="d0353-155">Bestätigen Sie den Löschvorgang.</span><span class="sxs-lookup"><span data-stu-id="d0353-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
