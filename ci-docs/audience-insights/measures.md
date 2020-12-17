---
title: Erstellen und Bearbeiten von Kennzahlen
description: Definieren Sie kundenbezogene Kennzahlen, um die Leistung bestimmter Geschäftsbereiche zu analysieren und widerzuspiegeln.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405793"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="af968-103">Definieren und Verwalten von Kennzahlen</span><span class="sxs-lookup"><span data-stu-id="af968-103">Define and manage measures</span></span>

<span data-ttu-id="af968-104">**Kennzahlen** stellen Key Performance Indicators (KPIs) dar, die die Leistung und den Gesundheitszustand bestimmter Geschäftsbereiche widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="af968-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="af968-105">Zielgruppen-Insights bietet ein intuitives Erlebnis für die Erstellung verschiedener Arten von Kennzahlen mithilfe eines Query Builders, der es nicht erforderlich macht, dass Sie Ihre Kennzahlen manuell codieren oder validieren müssen.</span><span class="sxs-lookup"><span data-stu-id="af968-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="af968-106">Sie können Ihre Geschäftskennzahlen auf der Seite **Home** verfolgen, Kennzahlen für bestimmte Kunden auf der Seite **Kundenkarte** sehen und Kennzahlen zur Definition von Kundensegmenten auf der Seite **Segmente** verwenden.</span><span class="sxs-lookup"><span data-stu-id="af968-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="af968-107">Eine Kennzahl erstellen</span><span class="sxs-lookup"><span data-stu-id="af968-107">Create a measure</span></span>

<span data-ttu-id="af968-108">Dieser Abschnitt führt Sie durch die Erstellung einer Kennzahl von Grund auf.</span><span class="sxs-lookup"><span data-stu-id="af968-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="af968-109">Sie können Kennzahlen mit Daten aus mehreren Datenquellen erstellen, die über die Entität Kunde verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="af968-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="af968-110">Es gelten einige [Serviceeinschränkungen](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="af968-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="af968-111">Gehen Sie in den Zielgruppen-Insights auf **Kennzahlen**.</span><span class="sxs-lookup"><span data-stu-id="af968-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="af968-112">Wählen Sie **Neue Kennzahl**.</span><span class="sxs-lookup"><span data-stu-id="af968-112">Select **New measure**.</span></span>

3. <span data-ttu-id="af968-113">Wählen Sie die Kennzahl **Typ**:</span><span class="sxs-lookup"><span data-stu-id="af968-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="af968-114">**Kundenattribut**: Ein einzelnes Feld pro Kunde, das einen Score, Wert oder Zustand für den Kunden widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="af968-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="af968-115">Kundenattribute werden als Attribute in einer neuen, vom System generierten Entität mit dem Namen **Customer_Measure** angelegt.</span><span class="sxs-lookup"><span data-stu-id="af968-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="af968-116">**Kundenkennzahlen**: Einblicke in das Kundenverhalten mit Aufschlüsselung nach ausgewählten Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="af968-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="af968-117">Für jede Kennzahl wird eine neue Einheit generiert, möglicherweise mit mehreren Datensätzen pro Kunde.</span><span class="sxs-lookup"><span data-stu-id="af968-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="af968-118">**Business-Kennzahlen**: Verfolgt Ihre geschäftliche Leistung und den Zustand des Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="af968-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="af968-119">Geschäftskennzahlen können zwei verschiedene Ausgaben haben: eine numerische Ausgabe, die auf der Seite **Start** angezeigt wird, oder eine neue Einheit, die Sie auf der Seite **Entitäten** finden.</span><span class="sxs-lookup"><span data-stu-id="af968-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="af968-120">Geben Sie einen **Name** und einen optionalen **Anzeigename** ein und wählen Sie dann **Nächster**.</span><span class="sxs-lookup"><span data-stu-id="af968-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="af968-121">Wählen Sie im Bereich **Entitäten** die erste Entität aus der Dropdown-Liste aus.</span><span class="sxs-lookup"><span data-stu-id="af968-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="af968-122">An diesem Punkt sollten Sie entscheiden, ob zusätzliche Entitäten als Teil Ihrer Kennzahlendefinition benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="af968-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="af968-123">![Kennzahldefinition](media/measure-definition.png "Definition der Kennzahl")</span><span class="sxs-lookup"><span data-stu-id="af968-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="af968-124">Um weitere Entitäten hinzuzufügen, wählen Sie **Entität hinzufügen** und wählen Sie die Entitäten aus, die Sie für die Kennzahl verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="af968-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="af968-125">Sie können nur Entitäten auswählen, die Beziehungen zu Ihrer Ausgangsentität haben.</span><span class="sxs-lookup"><span data-stu-id="af968-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="af968-126">Weitere Informationen zur Definition von Beziehungen finden Sie unter [Beziehungen](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="af968-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="af968-127">Optional können Sie Variablen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="af968-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="af968-128">Wählen Sie im Abschnitt **Variablen** **Neue Variable**.</span><span class="sxs-lookup"><span data-stu-id="af968-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="af968-129">Variablen sind Berechnungen, die für jeden Ihrer ausgewählten Datensätze durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="af968-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="af968-130">Zum Beispiel die Summierung von Point-of-Sale (POS) und Online-Verkäufen für jeden Datensatz Ihrer Kunden.</span><span class="sxs-lookup"><span data-stu-id="af968-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="af968-131">Geben Sie einen **Name** für die Variable an.</span><span class="sxs-lookup"><span data-stu-id="af968-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="af968-132">Wählen Sie im Bereich **Ausdruck** ein Feld aus, mit dem Ihre Berechnung beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="af968-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="af968-133">Geben Sie einen Ausdruck in den Bereich **Ausdruck** ein und wählen Sie gleichzeitig weitere Felder aus, die in Ihre Berechnung einbezogen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="af968-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="af968-134">Zurzeit werden nur arithmetische Ausdrücke unterstützt.</span><span class="sxs-lookup"><span data-stu-id="af968-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="af968-135">Darüber hinaus wird die Berechnung von Variablen für Entitäten von verschiedenen [Entitätspfaden](relationships.md) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="af968-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="af968-136">**Fertig** auswählen</span><span class="sxs-lookup"><span data-stu-id="af968-136">Select **Done**.</span></span>

11. <span data-ttu-id="af968-137">Im Abschnitt **Kennzahldefinition** definieren Sie, wie die von Ihnen gewählten Entitäten und berechneten Variablen in einer neuen Kennzahlentität oder einem neuen Attribut aggregiert werden.</span><span class="sxs-lookup"><span data-stu-id="af968-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="af968-138">Wählen Sie **Neue Dimension**.</span><span class="sxs-lookup"><span data-stu-id="af968-138">Select **New dimension**.</span></span> <span data-ttu-id="af968-139">Sie können sich eine Dimension als eine Funktion *Gruppieren nach* vorstellen.</span><span class="sxs-lookup"><span data-stu-id="af968-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="af968-140">Die Datenausgabe Ihrer Kennzahl-Entität oder Ihres Kennzahl-Attributs wird nach allen von Ihnen definierten Dimensionen gruppiert.</span><span class="sxs-lookup"><span data-stu-id="af968-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="af968-141">![Aggregatzyklus auswählen](media/measures-businessreport-measure-definition2.png "Wählen Sie den Aggregatzyklus")</span><span class="sxs-lookup"><span data-stu-id="af968-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="af968-142">Wählen Sie die folgenden Informationen aus oder geben Sie sie als Teil der Definition Ihrer Dimension ein:</span><span class="sxs-lookup"><span data-stu-id="af968-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="af968-143">**Entität**: Wenn Sie eine Entitätskennzahl definieren, sollte diese mindestens ein Attribut enthalten.</span><span class="sxs-lookup"><span data-stu-id="af968-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="af968-144">Wenn Sie ein Kennzahl-Attribut definieren, wird es standardmäßig nur ein Attribut enthalten.</span><span class="sxs-lookup"><span data-stu-id="af968-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="af968-145">Bei dieser Auswahl geht es um die Auswahl der Entität, die dieses Attribut enthält.</span><span class="sxs-lookup"><span data-stu-id="af968-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="af968-146">**Feld**: Wählen Sie das spezifische Attribut, das entweder in Ihre Kennzahlentität oder in das Attribut aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="af968-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="af968-147">**Bucket**: Wählen Sie, ob Sie Daten auf Tages-, Monats- oder Jahresbasis aggregieren möchten.</span><span class="sxs-lookup"><span data-stu-id="af968-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="af968-148">Diese Auswahl ist nur erforderlich, wenn Sie ein Datumstypattribut ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="af968-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="af968-149">**Als**: Definiert den Namen Ihres neuen Feldes.</span><span class="sxs-lookup"><span data-stu-id="af968-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="af968-150">**Anzeigename**: Definiert den Anzeigenamen Ihres Feldes.</span><span class="sxs-lookup"><span data-stu-id="af968-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="af968-151">Ihre Geschäftskennzahl wird als Einzahl-Einheit gespeichert und erscheint auf der Seite **Home**, es sei denn, Sie fügen weitere Dimensionen zu Ihrer Kennzahl hinzu.</span><span class="sxs-lookup"><span data-stu-id="af968-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="af968-152">Nachdem Sie weitere Dimensionen hinzugefügt haben, wird die Kennzahl *nicht* auf der Seite **Start** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="af968-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="af968-153">Optional können Sie Aggregationsfunktionen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="af968-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="af968-154">Jede Aggregation, die Sie erstellen, führt zu einem neuen Wert innerhalb Ihrer Kennzahlen-Entität oder Ihres Attributs.</span><span class="sxs-lookup"><span data-stu-id="af968-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="af968-155">Unterstützte Aggregationsfunktionen sind: **Min**, **Max**, **Durchschnitt**, **Median**, **Summe**, **Zahl eindeutig**, **Erster** (nimmt den ersten Satz eines Dimensionswertes) und **Letzter** (nimmt den letzten zu einem Dimensionswert addierten Satz).</span><span class="sxs-lookup"><span data-stu-id="af968-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="af968-156">Wählen Sie **Speichern**, um Ihre Änderungen auf die Kennzahl anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="af968-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="af968-157">Verwalten von Kennzahlen</span><span class="sxs-lookup"><span data-stu-id="af968-157">Manage your measures</span></span>

<span data-ttu-id="af968-158">Nachdem Sie mindestens eine Kennzahl erstellt haben, sehen Sie eine Liste der Kennzahlen auf der Seite **Kennzahlen**.</span><span class="sxs-lookup"><span data-stu-id="af968-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="af968-159">Dort finden Sie Informationen über den Kennzahlentyp, den Ersteller, Erstellungsdatum und -uhrzeit, Datum und Uhrzeit der letzten Bearbeitung, den Status (ob die Kennzahl aktiv, inaktiv oder fehlgeschlagen ist) sowie Datum und Uhrzeit der letzten Aktualisierung.</span><span class="sxs-lookup"><span data-stu-id="af968-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="af968-160">Wenn Sie eine Kennzahl aus der Liste auswählen, wird eine Vorschau der Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="af968-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="af968-161">Um alle Ihre Kennzahlen gleichzeitig zu aktualisieren, wählen Sie **Alle aktualisieren** aus, ohne eine bestimmte Kennzahl auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="af968-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="af968-162">![Maßnahmen zur Verwaltung einzelner Kennzahlen](media/measure-actions.png "Maßnahmen zur Verwaltung einzelner Kennzahlen")</span><span class="sxs-lookup"><span data-stu-id="af968-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="af968-163">Alternativ können Sie eine Kennzahl aus der Liste auswählen und eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="af968-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="af968-164">Wählen Sie den Kennzahlnamen aus, um dessen Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="af968-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="af968-165">**Bearbeiten** der Konfiguration der Kennzahl.</span><span class="sxs-lookup"><span data-stu-id="af968-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="af968-166">**Umbenennen** der Kennzahl.</span><span class="sxs-lookup"><span data-stu-id="af968-166">**Rename** the measure.</span></span>
- <span data-ttu-id="af968-167">**Löschen** der Kennzahl.</span><span class="sxs-lookup"><span data-stu-id="af968-167">**Delete** the measure.</span></span>
- <span data-ttu-id="af968-168">Wählen Sie die Auslassungspunkte (...) und dann **Aktualisieren** aus, um den Aktualisierungsprozess für die Kennzahl zu starten.</span><span class="sxs-lookup"><span data-stu-id="af968-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="af968-169">Wählen Sie die Auslassungspunkte (...) und dann **Herunterladen** aus, um eine CSV-Datei der Kennzahl zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="af968-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="af968-170">Es gibt [sechs Arten von Status](system.md#status-types) für Aufgaben/Prozesse.</span><span class="sxs-lookup"><span data-stu-id="af968-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="af968-171">Darüber hinaus [hängen die meisten Prozesse von anderen nachfolgenden Prozessen ab](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="af968-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="af968-172">Sie können den Status eines Prozesses auswählen, um Details zum Fortschritt des gesamten Auftrags anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="af968-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="af968-173">Nach der Auswahl von **Siehe Details** für eine der Aufgaben des Auftrags finden Sie zusätzliche Informationen: Verarbeitungszeit, das letzte Verarbeitungsdatum sowie alle mit der Aufgabe verbundenen Fehler und Warnungen.</span><span class="sxs-lookup"><span data-stu-id="af968-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="af968-174">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="af968-174">Next step</span></span>

<span data-ttu-id="af968-175">Sie nutzen bestehende Kennzahlen, um Ihr erstes Kundensegment auf der Seite **Segmente** zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="af968-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="af968-176">Weitere Informationen finden Sie unter [Segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="af968-176">For more information, see [Segments](segments.md).</span></span>
