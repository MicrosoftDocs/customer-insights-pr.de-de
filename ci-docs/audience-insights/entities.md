---
title: Entitäten und Datasets
description: Zeigen Sie Daten auf der Seite Entitäten an.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049393"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="b6836-103">Entitäten in Zielgruppen-Insights</span><span class="sxs-lookup"><span data-stu-id="b6836-103">Entities in audience insights</span></span>

<span data-ttu-id="b6836-104">Nachdem Sie [Konfiguration Ihrer Datenquellen](data-sources.md), gehen Sie zur Seite **Entitäten**, um die Qualität der aufgenommenen Daten zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="b6836-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="b6836-105">Entitäten werden als Datasets betrachtet.</span><span class="sxs-lookup"><span data-stu-id="b6836-105">Entities are considered datasets.</span></span> <span data-ttu-id="b6836-106">Mehrere Funktionalitäten von Dynamics 365 Customer Insights sind um diese Entitäten herum aufgebaut.</span><span class="sxs-lookup"><span data-stu-id="b6836-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="b6836-107">Eine genaue Überprüfung kann Ihnen helfen, die Ausgabe dieser Fähigkeiten zu validieren.</span><span class="sxs-lookup"><span data-stu-id="b6836-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="b6836-108">Die Seite **Entitäten** listet Entitäten auf und enthält mehrere Spalten:</span><span class="sxs-lookup"><span data-stu-id="b6836-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="b6836-109">**Name**: Der Name Ihrer Datenentität.</span><span class="sxs-lookup"><span data-stu-id="b6836-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="b6836-110">Wenn Sie ein Warnsymbol neben einem Entitätsnamen sehen, bedeutet dies, dass die Daten für diese Entität nicht erfolgreich geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="b6836-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="b6836-111">**Quelle**: Zeigt die Datenquelle der Entität an</span><span class="sxs-lookup"><span data-stu-id="b6836-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="b6836-112">**Erstellt von**: Name der Person, die die Entität erstellt hat</span><span class="sxs-lookup"><span data-stu-id="b6836-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="b6836-113">**Erstellt**: Datum und Uhrzeit der Entitätserstellung</span><span class="sxs-lookup"><span data-stu-id="b6836-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="b6836-114">**Aktualisiert von**: Name der Person, die die Entität aktualisiert hat</span><span class="sxs-lookup"><span data-stu-id="b6836-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="b6836-115">**Zuletzt aktualisiert**: Datum und Uhrzeit der letzten Aktualisierung der Entität</span><span class="sxs-lookup"><span data-stu-id="b6836-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="b6836-116">**Letzte Aktualisierung**: Datum und Uhrzeit der letzten Datenaktualisierung</span><span class="sxs-lookup"><span data-stu-id="b6836-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="b6836-117">Erforschung der Daten einer bestimmten Einheit</span><span class="sxs-lookup"><span data-stu-id="b6836-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="b6836-118">Wählen Sie eine Entität aus, um die verschiedenen Felder und Datensätze innerhalb dieser Entität zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="b6836-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b6836-119">![Eine Entität auswählen](media/data-manager-entities-data.png "Wählen Sie eine Entität")</span><span class="sxs-lookup"><span data-stu-id="b6836-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="b6836-120">Die Registerkarte **Daten** zeigt eine Tabelle mit Details zu einzelnen Datensätzen der Entität.</span><span class="sxs-lookup"><span data-stu-id="b6836-120">The **Data** tab shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b6836-121">![Feldtabelle](media/data-manager-entities-fields.PNG "Tabelle Felder")</span><span class="sxs-lookup"><span data-stu-id="b6836-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="b6836-122">Die Registerkarte **Attribute** ist standardmäßig ausgewählt und zeigt eine Tabelle an, in der Details für die ausgewählte Entität wie Feldnamen, Datentypen und Typen überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="b6836-122">The **Attributes** tab is selected by default and shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="b6836-123">Die Spalte **Typ** zeigt die mit dem Common Data Model verbundenen Typen, die entweder vom System automatisch identifiziert oder von den Benutzern [manuell abgebildet](map-entities.md) werden.</span><span class="sxs-lookup"><span data-stu-id="b6836-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="b6836-124">Es handelt sich um semantische Typen, die sich von den Datentypen der Attribute unterscheiden können, z. B. hat das Feld *Email* unten einen Datentyp *Text*, aber sein (semantischer) Common Data Model Typ könnte *Email* oder *EmailAddress* sein.</span><span class="sxs-lookup"><span data-stu-id="b6836-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="b6836-125">Beide Tabellen zeigen nur einen Ausschnitt der Daten Ihrer Entität.</span><span class="sxs-lookup"><span data-stu-id="b6836-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="b6836-126">Um den vollständigen Datensatz anzuzeigen, gehen Sie zur Seite **Datenquellen**, wählen Sie eine Entität, wählen Sie **Bearbeiten** und zeigen Sie dann die Daten dieser Entität mit dem Power Query-Editor an, wie unter [Datenquellen](data-sources.md) erläutert.</span><span class="sxs-lookup"><span data-stu-id="b6836-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="b6836-127">Um mehr über die in die Entität aufgenommenen Daten zu erfahren, finden Sie in der Spalte **Zusammenfassung** einige wichtige Merkmale der Daten, wie z. B. Nullen, fehlende Werte, eindeutige Werte, Zählungen und Verteilungen, die auf Ihre Daten anwendbar sind.</span><span class="sxs-lookup"><span data-stu-id="b6836-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="b6836-128">Wählen Sie das Diagrammsymbol, um die Zusammenfassung der Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b6836-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b6836-129">![Zusammenfassungssymbol](media/data-manager-entities-summary.png "Daten-Zusammenfassungstabelle")</span><span class="sxs-lookup"><span data-stu-id="b6836-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="b6836-130">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="b6836-130">Next step</span></span>

<span data-ttu-id="b6836-131">Siehe [Vereinheitlichung](data-unification.md), um zu erfahren, wie *Karte*, *Abgleich* und *Zusammenführung* der aufgenommenen Daten.</span><span class="sxs-lookup"><span data-stu-id="b6836-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
