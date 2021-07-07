---
title: Exportieren Sie Daten aus Customer Insights
description: Verwalten Sie Datenexporte, um Daten freizugeben.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305477"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="cfce8-103">Exporte (Vorschau) – Übersicht</span><span class="sxs-lookup"><span data-stu-id="cfce8-103">Exports (preview) overview</span></span>

<span data-ttu-id="cfce8-104">Die Seite **Exporte** zeigt Ihnen alle konfigurierten Exporte.</span><span class="sxs-lookup"><span data-stu-id="cfce8-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="cfce8-105">Exporte teilen bestimmte Daten mit verschiedenen Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="cfce8-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="cfce8-106">Sie können Kundenprofile oder -entitäten, Schemas und Zuordnungsdetails enthalten.</span><span class="sxs-lookup"><span data-stu-id="cfce8-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="cfce8-107">Jeder Export erfordert eine [Verbindung, die von einem Administrator eingerichtet wurde, um die Authentifizierung und den Zugriff zu verwalten](connections.md).</span><span class="sxs-lookup"><span data-stu-id="cfce8-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="cfce8-108">Gehen Sie zu **Daten** > **Exporte**, um die Exportseite anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cfce8-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="cfce8-109">Alle Benutzerrollen können konfigurierte Exporte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="cfce8-109">All user roles can view configured exports.</span></span> <span data-ttu-id="cfce8-110">Verwenden Sie das Suchfeld in der Befehlsleiste, um Exporte anhand ihres Namens, Verbindungsnamens oder Verbindungstyps zu suchen.</span><span class="sxs-lookup"><span data-stu-id="cfce8-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="cfce8-111">Einen neuen Export einrichten</span><span class="sxs-lookup"><span data-stu-id="cfce8-111">Set up a new export</span></span>

<span data-ttu-id="cfce8-112">Um einen Export einzurichten oder zu bearbeiten, müssen Verbindungen verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="cfce8-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="cfce8-113">Verbindungen hängen von Ihrer [Benutzerrolle](permissions.md) ab:</span><span class="sxs-lookup"><span data-stu-id="cfce8-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="cfce8-114">Administratoren haben Zugriff auf alle Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="cfce8-114">Administrators have access to all connections.</span></span> <span data-ttu-id="cfce8-115">Sie können beim Einrichten eines Exports auch neue Verbindungen herstellen.</span><span class="sxs-lookup"><span data-stu-id="cfce8-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="cfce8-116">Mitwirkende können auf bestimmte Verbindungen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="cfce8-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="cfce8-117">Sie hängen von Administratoren ab, um Verbindungen zu konfigurieren und gemeinsam zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="cfce8-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="cfce8-118">Die Exportliste zeigt den Mitwirkenden an, ob sie einen Export bearbeiten oder nur in der Spalte **Ihre Berechtigungen** anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="cfce8-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="cfce8-119">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="cfce8-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="cfce8-120">Betrachter können nur vorhandene Exporte anzeigen, aber nicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="cfce8-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="cfce8-121">Definieren eines neuen Exports</span><span class="sxs-lookup"><span data-stu-id="cfce8-121">Define a new export</span></span>

1. <span data-ttu-id="cfce8-122">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="cfce8-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="cfce8-123">Wählen Sie **Export hinzufügen** aus, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cfce8-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="cfce8-124">Im Bereich **Export einrichten** wählen Sie aus, welche Verbindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cfce8-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="cfce8-125">[Verbindungen](connections.md) werden von Administratoren verwaltet.</span><span class="sxs-lookup"><span data-stu-id="cfce8-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="cfce8-126">Geben Sie die erforderlichen Details ein und wählen Sie **Speichern**, um den Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cfce8-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="cfce8-127">Definieren eines neuen Exports basierend auf einem vorhandenen Export</span><span class="sxs-lookup"><span data-stu-id="cfce8-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="cfce8-128">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="cfce8-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="cfce8-129">Wählen Sie in der Liste der Exporte den Export aus, den Sie duplizieren möchten.</span><span class="sxs-lookup"><span data-stu-id="cfce8-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="cfce8-130">Wählen Sie in der Befehlsleiste **Duplikat erstellen** aus, um den Bereich **Export einrichten** mit den Details des ausgewählten Exports zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="cfce8-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="cfce8-131">Überprüfen und passen Sie den Export an und wählen Sie **Speichern** aus, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cfce8-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="cfce8-132">Einen Export bearbeiten</span><span class="sxs-lookup"><span data-stu-id="cfce8-132">Edit an export</span></span>

1. <span data-ttu-id="cfce8-133">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="cfce8-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="cfce8-134">Wählen Sie in der Liste der Exporte den Export aus, den Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="cfce8-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="cfce8-135">Wählen Sie in der Befehlsleiste **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="cfce8-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="cfce8-136">Ändern Sie die gewünschten Werte zur Aktualisierung und wählen **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="cfce8-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="cfce8-137">Anzeigen von Exporten und Exportdetails</span><span class="sxs-lookup"><span data-stu-id="cfce8-137">View exports and export details</span></span>

<span data-ttu-id="cfce8-138">Nach dem Erstellen von Exportzielen werden diese unter **Daten** > **Exporte** aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="cfce8-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="cfce8-139">Alle Benutzer können sehen, welche Daten gemeinsam genutzt werden und welchen Status sie haben.</span><span class="sxs-lookup"><span data-stu-id="cfce8-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="cfce8-140">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="cfce8-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="cfce8-141">Benutzer ohne Bearbeitungsberechtigungen wählen **Ansicht** anstatt **Bearbeiten**, um die Exportdetails anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cfce8-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="cfce8-142">Der Seitenbereich zeigt die Konfiguration eines Exports an.</span><span class="sxs-lookup"><span data-stu-id="cfce8-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="cfce8-143">Ohne Bearbeitungsberechtigungen können Sie keine Werte ändern.</span><span class="sxs-lookup"><span data-stu-id="cfce8-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="cfce8-144">Wählen Sie **Schließen** aus, um zur Exportseite zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="cfce8-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="cfce8-145">Planen und Ausführen von Exporten</span><span class="sxs-lookup"><span data-stu-id="cfce8-145">Schedule and run exports</span></span>

<span data-ttu-id="cfce8-146">Jeder von Ihnen konfigurierte Export verfügt über einen Aktualisierungszeitplan.</span><span class="sxs-lookup"><span data-stu-id="cfce8-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="cfce8-147">Während einer Aktualisierung sucht das System nach neuen oder aktualisierten Daten, die in einen Export aufgenommen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cfce8-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="cfce8-148">Standardmäßig werden Exporte als Teil einer jeden [geplanten Systemaktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cfce8-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="cfce8-149">Sie können den Aktualisierungszeitplan anpassen oder deaktivieren, um Exporte manuell auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cfce8-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="cfce8-150">Exportzeitpläne hängen vom Status Ihrer Umgebung ab.</span><span class="sxs-lookup"><span data-stu-id="cfce8-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="cfce8-151">Wenn Aktualisierungen in Bearbeitung von [Abhängigkeiten](system.md#refresh-policies) sind, wenn ein geplanter Export gestartet werden soll, führt das System zuerst die Aktualisierungen durch und führt dann den Export aus.</span><span class="sxs-lookup"><span data-stu-id="cfce8-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="cfce8-152">In der Spalte **Aktualisiert** sehen Sie, wann ein Export letztmalig aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="cfce8-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="cfce8-153">Planen von Exporten</span><span class="sxs-lookup"><span data-stu-id="cfce8-153">Schedule exports</span></span>

<span data-ttu-id="cfce8-154">Sie können benutzerdefinierte Aktualisierungszeitpläne für einzelne Exporte oder mehrere Exporte gleichzeitig definieren.</span><span class="sxs-lookup"><span data-stu-id="cfce8-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="cfce8-155">Der aktuell definierte Zeitplan ist in der Spalte **Zeitplan** der Exportliste angegeben.</span><span class="sxs-lookup"><span data-stu-id="cfce8-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="cfce8-156">Die Berechtigung zum Ändern des Zeitplans ist die gleiche wie für das [Bearbeiten und Definieren von Exporten](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="cfce8-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="cfce8-157">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="cfce8-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="cfce8-158">Wählen Sie den Export aus, den Sie planen möchten.</span><span class="sxs-lookup"><span data-stu-id="cfce8-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="cfce8-159">Wählen Sie in der Befehlsleiste **Planen** aus.</span><span class="sxs-lookup"><span data-stu-id="cfce8-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="cfce8-160">Legen Sie im Bereich **Export planen** die Option **Zeitplanausführung** auf **Ein** fest, um den Export automatisch auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cfce8-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="cfce8-161">Legen Sie die Option auf **Aus** fest, um die Aktualisierung manuell durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="cfce8-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="cfce8-162">Wählen Sie für automatisch aktualisierte Exporte einen Wert für **Wiederholung** aus und geben Sie die Details dafür an.</span><span class="sxs-lookup"><span data-stu-id="cfce8-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="cfce8-163">Die definierte Zeit gilt für alle Wiederholungen.</span><span class="sxs-lookup"><span data-stu-id="cfce8-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="cfce8-164">Dies ist der Zeitpunkt, an dem die Aktualisierung eines Exports beginnen sollte.</span><span class="sxs-lookup"><span data-stu-id="cfce8-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="cfce8-165">Übernehmen und aktivieren Sie Ihre Änderungen, indem Sie **Speichern** auswählen.</span><span class="sxs-lookup"><span data-stu-id="cfce8-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="cfce8-166">Wenn Sie den Zeitplan für mehrere Exporte bearbeiten, müssen Sie unter **Zeitpläne beibehalten oder überschreiben** eine Auswahl treffen:</span><span class="sxs-lookup"><span data-stu-id="cfce8-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="cfce8-167">**Individuelle Zeitpläne beibehalten**: Behalten Sie den zuvor definierten Zeitplan für die ausgewählten Exporte bei und deaktivieren oder aktivieren Sie sie nur.</span><span class="sxs-lookup"><span data-stu-id="cfce8-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="cfce8-168">**Neuen Zeitplan für alle ausgewählten Exporte definieren**: Überschreiben Sie die bestehenden Zeitpläne der ausgewählten Exporte.</span><span class="sxs-lookup"><span data-stu-id="cfce8-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="cfce8-169">Exporte Bedarfsgesteuert ausführen</span><span class="sxs-lookup"><span data-stu-id="cfce8-169">Run exports on demand</span></span>

<span data-ttu-id="cfce8-170">Um Daten zu exportieren, ohne auf eine geplante Aktualisierung zu warten, gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="cfce8-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="cfce8-171">Um alle Exporte auszuführen, wählen Sie **Alle ausführen** in der Befehlsleiste aus.</span><span class="sxs-lookup"><span data-stu-id="cfce8-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="cfce8-172">Diese Aktion führt nur Exporte aus, die über einen aktiven Zeitplan verfügen.</span><span class="sxs-lookup"><span data-stu-id="cfce8-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="cfce8-173">Um einen einzelnen Export auszuführen, wählen Sie ihn in der Liste aus und wählen Sie dann in der Befehlsleiste **Ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="cfce8-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="cfce8-174">So führen Sie Exporte ohne aktiven Zeitplan aus.</span><span class="sxs-lookup"><span data-stu-id="cfce8-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="cfce8-175">Einen Export entfernen</span><span class="sxs-lookup"><span data-stu-id="cfce8-175">Remove an Export</span></span>

1. <span data-ttu-id="cfce8-176">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="cfce8-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="cfce8-177">Wählen Sie den Export aus, den Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="cfce8-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="cfce8-178">Wählen Sie in der Befehlsleiste **Entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="cfce8-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="cfce8-179">Bestätigen Sie das Entfernen, indem Sie **Entfernen** auf dem Bestätigungsbildschirm wählen.</span><span class="sxs-lookup"><span data-stu-id="cfce8-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
