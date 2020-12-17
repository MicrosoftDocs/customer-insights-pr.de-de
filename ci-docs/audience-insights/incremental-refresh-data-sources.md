---
title: Inkrementelle Aktualisierung für Power Query-basierte Datenquellen
description: Aktualisieren Sie neue und aktualisierte Daten für große Datenquellen basierend auf Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405785"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="9321f-103">Inkrementelle Aktualisierung für Datenquellen basierend auf Power Query</span><span class="sxs-lookup"><span data-stu-id="9321f-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="9321f-104">Die inkrementelle Aktualisierung für Datenquellen bietet die folgenden Vorteile:</span><span class="sxs-lookup"><span data-stu-id="9321f-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="9321f-105">**Schneller aktualisiert** – Nur geänderte Daten werden aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="9321f-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="9321f-106">Beispielsweise können Sie nur die letzten fünf Tage eines historischen DataSet aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="9321f-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="9321f-107">**Erhöhte Zuverlässigkeit** – Bei kleineren Aktualisierungen müssen Sie die Verbindungen zu flüchtigen Quellsystemen nicht so lange aufrechterhalten, um das Risiko von Verbindungsproblemen zu verringern.</span><span class="sxs-lookup"><span data-stu-id="9321f-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="9321f-108">**Reduzierter Ressourcenverbrauch** – Das Aktualisieren nur einer Teilmenge Ihrer Gesamtdaten führt zu einer effizienteren Nutzung der Computerressourcen und verringert den ökologischen Fußabdruck.</span><span class="sxs-lookup"><span data-stu-id="9321f-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="9321f-109">Inkrementelle Aktualisierung konfigurieren</span><span class="sxs-lookup"><span data-stu-id="9321f-109">Configure incremental refresh</span></span>

<span data-ttu-id="9321f-110">Zielgruppen-Insights ermöglicht eine inkrementelle Aktualisierung für Datenquellen, die über Power Query importiert wurden und eine inkrementelle Datenerfassung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9321f-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="9321f-111">Azure SQL-Datenbanken mit Datums- und Zeitfeldern geben beispielsweise an, wann Datensätze zuletzt aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="9321f-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="9321f-112">[Erstellen Sie eine neue Datenquelle basierend auf Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="9321f-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="9321f-113">Geben Sie dann einen Namen für die Datenquelle ein.</span><span class="sxs-lookup"><span data-stu-id="9321f-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="9321f-114">Wählen Sie ein Datenquelle aus, das inkrementelle Aktualisierungen unterstützt, z. B. die Azure SQL-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9321f-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="9321f-115">Wählen Sie die Entitäten oder Tabellen aus, die erfasst werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9321f-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="9321f-116">Schließen Sie die Transformationsschritte ab und wählen Sie **Nächster**.</span><span class="sxs-lookup"><span data-stu-id="9321f-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="9321f-117">In dem **Richten Sie eine inkrementelle Aktualisierung ein** Dialogfeld wählen Sie **Konfiguration**, um die **Inkrementelle Aktualisierungseinstellungen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9321f-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="9321f-118">Wenn Sie **Überspringen** auswählen, aktualisiert die Datenquelle das gesamte Dataset.</span><span class="sxs-lookup"><span data-stu-id="9321f-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="9321f-119">Sie können die inkrementelle Aktualisierung auch später anwenden, indem Sie ein vorhandenes Datenquelle bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="9321f-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="9321f-120">Auf **Inkrementelle Aktualisierungseinstellungen** konfigurieren Sie die inkrementelle Aktualisierung für alle Entitäten, die Sie beim Erstellen des Datenquelle ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="9321f-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9321f-121">![Konfigurieren Sie Entitäten in einem Datenquelle für die inkrementelle Aktualisierung](media/incremental-refresh-settings.png "Konfigurieren Sie Entitäten in einem Datenquelle für die inkrementelle Aktualisierung")</span><span class="sxs-lookup"><span data-stu-id="9321f-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="9321f-122">Wählen Sie eine Entität aus und geben Sie die folgenden Details an:</span><span class="sxs-lookup"><span data-stu-id="9321f-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="9321f-123">**Definieren Sie den Primärschlüssel**: Wählen Sie einen Primärschlüssel für die Entität oder Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="9321f-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="9321f-124">**Definieren Sie das Feld Zuletzt aktualisiert** : In diesem Feld werden nur Attribute vom Typ Datum oder Uhrzeit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9321f-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="9321f-125">Wählen Sie ein Attribut aus, das angibt, wann die Datensätze zuletzt aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="9321f-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="9321f-126">Es wird verwendet, um die Datensätze zu identifizieren, die in den inkrementellen Aktualisierungszeitrahmen fallen.</span><span class="sxs-lookup"><span data-stu-id="9321f-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="9321f-127">**Nach Updates suche, alle** : Geben Sie an, wie lange der Zeitrahmen für die inkrementelle Aktualisierung dauern soll.</span><span class="sxs-lookup"><span data-stu-id="9321f-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="9321f-128">Wählen Sie **speichern**, um die Erstellung des Datenquelle abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="9321f-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="9321f-129">Die anfängliche Datenaktualisierung ist eine vollständige Aktualisierung.</span><span class="sxs-lookup"><span data-stu-id="9321f-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="9321f-130">Anschließend erfolgt die inkrementelle Datenaktualisierung wie im vorherigen Schritt konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="9321f-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>
