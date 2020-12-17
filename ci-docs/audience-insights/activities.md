---
title: Kundenaktivitäten
description: Definieren Sie Kundenaktivitäten und zeigen Sie diese in der Kundenzeitleiste an.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667228"
---
# <a name="customer-activities"></a><span data-ttu-id="3d2f8-103">Kundenaktivitäten</span><span class="sxs-lookup"><span data-stu-id="3d2f8-103">Customer activities</span></span>

<span data-ttu-id="3d2f8-104">Kombinieren Sie Kundenaktivitäten aus [verschiedenen Datenquellen](data-sources.md) in Dynamics 365 Customer Insights, um eine Kunden-Zeitleiste zu erstellen, die die Aktivitäten in chronologischer Reihenfolge auflistet.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="3d2f8-105">Sie können die Zeitleiste in Customer Engagement Apps in Dynamics 365 über [Kundenkarten-Add-In](customer-card-add-in.md)oder in einem Power BI Dashboard integrieren.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="3d2f8-106">Definieren Sie eine Aktivität</span><span class="sxs-lookup"><span data-stu-id="3d2f8-106">Define an activity</span></span>

<span data-ttu-id="3d2f8-107">Ihre Datenquellen umfassen Entitäten mit Transaktions- und Aktivitätsdaten aus mehreren Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="3d2f8-108">Identifizieren Sie diese Einheiten und wählen Sie die Aktivitäten aus, die Sie auf der Zeitachse des Kunden anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="3d2f8-109">Wählen Sie die Entität, die Ihre Zielaktivität oder -aktivitäten enthält.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="3d2f8-110">Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Aktivitäten**.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="3d2f8-111">Wählen Sie **Aktivität hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3d2f8-112">Eine Entität muss mindestens ein Attribut vom Typ **Datum** haben, um in eine Kundenzeitachse aufgenommen zu werden, und Sie können keine Entitäten ohne **Datum** Felder hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="3d2f8-113">Die Kontrolle **Aktivität hinzufügen** ist deaktiviert, wenn keine solche Entität gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="3d2f8-114">Legen Sie im Bereich **Aktivität hinzufügen** die Werte für die folgenden Felder fest:</span><span class="sxs-lookup"><span data-stu-id="3d2f8-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="3d2f8-115">**Entität**: Wählen Sie eine Entität, die Transaktions- oder Aktivitätsdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="3d2f8-116">**Primärschlüssel**: Wählen Sie das Feld, das einen Datensatz eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="3d2f8-117">Sie sollte keine doppelten Werte, leere Werte oder fehlende Werte enthalten.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="3d2f8-118">**Zeitstempel**: Wählen Sie das Feld, das die Startzeit Ihrer Aktivität darstellt.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="3d2f8-119">**Ereignis**: Wählen Sie das Feld aus, das das Ereignis für die Aktivität ist.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="3d2f8-120">**Internetadresse**: Wählen Sie das Feld, das eine URL darstellt, die zusätzliche Informationen zu dieser Aktivität liefert.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="3d2f8-121">Zum Beispiel das Transaktionssystem, aus dem diese Aktivität stammt.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="3d2f8-122">Diese URL kann ein beliebiges Feld aus der Datenquelle sein, oder sie kann mit Hilfe einer Power-Query-Transformation als neues Feld konstruiert werden.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="3d2f8-123">Diese URL-Daten werden in der Entität Unified Activity gespeichert, die stromabwärts über APIs konsumiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="3d2f8-124">**Details**: Wählen Sie optional das Feld, das für zusätzliche Details hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="3d2f8-125">**Symbol**: Wählen Sie optional das Symbol, das diese Aktivität repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="3d2f8-126">**Aktivitätstyp**: Definieren Sie den Aktivitätstyp-Verweis auf das Common Data Model, der die semantische Definition der Aktivität am besten beschreibt.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="3d2f8-127">Konfigurieren Sie im Abschnitt **Beziehung einrichten** die Details, die zum Verbinden Ihrer Aktivitätsdaten mit dem entsprechenden Kunden verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3d2f8-128">![Definieren der Entitätsbeziehung](media/activities-entities-define.png "Definieren Sie die Entitätsbeziehung")</span><span class="sxs-lookup"><span data-stu-id="3d2f8-128">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

    - <span data-ttu-id="3d2f8-129">**Aktivitätsentitätsfeld**: Wählen Sie das Feld in Ihrer Aktivitätsentität aus, das zum Herstellen einer Beziehung mit einer anderen Entität verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-129">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="3d2f8-130">**Kundenentität**: Wählen Sie die entsprechende Quellkundenentität aus, mit der Ihre Aktivitätsentität in Beziehung steht.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-130">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="3d2f8-131">Sie können sich nur auf die Quellkundenentitäten beziehen, die im Datenvereinigungsprozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-131">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="3d2f8-132">**Kundenentitätsfeld**: In diesem Feld wird der im Map-Prozess ausgewählte Primärschlüssel der Quellkundenentität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-132">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="3d2f8-133">Dieses Primärschlüsselfeld in der Quellkundenentität wird verwendet, um eine Beziehung zur Aktivitätsentität herzustellen.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-133">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="3d2f8-134">**Name**: Wenn bereits eine Beziehung zwischen dieser Aktivitätsentität und der ausgewählten Quellkundenentität besteht, ist der Beziehungsname schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-134">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="3d2f8-135">Wenn keine solche Beziehung besteht, wird eine neue Beziehung mit dem hier angegebenen Namen erstellt.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-135">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>

1. <span data-ttu-id="3d2f8-136">Wählen Sie **Speichern**, um Ihre Änderungen zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="3d2f8-137">Auf der Seite **Aktivitäten** wählen Sie **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="3d2f8-138">Es gibt [sechs Arten von Status](system.md#status-types) für Aufgaben/Prozesse.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="3d2f8-139">Darüber hinaus [hängen die meisten Prozesse von anderen nachfolgenden Prozessen ab](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="3d2f8-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="3d2f8-140">Sie können den Status eines Prozesses auswählen, um Details zum Fortschritt des gesamten Auftrags anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="3d2f8-141">Nach der Auswahl von **Siehe Details** für eine der Aufgaben des Auftrags finden Sie zusätzliche Informationen: Verarbeitungszeit, das letzte Verarbeitungsdatum sowie alle mit der Aufgabe verbundenen Fehler und Warnungen.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="3d2f8-142">Eine Aktivität bearbeiten</span><span class="sxs-lookup"><span data-stu-id="3d2f8-142">Edit an activity</span></span>

1. <span data-ttu-id="3d2f8-143">Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Aktivitäten**.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="3d2f8-144">Wählen Sie die Aktivitätsentität aus, die Sie bearbeiten möchten, und wählen Sie **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="3d2f8-145">Sie können auch die Maus über die Entitätszeile bewegen und das Symbol **Bearbeiten** auswählen.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="3d2f8-146">Klicken Sie auf das Symbol **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="3d2f8-147">Aktualisieren Sie im Fensterbereich **Aktivität bearbeiten** die Werte und wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="3d2f8-148">Auf der Seite **Aktivitäten** wählen Sie **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="3d2f8-149">Löschen einer Aktivität</span><span class="sxs-lookup"><span data-stu-id="3d2f8-149">Delete an activity</span></span>

1. <span data-ttu-id="3d2f8-150">Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Aktivitäten**.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="3d2f8-151">Wählen Sie die Aktivitätsentität aus, die Sie entfernen möchten, und wählen Sie **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="3d2f8-152">Sie können auch die Maus über die Entitätszeile bewegen und das Symbol **Löschen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="3d2f8-153">Darüber hinaus können Sie mehrere Aktivitätsentitäten auswählen, die gleichzeitig gelöscht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3d2f8-154">![Bearbeiten oder Löschen der Entitätsbeziehung](media/activities-entities-edit-delete.png "Bearbeiten oder Löschen der Entitätsbeziehung")</span><span class="sxs-lookup"><span data-stu-id="3d2f8-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="3d2f8-155">Wählen Sie das Symbol **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="3d2f8-156">Bestätigen Sie den Löschvorgang.</span><span class="sxs-lookup"><span data-stu-id="3d2f8-156">Confirm your deletion.</span></span>
