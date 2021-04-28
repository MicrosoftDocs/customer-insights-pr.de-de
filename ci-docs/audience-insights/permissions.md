---
title: Verwalten von Benutzerberechtigungen
description: Erfahren Sie mehr über Berechtigungen und Benutzerrollen.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8638489dba908d4504278916d2c28454e3ea9e18
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760372"
---
# <a name="user-permissions"></a><span data-ttu-id="340ee-103">Benutzerberechtigungen</span><span class="sxs-lookup"><span data-stu-id="340ee-103">User permissions</span></span>

<span data-ttu-id="340ee-104">Auf der Seite **Berechtigungen** richten Sie Rollen und Berechtigungen für die Verwendung von Zielgruppen-Insights ein.</span><span class="sxs-lookup"><span data-stu-id="340ee-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="340ee-105">Sie benötigen Administratorberechtigungen, um diese Seite zu sehen.</span><span class="sxs-lookup"><span data-stu-id="340ee-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="340ee-106">Um auf die Seite mit den Berechtigungen in Zielgruppen-Insights zuzugreifen, gehen Sie zu **Admin** > **Berechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="340ee-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="340ee-107">Es gibt drei Arten von Rollen:</span><span class="sxs-lookup"><span data-stu-id="340ee-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="340ee-108">Zuschauer</span><span class="sxs-lookup"><span data-stu-id="340ee-108">Viewer</span></span>

- <span data-ttu-id="340ee-109">Erkunden Sie Insights und Segmente innerhalb der Seiten **Home** und **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="340ee-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="340ee-110">Suchen und filtern Sie Kundenprofile mit Hilfe der Seite **Kunden**.</span><span class="sxs-lookup"><span data-stu-id="340ee-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="340ee-111">Felder müssen durchsuchbar sein.</span><span class="sxs-lookup"><span data-stu-id="340ee-111">Fields must be searchable.</span></span>
- <span data-ttu-id="340ee-112">Erkunden Sie die Seite **Bereicherung**.</span><span class="sxs-lookup"><span data-stu-id="340ee-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="340ee-113">Erforschen und exportieren Sie Entitäten mit Hilfe der Seite **Entitäten**.</span><span class="sxs-lookup"><span data-stu-id="340ee-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="340ee-114">Den Status von Systemprozessen können Sie über die Seite **System** einsehen.</span><span class="sxs-lookup"><span data-stu-id="340ee-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="340ee-115">Exporte auf der Seite **Exporte** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="340ee-115">View exports in **Exports** page.</span></span>
- <span data-ttu-id="340ee-116">Installieren und verwenden Sie das **Power BI Customer Insights** Dashboard.</span><span class="sxs-lookup"><span data-stu-id="340ee-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="340ee-117">Beitragender</span><span class="sxs-lookup"><span data-stu-id="340ee-117">Contributor</span></span>

- <span data-ttu-id="340ee-118">Alle dem Betrachter zur Verfügung stehenden Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="340ee-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="340ee-119">Laden und transformieren Sie die Daten mithilfe der Seite **Datenquellen**.</span><span class="sxs-lookup"><span data-stu-id="340ee-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="340ee-120">Vervollständigen Sie die Abschnitte *Datenvereinheitlichung* (**Zuordnen**, **Abgleichen** und **Zusammenführen**), die zu der vereinheitlichten Entität „Kundenprofil“ führen.</span><span class="sxs-lookup"><span data-stu-id="340ee-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="340ee-121">Definieren Sie **Beziehungen** und **Aktivitäten**.</span><span class="sxs-lookup"><span data-stu-id="340ee-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="340ee-122">Erstellen Sie Segmente mit der Seite **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="340ee-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="340ee-123">Legen Sie Kennzahlen mit Hilfe der Seite **Kennzahlen** an.</span><span class="sxs-lookup"><span data-stu-id="340ee-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="340ee-124">Verwalten Sie die Konfiguration und reichern Sie Kundenprofile über die Seite **Anreicherung** an (nur für First-Party-Anreicherungen).</span><span class="sxs-lookup"><span data-stu-id="340ee-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>
- <span data-ttu-id="340ee-125">Verwalten und erstellen Sie Exporte basierend auf Verbindungen, die mit Mitwirkenden geteilt werden.</span><span class="sxs-lookup"><span data-stu-id="340ee-125">Manage and create exports based on connections shared with contributors.</span></span> <span data-ttu-id="340ee-126">[Erfahren Sie mehr darüber, wie Administratoren Mitwirkenden erlauben, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="340ee-126">[Learn more about how administrators allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

## <a name="administrator"></a><span data-ttu-id="340ee-127">Administrator</span><span class="sxs-lookup"><span data-stu-id="340ee-127">Administrator</span></span>

- <span data-ttu-id="340ee-128">Alle dem Beitragenden zur Verfügung stehenden Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="340ee-128">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="340ee-129">Ändern Sie die Einstellungen auf der Seite **System**, einschließlich der Arbeitssprache und der Aktualisierungszeitpläne für Ihre Systemprozesse.</span><span class="sxs-lookup"><span data-stu-id="340ee-129">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="340ee-130">Anzeigen und Hinzufügen von Berechtigungen über die Seite **Berechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="340ee-130">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="340ee-131">Legen Sie Such- und Filterdefinitionen für die Seite „Kunden“ über die Seite **Such- & Filterindex** fest (Zugriff über die Seite **Kunden**).</span><span class="sxs-lookup"><span data-stu-id="340ee-131">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="340ee-132">Verwalten Sie Verbindungen und lassen Sie sie für andere Benutzerrollen auf der Seite **Verbindungen** zu.</span><span class="sxs-lookup"><span data-stu-id="340ee-132">Manage connections and allow them for other user roles on **Connections** page.</span></span>
- <span data-ttu-id="340ee-133">Verwalten Sie die Konfiguration und reichern Sie Kundenprofile über die Seite **Anreicherung** an (für alle Anreicherungen).</span><span class="sxs-lookup"><span data-stu-id="340ee-133">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="340ee-134">Verwalten und Erstellen von Exporten auf der **Exporte**-Seite.</span><span class="sxs-lookup"><span data-stu-id="340ee-134">Manage and create exports on **Exports** page.</span></span>
- <span data-ttu-id="340ee-135">Installieren und verwenden Sie das **Kundenkarten-Add-in**.</span><span class="sxs-lookup"><span data-stu-id="340ee-135">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="340ee-136">Fügen Sie den **Power Apps-Konnektor** hinzu und verwenden Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="340ee-136">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="340ee-137">Aktivieren Sie die Verwendung der [Customer Insights APIs](apis.md).</span><span class="sxs-lookup"><span data-stu-id="340ee-137">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="340ee-138">Rollen und Berechtigungen zuweisen</span><span class="sxs-lookup"><span data-stu-id="340ee-138">Assign roles and permissions</span></span>

1. <span data-ttu-id="340ee-139">Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Berechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="340ee-139">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="340ee-140">Wählen Sie **Benutzer hinzufügen**, um den Bereich **Berechtigungen hinzufügen/bearbeiten** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="340ee-140">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="340ee-141">Verwenden Sie das Feld **Suchen**, um den Benutzer oder die Gruppe Azure Active Directory zu finden, deren Berechtigungen Sie anpassen möchten.</span><span class="sxs-lookup"><span data-stu-id="340ee-141">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="340ee-142">Wählen Sie ein **Rolle**, das Sie diesem Benutzer oder dieser Gruppe zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="340ee-142">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="340ee-143">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="340ee-143">Select **Save**.</span></span> <span data-ttu-id="340ee-144">Die aktuelle Umgebung wird automatisch für den Benutzer oder die Mitglieder der Gruppe freigegeben, deren Berechtigungen Sie geändert haben.</span><span class="sxs-lookup"><span data-stu-id="340ee-144">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="340ee-145">Benutzer können auf die Customer Insights App zugreifen und entsprechend ihrer angegebenen Rolle arbeiten.</span><span class="sxs-lookup"><span data-stu-id="340ee-145">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="340ee-146">Aktuelle Berechtigungen anzeigen</span><span class="sxs-lookup"><span data-stu-id="340ee-146">View current permissions</span></span>

<span data-ttu-id="340ee-147">Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Berechtigungen**, um zu sehen, welche Rollenzuweisungen gerade aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="340ee-147">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="340ee-148">Die Spalte **Typ** gibt einen einzelnen Benutzer, eine Gruppe oder eine Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="340ee-148">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="340ee-149">Das System unterstützt einzelne Benutzer und Gruppen.</span><span class="sxs-lookup"><span data-stu-id="340ee-149">The system supports individual users and groups.</span></span>
- <span data-ttu-id="340ee-150">Die Rollen werden in der Spalte **Rolle** angegeben.</span><span class="sxs-lookup"><span data-stu-id="340ee-150">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="340ee-151">Wählen Sie einen beliebigen Spaltentitel, um die Ergebnisse nach dem Wert dieser Spalte zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="340ee-151">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="340ee-152">Verwenden Sie das Feld **Suchen** oben auf der Seite, um bestimmte Benutzer zu finden.</span><span class="sxs-lookup"><span data-stu-id="340ee-152">Use the **Search** field at the top of the page to locate specific users.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
