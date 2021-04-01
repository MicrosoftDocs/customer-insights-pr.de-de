---
title: Kennzahlen erstellen und verwalten
description: Kennzahlen definieren, um Leistung und Zustand Ihres Unternehmens zu analysieren und widerzuspiegeln.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654731"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="05d00-103">Definieren und Verwalten von Kennzahlen</span><span class="sxs-lookup"><span data-stu-id="05d00-103">Define and manage measures</span></span>

<span data-ttu-id="05d00-104">Mithilfe von Kennzahlen können Sie das Kundenverhalten und die Geschäftsleistung besser verstehen, indem Sie relevante Werte von [einheitlichen Profilen](data-unification.md) abrufen.</span><span class="sxs-lookup"><span data-stu-id="05d00-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="05d00-105">Zum Beispiel möchte ein Unternehmen die *Gesamtausgaben pro Kunde* ermitteln, um die Kaufhistorie des einzelnen Kunden zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="05d00-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="05d00-106">Oder messen Sie den *Gesamtumsatz des Unternehmens*, um den aggregierten Gesamtumsatz im gesamten Unternehmen zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="05d00-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="05d00-107">Kennzahlen werden mit dem Kennzahlungsgenerator erstellt, einer Datenabfrageplattform mit verschiedenen Operatoren und einfachen Zuordnungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="05d00-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="05d00-108">Sie können die Daten filtern, Ergebnisse gruppieren und [Entitätsbeziehungspfade](relationships.md) erkennen und zeigen eine Vorschau der Ausgabe anzeigen.</span><span class="sxs-lookup"><span data-stu-id="05d00-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="05d00-109">Verwenden Sie die Kennzahlenerstellung, um Geschäftsaktivitäten zu planen, indem Sie Kundendaten abfragen und Erkenntnisse extrahieren.</span><span class="sxs-lookup"><span data-stu-id="05d00-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="05d00-110">Erstellen Sie beispielsweise eine Kennzahl für *Gesamtausgaben pro Kunde* und *Gesamtrendite pro Kunde* hilft bei der Identifizierung einer Gruppe von Kunden mit hohen Ausgaben und hoher Rendite.</span><span class="sxs-lookup"><span data-stu-id="05d00-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="05d00-111">Sie können [ein Segment erstellen](segments.md), um die nächstbesten Aktionen zu fahren.</span><span class="sxs-lookup"><span data-stu-id="05d00-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="05d00-112">Eine Kennzahl erstellen</span><span class="sxs-lookup"><span data-stu-id="05d00-112">Create a measure</span></span>

<span data-ttu-id="05d00-113">In diesem Abschnitt erfahren Sie, wie Sie eine neue Kennzahl von Grund auf neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="05d00-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="05d00-114">Sie können eine Kennzahl mit Datenattributen aus Datenentitäten erstellen, für die eine Beziehung zur Verbindung mit der Kundenentität eingerichtet wurde.</span><span class="sxs-lookup"><span data-stu-id="05d00-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="05d00-115">Gehen Sie in den Zielgruppen-Insights auf **Kennzahlen**.</span><span class="sxs-lookup"><span data-stu-id="05d00-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="05d00-116">Wählen Sie **Neu**.</span><span class="sxs-lookup"><span data-stu-id="05d00-116">Select **New**.</span></span>

1. <span data-ttu-id="05d00-117">Wählen **Namen bearbeiten** und stellen einen **Namen** für die Kennzahl bereit.</span><span class="sxs-lookup"><span data-stu-id="05d00-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="05d00-118">Wenn Ihre neue Kennzahlkonfiguration nur zwei Felder enthält, z. B. CustomerID und eine Berechnung, wird die Ausgabe als neue Spalte zu der vom System generierten Entität Customer_Measure hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="05d00-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="05d00-119">Und Sie können den Wert der Kennzahl im einheitlichen Kundenprofil sehen.</span><span class="sxs-lookup"><span data-stu-id="05d00-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="05d00-120">Andere Kennzahlen werden ihre eigenen Einheiten erzeugen.</span><span class="sxs-lookup"><span data-stu-id="05d00-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="05d00-121">Wählen Sie im Konfigurationsbereich die Aggregationsfunktion aus dem **Funktion auswählen** Dropdownmenü aus.</span><span class="sxs-lookup"><span data-stu-id="05d00-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="05d00-122">Zu den Aggregationsfunktionen gehören:</span><span class="sxs-lookup"><span data-stu-id="05d00-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="05d00-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="05d00-123">**Sum**</span></span>
   - <span data-ttu-id="05d00-124">**Durchschnitt**</span><span class="sxs-lookup"><span data-stu-id="05d00-124">**Average**</span></span>
   - <span data-ttu-id="05d00-125">**Anzahl**</span><span class="sxs-lookup"><span data-stu-id="05d00-125">**Count**</span></span>
   - <span data-ttu-id="05d00-126">**Anzahl einzigartiger Elemente**</span><span class="sxs-lookup"><span data-stu-id="05d00-126">**Count Unique**</span></span>
   - <span data-ttu-id="05d00-127">**Max.**</span><span class="sxs-lookup"><span data-stu-id="05d00-127">**Max**</span></span>
   - <span data-ttu-id="05d00-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="05d00-128">**Min**</span></span>
   - <span data-ttu-id="05d00-129">**Erste**: Nimmt den ersten Wert des Datensatzes</span><span class="sxs-lookup"><span data-stu-id="05d00-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="05d00-130">**Letzte**: Nimmt den letzten Wert, der dem Datensatz hinzugefügt wurde</span><span class="sxs-lookup"><span data-stu-id="05d00-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatoren für Kennzahlberechnungen.":::

1. <span data-ttu-id="05d00-132">WählenSie **Attribute hinzufügen**, um die Daten auszuwählen, die Sie zum Erstellen dieser Kennzahl benötigen.</span><span class="sxs-lookup"><span data-stu-id="05d00-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="05d00-133">Die **Attribute**-Registerkarte auswählen.</span><span class="sxs-lookup"><span data-stu-id="05d00-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="05d00-134">Datenentität: Wählen Sie die Entität aus, die das Attribut enthält, das Sie messen möchten.</span><span class="sxs-lookup"><span data-stu-id="05d00-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="05d00-135">Datenattribut: Wählen Sie das Attribut aus, das Sie in der Aggregationsfunktion zur Berechnung der Kennzahl verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="05d00-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="05d00-136">Sie können jeweils nur ein Attribut auswählen.</span><span class="sxs-lookup"><span data-stu-id="05d00-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="05d00-137">Sie können auch ein Datenattribut aus einer vorhandenen Kennzahl auswählen, indem Sie die Registerkarte **Kennzahlen** auswählen. Sie können auch nach einem Entitäts- oder Kennzahlnamen suchen.</span><span class="sxs-lookup"><span data-stu-id="05d00-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="05d00-138">WählenSie **Hinzufügen**, um das ausgewählte Attribut zur Kennzahl hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="05d00-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Wählen Sie ein Attribut aus, das in Berechnungen verwendet werden soll.":::

1. <span data-ttu-id="05d00-140">Um komplexere Kennzahlen zu erstellen, können Sie weitere Attribute hinzufügen oder mathematische Operatoren für Ihre Kennzahlfunktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="05d00-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Erstellen Sie eine komplexe Kennzahl mit mathematischen Operatoren.":::

1. <span data-ttu-id="05d00-142">Um Filter hinzuzufügen, wählen Sie **Filter** im Konfigurationsbereich.</span><span class="sxs-lookup"><span data-stu-id="05d00-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="05d00-143">Im **Attribut hinzufügen**-Abschnitt des **Filter** -Bereichs wählen Sie das Attribut aus, mit dem Sie Filter erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="05d00-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="05d00-144">Legen Sie die Filteroperatoren fest, um den Filter für jedes ausgewählte Attribut zu definieren.</span><span class="sxs-lookup"><span data-stu-id="05d00-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="05d00-145">Wählen Sie **Anwenden**, um den Filter zur Kennzahl hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="05d00-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="05d00-146">Um Dimensionen hinzuzufügen, wählen Sie **Dimension** im Konfigurationsbereich.</span><span class="sxs-lookup"><span data-stu-id="05d00-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="05d00-147">Dimensionen werden als Spalten in der Kennzahlausgabeeinheit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="05d00-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="05d00-148">Wählen Sie **Dimensionen bearbeiten** aus, um Datenattribute hinzuzufügen, nach denen Sie die Kennzahlen gruppieren möchten.</span><span class="sxs-lookup"><span data-stu-id="05d00-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="05d00-149">Zum Beispiel Stadt oder Geschlecht.</span><span class="sxs-lookup"><span data-stu-id="05d00-149">For example, city or gender.</span></span> <span data-ttu-id="05d00-150">Standardmäßig wird die *Kundennummer*-Dimension zum Erstellen von *Kennzahlen auf Kundenebene* ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="05d00-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="05d00-151">Sie können die Standarddimension entfernen, wenn Sie *Kennzahlen auf Unternehmensebene* erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="05d00-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="05d00-152">Wählen Sie **Fertig**, um die Dimensionen zur Kennzahl hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="05d00-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="05d00-153">Wenn zwischen der von Ihnen zugeordneten Datenentität und der *Kunden* Entität mehrere Pfade vorhanden sind, müssen Sie einen der identifizierten [Entitätsbeziehungspfade auswählen](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="05d00-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="05d00-154">Die Kennzahlenergebnisse können je nach ausgewähltem Pfad variieren.</span><span class="sxs-lookup"><span data-stu-id="05d00-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="05d00-155">Wählen Sie **Dateneinstellungen**, und wählen Sie den Entitätspfad aus, der zur Identifizierung Ihrer Kennzahl verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="05d00-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="05d00-156">Wenn es nur einen einzigen Weg zur Entität *Kunde* gibt, wird dieses Steuerelement nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="05d00-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="05d00-157">Wählen **Fertig**, um Ihre Auswahl anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="05d00-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Wählen Sie den Entitätspfad für die Kennzahl aus.":::

1. <span data-ttu-id="05d00-159">Wählen Sie aus **Neue Berechnung**, um weitere Berechnungen für die Kennzahl hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="05d00-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="05d00-160">Sie können nur Entitäten im selben Entitätspfad für neue Berechnungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="05d00-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="05d00-161">Weitere Berechnungen werden als neue Spalten in der Kennzahlausgabeeinheit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="05d00-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="05d00-162">Wählen Sie **...** für die Berechnung aus, um **Duplikat**, **Umbenennen** oder **Entfernen** zur Berechnung einer Kennzahl auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="05d00-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="05d00-163">Im Bereich **Vorschau** sehen Sie das Datenschema der Kennzahlausgabeentität, einschließlich Filter und Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="05d00-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="05d00-164">Die Vorschau reagiert dynamisch auf Änderungen in der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="05d00-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="05d00-165">Wählen **Ausführen**, um die Ergebnisse für die konfigurierte Messung zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="05d00-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="05d00-166">Wählen Sie **Speichern und schließen** aus, wenn Sie die aktuelle Konfiguration beibehalten und die Kennzahlmessung später ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="05d00-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="05d00-167">Gehen Sie zu **Kennzahlen**, um die neu erstellte Kennzahl in der Liste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="05d00-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="05d00-168">Verwalten von Kennzahlen</span><span class="sxs-lookup"><span data-stu-id="05d00-168">Manage your measures</span></span>

<span data-ttu-id="05d00-169">Nachdem Sie mindestens eine [Kennzahl erstellt](#create-a-measure) haben, sehen Sie eine Liste der Kennzahlen auf der Seite **Kennzahlen**.</span><span class="sxs-lookup"><span data-stu-id="05d00-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="05d00-170">Sie finden Informationen zu Kennzahlentyp, Ersteller, Erstellungsdatum, Status und Zustand.</span><span class="sxs-lookup"><span data-stu-id="05d00-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="05d00-171">Wenn Sie eine Kennzahl aus der Liste auswählen, können Sie eine Vorschau der Ausgabe anzeigen und eine CSV-Datei herunterladen.</span><span class="sxs-lookup"><span data-stu-id="05d00-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="05d00-172">Um alle Ihre Kennzahlen gleichzeitig zu aktualisieren, wählen Sie **Alle aktualisieren** aus, ohne eine bestimmte Kennzahl auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="05d00-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="05d00-173">![Maßnahmen zur Verwaltung einzelner Kennzahlen](media/measure-actions.png "Maßnahmen zur Verwaltung einzelner Kennzahlen")</span><span class="sxs-lookup"><span data-stu-id="05d00-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="05d00-174">Wählen Sie eine Kennzahl aus den folgenden Optionen in der Liste aus:</span><span class="sxs-lookup"><span data-stu-id="05d00-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="05d00-175">Wählen Sie den Kennzahlnamen aus, um dessen Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="05d00-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="05d00-176">**Bearbeiten** der Konfiguration der Kennzahl.</span><span class="sxs-lookup"><span data-stu-id="05d00-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="05d00-177">**Aktualisieren** Sie die Maßnahme basierend auf den neuesten Daten.</span><span class="sxs-lookup"><span data-stu-id="05d00-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="05d00-178">**Umbenennen** der Kennzahl.</span><span class="sxs-lookup"><span data-stu-id="05d00-178">**Rename** the measure.</span></span>
- <span data-ttu-id="05d00-179">**Löschen** der Kennzahl.</span><span class="sxs-lookup"><span data-stu-id="05d00-179">**Delete** the measure.</span></span>
- <span data-ttu-id="05d00-180">**Aktivieren** oder **Deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="05d00-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="05d00-181">Inaktive Maßnahmen werden während einer [geplanten Aktualisierung](system.md#schedule-tab) nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="05d00-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="05d00-182">Es gibt [sechs Arten von Status](system.md#status-types) für Aufgaben/Prozesse.</span><span class="sxs-lookup"><span data-stu-id="05d00-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="05d00-183">Darüber hinaus [hängen die meisten Prozesse von anderen nachfolgenden Prozessen ab](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="05d00-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="05d00-184">Sie können den Status eines Prozesses auswählen, um Details zum Fortschritt des gesamten Auftrags anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="05d00-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="05d00-185">Nach der Auswahl von **Siehe Details** für eine der Aufgaben des Auftrags finden Sie zusätzliche Informationen: Verarbeitungszeit, das letzte Verarbeitungsdatum sowie alle mit der Aufgabe verbundenen Fehler und Warnungen.</span><span class="sxs-lookup"><span data-stu-id="05d00-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="05d00-186">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="05d00-186">Next step</span></span>

<span data-ttu-id="05d00-187">Sie können vorhandene Kennzahlen zum Erstellen [eines Kundensegments](segments.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="05d00-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]