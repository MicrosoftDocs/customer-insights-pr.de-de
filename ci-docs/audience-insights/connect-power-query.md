---
title: Datenerfassung über einen Power Query Konnektor
description: Connectors für Datenquellen basierend auf Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d51a7efa5fd9f7336d1662500eb804a674738493
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267768"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="e4ad5-103">Mit einer Power Query-Datenquelle verbinden</span><span class="sxs-lookup"><span data-stu-id="e4ad5-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="e4ad5-104">Power Query bietet eine breite Palette von Connectos zum Erfassen von Daten.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="e4ad5-105">Die meisten dieser Connectors werden von Dynamics 365 Customer Insights unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="e4ad5-106">Das Hinzufügen von Datenquellen basierend auf Power Query-Connectors erfolgt im Allgemeinen gemäß den im nächsten Abschnitt beschriebenen Schritten.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="e4ad5-107">Abhängig vom verwendeten Connector sind jedoch unterschiedliche Informationen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="e4ad5-108">Weitere Informationen finden Sie in der Dokumentation zu den einzelnen Connectors im [Power Query-Connectorverweis](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="e4ad5-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="e4ad5-109">Erstellen Sie eine neue Datenquelle</span><span class="sxs-lookup"><span data-stu-id="e4ad5-109">Create a new data source</span></span>

1. <span data-ttu-id="e4ad5-110">Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="e4ad5-111">Wählen Sie **Datenquelle hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="e4ad5-112">Wählen Sie die Methode **Daten importieren** und wählen Sie **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="e4ad5-113">Geben Sie einen **Namen** für die Datenquelle und wählen Sie **Weiter**, um die Datenquelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="e4ad5-114">Namensrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="e4ad5-114">Name guidelines:</span></span> 
   - <span data-ttu-id="e4ad5-115">Beginnen Sie mit einem Buchstaben.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-115">Start with a letter.</span></span>
   - <span data-ttu-id="e4ad5-116">Verwenden Sie nur Buchstaben und Zahlen.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-116">Use letters and numbers only.</span></span> <span data-ttu-id="e4ad5-117">Leerzeichen und Sonderzeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="e4ad5-118">Verwenden Sie zwischen 3 und 64 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="e4ad5-119">Wählen Sie einen der [verfügbaren Konnektoren](#available-power-query-data-sources) aus.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="e4ad5-120">Für dieses Beispiel wählen wir den Connector **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="e4ad5-121">Geben Sie die erforderlichen Details für den ausgewählten Connector in das Feld **Verbindungseinstellungen** ein und wählen Sie **Weiter**, um eine Vorschau der Daten zu sehen.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="e4ad5-122">Wählen Sie **Daten transformieren** aus.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-122">Select **Transform data**.</span></span> <span data-ttu-id="e4ad5-123">In diesem Schritt fügen Sie Entitäten zu Ihrer Datenquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="e4ad5-124">Entitäten sind Datasets.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-124">Entities are datasets.</span></span> <span data-ttu-id="e4ad5-125">Wenn Sie eine Datenbank haben, die mehrere Datensätze enthält, ist jeder Datensatz eine eigene Entität.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="e4ad5-126">Im Dialogfeld **Power Query – Abfragen bearbeiten** können Sie die Daten überprüfen und verfeinern.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="e4ad5-127">Die Entitäten, die die in Ihrer ausgewählten Datenquelle identifizierten Systeme aufweisen, erscheinen im linken Fensterbereich.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e4ad5-128">![Dialogfeld „Abfragen bearbeiten“](media/data-manager-configure-edit-queries.png "Dialogfeld „Abfragen bearbeiten“")</span><span class="sxs-lookup"><span data-stu-id="e4ad5-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="e4ad5-129">Sie können Ihre Daten auch transformieren.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-129">You can also transform your data.</span></span> <span data-ttu-id="e4ad5-130">Wählen Sie eine Entität zum Bearbeiten oder Transformieren aus.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="e4ad5-131">Verwenden Sie die Optionen im Fenster „Power Query“, um Transformationen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="e4ad5-132">Jede Transformation wird unter **Angewandte Schritte** aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="e4ad5-133">Power Query bietet zahlreiche vorgefertigte Transformationsoptionen.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="e4ad5-134">Weitere Informationen finden Sie im Artikel [Power Query-Transformationen](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="e4ad5-134">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="e4ad5-135">Sie können Ihrer Datenquelle weitere Entitäten hinzufügen, indem Sie im Dialog **Abfragen bearbeiten** **Daten holen** wählen.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="e4ad5-136">Diese Transformationen werden dringend empfohlen:</span><span class="sxs-lookup"><span data-stu-id="e4ad5-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="e4ad5-137">Wenn Sie Daten aus einer CSV-Datei erfassen, enthält die erste Zeile häufig Überschriften.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="e4ad5-138">Wechseln Sie zu **Tabelle transformieren** aus und danach **Überschriften als erste Zeile verwenden**.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="e4ad5-139">Stellen Sie sicher, dass der Datentyp richtig eingestellt ist.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="e4ad5-140">Wählen Sie in der rechten unteren Ecke des Fensters „Power Query“ **Speichern** aus, um die Transformationen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="e4ad5-141">Nach dem Speichern finden Sie Ihre Datenquelle auf **Daten** > **Datenquellen**.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="e4ad5-142">Auf dieser Seite **Datenquellen** werden Sie feststellen, dass sich das neue Datenquelle im Status **Wird aktualisiert** befindet.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="e4ad5-143">Verfügbare Power Query-Datenquellen</span><span class="sxs-lookup"><span data-stu-id="e4ad5-143">Available Power Query data sources</span></span>

<span data-ttu-id="e4ad5-144">Eine aktuelle Liste derConnectors, die Sie zum Importieren von Daten in Customer Insights auswählen können, finden Sie unter [Power Query-Connectorverweis](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="e4ad5-144">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="e4ad5-145">Connectors mit einem Häkchen in der Spalte **Customer Insights (Datenflows)** sind verfügbar, um neue Datenquellen basierend auf Power Query zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="e4ad5-146">Lesen Sie die Dokumentation eines bestimmten Connectors, um mehr über seine Voraussetzungen, Einschränkungen und andere Details zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="e4ad5-147">Power Query-Datenquellen bearbeiten</span><span class="sxs-lookup"><span data-stu-id="e4ad5-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="e4ad5-148">Es ist möglicherweise nicht möglich, Änderungen an Datenquellen vorzunehmen, die derzeit in einem der Prozesse der App verwendet werden (z. B. *Segmentierung*, *Abgleich* oder *Zusammenführung*).</span><span class="sxs-lookup"><span data-stu-id="e4ad5-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="e4ad5-149">Über die Seite **Einstellungen** können Sie den Fortschritt jedes aktiven Prozesses verfolgen.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="e4ad5-150">Wenn ein Prozess abgeschlossen ist, können Sie zur Seite **Datenquellen** zurückkehren und Ihre Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="e4ad5-151">Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="e4ad5-152">Wählen Sie die vertikalen Auslassungspunkte neben der Datenquelle aus, die Sie ändern möchten, und wählen Sie **Bearbeiten** aus dem Dropdownmenü aus.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e4ad5-153">![Optionen bearbeiten](media/edit-option-data-sources.png "Optionen bearbeiten")</span><span class="sxs-lookup"><span data-stu-id="e4ad5-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="e4ad5-154">Übernehmen Sie Ihre Änderungen und Transformationen in das Dialogfeld **Power Query – Abfragen bearbeiten** wie im Abschnitt [Eine neue Datenquelle erstellen](#create-a-new-data-source) beschrieben ein.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="e4ad5-155">Wählen Sie in Power Query nach Abschluss Ihrer Änderungen **Speichern** aus, um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e4ad5-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]