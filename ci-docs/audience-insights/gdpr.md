---
title: Anträge zu den Rechten des Datensubjekts (DSR) gemäß der DSGVO | Microsoft Docs
description: Reagieren Sie auf Anfragen von betroffenen Personen für die Funktionalität Dynamics 365 Customer Insights Zielgruppen-Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405781"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="00aac-103">Daten-abhängige Rechteanforderungen unter DSGVO</span><span class="sxs-lookup"><span data-stu-id="00aac-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="00aac-104">Reagieren auf DSGVO-Löschanfragen von betroffenen Personen für Dynamics 365 Customer Insights Zielgruppen-Insights-Funktionalitäten</span><span class="sxs-lookup"><span data-stu-id="00aac-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="00aac-105">Das "Recht auf Löschung" durch die Entfernung persönlicher Daten aus den Kundendaten eines Unternehmens ist ein wichtiger Schutz in der Datenschutz-Grundverordnung (DSGVO).</span><span class="sxs-lookup"><span data-stu-id="00aac-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="00aac-106">Durch das Entfernen von persönlichen Daten zählen alle persönlichen Daten und vom System generierte Protokolle, ausgenommen Überwachungsprotokollinformationen.</span><span class="sxs-lookup"><span data-stu-id="00aac-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="00aac-107">Verwaltung von Löschungsanträgen von Betroffenen</span><span class="sxs-lookup"><span data-stu-id="00aac-107">Manage data subject delete requests</span></span>

<span data-ttu-id="00aac-108">Zielgruppen-Insights bietet die folgenden produktinternen Erfahrungen, um persönliche Daten für einen bestimmten Kunden oder Benutzer zu löschen:</span><span class="sxs-lookup"><span data-stu-id="00aac-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="00aac-109">**Löschanträge für Kundendaten verwalten**: Kundendaten in Customer Insights werden aus Originaldatenquellen außerhalb von Customer Insights aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="00aac-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="00aac-110">Alle DSGVO-Löschungsanfragen müssen in der ursprünglichen Datenquelle durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="00aac-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="00aac-111">**Löschanfragen für Customer Insights-Benutzerdaten verwalten**: Daten für Benutzer werden von Customer Insights erstellt.</span><span class="sxs-lookup"><span data-stu-id="00aac-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="00aac-112">Alle DSGVO-Löschungsanfragen müssen in Customer Insights durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="00aac-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="00aac-113">Verwalten von Löschanforderungen für Kundendaten</span><span class="sxs-lookup"><span data-stu-id="00aac-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="00aac-114">Ein Administrator von Customer Insights kann die folgenden Schritte ausführen, um Kundendaten zu entfernen, die in der Datenquelle gelöscht wurden:</span><span class="sxs-lookup"><span data-stu-id="00aac-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="00aac-115">Melden Sie sich bei Dynamics 365 Customer Insights an.</span><span class="sxs-lookup"><span data-stu-id="00aac-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="00aac-116">Gehen Sie in Zielgruppen-Insights zu **Daten** > **Datenquellen**</span><span class="sxs-lookup"><span data-stu-id="00aac-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="00aac-117">Für jede Datenquelle in der Liste, die gelöschte Kundendaten enthält:</span><span class="sxs-lookup"><span data-stu-id="00aac-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="00aac-118">Wählen Sie (...) und wählen Sie dann **Aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="00aac-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="00aac-119">Überprüfen Sie den Status der Datenquelle unter **Status**.</span><span class="sxs-lookup"><span data-stu-id="00aac-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="00aac-120">Ein Häkchen bedeutet, dass die Aktualisierung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="00aac-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="00aac-121">Ein Warndreieck bedeutet, dass etwas schief gelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="00aac-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="00aac-122">Wenn ein Warndreieck angezeigt wird, wenden Sie sich an D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="00aac-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="00aac-123">![Behandlung von DSGVO-Löschanträgen für Kundendaten](media/gdpr-data-sources.png "Behandlung von DSGVO-Löschungsanträgen für Kundendaten")</span><span class="sxs-lookup"><span data-stu-id="00aac-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="00aac-124">Verwalten von Löschanfragen für Benutzerdaten</span><span class="sxs-lookup"><span data-stu-id="00aac-124">Manage delete requests for user data</span></span>

<span data-ttu-id="00aac-125">Ein Customer Insights-Administrator kann folgende Schritte durchführen, um Customer Insights-Benutzerdaten zu löschen:</span><span class="sxs-lookup"><span data-stu-id="00aac-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="00aac-126">Melden Sie sich bei Dynamics 365 Customer Insights an.</span><span class="sxs-lookup"><span data-stu-id="00aac-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="00aac-127">Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Berechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="00aac-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="00aac-128">Markieren Sie das Kontrollkästchen für den Benutzer, den Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="00aac-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="00aac-129">Klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="00aac-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="00aac-130">![Handhabung von DSGVO-Löschanfragen für Benutzerdaten](media/gdpr-permissions.png "Handhabung von DSGVO-Löschanfragen für Benutzerdaten")</span><span class="sxs-lookup"><span data-stu-id="00aac-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="00aac-131">Reagieren auf DSGVO-Exportanfragen von Datensubjekten</span><span class="sxs-lookup"><span data-stu-id="00aac-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="00aac-132">Als Teil unserer Verpflichtung, Sie auf Ihrem Weg zur Datenschutz-Grundverordnung (DSGVO) zu begleiten, haben wir eine Dokumentation entwickelt, die Ihnen bei der Vorbereitung hilft.</span><span class="sxs-lookup"><span data-stu-id="00aac-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="00aac-133">Diese Dokumentation beschreibt Schritte, die Sie heute unternehmen können, um die Einhaltung der DSGVO zu unterstützen, wenn Sie Zielgruppen-Insights verwenden.</span><span class="sxs-lookup"><span data-stu-id="00aac-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="00aac-134">Verwalten von Export- und Anzeigeanforderungen</span><span class="sxs-lookup"><span data-stu-id="00aac-134">Manage export and view requests</span></span>

<span data-ttu-id="00aac-135">Das Recht auf Datenportabilität ermöglicht es den betroffenen Personen, eine Kopie ihrer persönlichen Daten in einem elektronischen Format (ein "strukturiertes, allgemein verwendetes, maschinenlesbares und interoperables Format") anzufordern, das an einen anderen für die Datenverarbeitung Verantwortlichen übermittelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="00aac-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="00aac-136">Kundendaten exportieren (Mandantenverwaltung)</span><span class="sxs-lookup"><span data-stu-id="00aac-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="00aac-137">Ein Mandanten-Administrator kann diese Schritte befolgen, um Daten zu exportieren:</span><span class="sxs-lookup"><span data-stu-id="00aac-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="00aac-138">Senden Sie eine E-Mail an D365CI@microsoft.com und geben Sie die E-Mail-Adresse des Kunden in der Anfrage an.</span><span class="sxs-lookup"><span data-stu-id="00aac-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="00aac-139">Das Customer Insights-Team sendet eine E-Mail an die registrierte Admin-E-Mail-Adresse des Mandanten und bittet um eine Bestätigung für den Datenexport.</span><span class="sxs-lookup"><span data-stu-id="00aac-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="00aac-140">Bestätigen Sie die Meldung zum Export der Daten für den angeforderten Kunden.</span><span class="sxs-lookup"><span data-stu-id="00aac-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="00aac-141">Erhalten Sie die exportierten Daten über die E-Mail-Adresse des Mandantenverwalters.</span><span class="sxs-lookup"><span data-stu-id="00aac-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="00aac-142">Benutzerdaten exportieren (Mandant Admin)</span><span class="sxs-lookup"><span data-stu-id="00aac-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="00aac-143">Senden Sie eine E-Mail an D365CI@microsoft.com, wobei Sie die E-Mail-Adresse des Benutzers in der Anfrage angeben.</span><span class="sxs-lookup"><span data-stu-id="00aac-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="00aac-144">Das Customer Insights-Team sendet eine E-Mail an die registrierte Admin-E-Mail-Adresse des Mandanten und bittet um eine Bestätigung für den Datenexport.</span><span class="sxs-lookup"><span data-stu-id="00aac-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="00aac-145">Bestätigen Sie die Meldung, um die Daten für den angeforderten Benutzer zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="00aac-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="00aac-146">Erhalten Sie die exportierten Daten über die E-Mail-Adresse des Mandantenverwalters.</span><span class="sxs-lookup"><span data-stu-id="00aac-146">Receive the exported data through the tenant admin email address.</span></span>
