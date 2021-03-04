---
title: Datenerfassung in Echtzeit und Einschränkungen
description: Allgemeine Informationen zu den Funktionalitäten von Zielgruppen-Insights in Echtzeit.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270279"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="963b8-103">Datenerfassung in Echtzeit (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="963b8-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="963b8-104">Mit der Echtzeitfunktion können Sie innerhalb von Sekunden die aktuellen Interaktionen anzeigen, die Ihre Kunden mit Ihren Produkten oder Dienstleistungen durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="963b8-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="963b8-105">[Geplante Aktualisierungen](system.md#schedule-tab) umfassen eine große Anzahl von Datensätzen und mehrere komplexe Operationen.</span><span class="sxs-lookup"><span data-stu-id="963b8-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="963b8-106">Zunächst werden die Daten aus der Datenquelle gezogen.</span><span class="sxs-lookup"><span data-stu-id="963b8-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="963b8-107">Dann werden die Daten vereinheitlicht und mit zusätzlichen Informationen angereichert.</span><span class="sxs-lookup"><span data-stu-id="963b8-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="963b8-108">Jeder Durchlauf dieses Vorgangs kann Minuten bis Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="963b8-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="963b8-109">Die Echtzeit-Funktionalität stellt die Daten sofort zum Verbrauch bereit, bis die nachfolgende geplante Aktualisierung diese Daten aus der Datenquelle zieht.</span><span class="sxs-lookup"><span data-stu-id="963b8-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="963b8-110">Echtzeitaktualisierungen haben eine Ablaufzeit, nach der sie den Wert aus Datenquelle nicht mehr überschreiben:</span><span class="sxs-lookup"><span data-stu-id="963b8-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="963b8-111">Profilaktualisierungen werden 4 Stunden lang aufbewahrt</span><span class="sxs-lookup"><span data-stu-id="963b8-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="963b8-112">Aktivitäten werden 30 Tage lang aufbewahrt</span><span class="sxs-lookup"><span data-stu-id="963b8-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="963b8-113">Diese Werte sind API-Aufrufparameter, die Sie ändern können.</span><span class="sxs-lookup"><span data-stu-id="963b8-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="963b8-114">Sie sollen sicherstellen, dass Ihre Quelldaten eine vertrauenswürdige Quelle bleiben.</span><span class="sxs-lookup"><span data-stu-id="963b8-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="963b8-115">Wenn Sie möchten, dass Echtzeit-Updates länger berücksichtigt werden, müssen Sie sie zu einer Datenquelle hinzufügen, damit sie bei der nächsten geplanten Aktualisierung gezogen werden.</span><span class="sxs-lookup"><span data-stu-id="963b8-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="963b8-116">Echtzeitaktualisierung der Felder des vereinheitlichten Kundenprofils</span><span class="sxs-lookup"><span data-stu-id="963b8-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="963b8-117">Aktualisierte Profile werden innerhalb weniger Sekunden in der Kundenkartenansicht oder einer anderen Visualisierung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="963b8-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="963b8-118">Da Echtzeitvorgänge nach der Datenvereinheitlichung stattfinden, gelten sie nur für die vereinheitlichten Kundenprofile.</span><span class="sxs-lookup"><span data-stu-id="963b8-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="963b8-119">Folglich werden keine Maßnahmen, Segmentmitgliedschaften oder Anreicherungen durch Änderungen des Echtzeitprofils aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="963b8-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="963b8-120">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="963b8-120">Limitations</span></span>

- <span data-ttu-id="963b8-121">Kundenprofile können aktualisiert, aber nicht erstellt oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="963b8-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="963b8-122">Das Exportieren von Echtzeitaktualisierungen auf externe Systeme wie Power BI ist momentan nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="963b8-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="963b8-123">Erstellung von Aktivitäten in Echtzeit</span><span class="sxs-lookup"><span data-stu-id="963b8-123">Real-time creation of activities</span></span>

<span data-ttu-id="963b8-124">Mit der Echtzeit-API können Sie eine neue Aktivität aus Ihrem Quellsystem (einen einzelnen Quelldatensatz) in einem einheitlichen Kundenprofil veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="963b8-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="963b8-125">Die neue Aktivität wird innerhalb von Sekunden als vereinheitlichte Aktivität in der Zeitleiste dieses vereinheitlichten Kundenprofils verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="963b8-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="963b8-126">Sie können die Zeitleiste in der Kundenkartenansicht oder einer anderen von Ihnen konfigurierten Zeitleistenintegration sehen.</span><span class="sxs-lookup"><span data-stu-id="963b8-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="963b8-127">Aktivitäten sind unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="963b8-127">Activities are immutable.</span></span> <span data-ttu-id="963b8-128">Sie ändern sich nicht, wenn sie einmal erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="963b8-128">They don't change once created.</span></span>
> - <span data-ttu-id="963b8-129">Derzeit werden Segmente und Kennzahlen nicht basierend auf der neuen Aktivität aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="963b8-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="963b8-130">Aktivitäten, die nur über die Echtzeit-API hinzugefügt werden, sind nicht Teil des Exports und werden in PowerBI nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="963b8-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="963b8-131">Es gibt zwei Möglichkeiten, sich mit der Echtzeit-API zu verbinden:</span><span class="sxs-lookup"><span data-stu-id="963b8-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="963b8-132">[indirekt](#connect-via-the-dynamics-365-customer-insights-connector) unter Verwendung des [Dynamics 365 Customer Insights-Connectors](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="963b8-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="963b8-133">[direkt](#connect-directly-to-the-real-time-api) mit Code</span><span class="sxs-lookup"><span data-stu-id="963b8-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="963b8-134">Die folgenden Voraussetzungen gelten für beide Methoden:</span><span class="sxs-lookup"><span data-stu-id="963b8-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="963b8-135">Eine Customer Insights-Umgebung</span><span class="sxs-lookup"><span data-stu-id="963b8-135">A Customer Insights environment</span></span>
- <span data-ttu-id="963b8-136">Vereinheitlichte Kundenprofile</span><span class="sxs-lookup"><span data-stu-id="963b8-136">Unified customer profiles</span></span>
- <span data-ttu-id="963b8-137">Aktivitäten konfiguriert und ausgeführt</span><span class="sxs-lookup"><span data-stu-id="963b8-137">Activities configured and run</span></span>
- <span data-ttu-id="963b8-138">Mitwirkender- oder Administratorberechtigungen zur Authentifizierung Ihres Kontos</span><span class="sxs-lookup"><span data-stu-id="963b8-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="963b8-139">Über den Dynamics 365 Customer Insights-Connector verbinden</span><span class="sxs-lookup"><span data-stu-id="963b8-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="963b8-140">Die Echtzeit-API kann Daten von einem dedizierten Power Platform-Connector, dem [Dynamics 365 Customer Insights-Connector](https://docs.microsoft.com/connectors/customerinsights/), erfassen, ohne dass Code geschrieben und bereitgestellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="963b8-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="963b8-141">Der Connector kann dieselben Echtzeitaktionen wie die API ausführen.</span><span class="sxs-lookup"><span data-stu-id="963b8-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="963b8-142">Sie benötigen eine gültige Lizenz für Premium-Connectors.</span><span class="sxs-lookup"><span data-stu-id="963b8-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="963b8-143">Weitere Informationen finden Sie unter [FAQs zur Power Apps- und Power Automate-Lizenzierung](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="963b8-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="963b8-144">Power Platform [Power Apps und/oder Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="963b8-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="963b8-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="963b8-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="963b8-146">Einzelheiten zum Erstellen von Flows finden Sie in der [Power Automate-Dokumentation](https://docs.microsoft.com/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="963b8-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="963b8-147">Eine direkte Verbindung zur Echtzeit-API herstellen</span><span class="sxs-lookup"><span data-stu-id="963b8-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="963b8-148">Sie können die Funktionalitäten in Echtzeit nutzen, indem Sie Ihre eigene Pipeline erstellen und sich direkt mit der Echtzeit-API verbinden.</span><span class="sxs-lookup"><span data-stu-id="963b8-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="963b8-149">Sie können eine Aktivität im Format Ihres Quellsystems oder im UnifiedActivity-Format veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="963b8-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="963b8-150">Rufen Sie das Format ab, indem Sie einen API-Aufruf an /api/instances/{instanceId}/manage/entities/UnifiedActivity senden.</span><span class="sxs-lookup"><span data-stu-id="963b8-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="963b8-151">Details zu dieser API, einschließlich Parameter und Antworten, finden Sie im Abschnitt **EntityData** auf der [Customer Insights APIs-Referenz](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="963b8-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="963b8-152">Weitere Informationen finden Sie unter [Arbeiten mit Customer Insights APIs](apis.md).</span><span class="sxs-lookup"><span data-stu-id="963b8-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="963b8-153">Verstehen Sie Ihre Echtzeit-Nutzung mit Telemetrie</span><span class="sxs-lookup"><span data-stu-id="963b8-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="963b8-154">Erhalten Sie einen Überblick über das Volumen der Anfragen an die Echtzeit-API und Informationen über mögliche Probleme des Systems.</span><span class="sxs-lookup"><span data-stu-id="963b8-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="963b8-155">Sie können [auf die Echtzeit-Telemetrie zugreifen](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="963b8-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]