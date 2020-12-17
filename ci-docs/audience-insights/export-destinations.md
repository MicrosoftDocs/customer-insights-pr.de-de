---
title: Exportziele
description: Daten exportieren und Exportziele verwalten.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643862"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="a98f5-103">Exportziele (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="a98f5-103">Export destinations (preview)</span></span>

<span data-ttu-id="a98f5-104">Die Seite **Exportziele** zeigt Ihnen die Orte, die Sie für den Export von Daten eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="a98f5-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="a98f5-105">Sie können auch neue Ziele für den Export hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a98f5-105">You can also add new destinations for export.</span></span> <span data-ttu-id="a98f5-106">Zusätzlich zeigt es die aktuell verfügbaren Exportoptionen an.</span><span class="sxs-lookup"><span data-stu-id="a98f5-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="a98f5-107">Verschaffen Sie sich einen schnellen Überblick und eine Beschreibung und finden Sie heraus, was Sie mit den einzelnen Erweiterungsoptionen tun können.</span><span class="sxs-lookup"><span data-stu-id="a98f5-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="a98f5-108">Exportieren Sie vereinheitlichte Profile, Messgrößen und Segmente in unterstützte Anwendungen, die für Ihr Unternehmen relevant sind.</span><span class="sxs-lookup"><span data-stu-id="a98f5-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="a98f5-109">Gehen Sie zu **Admin** > **Exportziele**, um die folgenden Erweiterungsoptionen zu finden:</span><span class="sxs-lookup"><span data-stu-id="a98f5-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="a98f5-110">Dynamics 365 Customer Card Add-in</span><span class="sxs-lookup"><span data-stu-id="a98f5-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="a98f5-111">Facebook Ads Manager-Connector</span><span class="sxs-lookup"><span data-stu-id="a98f5-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="a98f5-112">Power AutomateConnector</span><span class="sxs-lookup"><span data-stu-id="a98f5-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="a98f5-113">Power AppsConnector</span><span class="sxs-lookup"><span data-stu-id="a98f5-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="a98f5-114">Power BIConnector</span><span class="sxs-lookup"><span data-stu-id="a98f5-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="a98f5-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="a98f5-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="a98f5-116">Dynamics 365 for Sales</span><span class="sxs-lookup"><span data-stu-id="a98f5-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="a98f5-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="a98f5-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="a98f5-118">Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="a98f5-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="a98f5-119">LiveRamp&reg; Connector</span><span class="sxs-lookup"><span data-stu-id="a98f5-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="a98f5-120">Bot für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a98f5-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="a98f5-121">Mailchimp</span><span class="sxs-lookup"><span data-stu-id="a98f5-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="a98f5-122">Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="a98f5-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="a98f5-123">Neues Exportziel hinzufügen</span><span class="sxs-lookup"><span data-stu-id="a98f5-123">Add a new export destination</span></span>

<span data-ttu-id="a98f5-124">Um Exportziele hinzuzufügen, haben Sie [Administrator-Berechtigungen](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a98f5-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="a98f5-125">Wenn Sie zu Microsoft-Diensten exportieren, gehen wir davon aus, dass sich beide Dienste in derselben Organisation befinden.</span><span class="sxs-lookup"><span data-stu-id="a98f5-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="a98f5-126">Gehen Sie zu **Administrator** > **Exportziele**.</span><span class="sxs-lookup"><span data-stu-id="a98f5-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a98f5-127">Wechseln Sie zur Registerkarte **Meine Exportziele**.</span><span class="sxs-lookup"><span data-stu-id="a98f5-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="a98f5-128">Wählen **Ziel hinzufügen**, um ein neues Exportziel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a98f5-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="a98f5-129">In dem Bereich **Ziel hinzufügen** wählen Sie den **Typ** des Exportziels in der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="a98f5-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="a98f5-130">Geben Sie die erforderlichen Details ein und wählen Sie **Weiter**, um das Exportziel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a98f5-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="a98f5-131">Sie können auch auf einer Kachel **Installieren** in der Registerkarte **Entdecken** auswählen.</span><span class="sxs-lookup"><span data-stu-id="a98f5-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="a98f5-132">Exportziele anzeigen</span><span class="sxs-lookup"><span data-stu-id="a98f5-132">View Export destinations</span></span>

<span data-ttu-id="a98f5-133">Nachdem Sie Exportziele erstellt haben, finden Sie diese in einer Tabelle auf der Registerkarte **Meine Exportziele**. Diese Tabelle enthält drei Spalten:</span><span class="sxs-lookup"><span data-stu-id="a98f5-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="a98f5-134">**Anzeigename**: Der Name, den Sie beim Erstellen des Ziels eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="a98f5-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="a98f5-135">**Typ**:  Der Exportzieltyp, den Sie beim Erstellen des Ziels festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="a98f5-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="a98f5-136">**Erstellt am**: Das Datum, an dem das Ziel erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a98f5-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="a98f5-137">Ein Exportziel bearbeiten</span><span class="sxs-lookup"><span data-stu-id="a98f5-137">Edit an export destination</span></span>

1. <span data-ttu-id="a98f5-138">Wählen Sie die vertikale Auslassung für das Exportziel aus, das Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="a98f5-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a98f5-139">![Vertikale Ellipsen](media/export-destinations-page-ellipsis.png "Vertikale Ellipsen")</span><span class="sxs-lookup"><span data-stu-id="a98f5-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="a98f5-140">Wählen Sie **Bearbeiten** aus dem Dropdown-Menü aus.</span><span class="sxs-lookup"><span data-stu-id="a98f5-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="a98f5-141">Ändern Sie die zu aktualisierenden Werte und wählen Sie **speichern**.</span><span class="sxs-lookup"><span data-stu-id="a98f5-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="a98f5-142">Daten nach Bedarf exportieren</span><span class="sxs-lookup"><span data-stu-id="a98f5-142">Export data on demand</span></span>

<span data-ttu-id="a98f5-143">Nach dem Konfigurieren eines Connectors für ein Exportziel werden die Exporte mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a98f5-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="a98f5-144">Um Daten zu exportieren, ohne auf eine geplante Aktualisierung zu warten, gehen Sie zur Regisgerkarte **Meine Exportziele** unter **Administrator** > **Ziele exportieren**.</span><span class="sxs-lookup"><span data-stu-id="a98f5-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a98f5-145">![Vertikale Ellipsen](media/export-destinations-page-ellipsis.png "Vertikale Ellipsen")</span><span class="sxs-lookup"><span data-stu-id="a98f5-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="a98f5-146">Wählen Sie **Exportieren** oben in der Liste aus, um den Export zu allen Exportzielen gleichzeitig auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a98f5-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="a98f5-147">Wählen Sie die Auslassungspunkte (...) nach einem Listenelement aus und wählen Sie dann die Option **Exportieren** zum Ausführen des Exports für ein einzelnes Exportziel.</span><span class="sxs-lookup"><span data-stu-id="a98f5-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="a98f5-148">Ein Exportziel entfernen</span><span class="sxs-lookup"><span data-stu-id="a98f5-148">Remove an Export destination</span></span>

<span data-ttu-id="a98f5-149">Um ein Exportziel zu entfernen, beginnen Sie auf der Hauptseite **Exportziele**.</span><span class="sxs-lookup"><span data-stu-id="a98f5-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="a98f5-150">Wählen Sie die vertikale Auslassung für das Exportziel aus, das Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="a98f5-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a98f5-151">![Vertikale Ellipsen](media/export-destinations-page-ellipsis.png "Vertikale Ellipsen")</span><span class="sxs-lookup"><span data-stu-id="a98f5-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="a98f5-152">Klicken Sie im Dropdown-Menü auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="a98f5-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="a98f5-153">Bestätigen Sie das Entfernen, indem Sie **Entfernen** auf dem Bestätigungsbildschirm wählen.</span><span class="sxs-lookup"><span data-stu-id="a98f5-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
