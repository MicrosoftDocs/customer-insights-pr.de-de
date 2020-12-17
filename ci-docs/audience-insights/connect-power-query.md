---
title: Datenerfassung über einen Power Query Konnektor
description: Connectors für Datenquellen basierend auf Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405774"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="57588-103">Mit einer Power Query-Datenquelle verbinden</span><span class="sxs-lookup"><span data-stu-id="57588-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="57588-104">Power Query bietet eine breite Palette von Connectos zum Erfassen von Daten.</span><span class="sxs-lookup"><span data-stu-id="57588-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="57588-105">Die meisten dieser Connectors werden von Dynamics 365 Customer Insights unterstützt.</span><span class="sxs-lookup"><span data-stu-id="57588-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="57588-106">Das Hinzufügen von Datenquellen basierend auf Power Query-Connectors erfolgt im Allgemeinen gemäß den im nächsten Abschnitt beschriebenen Schritten.</span><span class="sxs-lookup"><span data-stu-id="57588-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="57588-107">Abhängig vom verwendeten Connector sind jedoch unterschiedliche Informationen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="57588-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="57588-108">Weitere Informationen finden Sie in der Dokumentation zu den einzelnen Connectors im [Power Query-Connectorverweis](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="57588-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="57588-109">Erstellen Sie eine neue Datenquelle</span><span class="sxs-lookup"><span data-stu-id="57588-109">Create a new data source</span></span>

1. <span data-ttu-id="57588-110">Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.</span><span class="sxs-lookup"><span data-stu-id="57588-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="57588-111">Wählen Sie **Datenquelle hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="57588-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="57588-112">Wählen Sie die Methode **Daten importieren** und wählen Sie **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57588-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="57588-113">Geben Sie einen **Namen** für die Datenquelle und wählen Sie **Weiter**, um die Datenquelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="57588-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="57588-114">Wählen Sie einen der [verfügbaren Konnektoren](#available-power-query-data-sources) aus.</span><span class="sxs-lookup"><span data-stu-id="57588-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="57588-115">Für dieses Beispiel wählen wir den Connector **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="57588-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="57588-116">Geben Sie die erforderlichen Details für den ausgewählten Connector in das Feld **Verbindungseinstellungen** ein und wählen Sie **Weiter**, um eine Vorschau der Daten zu sehen.</span><span class="sxs-lookup"><span data-stu-id="57588-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="57588-117">Wählen Sie **Daten transformieren** aus.</span><span class="sxs-lookup"><span data-stu-id="57588-117">Select **Transform data**.</span></span> <span data-ttu-id="57588-118">In diesem Schritt fügen Sie Entitäten zu Ihrer Datenquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="57588-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="57588-119">Entitäten sind Datasets.</span><span class="sxs-lookup"><span data-stu-id="57588-119">Entities are datasets.</span></span> <span data-ttu-id="57588-120">Wenn Sie eine Datenbank haben, die mehrere Datensätze enthält, ist jeder Datensatz eine eigene Entität.</span><span class="sxs-lookup"><span data-stu-id="57588-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="57588-121">Im Dialogfeld **Power Query – Abfragen bearbeiten** können Sie die Daten überprüfen und verfeinern.</span><span class="sxs-lookup"><span data-stu-id="57588-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="57588-122">Die Entitäten, die die in Ihrer ausgewählten Datenquelle identifizierten Systeme aufweisen, erscheinen im linken Fensterbereich.</span><span class="sxs-lookup"><span data-stu-id="57588-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="57588-123">![Dialogfeld „Abfragen bearbeiten“](media/data-manager-configure-edit-queries.png "Dialogfeld „Abfragen bearbeiten“")</span><span class="sxs-lookup"><span data-stu-id="57588-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="57588-124">Sie können Ihre Daten auch transformieren.</span><span class="sxs-lookup"><span data-stu-id="57588-124">You can also transform your data.</span></span> <span data-ttu-id="57588-125">Wählen Sie eine Entität zum Bearbeiten oder Transformieren aus.</span><span class="sxs-lookup"><span data-stu-id="57588-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="57588-126">Verwenden Sie die Optionen im Fenster „Power Query“, um Transformationen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="57588-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="57588-127">Jede Transformation wird unter **Angewandte Schritte** aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="57588-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="57588-128">Power Query bietet zahlreiche vorgefertigte Transformationsoptionen.</span><span class="sxs-lookup"><span data-stu-id="57588-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="57588-129">Weitere Informationen finden Sie im Artikel [Power Query-Transformationen](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="57588-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="57588-130">Sie können Ihrer Datenquelle weitere Entitäten hinzufügen, indem Sie im Dialog **Abfragen bearbeiten** **Daten holen** wählen.</span><span class="sxs-lookup"><span data-stu-id="57588-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="57588-131">Diese Transformationen werden dringend empfohlen:</span><span class="sxs-lookup"><span data-stu-id="57588-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="57588-132">Wenn Sie Daten aus einer CSV-Datei erfassen, enthält die erste Zeile häufig Überschriften.</span><span class="sxs-lookup"><span data-stu-id="57588-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="57588-133">Wechseln Sie zu **Tabelle transformieren** aus und danach **Überschriften als erste Zeile verwenden**.</span><span class="sxs-lookup"><span data-stu-id="57588-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="57588-134">Stellen Sie sicher, dass der Datentyp richtig eingestellt ist.</span><span class="sxs-lookup"><span data-stu-id="57588-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="57588-135">Wählen Sie in der rechten unteren Ecke des Fensters „Power Query“ **Speichern** aus, um die Transformationen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="57588-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="57588-136">Nach dem Speichern finden Sie Ihre Datenquelle auf **Daten** > **Datenquellen**.</span><span class="sxs-lookup"><span data-stu-id="57588-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="57588-137">Auf dieser Seite **Datenquellen** werden Sie feststellen, dass sich das neue Datenquelle im Status **Wird aktualisiert** befindet.</span><span class="sxs-lookup"><span data-stu-id="57588-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="57588-138">Verfügbare Power Query-Datenquellen</span><span class="sxs-lookup"><span data-stu-id="57588-138">Available Power Query data sources</span></span>

<span data-ttu-id="57588-139">Eine aktuelle Liste derConnectors, die Sie zum Importieren von Daten in Customer Insights auswählen können, finden Sie unter [Power Query-Connectorverweis](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="57588-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="57588-140">Connectors mit einem Häkchen in der Spalte **Customer Insights (Datenflows)** sind verfügbar, um neue Datenquellen basierend auf Power Query zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="57588-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="57588-141">Lesen Sie die Dokumentation eines bestimmten Connectors, um mehr über seine Voraussetzungen, Einschränkungen und andere Details zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="57588-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="57588-142">Power Query-Datenquellen bearbeiten</span><span class="sxs-lookup"><span data-stu-id="57588-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="57588-143">Es ist möglicherweise nicht möglich, Änderungen an Datenquellen vorzunehmen, die derzeit in einem der Prozesse der App verwendet werden (z. B. *Segmentierung*, *Abgleich* oder *Zusammenführung*).</span><span class="sxs-lookup"><span data-stu-id="57588-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="57588-144">Über die Seite **Einstellungen** können Sie den Fortschritt jedes aktiven Prozesses verfolgen.</span><span class="sxs-lookup"><span data-stu-id="57588-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="57588-145">Wenn ein Prozess abgeschlossen ist, können Sie zur Seite **Datenquellen** zurückkehren und Ihre Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="57588-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="57588-146">Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.</span><span class="sxs-lookup"><span data-stu-id="57588-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="57588-147">Wählen Sie die vertikalen Auslassungspunkte neben der Datenquelle aus, die Sie ändern möchten, und wählen Sie **Bearbeiten** aus dem Dropdownmenü aus.</span><span class="sxs-lookup"><span data-stu-id="57588-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="57588-148">![Optionen bearbeiten](media/edit-option-data-sources.png "Optionen bearbeiten")</span><span class="sxs-lookup"><span data-stu-id="57588-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="57588-149">Übernehmen Sie Ihre Änderungen und Transformationen in das Dialogfeld **Power Query – Abfragen bearbeiten** wie im Abschnitt [Eine neue Datenquelle erstellen](#create-a-new-data-source) beschrieben ein.</span><span class="sxs-lookup"><span data-stu-id="57588-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="57588-150">Wählen Sie in Power Query nach Abschluss Ihrer Änderungen **Speichern** aus, um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="57588-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
