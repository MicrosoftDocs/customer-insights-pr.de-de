---
title: Entitäten bei der Datenvereinheitlichung zusammenführen
description: Führen Sie Entitäten zusammen, um vereinheitlichte Kundenprofile zu erstellen.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597832"
---
# <a name="merge-entities"></a><span data-ttu-id="686b0-103">Entitäten zusammenführen</span><span class="sxs-lookup"><span data-stu-id="686b0-103">Merge entities</span></span>

<span data-ttu-id="686b0-104">Die Zusammenführungsphase ist die letzte Phase des Datenvereinheitlichungsprozesses.</span><span class="sxs-lookup"><span data-stu-id="686b0-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="686b0-105">Sein Zweck ist es, widersprüchliche Daten abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="686b0-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="686b0-106">Beispiele für widersprüchliche Daten könnten ein Kundenname sein, der in zwei Ihrer Datensätze gefunden wurde, der jedoch in jedem etwas anders angezeigt wird („Grant Marshall“ gegenüber "Grant Marshal"), oder eine Telefonnummer, die sich im Format (617-803-091X im Vergleich zu 617803091X unterscheidet).</span><span class="sxs-lookup"><span data-stu-id="686b0-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="686b0-107">Die Zusammenführung dieser widersprüchlichen Datenpunkte erfolgt auf einer attributweisen Basis.</span><span class="sxs-lookup"><span data-stu-id="686b0-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="686b0-108">Nach Abschluss der [Match-Phase](match-entities.md) starten Sie die Zusammenführungsphase durch Auswahl der Kachel **zusammenführen** auf der Seite **Vereinheitlichen**.</span><span class="sxs-lookup"><span data-stu-id="686b0-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="686b0-109">Empfehlungen für die Überprüfung des Systems</span><span class="sxs-lookup"><span data-stu-id="686b0-109">Review system recommendations</span></span>

<span data-ttu-id="686b0-110">Auf der Seite **zusammenführen** wählen Sie Attribute aus, die in Ihrer einheitlichen Kundenprofilentität zusammengeführt werden sollen (das Ergebnis des Konfigurationsprozesses).</span><span class="sxs-lookup"><span data-stu-id="686b0-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="686b0-111">Einige Attribute werden vom System automatisch zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="686b0-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="686b0-112">Zusammengeführte Attribute anzeigen</span><span class="sxs-lookup"><span data-stu-id="686b0-112">View merged attributes</span></span>

<span data-ttu-id="686b0-113">Um die Attribute anzuzeigen, die in einem Ihrer automatisch abgemischten Attribute enthalten sind, markieren Sie das abgemischte Attribut.</span><span class="sxs-lookup"><span data-stu-id="686b0-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="686b0-114">Die beiden Attribute, aus denen das zusammengeführte Attribut besteht, werden in zwei neuen Zeilen unterhalb des zusammengeführten Attributs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="686b0-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="686b0-115">![Gemischtes Attribut auswählen](media/configure-data-merge-profile-attributes.png "Zusammengeführtes Attribut auswählen")</span><span class="sxs-lookup"><span data-stu-id="686b0-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="686b0-116">Separate zusammengeführte Attribute</span><span class="sxs-lookup"><span data-stu-id="686b0-116">Separate merged attributes</span></span>

<span data-ttu-id="686b0-117">Um eines der automatisch zusammengefügten Attribute zu trennen oder aufzuheben, suchen Sie das Attribut in der Tabelle **Profilattribute**.</span><span class="sxs-lookup"><span data-stu-id="686b0-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="686b0-118">Aktivieren Sie die Schaltfläche Auslassungspunkte (...).</span><span class="sxs-lookup"><span data-stu-id="686b0-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="686b0-119">Wählen Sie in der Dropdown-Liste **Separate Felder** aus.</span><span class="sxs-lookup"><span data-stu-id="686b0-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="686b0-120">Zusammengeführte Attribute entfernen</span><span class="sxs-lookup"><span data-stu-id="686b0-120">Remove merged attributes</span></span>

<span data-ttu-id="686b0-121">Um ein Attribut aus der Endkundenprofil-Entität auszuschließen, finden Sie es in der Tabelle **Profilattribute**.</span><span class="sxs-lookup"><span data-stu-id="686b0-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="686b0-122">Aktivieren Sie die Schaltfläche Auslassungspunkte (...).</span><span class="sxs-lookup"><span data-stu-id="686b0-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="686b0-123">Wählen Sie in der Dropdownliste die Option **Nicht zusammenführen** aus.</span><span class="sxs-lookup"><span data-stu-id="686b0-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="686b0-124">Das Attribut wird in den Abschnitt **Entfernt aus Kundendatensatz** verschoben.</span><span class="sxs-lookup"><span data-stu-id="686b0-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="686b0-125">Manuelles Hinzufügen eines zusammengeführten Attributs</span><span class="sxs-lookup"><span data-stu-id="686b0-125">Manually add a merged attribute</span></span>

<span data-ttu-id="686b0-126">Um ein zusammengeführtes Attribut hinzuzufügen, gehen Sie auf die Seite **Zusammenführen**.</span><span class="sxs-lookup"><span data-stu-id="686b0-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="686b0-127">Wählen Sie **Zusammengeführtes Attribut hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="686b0-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="686b0-128">Geben Sie einen **Name** ein, um sie später auf der Seite **Zusammenführen** zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="686b0-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="686b0-129">Optional können Sie einen **Anzeigenamen** in der einheitlichen Kundenprofilentität anzeigen.</span><span class="sxs-lookup"><span data-stu-id="686b0-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="686b0-130">Konfigurieren Sie **Duplizierte Attribute auswählen**, um die Attribute, die Sie aus den abgeglichenen Einheiten zusammenführen möchten, auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="686b0-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="686b0-131">Sie können auch nach Attributen suchen.</span><span class="sxs-lookup"><span data-stu-id="686b0-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="686b0-132">Setzen Sie den **Rang nach Wichtigkeit**, um ein Attribut über die anderen zu priorisieren.</span><span class="sxs-lookup"><span data-stu-id="686b0-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="686b0-133">Wenn beispielsweise die Entität *WebAccountCSV* die genauesten Daten über das Attribut *Vollständige Namen* enthält, könnten Sie diese Entität gegenüber *ContactCSV* priorisieren, indem Sie *WebAccountCSV* auswählen.</span><span class="sxs-lookup"><span data-stu-id="686b0-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="686b0-134">Infolgedessen wird *WebAccountCSV* auf die erste Priorität verschoben, während *ContactCSV* auf die zweite Priorität verschoben wird, wenn Werte für das Attribut *Vollständiger Name* gezogen werden.</span><span class="sxs-lookup"><span data-stu-id="686b0-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="686b0-135">Führen Sie Ihre Zusammenführung durch</span><span class="sxs-lookup"><span data-stu-id="686b0-135">Run your merge</span></span>

<span data-ttu-id="686b0-136">Unabhängig davon, ob Sie Attribute manuell zusammenführen oder vom System zusammenführen lassen, können Sie Ihre Zusammenführung immer durchführen.</span><span class="sxs-lookup"><span data-stu-id="686b0-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="686b0-137">Wählen Sie **Ausführen** auf der Seite **Zusammenführen**, um den Prozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="686b0-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="686b0-138">![Datenzusammenführung Speichern und Ausführen](media/configure-data-merge-save-run.png "Datenzusammenführung Speichern und Ausführen")</span><span class="sxs-lookup"><span data-stu-id="686b0-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="686b0-139">Um weitere Änderungen vorzunehmen und den Schritt erneut auszuführen, können Sie eine laufende Zusammenführung abbrechen.</span><span class="sxs-lookup"><span data-stu-id="686b0-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="686b0-140">Wählen Sie den Text **Wird aktualisiert ...** und **Auftrag abbrechen** im angezeigten Seitenbereich aus.</span><span class="sxs-lookup"><span data-stu-id="686b0-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="686b0-141">Nachdem der Text **Wird aktualisiert ...** zu **Erfolgreich** geändert wurde, ist die Zusammenführung abgeschlossen und hat Widersprüche in Ihren Daten gemäß den von Ihnen definierten Richtlinien behoben.</span><span class="sxs-lookup"><span data-stu-id="686b0-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="686b0-142">Zusammengeführte und nicht zusammengeführte Attribute sind in der einheitlichen Profilentität enthalten.</span><span class="sxs-lookup"><span data-stu-id="686b0-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="686b0-143">Ausgeschlossene Attribute sind nicht in der einheitlichen Profilentität enthalten.</span><span class="sxs-lookup"><span data-stu-id="686b0-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="686b0-144">Wenn Sie eine Zusammenführung nicht zum ersten Mal erfolgreich ausgeführt haben, werden alle nachfolgenden Prozesse, einschließlich Anreicherung, Segmentierung und Kennzahlen, automatisch erneut ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="686b0-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="686b0-145">Nachdem alle nachfolgenden Prozesse erneut ausgeführt wurden, spiegeln die Kundenprofile alle von Ihnen vorgenommenen Änderungen wider.</span><span class="sxs-lookup"><span data-stu-id="686b0-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="686b0-146">Es gibt [sechs Arten von Status](system.md#status-types) für Aufgaben/Prozesse.</span><span class="sxs-lookup"><span data-stu-id="686b0-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="686b0-147">Darüber hinaus [hängen die meisten Prozesse von anderen nachfolgenden Prozessen ab](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="686b0-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="686b0-148">Sie können den Status eines Prozesses auswählen, um Details zum Fortschritt des gesamten Auftrags anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="686b0-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="686b0-149">Nach der Auswahl von **Siehe Details** für eine der Aufgaben des Auftrags finden Sie zusätzliche Informationen: Verarbeitungszeit, das letzte Verarbeitungsdatum sowie alle mit der Aufgabe verbundenen Fehler und Warnungen.</span><span class="sxs-lookup"><span data-stu-id="686b0-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="686b0-150">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="686b0-150">Next Step</span></span>

<span data-ttu-id="686b0-151">Konfigurieren von [Aktivitäten](activities.md), [Anreicherung](enrichment-microsoft-graph.md), oder [Beziehungen](relationships.md), um mehr Einblicke über Ihre Kunden zu gewinnen.</span><span class="sxs-lookup"><span data-stu-id="686b0-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="686b0-152">Wenn Sie bereits Aktivitäten, Anreicherungen oder Beziehungen konfiguriert haben oder Segmente definiert haben, werden diese automatisch verarbeitet, um die neuesten Kundendaten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="686b0-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]