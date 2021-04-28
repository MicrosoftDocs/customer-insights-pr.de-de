---
title: Exportieren Sie Daten aus Customer Insights
description: Verwalten Sie Datenexporte, um Daten freizugeben.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896142"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="e2d61-103">Exporte (Vorschau) – Übersicht</span><span class="sxs-lookup"><span data-stu-id="e2d61-103">Exports (preview) overview</span></span>

<span data-ttu-id="e2d61-104">Die Seite **Exporte** zeigt Ihnen alle konfigurierten Exporte.</span><span class="sxs-lookup"><span data-stu-id="e2d61-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="e2d61-105">Exporte teilen bestimmte Daten mit verschiedenen Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="e2d61-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="e2d61-106">Sie können Kundenprofile oder -entitäten, Schemas und Zuordnungsdetails enthalten.</span><span class="sxs-lookup"><span data-stu-id="e2d61-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="e2d61-107">Jeder Export erfordert eine [Verbindung, die von einem Administrator eingerichtet wurde, um die Authentifizierung und den Zugriff zu verwalten](connections.md).</span><span class="sxs-lookup"><span data-stu-id="e2d61-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e2d61-108">Bis März 2021 stellten Exporte automatisch eine Verbindung zum entsprechenden Dienst her.</span><span class="sxs-lookup"><span data-stu-id="e2d61-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="e2d61-109">Exporte erfordern jetzt eine [Verbindung, die von einem Administrator erstellt und geteilt wurde](connections.md), bevor Sie sie erstellen können.</span><span class="sxs-lookup"><span data-stu-id="e2d61-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="e2d61-110">Gehen Sie zu **Daten** > **Exporte**, um die Exportseite anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e2d61-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="e2d61-111">Alle Benutzerrollen haben Zugriff auf die angezeigten Exporte.</span><span class="sxs-lookup"><span data-stu-id="e2d61-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="e2d61-112">Verwenden Sie das Suchfeld in der Befehlsleiste, um Exporte nach Name, Verbindungsname oder Verbindungstyp zu suchen.</span><span class="sxs-lookup"><span data-stu-id="e2d61-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="e2d61-113">Einen neuen Export einrichten</span><span class="sxs-lookup"><span data-stu-id="e2d61-113">Set up a new export</span></span>

<span data-ttu-id="e2d61-114">Um einen Export einzurichten oder zu bearbeiten, müssen Verbindungen verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="e2d61-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="e2d61-115">Verbindungen hängen von Ihrer [Benutzerrolle](permissions.md) ab:</span><span class="sxs-lookup"><span data-stu-id="e2d61-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="e2d61-116">Administratoren haben Zugriff auf alle Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="e2d61-116">Administrators have access to all connections.</span></span> <span data-ttu-id="e2d61-117">Sie können beim Einrichten eines Exports auch neue Verbindungen herstellen.</span><span class="sxs-lookup"><span data-stu-id="e2d61-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="e2d61-118">Mitwirkende können auf bestimmte Verbindungen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e2d61-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="e2d61-119">Sie hängen von Administratoren ab, um Verbindungen zu konfigurieren und gemeinsam zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="e2d61-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="e2d61-120">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e2d61-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="e2d61-121">Betrachter können nur vorhandene Exporte anzeigen, aber nicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="e2d61-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="e2d61-122">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="e2d61-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e2d61-123">Wählen Sie **Export hinzufügen**, um ein neues Exportziel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e2d61-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="e2d61-124">Im Bereich **Export einrichten** wählen Sie aus, welche Verbindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e2d61-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="e2d61-125">[Verbindungen](connections.md) werden von Administratoren verwaltet.</span><span class="sxs-lookup"><span data-stu-id="e2d61-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="e2d61-126">Geben Sie die erforderlichen Details ein und wählen Sie **Speichern**, um den Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e2d61-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="e2d61-127">Einen Export bearbeiten</span><span class="sxs-lookup"><span data-stu-id="e2d61-127">Edit an export</span></span>

1. <span data-ttu-id="e2d61-128">Wählen Sie die vertikale Auslassung für das Exportziel aus, das Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="e2d61-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="e2d61-129">Wählen Sie **Bearbeiten** aus dem Dropdownmenü aus.</span><span class="sxs-lookup"><span data-stu-id="e2d61-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="e2d61-130">Ändern Sie die gewünschten Werte zur Aktualisierung und wählen **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="e2d61-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="e2d61-131">Exporte anzeigen und Details exportieren</span><span class="sxs-lookup"><span data-stu-id="e2d61-131">View Exports and export details</span></span>

<span data-ttu-id="e2d61-132">Nach dem Erstellen von Exportzielen werden diese in **Daten** > **Exporte** aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="e2d61-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="e2d61-133">Alle Benutzer können sehen, welche Daten gemeinsam genutzt werden und welchen Status sie haben.</span><span class="sxs-lookup"><span data-stu-id="e2d61-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="e2d61-134">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="e2d61-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e2d61-135">Benutzer ohne Bearbeitungsberechtigung wählen **Anzeigen** statt **Bearbeiten** aus, um die Exportdetails anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e2d61-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="e2d61-136">Dieser Seitenbereich zeigt die Einrichtung dieses Exports.</span><span class="sxs-lookup"><span data-stu-id="e2d61-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="e2d61-137">Ohne Bearbeitungsberechtigungen können Sie keine Werte ändern.</span><span class="sxs-lookup"><span data-stu-id="e2d61-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="e2d61-138">Wählen Sie **Schließen** aus, um zur Exportseite zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="e2d61-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="e2d61-139">Exporte Bedarfsgesteuert ausführen</span><span class="sxs-lookup"><span data-stu-id="e2d61-139">Run exports on demand</span></span>

<span data-ttu-id="e2d61-140">Nach dem Konfigurieren eines Exports wird er mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt, solange es eine funktionierende Verbindung gibt.</span><span class="sxs-lookup"><span data-stu-id="e2d61-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="e2d61-141">Um Daten zu exportieren, ohne auf eine geplante Aktualisierung zu warten, gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="e2d61-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="e2d61-142">Sie haben zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="e2d61-142">You have two options:</span></span>

- <span data-ttu-id="e2d61-143">Um alle Exporte auszuführen, wählen Sie **Alle ausführen** in der Befehlsleiste aus.</span><span class="sxs-lookup"><span data-stu-id="e2d61-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="e2d61-144">Um einen einzelnen Export auszuführen, wählen Sie die Auslassungspunkte (...) in einem Listenelement aus und wählen Sie dann **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e2d61-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="e2d61-145">Einen Export entfernen</span><span class="sxs-lookup"><span data-stu-id="e2d61-145">Remove an Export</span></span>

1. <span data-ttu-id="e2d61-146">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="e2d61-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e2d61-147">Wählen Sie die vertikale Auslassung für den Export aus, den Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="e2d61-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="e2d61-148">Klicken Sie im Dropdown-Menü auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="e2d61-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="e2d61-149">Bestätigen Sie das Entfernen, indem Sie **Entfernen** auf dem Bestätigungsbildschirm wählen.</span><span class="sxs-lookup"><span data-stu-id="e2d61-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
