---
title: Segmente erstellen und verwalten
description: Erstellen Sie Kundensegmente, um sie auf der Grundlage verschiedener Attribute zu gruppieren.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: a1308f07ac3ba7d4b09931bab3d19b6dfaf479ee
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270355"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="2aaae-103">Segmente erstellen und verwalten</span><span class="sxs-lookup"><span data-stu-id="2aaae-103">Create and manage segments</span></span>

<span data-ttu-id="2aaae-104">Mit Segmenten können Sie Ihre Kunden anhand von demografischen, transaktionalen oder verhaltensbezogenen Attributen gruppieren.</span><span class="sxs-lookup"><span data-stu-id="2aaae-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="2aaae-105">Sie können Segmente verwenden, um Werbekampagnen, Vertriebsaktivitäten und Kundensupportaktionen gezielt auf die Erreichung Ihrer Geschäftsziele auszurichten.</span><span class="sxs-lookup"><span data-stu-id="2aaae-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="2aaae-106">Sie können komplexe Filter um die Entität Kundenprofil und die damit verbundenen Entitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="2aaae-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="2aaae-107">Jedes Segment erstellt nach der Verarbeitung eine Reihe von Kundendatensätzen, die Sie exportieren und für die Sie Maßnahmen ergreifen können.</span><span class="sxs-lookup"><span data-stu-id="2aaae-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="2aaae-108">Es gelten einige [Serviceeinschränkungen](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="2aaae-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="2aaae-109">Wenn nicht anders angegeben, handelt es sich bei allen Segmenten um **Dynamische Segmente**, die in einem wiederkehrenden Zeitplan aufgefrischt werden.</span><span class="sxs-lookup"><span data-stu-id="2aaae-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="2aaae-110">Das folgende Beispiel veranschaulicht die Funktionalität der Segmentierung.</span><span class="sxs-lookup"><span data-stu-id="2aaae-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="2aaae-111">Wir haben ein Segment für Kunden definiert, die in den letzten 90 Tagen Waren im Wert von mindestens 500 US-Dollar bestellt haben *und* die an einem Kundenserviceanruf beteiligt waren, der eskaliert wurde.</span><span class="sxs-lookup"><span data-stu-id="2aaae-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2aaae-112">![Mehrere Gruppen](media/segmentation-group1-2.png "Mehrere Gruppen")</span><span class="sxs-lookup"><span data-stu-id="2aaae-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="2aaae-113">Ein neues Segment erstellen</span><span class="sxs-lookup"><span data-stu-id="2aaae-113">Create a new segment</span></span>

<span data-ttu-id="2aaae-114">Segmente werden auf der Seite **Segmente** verwaltet.</span><span class="sxs-lookup"><span data-stu-id="2aaae-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="2aaae-115">Gehen Sie in den Zielgruppen-Insights auf die Seite **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="2aaae-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="2aaae-116">Wählen Sie **Neu** > **Leeres Segment** aus.</span><span class="sxs-lookup"><span data-stu-id="2aaae-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="2aaae-117">Wählen Sie im Bereich **Neues Segment** einen Segmenttyp und geben Sie **Name** ein.</span><span class="sxs-lookup"><span data-stu-id="2aaae-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="2aaae-118">Geben Sie optional einen Anzeigenamen und eine Beschreibung an, die die Identifizierung des Segments erleichtert.</span><span class="sxs-lookup"><span data-stu-id="2aaae-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="2aaae-119">Wählen Sie **Weiter**, um zu der Seite **Segment-Builder** zu gelangen, auf der Sie eine Gruppe definieren.</span><span class="sxs-lookup"><span data-stu-id="2aaae-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="2aaae-120">Eine Gruppe ist eine Gruppe von Kunden.</span><span class="sxs-lookup"><span data-stu-id="2aaae-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="2aaae-121">Wählen Sie die Entität, die das Attribut enthält, nach dem Sie segmentieren möchten.</span><span class="sxs-lookup"><span data-stu-id="2aaae-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="2aaae-122">Wählen Sie das Attribut aus, nach dem segmentiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="2aaae-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="2aaae-123">Dieses Attribut kann einen von vier Werttypen haben: numerisch, Zeichenfolge, Datum oder boolesch.</span><span class="sxs-lookup"><span data-stu-id="2aaae-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="2aaae-124">Wählen Sie einen Operator und einen Wert für das ausgewählte Attribut.</span><span class="sxs-lookup"><span data-stu-id="2aaae-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2aaae-125">![Benutzerdefinierter Gruppenfilter](media/customer-group-numbers.png "Kundengruppen-Filter")</span><span class="sxs-lookup"><span data-stu-id="2aaae-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="2aaae-126">Anzahl</span><span class="sxs-lookup"><span data-stu-id="2aaae-126">Number</span></span> |<span data-ttu-id="2aaae-127">Definition</span><span class="sxs-lookup"><span data-stu-id="2aaae-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="2aaae-128">1</span><span class="sxs-lookup"><span data-stu-id="2aaae-128">1</span></span>     |<span data-ttu-id="2aaae-129">Entity</span><span class="sxs-lookup"><span data-stu-id="2aaae-129">Entity</span></span>          |
   |<span data-ttu-id="2aaae-130">2</span><span class="sxs-lookup"><span data-stu-id="2aaae-130">2</span></span>     |<span data-ttu-id="2aaae-131">Attribut</span><span class="sxs-lookup"><span data-stu-id="2aaae-131">Attribute</span></span>          |
   |<span data-ttu-id="2aaae-132">3</span><span class="sxs-lookup"><span data-stu-id="2aaae-132">3</span></span>    |<span data-ttu-id="2aaae-133">Operator</span><span class="sxs-lookup"><span data-stu-id="2aaae-133">Operator</span></span>         |
   |<span data-ttu-id="2aaae-134">4</span><span class="sxs-lookup"><span data-stu-id="2aaae-134">4</span></span>    |<span data-ttu-id="2aaae-135">Wert</span><span class="sxs-lookup"><span data-stu-id="2aaae-135">Value</span></span>         |

8. <span data-ttu-id="2aaae-136">Wenn die Entität über [Beziehungen](relationships.md) mit der einheitlichen Kundenentität verbunden ist, müssen Sie den Beziehungspfad definieren, um ein gültiges Segment zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2aaae-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="2aaae-137">Fügen Sie die Entitäten aus dem Beziehungspfad hinzu, bis Sie die Entität **Kunde: Customer Insights** aus der Dropdownliste auswählen können.</span><span class="sxs-lookup"><span data-stu-id="2aaae-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="2aaae-138">Wählen Sie dann **Alle Datensätze** für jede Bedingung aus.</span><span class="sxs-lookup"><span data-stu-id="2aaae-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2aaae-139">![Beziehungspfad während der Segmenterstellung](media/segments-multiple-relationships.png "Beziehungspfad während der Segmenterstellung")</span><span class="sxs-lookup"><span data-stu-id="2aaae-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="2aaae-140">Wählen Sie **Speichern**, um Ihr Segment zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2aaae-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="2aaae-141">Ihr Segment wird gespeichert und verarbeitet, wenn alle Anforderungen validiert sind.</span><span class="sxs-lookup"><span data-stu-id="2aaae-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="2aaae-142">Andernfalls wird es als Entwurf gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2aaae-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="2aaae-143">Wählen Sie **Zurück zu Segmenten**, um zur Seite **Segmente** zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="2aaae-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="2aaae-144">Vorhandene Segmente verwalten</span><span class="sxs-lookup"><span data-stu-id="2aaae-144">Manage existing segments</span></span>

<span data-ttu-id="2aaae-145">Auf der Seite **Segmente** können Sie alle Ihre gespeicherten Segmente anzeigen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="2aaae-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="2aaae-146">Jedes Segment wird durch eine Zeile dargestellt, die zusätzliche Informationen über das Segment enthält.</span><span class="sxs-lookup"><span data-stu-id="2aaae-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="2aaae-147">Sie können die Segmente in einer Spalte sortieren, indem Sie die Spaltenüberschrift auswählen.</span><span class="sxs-lookup"><span data-stu-id="2aaae-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="2aaae-148">Verwenden Sie das Feld **Suchen** in der oberen rechten Ecke, um die Segmente zu filtern.</span><span class="sxs-lookup"><span data-stu-id="2aaae-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2aaae-149">![Optionen zum Verwalten eines vorhandenen Segments](media/segments-selected-segment.png "Optionen zum Verwalten eines vorhandenen Segments")</span><span class="sxs-lookup"><span data-stu-id="2aaae-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="2aaae-150">Die folgende Aktion ist verfügbar, wenn Sie ein Segment auswählen:</span><span class="sxs-lookup"><span data-stu-id="2aaae-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="2aaae-151">**Anzeigen** der Segmentdetails, einschließlich Trend der Anzahl der Mitglieder, Vorschau der Segmentmitglieder.</span><span class="sxs-lookup"><span data-stu-id="2aaae-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="2aaae-152">**Bearbeiten** des Segments, um seine Eigenschaften zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2aaae-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="2aaae-153">**Aktualisieren** des Segments, um die neuesten Daten einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="2aaae-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="2aaae-154">**Aktivieren** oder **Deaktivieren** des Segments.</span><span class="sxs-lookup"><span data-stu-id="2aaae-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="2aaae-155">Segmente haben zwei mögliche Status – aktiv oder inaktiv.</span><span class="sxs-lookup"><span data-stu-id="2aaae-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="2aaae-156">Diese Status sind nützlich, wenn Sie ein Segment bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="2aaae-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="2aaae-157">Für inaktive Segmente ist die Segmentdefinition vorhanden, enthält jedoch noch keine Kunden.</span><span class="sxs-lookup"><span data-stu-id="2aaae-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="2aaae-158">Wenn Sie ein Segment aktivieren, ändert sich sein Status von inaktiv in aktiv und es wird nach Kunden gesucht, die der Segmentdefinition entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2aaae-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="2aaae-159">Wenn eine [geplante Aktualisierung](system.md#schedule-tab) konfiguriert ist, haben inaktive Segmente den **Status** aufgelistet als **Übersprungen**. Dies zeigt an, dass nicht einmal eine Aktualisierung versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="2aaae-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="2aaae-160">Wenn ein inaktives Segment aktiviert wird, wird es aktualisiert und in geplante Aktualisierungen einbezogen.</span><span class="sxs-lookup"><span data-stu-id="2aaae-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="2aaae-161">Alternativ können Sie die Funktionalität **Planen Sie später** im Auswahlmenü unter **Aktivieren/Deaktivieren** zur Angabe eines zukünftigen Datums und einer zukünftigen Uhrzeit für die Aktivierung und Deaktivierung eines bestimmten Segments verwenden.</span><span class="sxs-lookup"><span data-stu-id="2aaae-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="2aaae-162">**Umbenennen** des Segments.</span><span class="sxs-lookup"><span data-stu-id="2aaae-162">**Rename** the segment.</span></span>
- <span data-ttu-id="2aaae-163">**Download** die Liste der Mitglieder als .CSV-Datei herunterladen.</span><span class="sxs-lookup"><span data-stu-id="2aaae-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="2aaae-164">**Hinzufügen zu**-Option sendet die Liste der Kunden-IDs im Segment zur Verarbeitung in einer anderen Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2aaae-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="2aaae-165">**Löschen** des Segments.</span><span class="sxs-lookup"><span data-stu-id="2aaae-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="2aaae-166">Aktualisieren von Segmenten</span><span class="sxs-lookup"><span data-stu-id="2aaae-166">Refresh segments</span></span>

<span data-ttu-id="2aaae-167">Sie können alle Segmente auf einmal aktualisieren, indem Sie **Alles aktualisieren** auf der Seite **Segmente** wählen, oder Sie können ein oder mehrere Segmente aktualisieren, wenn Sie sie auswählen und **Aktualisieren** aus den Optionen wählen.</span><span class="sxs-lookup"><span data-stu-id="2aaae-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="2aaae-168">Alternativ können Sie eine laufende Aktualisierung unter **Administrator** > **System** > **Zeitplan** konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2aaae-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="2aaae-169">Es gibt [sechs Arten von Status](system.md#status-types) für Aufgaben/Prozesse.</span><span class="sxs-lookup"><span data-stu-id="2aaae-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="2aaae-170">Darüber hinaus [hängen die meisten Prozesse von anderen nachfolgenden Prozessen ab](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="2aaae-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="2aaae-171">Sie können den Status eines Prozesses auswählen, um Details zum Fortschritt des gesamten Auftrags anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2aaae-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="2aaae-172">Nach der Auswahl von **Siehe Details** für eine der Aufgaben des Auftrags finden Sie zusätzliche Informationen: Verarbeitungszeit, das letzte Verarbeitungsdatum sowie alle mit der Aufgabe verbundenen Fehler und Warnungen.</span><span class="sxs-lookup"><span data-stu-id="2aaae-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="2aaae-173">Herunterladen und Exportieren von Segmenten</span><span class="sxs-lookup"><span data-stu-id="2aaae-173">Download and export segments</span></span>

<span data-ttu-id="2aaae-174">Sie können Ihre Segmente in eine CSV-Datei herunterladen oder nach Dynamics 365 Sales exportieren.</span><span class="sxs-lookup"><span data-stu-id="2aaae-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="2aaae-175">Herunterladen von Segmenten in eine CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="2aaae-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="2aaae-176">Gehen Sie in den Zielgruppen-Insights auf die Seite **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="2aaae-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="2aaae-177">Wählen Sie die Auslassungspunkte in der Kachel eines bestimmten Segments aus.</span><span class="sxs-lookup"><span data-stu-id="2aaae-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="2aaae-178">Wählen Sie **Download als CSV** aus der Dropdown-Liste Aktionen.</span><span class="sxs-lookup"><span data-stu-id="2aaae-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="2aaae-179">Exportieren von Segmenten nach Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="2aaae-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="2aaae-180">Vor dem Exportieren von Segmenten nach Dynamics 365 Sales muss ein Administrator [die Erstellung des Exportziels](export-destinations.md) für Dynamics 365 Sales vornehmen.</span><span class="sxs-lookup"><span data-stu-id="2aaae-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="2aaae-181">Gehen Sie in den Zielgruppen-Insights auf die Seite **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="2aaae-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="2aaae-182">Wählen Sie die Auslassungspunkte in der Kachel eines bestimmten Segments aus.</span><span class="sxs-lookup"><span data-stu-id="2aaae-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="2aaae-183">Wählen Sie aus der Aktionen-Dropdownliste die Option **Hinzufügen** und dann das Exportziel aus, an das Sie die Daten senden möchten.</span><span class="sxs-lookup"><span data-stu-id="2aaae-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="2aaae-184">Entwurfsmodus für Segmente</span><span class="sxs-lookup"><span data-stu-id="2aaae-184">Draft mode for segments</span></span>

<span data-ttu-id="2aaae-185">Wenn nicht alle Voraussetzungen für die Verarbeitung eines Segments erfüllt sind, können Sie das Segment als Entwurf speichern und von der Seite **Segmente** aufrufen.</span><span class="sxs-lookup"><span data-stu-id="2aaae-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="2aaae-186">Es wird als inaktives Segment gespeichert und kann erst aktiviert werden, wenn es gültig ist.</span><span class="sxs-lookup"><span data-stu-id="2aaae-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="2aaae-187">Weitere Bedingungen zu einer Gruppe hinzufügen</span><span class="sxs-lookup"><span data-stu-id="2aaae-187">Add more conditions to a group</span></span>

<span data-ttu-id="2aaae-188">Um weitere Bedingungen zu einer Gruppe hinzuzufügen, können Sie zwei logische Operatoren verwenden:</span><span class="sxs-lookup"><span data-stu-id="2aaae-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="2aaae-189">**AND** Operator: Beide Bedingungen müssen als Teil des Segmentierungsprozesses erfüllt sein.</span><span class="sxs-lookup"><span data-stu-id="2aaae-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="2aaae-190">Diese Option ist am nützlichsten, wenn Sie Bedingungen für verschiedene Entitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="2aaae-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="2aaae-191">**OR**-Operator: Jede der beiden Bedingungen muss als Teil des Segmentierungsprozesses erfüllt sein.</span><span class="sxs-lookup"><span data-stu-id="2aaae-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="2aaae-192">Diese Option ist am nützlichsten, wenn Sie mehrere Bedingungen für dieselbe Entität definieren.</span><span class="sxs-lookup"><span data-stu-id="2aaae-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2aaae-193">![OR-Operator, wobei jede der beiden Bedingungen erfüllt sein muss](media/segmentation-either-condition.png "OR-Operator, wobei jede der beiden Bedingungen erfüllt sein muss")</span><span class="sxs-lookup"><span data-stu-id="2aaae-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="2aaae-194">Es ist derzeit möglich, einen **OR** Operator unter einem **AND** Operator zu verschachteln, aber nicht umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="2aaae-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="2aaae-195">Kombinieren mehrerer Gruppen</span><span class="sxs-lookup"><span data-stu-id="2aaae-195">Combine multiple groups</span></span>

<span data-ttu-id="2aaae-196">Jede Gruppe produziert eine bestimmte Gruppe von Kunden.</span><span class="sxs-lookup"><span data-stu-id="2aaae-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="2aaae-197">Sie können diese Gruppen kombinieren, um die Kunden einzuschließen, die für Ihren Geschäftsfall erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="2aaae-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="2aaae-198">Gehen Sie in Zielgruppen-Insights auf die Seite **Segmente** und wählen Sie ein Segment aus.</span><span class="sxs-lookup"><span data-stu-id="2aaae-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="2aaae-199">Wählen Sie **Gruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2aaae-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2aaae-200">![Kundengruppe Gruppe hinzufügen](media/customer-group-add-group.png "Kundengruppe Gruppe hinzufügen")</span><span class="sxs-lookup"><span data-stu-id="2aaae-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="2aaae-201">Wählen Sie einen der folgenden Set-Operatoren aus: **Vereinigen**, **Überschneiden** oder **Außer**.</span><span class="sxs-lookup"><span data-stu-id="2aaae-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2aaae-202">![Kundengruppe Vereinigung hinzufügen](media/customer-group-union.png "Kundengruppe Vereinigung hinzufügen")</span><span class="sxs-lookup"><span data-stu-id="2aaae-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="2aaae-203">Wählen Sie einen Set-Operator aus, um eine neue Gruppe zu definieren.</span><span class="sxs-lookup"><span data-stu-id="2aaae-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="2aaae-204">Speichern Sie verschiedene Gruppen, um zu bestimmen, welche Daten erhalten bleiben sollen:</span><span class="sxs-lookup"><span data-stu-id="2aaae-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="2aaae-205">**Vereinigen** vereinigt die beiden Gruppen.</span><span class="sxs-lookup"><span data-stu-id="2aaae-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="2aaae-206">**Überschneiden** überschneidet die beiden Gruppen.</span><span class="sxs-lookup"><span data-stu-id="2aaae-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="2aaae-207">Nur Daten, die *beiden Gruppen gemeinsam* sind, werden in der vereinigten Gruppe beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2aaae-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="2aaae-208">**Außer** kombiniert die beiden Gruppen.</span><span class="sxs-lookup"><span data-stu-id="2aaae-208">**Except** combines the two groups.</span></span> <span data-ttu-id="2aaae-209">Nur Daten in Gruppe A, die *nicht gemeinsam* mit Daten in Gruppe B sind, bleiben erhalten.</span><span class="sxs-lookup"><span data-stu-id="2aaae-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="2aaae-210">Anzeigen der Verarbeitungsgeschichte und der Segmentmitglieder</span><span class="sxs-lookup"><span data-stu-id="2aaae-210">View processing history and segment members</span></span>

<span data-ttu-id="2aaae-211">Sie können konsolidierte Daten zu einem Segment anzeigen, indem Sie die Details des Segments überprüfen.</span><span class="sxs-lookup"><span data-stu-id="2aaae-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="2aaae-212">Wählen Sie auf der Seite **Segmente** das Segment aus, das Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="2aaae-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="2aaae-213">Der obere Teil der Seite enthält ein Trenddiagramm, das Änderungen in der Mitgliederzahl visualisiert.</span><span class="sxs-lookup"><span data-stu-id="2aaae-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="2aaae-214">Bewegen Sie die Maus über Datenpunkte, um die Mitgliederzahl an einem bestimmten Datum zu sehen.</span><span class="sxs-lookup"><span data-stu-id="2aaae-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="2aaae-215">Sie können den Zeitrahmen der Visualisierung aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="2aaae-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2aaae-216">![Segmentzeitbereich](media/segment-time-range.png "Segmentzeitbereich")</span><span class="sxs-lookup"><span data-stu-id="2aaae-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="2aaae-217">Der untere Teil enthält eine Liste der Segmentmitglieder.</span><span class="sxs-lookup"><span data-stu-id="2aaae-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="2aaae-218">Felder, die in dieser Liste erscheinen, basieren auf den Attributen der Entitäten Ihres Segments.</span><span class="sxs-lookup"><span data-stu-id="2aaae-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="2aaae-219">Die Liste ist eine Vorschau der passenden Segmentmitglieder und zeigt die ersten 100 Datensätze Ihres Segments an, so dass Sie es schnell auswerten und seine Definitionen bei Bedarf überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="2aaae-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="2aaae-220">Um alle übereinstimmenden Datensätze zu sehen, müssen Sie [Segment](export-destinations.md) exportieren.</span><span class="sxs-lookup"><span data-stu-id="2aaae-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="2aaae-221">Schnelle Segmente</span><span class="sxs-lookup"><span data-stu-id="2aaae-221">Quick segments</span></span>

<span data-ttu-id="2aaae-222">Zusätzlich zum Segment-Builder gibt es einen weiteren Weg, um Segmente zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2aaae-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="2aaae-223">Mit schnellen Segmenten können Sie einfache Segmente mit einem einzigen Operator schnell und mit sofortigen Erkenntnissen erstellen.</span><span class="sxs-lookup"><span data-stu-id="2aaae-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="2aaae-224">Wählen Sie auf der Seite **Segmente** die Option **Neu** > **Schnell erstellen aus**.</span><span class="sxs-lookup"><span data-stu-id="2aaae-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="2aaae-225">Wählen Sie die Option **Profile**, um ein Segment zu erstellen, das auf der einheitlichen Kundenentität basiert.</span><span class="sxs-lookup"><span data-stu-id="2aaae-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="2aaae-226">Wählen Sie die Option **Kennzahlen**, um ein Segment um jeden Kennzahlentyp vom Typ Kundenattribut herum aufzubauen, den Sie zuvor auf der Seite **Kennzahlen** erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="2aaae-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="2aaae-227">Wählen Sie die Option **Intelligenz** zum Erstellen eines Segments für eine der Ausgabeentitäten aus, die Sie mit einer der beiden Funktionen **Vorhersagen** oder **Benutzerdefinierte Modelle** generiert haben.</span><span class="sxs-lookup"><span data-stu-id="2aaae-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="2aaae-228">Wählen Sie im Dialogfeld **Neues schnelles Segment** ein Attribut aus der Dropdownliste **Feld** aus.</span><span class="sxs-lookup"><span data-stu-id="2aaae-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="2aaae-229">Das System liefert einige zusätzliche Erkenntnisse, die Ihnen helfen, bessere Segmente Ihrer Kunden zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2aaae-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="2aaae-230">Für kategoriale Felder werden 10 Top-Kundenzahlen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2aaae-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="2aaae-231">Wählen Sie einen **Wert** und wählen Sie **Überprüfung**.</span><span class="sxs-lookup"><span data-stu-id="2aaae-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="2aaae-232">Bei einem numerischen Attribut zeigt das System an, welcher Attributwert unter das Perzentil des jeweiligen Kunden fällt.</span><span class="sxs-lookup"><span data-stu-id="2aaae-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="2aaae-233">Wählen Sie einen **Bediener** und einen **Wert**, dann wählen Sie **Review**.</span><span class="sxs-lookup"><span data-stu-id="2aaae-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="2aaae-234">Das System liefert Ihnen eine **geschätzte Segmentgröße**.</span><span class="sxs-lookup"><span data-stu-id="2aaae-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="2aaae-235">Sie können wählen, ob Sie das von Ihnen definierte Segment generieren oder es zunächst erneut aufrufen, um eine andere Segmentgröße zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2aaae-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2aaae-236">![Name und Schätzung für ein Quick-Segment](media/quick-segment-name.png "Name und Schätzung für ein schnelles Segment")</span><span class="sxs-lookup"><span data-stu-id="2aaae-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="2aaae-237">Geben Sie einen **Name** für Ihr Segment an.</span><span class="sxs-lookup"><span data-stu-id="2aaae-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="2aaae-238">Geben Sie optional einen **Anzeigename** ein.</span><span class="sxs-lookup"><span data-stu-id="2aaae-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="2aaae-239">Wählen Sie **Speichern**, um Ihr Segment zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2aaae-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="2aaae-240">Nachdem das Segment fertig bearbeitet wurde, können Sie es wie jedes andere von Ihnen erstellte Segment anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2aaae-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="2aaae-241">Für die folgenden Szenarien empfehlen wir, den Segment-Builder statt der empfohlenen Segment-Fähigkeit zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="2aaae-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="2aaae-242">Erstellen von Segmenten mit Filtern auf kategoriale Felder, bei denen sich der Operator von dem Operator **Ist** unterscheidet</span><span class="sxs-lookup"><span data-stu-id="2aaae-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="2aaae-243">Erstellen von Segmenten mit Filtern für numerische Felder, bei denen der Operator sich von den Operatoren **Zwischen**, **Größer als** und **Kleiner als** unterscheidet</span><span class="sxs-lookup"><span data-stu-id="2aaae-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="2aaae-244">Erstellen von Segmenten mit Filtern für Datumsfelder</span><span class="sxs-lookup"><span data-stu-id="2aaae-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="2aaae-245">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="2aaae-245">Next steps</span></span>

<span data-ttu-id="2aaae-246">[Exportieren Sie ein Segment](export-destinations.md) und erkunden Sie die [Kundenkarte](customer-card-add-in.md) und [Connectors](export-power-bi.md), um Einblicke auf Kundenebene zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2aaae-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]