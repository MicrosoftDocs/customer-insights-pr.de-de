---
title: Segmente in Zielgruppenerkenntnissen
description: Übersicht über Segmente und wie man sie erstellt und verwaltet.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6cb7bd62bf0f61e6dc5811b20e5011e4a086c743
ms.sourcegitcommit: 84283d523a891298fca8aaf629d9f9ab2a1bc067
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "6111386"
---
# <a name="segments-overview"></a><span data-ttu-id="6dfc8-103">Übersicht über Segmente</span><span class="sxs-lookup"><span data-stu-id="6dfc8-103">Segments overview</span></span>

<span data-ttu-id="6dfc8-104">Mit Segmenten können Sie Ihre Kunden anhand von demografischen, transaktionalen oder verhaltensbezogenen Attributen gruppieren.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="6dfc8-105">Sie können Segmente verwenden, um Werbekampagnen, Vertriebsaktivitäten und Kundensupportaktionen gezielt auf die Erreichung Ihrer Geschäftsziele auszurichten.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="6dfc8-106">Kundenprofile, die den Filtern einer Segmentdefinition entsprechen, werden als *Mitglieder* eines Segments bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="6dfc8-107">Es gelten einige [Serviceeinschränkungen](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="6dfc8-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="6dfc8-108">Ein neues Segment erstellen</span><span class="sxs-lookup"><span data-stu-id="6dfc8-108">Create a new segment</span></span>

<span data-ttu-id="6dfc8-109">Es gibt mehrere Wege, ein neues Segment zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="6dfc8-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="6dfc8-110">Komplexes Segment mit Segment Builder: [Leeres Segment](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="6dfc8-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="6dfc8-111">Einfache Segmente mit einem Operator: [Schnelles Segment](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="6dfc8-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="6dfc8-112">KI-gestützter Weg, um ähnliche Kunden zu finden: [Ähnliche Kunden](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="6dfc8-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="6dfc8-113">KI-gestützte Vorschläge basierend auf Maßnahmen oder Attributen: [Vorgeschlagene Segmente zur Verbesserung der Maßnahmen](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="6dfc8-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="6dfc8-114">Vorschläge basierend auf Aktivitäten: [Vorgeschlagene Segmente basierend auf der Kundenaktivität](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="6dfc8-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="6dfc8-115">Vorhandene Segmente verwalten</span><span class="sxs-lookup"><span data-stu-id="6dfc8-115">Manage existing segments</span></span>

<span data-ttu-id="6dfc8-116">Gehen Sie zur Seite **Segmente**, um alle Ihre gespeicherten Segmente anzuzeigen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="6dfc8-117">Jedes Segment wird durch eine Zeile dargestellt, die zusätzliche Informationen über das Segment enthält.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Ausgewähltes Segment mit Dropdownliste und verfügbaren Optionen.":::

<span data-ttu-id="6dfc8-119">Die folgende Aktion ist verfügbar, wenn Sie ein Segment auswählen:</span><span class="sxs-lookup"><span data-stu-id="6dfc8-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="6dfc8-120">**Anzeigen** der Segmentdetails, einschließlich Trend der Anzahl der Mitglieder, Vorschau der Segmentmitglieder.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="6dfc8-121">**Bearbeiten** des Segments, um seine Eigenschaften zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="6dfc8-122">**Duplikat erstellen** eines Segments.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="6dfc8-123">Sie können die Eigenschaften sofort bearbeiten oder das Duplikat einfach speichern.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="6dfc8-124">**Aktualisieren** des Segments, um die neuesten Daten einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="6dfc8-125">**Aktivieren** oder **Deaktivieren** des Segments.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="6dfc8-126">Segmente haben zwei mögliche Status – aktiv oder inaktiv.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="6dfc8-127">Diese Status sind nützlich, wenn Sie ein Segment bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="6dfc8-128">Für inaktive Segmente ist die Segmentdefinition vorhanden, enthält jedoch noch keine Kunden.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="6dfc8-129">Wenn Sie ein Segment aktivieren, ändert sich sein Status von inaktiv in aktiv und es wird nach Kunden gesucht, die der Segmentdefinition entsprechen.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="6dfc8-130">Wenn eine [geplante Aktualisierung](system.md#schedule-tab) konfiguriert ist, haben inaktive Segmente den **Status** aufgelistet als **Übersprungen**. Dies zeigt an, dass nicht einmal eine Aktualisierung versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="6dfc8-131">Wenn ein inaktives Segment aktiviert wird, wird es aktualisiert und in geplante Aktualisierungen einbezogen.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="6dfc8-132">Alternativ können Sie die Funktionalität **Planen Sie später** im Auswahlmenü unter **Aktivieren/Deaktivieren** zur Angabe eines zukünftigen Datums und einer zukünftigen Uhrzeit für die Aktivierung und Deaktivierung eines bestimmten Segments verwenden.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="6dfc8-133">**Umbenennen** des Segments.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-133">**Rename** the segment.</span></span>
- <span data-ttu-id="6dfc8-134">**Download** die Liste der Mitglieder als .CSV-Datei herunterladen.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="6dfc8-135">**Exporte verwalten**, um exportbezogene Segmente anzuzeigen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="6dfc8-136">Weitere Informationen zu Exporten.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="6dfc8-137">**Löschen** des Segments.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="6dfc8-138">Aktualisieren von Segmenten</span><span class="sxs-lookup"><span data-stu-id="6dfc8-138">Refresh segments</span></span>

<span data-ttu-id="6dfc8-139">Sie können alle Segmente auf einmal aktualisieren, indem Sie **Alles aktualisieren** auf der Seite **Segmente** wählen, oder Sie können ein oder mehrere Segmente aktualisieren, wenn Sie sie auswählen und **Aktualisieren** aus den Optionen wählen.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="6dfc8-140">Alternativ können Sie eine laufende Aktualisierung unter **Administrator** > **System** > **Zeitplan** konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="6dfc8-141">Es gibt [sechs Arten von Status](system.md#status-types) für Aufgaben/Prozesse.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="6dfc8-142">Darüber hinaus [hängen die meisten Prozesse von anderen nachfolgenden Prozessen ab](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="6dfc8-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="6dfc8-143">Sie können den Status eines Prozesses auswählen, um Details zum Fortschritt des gesamten Auftrags anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="6dfc8-144">Nach der Auswahl von **Siehe Details** für eine der Aufgaben des Auftrags finden Sie zusätzliche Informationen: Verarbeitungszeit, das letzte Verarbeitungsdatum sowie alle mit der Aufgabe verbundenen Fehler und Warnungen.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="6dfc8-145">Segmente exportieren</span><span class="sxs-lookup"><span data-stu-id="6dfc8-145">Export segments</span></span>

<span data-ttu-id="6dfc8-146">Sie können ein Segment von der Segmentseite oder der [Exportseite](export-destinations.md) exportieren.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="6dfc8-147">Gehen Sie zur Seite **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="6dfc8-148">Wählen Sie für das Segment, das Sie exportieren möchten, **Mehr anzeigen [...]** aus.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="6dfc8-149">Wählen Sie aus der Dropdownliste für Aktionen die Option **Exporte verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-149">Select **Manage exports** from the actions drop-down list.</span></span>

1. <span data-ttu-id="6dfc8-150">Die Seite **Exporte (Vorschau) für Segment** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="6dfc8-151">Sie können alle konfigurierten Exporte gruppiert nach Exporten anzeigen, die das aktuelle Segment enthalten oder nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="6dfc8-152">Um das ausgewählte Segment zu einem Export hinzuzufügen, wählen Sie den Export in der Liste aus und wählen Sie dann **Segment hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="6dfc8-153">Um einen neuen Export mit dem ausgewählten Segment zu erstellen, wählen Sie **Export hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="6dfc8-154">Weitere Informationen zum Erstellen von Exporten finden Sie unter [Einrichten eines neuen Exports](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6dfc8-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6dfc8-155">Wählen Sie **Zurück** aus, um zur Hauptseite für Segmente zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="6dfc8-156">Anzeigen der Verarbeitungsgeschichte und der Segmentmitglieder</span><span class="sxs-lookup"><span data-stu-id="6dfc8-156">View processing history and segment members</span></span>

<span data-ttu-id="6dfc8-157">Sie können konsolidierte Daten zu einem Segment anzeigen, indem Sie die Details des Segments überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="6dfc8-158">Wählen Sie auf der Seite **Segmente** das Segment aus, das Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="6dfc8-159">Der obere Teil der Seite enthält ein Trenddiagramm, das Änderungen in der Mitgliederzahl visualisiert.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="6dfc8-160">Bewegen Sie die Maus über Datenpunkte, um die Mitgliederzahl an einem bestimmten Datum zu sehen.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="6dfc8-161">Sie können den Zeitrahmen der Visualisierung aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6dfc8-162">![Segmentzeitbereich](media/segment-time-range.png "Segmentzeitbereich")</span><span class="sxs-lookup"><span data-stu-id="6dfc8-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="6dfc8-163">Der untere Teil enthält eine Liste der Segmentmitglieder.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="6dfc8-164">Felder, die in dieser Liste erscheinen, basieren auf den Attributen der Entitäten Ihres Segments.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="6dfc8-165">Die Liste ist eine Vorschau der passenden Segmentmitglieder und zeigt die ersten 100 Datensätze Ihres Segments an, so dass Sie es schnell auswerten und seine Definitionen bei Bedarf überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="6dfc8-166">Um alle übereinstimmenden Datensätze zu sehen, müssen Sie [Segment](export-destinations.md) exportieren.</span><span class="sxs-lookup"><span data-stu-id="6dfc8-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
