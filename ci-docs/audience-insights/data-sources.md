---
title: Verwenden Sie Datenquellen zur Datenerfassung
description: Erfahren Sie, wie Daten aus unterschiedlichen Quellen importiert werden.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643952"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="48619-103">Übersicht über Datenquellen</span><span class="sxs-lookup"><span data-stu-id="48619-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="48619-104">Die Funktionalität „Zielgruppen-Insights“ in Dynamics 365 Customer Insights verbindet sich mit Daten aus einer breiten Palette von Quellen.</span><span class="sxs-lookup"><span data-stu-id="48619-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="48619-105">Das Herstellen einer Verbindung zu einem Datenquelle wird häufig als Prozess von *Datenerfassung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="48619-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="48619-106">Nach der Erfassung der Daten können Sie [vereinheitlichen](data-unification.md) und Aktionen durchführen.</span><span class="sxs-lookup"><span data-stu-id="48619-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="48619-107">Datenquelle hinzufügen</span><span class="sxs-lookup"><span data-stu-id="48619-107">Add a data source</span></span>

<span data-ttu-id="48619-108">In den ausführlichen Artikeln erfahren Sie, wie Sie ein Datenquelle hinzufügen, je nachdem, welche Option Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="48619-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="48619-109">Sie können ein Datenquelle auf drei Arten hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="48619-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="48619-110">Durch Dutzende von Power Query-Connectors</span><span class="sxs-lookup"><span data-stu-id="48619-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="48619-111">Aus einem Common Data Model-Ordner</span><span class="sxs-lookup"><span data-stu-id="48619-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="48619-112">Aus Ihrem eigenen Common Data Service-Lake</span><span class="sxs-lookup"><span data-stu-id="48619-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="48619-113">Sie können noch keine Daten aus lokalen Datenquellen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="48619-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="48619-114">Eingebundene Daten überprüfen</span><span class="sxs-lookup"><span data-stu-id="48619-114">Review ingested data</span></span>

<span data-ttu-id="48619-115">Sie sehen den Namen jeder aufgenommenen Datenquelle, ihren Status und das letzte Mal, dass die Daten für diese Quelle aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="48619-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="48619-116">Sie können die Liste der Datenquellen nach jeder Spalte sortieren.</span><span class="sxs-lookup"><span data-stu-id="48619-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="48619-117">![Datenquelle hinzugefügt](media/configure-data-datasource-added.png "Datenquelle hinzugefügt")</span><span class="sxs-lookup"><span data-stu-id="48619-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="48619-118">Status</span><span class="sxs-lookup"><span data-stu-id="48619-118">Status</span></span>  |<span data-ttu-id="48619-119">Beschreibung des Dataflows</span><span class="sxs-lookup"><span data-stu-id="48619-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="48619-120">Erfolgreich</span><span class="sxs-lookup"><span data-stu-id="48619-120">Successful</span></span>   |<span data-ttu-id="48619-121">Die Datenquelle wurde erfolgreich aufgenommen, wenn in der Spalte **Aufgefrischt** ein Zeitpunkt genannt wird.</span><span class="sxs-lookup"><span data-stu-id="48619-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="48619-122">Nicht gestartet</span><span class="sxs-lookup"><span data-stu-id="48619-122">Not started</span></span>   |<span data-ttu-id="48619-123">Die Datenquelle hat noch keine Datenerfassung oder ist noch im Entwurfsmodus.</span><span class="sxs-lookup"><span data-stu-id="48619-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="48619-124">Wird aktualisiert</span><span class="sxs-lookup"><span data-stu-id="48619-124">Refreshing</span></span>    |<span data-ttu-id="48619-125">Die Datenaufnahme ist im Gange.</span><span class="sxs-lookup"><span data-stu-id="48619-125">Data ingestion is in progress.</span></span> <span data-ttu-id="48619-126">Sie können diesen Vorgang abbrechen, indem Sie **Aktualisierung beenden** in der Spalte **Aktionen** wählen.</span><span class="sxs-lookup"><span data-stu-id="48619-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="48619-127">Wenn Sie die Aktualisierung einer Datenquelle stoppen, wird diese in ihren letzten Aktualisierungszustand zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="48619-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="48619-128">Fehlerhaft</span><span class="sxs-lookup"><span data-stu-id="48619-128">Failed</span></span>     |<span data-ttu-id="48619-129">Bei der Dateneingabe sind Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="48619-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="48619-130">Wählen Sie **Auffrischungsstatus**, um weitere Details zum Auffrischungsstatus zu prüfen, einschließlich Fehlerdetails und nachgelagerte Prozessaktualisierungen.</span><span class="sxs-lookup"><span data-stu-id="48619-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="48619-131">Das Laden von Daten kann einige Zeit dauern.</span><span class="sxs-lookup"><span data-stu-id="48619-131">Loading data can take some time.</span></span> <span data-ttu-id="48619-132">Nach einer erfolgreichen Aktualisierung können die aufgenommenen Daten von der Seite **Entitäten** überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="48619-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="48619-133">Weitere Informationen finden Sie unter [Entitäten](entities.md).</span><span class="sxs-lookup"><span data-stu-id="48619-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="48619-134">Aktualisieren einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="48619-134">Refresh a data source</span></span>

<span data-ttu-id="48619-135">Datenquellen können nach einem automatischen Zeitplan oder manuell bei Bedarf aufgefrischt werden.</span><span class="sxs-lookup"><span data-stu-id="48619-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="48619-136">Gehen Sie zu **Admin** > **System** > [**Planen**](system.md#schedule-tab), um geplante Aktualisierungen aller Ihrer aufgenommenen Datenquellen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="48619-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="48619-137">Um eine Datenquelle bei Bedarf zu aktualisieren, folgen Sie diesen Schritten:</span><span class="sxs-lookup"><span data-stu-id="48619-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="48619-138">Gehen Sie in Zielgruppen-Insights zu **Daten** > **Datenquellen**</span><span class="sxs-lookup"><span data-stu-id="48619-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="48619-139">Wählen Sie die vertikalen Auslassungspunkte neben der Datenquelle, die Sie aktualisieren möchten, und wählen Sie **Auffrischen** aus der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="48619-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="48619-140">Die Datenquelle wird jetzt für eine manuelle Aktualisierung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="48619-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="48619-141">Das Aktualisieren einer Datenquelle aktualisiert sowohl das Entitätsschema als auch die Daten für alle Entitäten, die in der Datenquelle angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="48619-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="48619-142">Wählen Sie **Auffrischung stoppen**, wenn Sie eine bestehende Auffrischung abbrechen wollen und die Datenquelle in ihren letzten Auffrischungsstatus zurückkehren soll.</span><span class="sxs-lookup"><span data-stu-id="48619-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="48619-143">Löschen einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="48619-143">Delete a data source</span></span>

1. <span data-ttu-id="48619-144">Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.</span><span class="sxs-lookup"><span data-stu-id="48619-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="48619-145">Wählen Sie die vertikalen Auslassungspunkte neben der Datenquelle aus, die Sie entfernen möchten, und wählen Sie **Löschen** aus dem Dropdownmenü aus.</span><span class="sxs-lookup"><span data-stu-id="48619-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="48619-146">Bestätigen Sie den Löschvorgang.</span><span class="sxs-lookup"><span data-stu-id="48619-146">Confirm your deletion.</span></span>
