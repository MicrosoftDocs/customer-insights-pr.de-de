---
title: Verbindungen zu anderen Diensten von Customer Insights.
description: Daten an andere Dienste weitergeben.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304971"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="9982b-103">Verbindungsübersicht (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="9982b-103">Connections (preview) overview</span></span>

<span data-ttu-id="9982b-104">Verbindungen sind der Schlüssel, um die gemeinsame Nutzung von Daten zu und von Customer Insights zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9982b-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="9982b-105">Jede Verbindung stellt die gemeinsame Nutzung von Daten mit einem bestimmten Dienst her.</span><span class="sxs-lookup"><span data-stu-id="9982b-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="9982b-106">Verbindungen sind das Fundament zum [Konfigurieren von Anreicherungen von Drittanbietern](enrichment-hub.md) und [Konfigurieren von Exporten](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="9982b-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="9982b-107">Dieselbe Verbindung kann mehrfach verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9982b-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="9982b-108">Beispielsweise funktioniert eine Verbindung zu Dynamics 365 Marketing für mehrere Exporte, und eine Leadspace-Verbindung kann für mehrere Anreicherungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9982b-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="9982b-109">Gehen Sie zu **Administrator** > **Verbindungen**, um Verbindungen zu erstellen und anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9982b-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="9982b-110">Die Registerkarte **Verbindungen** zeigt Ihnen alle aktiven Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="9982b-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="9982b-111">Die Liste zeigt eine Zeile für jede Verbindung.</span><span class="sxs-lookup"><span data-stu-id="9982b-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="9982b-112">Verschaffen Sie sich einen schnellen Überblick, erhalten Sie eine Beschreibung, und finden Sie heraus, was Sie mit den einzelnen Erweiterungsoptionen auf der Registerkarte **Entdecken** tun können.</span><span class="sxs-lookup"><span data-stu-id="9982b-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="9982b-113">Exporte</span><span class="sxs-lookup"><span data-stu-id="9982b-113">Exports</span></span>

<span data-ttu-id="9982b-114">Nur Administratoren können neue Verbindungen konfigurieren, sie können jedoch Mitwirkenden Zugriff gewähren, um vorhandene Verbindungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9982b-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="9982b-115">Administratoren steuern, wohin Daten gehen können, und die Mitwirkenden definieren die Nutzlast und Häufigkeit, die ihren Anforderungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9982b-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="9982b-116">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9982b-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="9982b-117">Anreicherungen</span><span class="sxs-lookup"><span data-stu-id="9982b-117">Enrichments</span></span>

<span data-ttu-id="9982b-118">Nur Administratoren können neue Verbindungen konfigurieren, aber die erstellten Verbindungen stehen sowohl Administratoren als auch Mitwirkenden immer zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="9982b-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="9982b-119">Administratoren verwalten Anmeldeinformationen und stimmen der Datenübertragung zu.</span><span class="sxs-lookup"><span data-stu-id="9982b-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="9982b-120">Die Verbindungen können dann sowohl von Administratoren als auch von Mitwirkenden zur Bereicherung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9982b-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="9982b-121">Eine neue Verbindung hinzufügen</span><span class="sxs-lookup"><span data-stu-id="9982b-121">Add a new connection</span></span>

<span data-ttu-id="9982b-122">Um Verbindungen hinzuzufügen, müssen Sie [Administratorberechtigungen](permissions.md) haben.</span><span class="sxs-lookup"><span data-stu-id="9982b-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="9982b-123">Wenn Sie eine Verbindung zu anderen Microsoft-Diensten herstellen, gehen wir davon aus, dass sich beide Dienste in derselben Organisation befinden.</span><span class="sxs-lookup"><span data-stu-id="9982b-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="9982b-124">Gehen Sie zu **Administrator** > **Verbindungen (Vorschau)**.</span><span class="sxs-lookup"><span data-stu-id="9982b-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="9982b-125">Zur Registerkarte **Verbindungen** wechseln.</span><span class="sxs-lookup"><span data-stu-id="9982b-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="9982b-126">Wählen Sie zu **Verbindung hinzufügen**, um eine neue Verbindung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9982b-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="9982b-127">Wählen Sie aus dem Dropdown-Menü aus, welche Art von Verbindung Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="9982b-127">Choose from the dropdown menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="9982b-128">Im Bereich **Verbindung herstellen** geben Sie die erforderlichen Details an.</span><span class="sxs-lookup"><span data-stu-id="9982b-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="9982b-129">Der **Anzeigename** und der Typ der Verbindung beschreiben eine Verbindung.</span><span class="sxs-lookup"><span data-stu-id="9982b-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="9982b-130">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel dieser Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="9982b-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="9982b-131">Die genauen Felder hängen davon ab, zu welchem Dienst Sie eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="9982b-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="9982b-132">Einzelheiten zu einem bestimmten Verbindungstyp finden Sie im Artikel über den Zieldienst.</span><span class="sxs-lookup"><span data-stu-id="9982b-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="9982b-133">Wählen Sie zum Erstellen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="9982b-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="9982b-134">Sie können auch auf einer Kachel **Installieren** in der Registerkarte **Entdecken** auswählen.</span><span class="sxs-lookup"><span data-stu-id="9982b-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="9982b-135">Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden</span><span class="sxs-lookup"><span data-stu-id="9982b-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="9982b-136">Beim Einrichten oder Bearbeiten einer Exportverbindung legen Sie fest, welche Benutzer diese bestimmte Verbindung zum Definieren von [Exporten](export-destinations.md) verwenden dürfen.</span><span class="sxs-lookup"><span data-stu-id="9982b-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="9982b-137">Standardmäßig steht Benutzern mit der Rolle „Administrator“ eine Verbindung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="9982b-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="9982b-138">Sie können diese Einstellung unter **Wählen Sie aus, wer diese Verbindung verwenden kann** ändern und Benutzern mit der Rolle „Mitwirkender“ erlauben, diese Verbindung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9982b-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="9982b-139">Mitwirkende können die Verbindung nicht anzeigen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="9982b-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="9982b-140">Sie sehen nur den Anzeigenamen und seinen Typ, wenn Sie einen Export erstellen.</span><span class="sxs-lookup"><span data-stu-id="9982b-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="9982b-141">Durch die Freigabe einer Verbindung können Mitwirkende eine Verbindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="9982b-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="9982b-142">Mitwirkende sehen gemeinsame Verbindungen, wenn sie Exporte einrichten.</span><span class="sxs-lookup"><span data-stu-id="9982b-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="9982b-143">Sie können jeden Export verwalten, der diese bestimmte Verbindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="9982b-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="9982b-144">Sie können diese Einstellung ändern, während Sie die Exporte beibehalten, die bereits von Mitwirkenden definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="9982b-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="9982b-145">Eine Verbindung bearbeiten</span><span class="sxs-lookup"><span data-stu-id="9982b-145">Edit a connection</span></span>

1. <span data-ttu-id="9982b-146">Gehen Sie zu **Administrator** > **Verbindungen (Vorschau)**.</span><span class="sxs-lookup"><span data-stu-id="9982b-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="9982b-147">Zur Registerkarte **Verbindungen** wechseln.</span><span class="sxs-lookup"><span data-stu-id="9982b-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="9982b-148">Wählen Sie die vertikale Auslassung für die Verbindung aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="9982b-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="9982b-149">Wählen Sie **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="9982b-149">Select **Edit**.</span></span>

1. <span data-ttu-id="9982b-150">Ändern Sie die gewünschten Werte zur Aktualisierung und wählen **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="9982b-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="9982b-151">Verbindung entfernen</span><span class="sxs-lookup"><span data-stu-id="9982b-151">Remove a connection</span></span>

<span data-ttu-id="9982b-152">Wenn die Verbindung, die Sie entfernen, von Anreicherungen oder Exporten verwendet wird, müssen Sie diese zuerst trennen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="9982b-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="9982b-153">Das Dialogfeld „Entfernen“ führt Sie zu den relevanten Anreicherungen oder Exporten.</span><span class="sxs-lookup"><span data-stu-id="9982b-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> 

<span data-ttu-id="9982b-154">Abgelöste Anreicherungen und Exporte werden inaktiv.</span><span class="sxs-lookup"><span data-stu-id="9982b-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="9982b-155">Sie reaktivieren sie, indem Sie ihnen eine weitere Verbindung auf den Seiten [Anreicherungen](enrichment-hub.md) oder [Exporte](export-destinations.md) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9982b-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="9982b-156">Gehen Sie zu **Administrator** > **Verbindungen (Vorschau)**.</span><span class="sxs-lookup"><span data-stu-id="9982b-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="9982b-157">Zur Registerkarte **Verbindungen** wechseln.</span><span class="sxs-lookup"><span data-stu-id="9982b-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="9982b-158">Wählen Sie die vertikale Auslassung für die Verbindung aus, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="9982b-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="9982b-159">Klicken Sie im Dropdown-Menü auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="9982b-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="9982b-160">Ein Bestätigungsdialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9982b-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="9982b-161">Wenn über diese Verbindung Anreicherungen oder Exporte erfolgen, klicken Sie auf die Schaltfläche, um zu sehen, was die Verbindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="9982b-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="9982b-162">**Exporte:** Sie können die Exporte entweder entfernen oder trennen, um die Verbindung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="9982b-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="9982b-163">Um einen Export zu trennen, können Administratoren die **Trennen**-Aktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="9982b-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="9982b-164">Diese Aktion ist für einzelne und mehrere ausgewählte Exporte verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9982b-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="9982b-165">Wenn Sie die Verbindung trennen, behalten Sie die Exportkonfiguration bei, sie wird jedoch erst ausgeführt, wenn eine weitere Verbindung hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="9982b-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="9982b-166">**Anreicherungen:** Sie können die Anreicherungen entweder entfernen oder deaktivieren, um die Verbindung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="9982b-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="9982b-167">Wenn die Verbindung keine Abhängigkeiten mehr aufweist, kehren Sie zu **Administrator** > **Verbindungen** zurück, und versuchen Sie erneut, die Verbindung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="9982b-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="9982b-168">Um den Löschvorgang zu bestätigen, wählen Sie **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="9982b-168">To confirm the deletion, select **Remove**.</span></span>

