---
title: Entitäten bei der Datenvereinheitlichung zusammenführen
description: Führen Sie Entitäten zusammen, um vereinheitlichte Kundenprofile zu erstellen.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305635"
---
# <a name="merge-entities"></a><span data-ttu-id="3546a-103">Entitäten zusammenführen</span><span class="sxs-lookup"><span data-stu-id="3546a-103">Merge entities</span></span>

<span data-ttu-id="3546a-104">Die Zusammenführungsphase ist die letzte Phase des Datenvereinheitlichungsprozesses.</span><span class="sxs-lookup"><span data-stu-id="3546a-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="3546a-105">Sein Zweck ist es, widersprüchliche Daten abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="3546a-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="3546a-106">Beispiele für widersprüchliche Daten könnten ein Kundenname sein, der in zwei Ihrer Datensätze gefunden wurde, der jedoch in jedem etwas anders angezeigt wird („Grant Marshall“ gegenüber "Grant Marshal"), oder eine Telefonnummer, die sich im Format (617-803-091X im Vergleich zu 617803091X unterscheidet).</span><span class="sxs-lookup"><span data-stu-id="3546a-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="3546a-107">Die Zusammenführung dieser widersprüchlichen Datenpunkte erfolgt auf einer attributweisen Basis.</span><span class="sxs-lookup"><span data-stu-id="3546a-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Zusammenführungsseite im Datenvereinigungsprozess mit Tabelle mit zusammengeführten Feldern, die das einheitliche Kundenprofil definieren.":::

<span data-ttu-id="3546a-109">Nach Abschluss der [Match-Phase](match-entities.md) starten Sie die Zusammenführungsphase durch Auswahl der Kachel **zusammenführen** auf der Seite **Vereinheitlichen**.</span><span class="sxs-lookup"><span data-stu-id="3546a-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="3546a-110">Systemempfehlungen überprüfen</span><span class="sxs-lookup"><span data-stu-id="3546a-110">Review system recommendations</span></span>

<span data-ttu-id="3546a-111">Unter **Daten** > **Vereinheitlichen** > **Zusammenführen** wählen Sie Attribute aus und schließen sie aus, um sie in Ihrer einheitlichen Kundenprofilentität zusammenzuführen.</span><span class="sxs-lookup"><span data-stu-id="3546a-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="3546a-112">Das einheitliche Kundenprofil ist das Ergebnis des Datenvereinigungsprozesses.</span><span class="sxs-lookup"><span data-stu-id="3546a-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="3546a-113">Einige Attribute werden vom System automatisch zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="3546a-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="3546a-114">Um die Attribute anzuzeigen, die in einem Ihrer automatisch zusammengeführten Attribute enthalten sind, wählen Sie dieses zusammengeführte Attribut in der Registerkarte **Kundenfelder** der Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="3546a-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="3546a-115">Die beiden Attribute, aus denen das zusammengeführte Attribut besteht, werden in zwei neuen Zeilen unterhalb des zusammengeführten Attributs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3546a-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="3546a-116">Trennen, umbenennen, ausschließen und bearbeiten Sie zusammengeführte Felder</span><span class="sxs-lookup"><span data-stu-id="3546a-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="3546a-117">Sie können ändern, wie das System zusammengeführte Attribute verarbeitet, um das einheitliche Kundenprofil zu generieren.</span><span class="sxs-lookup"><span data-stu-id="3546a-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="3546a-118">Wählen Sie **mehr anzeigen** und wählen Sie, was Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="3546a-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Optionen im Dropdown-Menü mehr anzeigen, um zusammengeführte Attribute zu verwalten.":::

<span data-ttu-id="3546a-120">Weitere Informationen finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="3546a-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="3546a-121">Separate zusammengeführte Felder</span><span class="sxs-lookup"><span data-stu-id="3546a-121">Separate merged fields</span></span>

<span data-ttu-id="3546a-122">Um zusammengeführte Felder zu trennen, suchen Sie das Attribut in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="3546a-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="3546a-123">Getrennte Felder werden als einzelne Datenpunkte im einheitlichen Kundenprofil angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3546a-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="3546a-124">Wählen Sie das zusammengeführte Feld aus.</span><span class="sxs-lookup"><span data-stu-id="3546a-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="3546a-125">Wählen Sie **mehr anzeigen** und wählen Sie **separate Felder** aus.</span><span class="sxs-lookup"><span data-stu-id="3546a-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="3546a-126">Bestätigen Sie die Trennung.</span><span class="sxs-lookup"><span data-stu-id="3546a-126">Confirm the separation.</span></span>

1. <span data-ttu-id="3546a-127">Klicken Sie auf **Speichern** und **Ausführen**, um die Änderungen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3546a-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="3546a-128">Zusammengeführte Felder umbenennen</span><span class="sxs-lookup"><span data-stu-id="3546a-128">Rename merged fields</span></span>

<span data-ttu-id="3546a-129">Ändern Sie den Anzeigename der zusammengeführten Attribute.</span><span class="sxs-lookup"><span data-stu-id="3546a-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="3546a-130">Der Name der ausgegebenen Entitäten kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="3546a-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="3546a-131">Wählen Sie das zusammengeführte Feld aus.</span><span class="sxs-lookup"><span data-stu-id="3546a-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="3546a-132">Wählen Sie **mehr anzeigen** und wählen Sie **umbenennen** aus.</span><span class="sxs-lookup"><span data-stu-id="3546a-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="3546a-133">Bestätigen Sie den geänderten Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="3546a-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="3546a-134">Klicken Sie auf **Speichern** und **Ausführen**, um die Änderungen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3546a-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="3546a-135">Zusammengeführte Felder ausschließen</span><span class="sxs-lookup"><span data-stu-id="3546a-135">Exclude merged fields</span></span>

<span data-ttu-id="3546a-136">Schließen Sie ein Attribut aus dem einheitlichen Kundenprofil aus.</span><span class="sxs-lookup"><span data-stu-id="3546a-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="3546a-137">Wenn das Feld in anderen Prozessen verwendet wird, z. B. in einem Segment, entfernen Sie es aus diesen Prozessen, bevor Sie es aus dem Kundenprofil ausschließen.</span><span class="sxs-lookup"><span data-stu-id="3546a-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="3546a-138">Wählen Sie das zusammengeführte Feld aus.</span><span class="sxs-lookup"><span data-stu-id="3546a-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="3546a-139">Wählen Sie **mehr anzeigen** und wählen Sie **ausschließen** aus.</span><span class="sxs-lookup"><span data-stu-id="3546a-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="3546a-140">Bestätigen Sie den Ausschluss.</span><span class="sxs-lookup"><span data-stu-id="3546a-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="3546a-141">Klicken Sie auf **Speichern** und **Ausführen**, um die Änderungen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3546a-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="3546a-142">Auf der Seite **Zusammenführen** wählen Sie **Ausgeschlossene Felder**, um die Liste aller ausgeschlossenen Felder anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3546a-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="3546a-143">In diesem Bereich können Sie ausgeschlossene Felder wieder hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3546a-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="3546a-144">Felder manuell kombinieren</span><span class="sxs-lookup"><span data-stu-id="3546a-144">Manually combine fields</span></span>

<span data-ttu-id="3546a-145">Zusammengeführtes Attribut manuell definieren.</span><span class="sxs-lookup"><span data-stu-id="3546a-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="3546a-146">Auf der Seite **Zusammenführen** wählen Sie **Felder kombinieren**.</span><span class="sxs-lookup"><span data-stu-id="3546a-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="3546a-147">Einen **Namen** und einen **Name des Ausgabefeldes** bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="3546a-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="3546a-148">Ein Feld zum Hinzufügen auswählen.</span><span class="sxs-lookup"><span data-stu-id="3546a-148">Choose a field to add.</span></span> <span data-ttu-id="3546a-149">Wählen Sie **Felder hinzufügen** aus, um mehr Felder zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="3546a-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="3546a-150">Bestätigen Sie den Ausschluss.</span><span class="sxs-lookup"><span data-stu-id="3546a-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="3546a-151">Klicken Sie auf **Speichern** und **Ausführen**, um die Änderungen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3546a-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="3546a-152">Die Reihenfolge von Feldern ändern</span><span class="sxs-lookup"><span data-stu-id="3546a-152">Change the order of fields</span></span>

<span data-ttu-id="3546a-153">Einige Entitäten enthalten mehr Details als andere.</span><span class="sxs-lookup"><span data-stu-id="3546a-153">Some entities contain more details than others.</span></span> <span data-ttu-id="3546a-154">Wenn eine Entität die neuesten Daten zu einem Feld enthält, können Sie diese beim Zusammenführen von Werten gegenüber anderen Entitäten priorisieren.</span><span class="sxs-lookup"><span data-stu-id="3546a-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="3546a-155">Wählen Sie das zusammengeführte Feld aus.</span><span class="sxs-lookup"><span data-stu-id="3546a-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="3546a-156">Wählen Sie **mehr anzeigen** und wählen Sie **bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="3546a-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="3546a-157">In dem Bereich **Felder kombinieren** wählen Sie **nach oben/unten bewegen**, um die Reihenfolge festzulegen oder ziehen Sie sie an die gewünschte Position.</span><span class="sxs-lookup"><span data-stu-id="3546a-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="3546a-158">Die Änderung bestätigen.</span><span class="sxs-lookup"><span data-stu-id="3546a-158">Confirm the change.</span></span>

1. <span data-ttu-id="3546a-159">Klicken Sie auf **Speichern** und **Ausführen**, um die Änderungen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3546a-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="3546a-160">Führen Sie Ihre Zusammenführung durch</span><span class="sxs-lookup"><span data-stu-id="3546a-160">Run your merge</span></span>

<span data-ttu-id="3546a-161">Unabhängig davon, ob Sie Attribute manuell zusammenführen oder vom System zusammenführen lassen, können Sie Ihre Zusammenführung immer durchführen.</span><span class="sxs-lookup"><span data-stu-id="3546a-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="3546a-162">Wählen Sie **Ausführen** auf der Seite **Zusammenführen**, um den Prozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="3546a-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3546a-163">![Datenzusammenführung Speichern und Ausführen](media/configure-data-merge-save-run.png "Datenzusammenführung Speichern und Ausführen")</span><span class="sxs-lookup"><span data-stu-id="3546a-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="3546a-164">Wählen Sie **nur Zusammenführen ausführen**, wenn Sie nur die Ausgabe in der einheitlichen Kundenentität anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="3546a-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="3546a-165">Nachgelagerte Prozesse werden als [im Aktualisierungsplan definiert](system.md#schedule-tab) aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="3546a-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="3546a-166">Wählen Sie **Merge- und Downstream-Prozesse ausführen**, um das System mit Ihren Änderungen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="3546a-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="3546a-167">Alle Prozesse, einschließlich Anreicherung, Segmente und Maßnahmen, werden automatisch erneut ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3546a-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="3546a-168">Nachdem alle nachgelagerten Prozesse abgeschlossen wurden, spiegeln die Kundenprofile alle von Ihnen vorgenommenen Änderungen wider.</span><span class="sxs-lookup"><span data-stu-id="3546a-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="3546a-169">Um weitere Änderungen vorzunehmen und den Schritt erneut auszuführen, können Sie eine laufende Zusammenführung abbrechen.</span><span class="sxs-lookup"><span data-stu-id="3546a-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="3546a-170">Wählen Sie den Text **Wird aktualisiert ...** und **Auftrag abbrechen**  im angezeigten Seitenbereich aus.</span><span class="sxs-lookup"><span data-stu-id="3546a-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="3546a-171">Es gibt [sechs Arten von Status](system.md#status-types) für Aufgaben/Prozesse.</span><span class="sxs-lookup"><span data-stu-id="3546a-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="3546a-172">Darüber hinaus [hängen die meisten Prozesse von anderen nachfolgenden Prozessen ab](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="3546a-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="3546a-173">Sie können den Status eines Prozesses auswählen, um Details zum Fortschritt des gesamten Auftrags anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3546a-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="3546a-174">Nach der Auswahl von **Siehe Details** für eine der Aufgaben des Auftrags finden Sie zusätzliche Informationen: Verarbeitungszeit, das letzte Verarbeitungsdatum sowie alle mit der Aufgabe verbundenen Fehler und Warnungen.</span><span class="sxs-lookup"><span data-stu-id="3546a-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="3546a-175">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="3546a-175">Next Step</span></span>

<span data-ttu-id="3546a-176">Konfigurieren von [Aktivitäten](activities.md), [Anreicherung](enrichment-hub.md), oder [Beziehungen](relationships.md), um mehr Einblicke über Ihre Kunden zu gewinnen.</span><span class="sxs-lookup"><span data-stu-id="3546a-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="3546a-177">Wenn Sie bereits Aktivitäten, Anreicherungen oder Segmente konfiguriert haben, werden diese automatisch verarbeitet, um die neuesten Kundendaten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3546a-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
