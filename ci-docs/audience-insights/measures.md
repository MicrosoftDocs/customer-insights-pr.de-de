---
title: Kennzahlen erstellen und verwalten
description: Kennzahlen definieren, um Leistung und Zustand Ihres Unternehmens zu analysieren und widerzuspiegeln.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a83caf2428f3dbd9791b9f746d00d370362a508c
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304792"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="23a99-103">Definieren und Verwalten von Kennzahlen</span><span class="sxs-lookup"><span data-stu-id="23a99-103">Define and manage measures</span></span>

<span data-ttu-id="23a99-104">Mithilfe von Kennzahlen können Sie das Kundenverhalten und die Geschäftsleistung besser verstehen.</span><span class="sxs-lookup"><span data-stu-id="23a99-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="23a99-105">Sie betrachten relevante Werte aus [einheitlichen Profilen](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="23a99-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="23a99-106">Ein Unternehmen möchte beispielsweise die *Gesamtausgaben pro Kunde* ermitteln, um den Kaufverlauf oder -messung eines einzelnen Kunden oder den *Gesamtumsatz des Unternehmens* zu verstehen, um den aggregierten Gesamtumsatz des gesamten Unternehmens zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="23a99-106">For example, a business wants to see the *total spend per customer* to understand an individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="23a99-107">Kennzahlen werden mit dem Kennzahlungsgenerator erstellt, einer Datenabfrageplattform mit verschiedenen Operatoren und einfachen Zuordnungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="23a99-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="23a99-108">Sie können die Daten filtern, Ergebnisse gruppieren und [Entitätsbeziehungspfade](relationships.md) erkennen und zeigen eine Vorschau der Ausgabe anzeigen.</span><span class="sxs-lookup"><span data-stu-id="23a99-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="23a99-109">Verwenden Sie die Kennzahlenerstellung, um Geschäftsaktivitäten zu planen, indem Sie Kundendaten abfragen und Erkenntnisse extrahieren.</span><span class="sxs-lookup"><span data-stu-id="23a99-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="23a99-110">Erstellen Sie beispielsweise eine Kennzahl für *Gesamtausgaben pro Kunde* und *Gesamtrendite pro Kunde* hilft bei der Identifizierung einer Gruppe von Kunden mit hohen Ausgaben und hoher Rendite.</span><span class="sxs-lookup"><span data-stu-id="23a99-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="23a99-111">Sie können [ein Segment erstellen](segments.md), um die nächstbesten Aktionen zu fahren.</span><span class="sxs-lookup"><span data-stu-id="23a99-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="23a99-112">Eigene Kennzahlen von Grund auf neu erstellen</span><span class="sxs-lookup"><span data-stu-id="23a99-112">Build your own measure from scratch</span></span>

<span data-ttu-id="23a99-113">In diesem Abschnitt erfahren Sie, wie Sie eine neue Kennzahl von Grund auf neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="23a99-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="23a99-114">Sie können eine Kennzahl mit Datenattributen aus Datenentitäten erstellen, für die eine Beziehung zur Verbindung mit der Kundenentität eingerichtet wurde.</span><span class="sxs-lookup"><span data-stu-id="23a99-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="23a99-115">Gehen Sie in den Zielgruppen-Insights auf **Kennzahlen**.</span><span class="sxs-lookup"><span data-stu-id="23a99-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="23a99-116">Wählen Sie **Neu** und dann **Eigene erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="23a99-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="23a99-117">Wählen **Namen bearbeiten** und stellen einen **Namen** für die Kennzahl bereit.</span><span class="sxs-lookup"><span data-stu-id="23a99-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="23a99-118">Wenn Ihre neue Kennzahlkonfiguration nur zwei Felder enthält, z. B. CustomerID und eine Berechnung, wird die Ausgabe als neue Spalte zu der vom System generierten Entität Customer_Measure hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="23a99-118">If your new measure configuration has only two fields—for example, CustomerID and one calculation—the output will be added as a new column to the system-generated entity called Customer_Measure.</span></span> <span data-ttu-id="23a99-119">Und Sie können den Wert der Kennzahl im einheitlichen Kundenprofil sehen.</span><span class="sxs-lookup"><span data-stu-id="23a99-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="23a99-120">Andere Kennzahlen werden ihre eigenen Einheiten erzeugen.</span><span class="sxs-lookup"><span data-stu-id="23a99-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="23a99-121">Wählen Sie im Konfigurationsbereich die Aggregationsfunktion aus dem Dropdown-Menü **Funktion auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="23a99-121">In the configuration area, choose the aggregation function from the **Select Function** dropdown menu.</span></span> <span data-ttu-id="23a99-122">Zu den Aggregationsfunktionen gehören:</span><span class="sxs-lookup"><span data-stu-id="23a99-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="23a99-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="23a99-123">**Sum**</span></span>
   - <span data-ttu-id="23a99-124">**Durchschnitt**</span><span class="sxs-lookup"><span data-stu-id="23a99-124">**Average**</span></span>
   - <span data-ttu-id="23a99-125">**Anzahl**</span><span class="sxs-lookup"><span data-stu-id="23a99-125">**Count**</span></span>
   - <span data-ttu-id="23a99-126">**Anzahl einzigartiger Elemente**</span><span class="sxs-lookup"><span data-stu-id="23a99-126">**Count Unique**</span></span>
   - <span data-ttu-id="23a99-127">**Max.**</span><span class="sxs-lookup"><span data-stu-id="23a99-127">**Max**</span></span>
   - <span data-ttu-id="23a99-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="23a99-128">**Min**</span></span>
   - <span data-ttu-id="23a99-129">**Erste**: Nimmt den ersten Wert des Datensatzes</span><span class="sxs-lookup"><span data-stu-id="23a99-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="23a99-130">**Letzte**: Nimmt den letzten Wert, der dem Datensatz hinzugefügt wurde</span><span class="sxs-lookup"><span data-stu-id="23a99-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatoren für Kennzahlberechnungen.":::

1. <span data-ttu-id="23a99-132">WählenSie **Attribute hinzufügen**, um die Daten auszuwählen, die Sie zum Erstellen dieser Kennzahl benötigen.</span><span class="sxs-lookup"><span data-stu-id="23a99-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="23a99-133">Die **Attribute**-Registerkarte auswählen.</span><span class="sxs-lookup"><span data-stu-id="23a99-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="23a99-134">Datenentität: Wählen Sie die Entität aus, die das Attribut enthält, das Sie messen möchten.</span><span class="sxs-lookup"><span data-stu-id="23a99-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="23a99-135">Datenattribut: Wählen Sie das Attribut aus, das Sie in der Aggregationsfunktion zur Berechnung der Kennzahl verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="23a99-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="23a99-136">Sie können jeweils nur ein Attribut auswählen.</span><span class="sxs-lookup"><span data-stu-id="23a99-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="23a99-137">Sie können auch ein Datenattribut aus einer vorhandenen Kennzahl auswählen, indem Sie die Registerkarte **Kennzahlen** auswählen. Sie können auch nach einem Entitäts- oder Kennzahlnamen suchen.</span><span class="sxs-lookup"><span data-stu-id="23a99-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="23a99-138">WählenSie **Hinzufügen**, um das ausgewählte Attribut zur Kennzahl hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="23a99-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Wählen Sie ein Attribut aus, das in Berechnungen verwendet werden soll.":::

1. <span data-ttu-id="23a99-140">Um komplexere Kennzahlen zu erstellen, können Sie weitere Attribute hinzufügen oder mathematische Operatoren für Ihre Kennzahlfunktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="23a99-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Erstellen Sie eine komplexe Kennzahl mit mathematischen Operatoren.":::

1. <span data-ttu-id="23a99-142">Um Filter hinzuzufügen, wählen Sie **Filter** im Konfigurationsbereich.</span><span class="sxs-lookup"><span data-stu-id="23a99-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="23a99-143">In dem Abschnitt **Attribute hinzufügen** des Bereichs **Filter** wählen Sie im Bereich das Attribut aus, das Sie zum Erstellen von Filtern verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="23a99-143">In the **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="23a99-144">Legen Sie die Filteroperatoren fest, um den Filter für jedes ausgewählte Attribut zu definieren.</span><span class="sxs-lookup"><span data-stu-id="23a99-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="23a99-145">Wählen Sie **Anwenden**, um den Filter zur Kennzahl hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="23a99-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="23a99-146">Um Dimensionen hinzuzufügen, wählen Sie **Dimension** im Konfigurationsbereich.</span><span class="sxs-lookup"><span data-stu-id="23a99-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="23a99-147">Dimensionen werden als Spalten in der Kennzahlausgabeeinheit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23a99-147">Dimensions will show as columns in the measure output entity.</span></span>
 
   1. <span data-ttu-id="23a99-148">Wählen Sie **Dimensionen bearbeiten** aus, um Datenattribute hinzuzufügen, nach denen Sie die Kennzahlen gruppieren möchten.</span><span class="sxs-lookup"><span data-stu-id="23a99-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="23a99-149">Zum Beispiel Stadt oder Geschlecht.</span><span class="sxs-lookup"><span data-stu-id="23a99-149">For example, city or gender.</span></span> <span data-ttu-id="23a99-150">Standardmäßig wird die *Kundennummer*-Dimension zum Erstellen von *Kennzahlen auf Kundenebene* ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="23a99-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="23a99-151">Sie können die Standarddimension entfernen, wenn Sie *Kennzahlen auf Unternehmensebene* erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="23a99-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="23a99-152">Wählen Sie **Fertig**, um die Dimensionen zur Kennzahl hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="23a99-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="23a99-153">Wenn Ihre Daten Werte enthalten, die Sie beispielsweise durch eine Ganzzahl ersetzen müssen, ersetzen Sie *null* mit *0* und wählen **Regeln** aus.</span><span class="sxs-lookup"><span data-stu-id="23a99-153">If there are values in your data that you need to replace with an integer—for example, replace *null* with *0*—select **Rules**.</span></span> <span data-ttu-id="23a99-154">Konfigurieren Sie die Regel und stellen Sie sicher, dass Sie nur ganze Zahlen als Ersatz auswählen.</span><span class="sxs-lookup"><span data-stu-id="23a99-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="23a99-155">Wenn zwischen der von Ihnen zugeordneten Datenentität und der *Kunden* Entität mehrere Pfade vorhanden sind, müssen Sie einen der identifizierten [Entitätsbeziehungspfade auswählen](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="23a99-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="23a99-156">Die Kennzahlenergebnisse können je nach ausgewähltem Pfad variieren.</span><span class="sxs-lookup"><span data-stu-id="23a99-156">Measure results can vary depending on the selected path.</span></span> 
   
   1. <span data-ttu-id="23a99-157">Wählen Sie **Dateneinstellungen**, und wählen Sie den Entitätspfad aus, der zur Identifizierung Ihrer Kennzahl verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="23a99-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="23a99-158">Wenn es nur einen einzigen Weg zur Entität *Kunde* gibt, wird dieses Steuerelement nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23a99-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="23a99-159">Wählen **Fertig**, um Ihre Auswahl anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="23a99-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Wählen Sie den Entitätspfad für die Kennzahl aus.":::

1. <span data-ttu-id="23a99-161">Wählen Sie aus **Neue Berechnung**, um weitere Berechnungen für die Kennzahl hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="23a99-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="23a99-162">Sie können nur Entitäten im selben Entitätspfad für neue Berechnungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="23a99-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="23a99-163">Weitere Berechnungen werden als neue Spalten in der Kennzahlausgabeeinheit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23a99-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="23a99-164">Wählen Sie **...** für die Berechnung aus, um **Duplikat**, **Umbenennen** oder **Entfernen** zur Berechnung einer Kennzahl auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="23a99-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="23a99-165">Im Bereich **Vorschau** sehen Sie das Datenschema der Kennzahlausgabeentität, einschließlich Filter und Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="23a99-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="23a99-166">Die Vorschau reagiert dynamisch auf Änderungen in der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="23a99-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="23a99-167">Wählen **Ausführen**, um die Ergebnisse für die konfigurierte Messung zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="23a99-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="23a99-168">Wählen Sie **Speichern und schließen** aus, wenn Sie die aktuelle Konfiguration beibehalten und die Kennzahlmessung später ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="23a99-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="23a99-169">Gehen Sie zu **Kennzahlen**, um die neu erstellte Kennzahl in der Liste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="23a99-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="23a99-170">Verwenden Sie eine Vorlage, um eine Kennzahl zu erstellen</span><span class="sxs-lookup"><span data-stu-id="23a99-170">Use a template to build a measure</span></span>

<span data-ttu-id="23a99-171">Sie können vordefinierte Vorlagen häufig verwendeter Kennzahlen verwenden, um sie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="23a99-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="23a99-172">Detaillierte Beschreibungen der Vorlagen und eine geführte Erfahrung helfen Ihnen bei der effizienten Erstellung von Kennzahlen.</span><span class="sxs-lookup"><span data-stu-id="23a99-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="23a99-173">Vorlagen bauen auf zugeordneten Daten aus der *Einheitliche Aktivität*-Entität auf.</span><span class="sxs-lookup"><span data-stu-id="23a99-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="23a99-174">Stellen Sie also sicher, dass Sie [Kundenaktivitäten](activities.md) konfiguriert haben, bevor Sie eine Kennzahl aus einer Vorlage erstellen.</span><span class="sxs-lookup"><span data-stu-id="23a99-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="23a99-175">Verfügbare Kennzahlenvorlagen:</span><span class="sxs-lookup"><span data-stu-id="23a99-175">Available measure templates:</span></span> 
- <span data-ttu-id="23a99-176">Durchschnittlicher Transaktionswert (ATV)</span><span class="sxs-lookup"><span data-stu-id="23a99-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="23a99-177">Transaktionswert insgesamt</span><span class="sxs-lookup"><span data-stu-id="23a99-177">Total transaction value</span></span>
- <span data-ttu-id="23a99-178">Durchschnittlicher täglicher Umsatz</span><span class="sxs-lookup"><span data-stu-id="23a99-178">Average daily revenue</span></span>
- <span data-ttu-id="23a99-179">Durchschnittlicher Jahresumsatz</span><span class="sxs-lookup"><span data-stu-id="23a99-179">Average yearly revenue</span></span>
- <span data-ttu-id="23a99-180">Transaktionsanzahl</span><span class="sxs-lookup"><span data-stu-id="23a99-180">Transaction count</span></span>
- <span data-ttu-id="23a99-181">Erhaltene Treuepunkte</span><span class="sxs-lookup"><span data-stu-id="23a99-181">Loyalty points earned</span></span>
- <span data-ttu-id="23a99-182">Eingelöste Treuepunkte</span><span class="sxs-lookup"><span data-stu-id="23a99-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="23a99-183">Treuepunktebilanz</span><span class="sxs-lookup"><span data-stu-id="23a99-183">Loyalty points balance</span></span>
- <span data-ttu-id="23a99-184">Aktive Kundenlebensdauer</span><span class="sxs-lookup"><span data-stu-id="23a99-184">Active customer lifespan</span></span>
- <span data-ttu-id="23a99-185">Dauer der Treuemitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="23a99-185">Loyalty membership duration</span></span>
- <span data-ttu-id="23a99-186">Zeit seit dem letzten Kauf</span><span class="sxs-lookup"><span data-stu-id="23a99-186">Time since last purchase</span></span>

<span data-ttu-id="23a99-187">Das folgende Verfahren beschreibt die Schritte zum Erstellen einer neuen Kennzahl mithilfe einer Vorlage.</span><span class="sxs-lookup"><span data-stu-id="23a99-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="23a99-188">Gehen Sie in den Zielgruppen-Insights auf **Kennzahlen**.</span><span class="sxs-lookup"><span data-stu-id="23a99-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="23a99-189">Wählen Sie **Neu** und dann **Vorlage auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="23a99-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Screenshot des Dropdown-Menüs beim Erstellen einer neuen Kennzahl mit Hervorhebung auf der Vorlage.":::

1. <span data-ttu-id="23a99-191">Suchen Sie die Vorlage, die Ihren Anforderungen entspricht, und wählen Sie **Vorlage auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="23a99-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="23a99-192">Überprüfen Sie die erforderlichen Daten und wählen Sie **Los geht's** aus, wenn Sie alle Daten an Ort und Stelle haben.</span><span class="sxs-lookup"><span data-stu-id="23a99-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="23a99-193">Im Bereich **Name bearbeiten** legen Sie den Namen für Ihre Kennzahl und die Ausgabeentität fest.</span><span class="sxs-lookup"><span data-stu-id="23a99-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="23a99-194">Wählen Sie **Fertig** aus.</span><span class="sxs-lookup"><span data-stu-id="23a99-194">Select **Done**.</span></span>

1. <span data-ttu-id="23a99-195">Im Abschnitt **Zeitraum festlegen** definieren Sie den Zeitrahmen der zu verwendenden Daten.</span><span class="sxs-lookup"><span data-stu-id="23a99-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="23a99-196">Wählen Sie aus, ob die neue Kennzahl das gesamte DataSet abdecken soll, indem Sie **Immer** oder **Spezifischen Zeitraum** auswählen, wenn Sie möchten, dass sich die Kennzahl nur auf einen bestimmten Zeitraum bezieht.</span><span class="sxs-lookup"><span data-stu-id="23a99-196">Choose if you want the new measure to cover the entire dataset by selecting **All time**, or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Screenshot mit dem Abschnitt zum Zeitraum beim Konfigurieren einer Kennzahl aus einer Vorlage.":::

1. <span data-ttu-id="23a99-198">Wählen Sie im nächsten Abschnitt **Daten hinzufügen** aus, um die Aktivitäten auszuwählen und die entsprechenden Daten von Ihrer *Einheitliche Aktivität*-Entität zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="23a99-198">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="23a99-199">Schritt 1 von 2: Unter **Aktivitätstyp** wählen Sie den Typ der Entität, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="23a99-199">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="23a99-200">Für **Aktivitäten** wählen Sie die Objekte aus, die Sie zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="23a99-200">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="23a99-201">Schritt 2 von 2: Wählen Sie das Attribut aus der *Einheitliche Aktivität*-Entität für die von der Formel geforderte Komponente aus.</span><span class="sxs-lookup"><span data-stu-id="23a99-201">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="23a99-202">Für den durchschnittlichen Transaktionswert ist dies beispielsweise das Attribut, das den Transaktionswert darstellt.</span><span class="sxs-lookup"><span data-stu-id="23a99-202">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="23a99-203">Für **Aktivitätszeitstempel** wählen Sie das Attribut aus der Entität „Einheitliche Aktivität“ aus, das Datum und Uhrzeit der Aktivität darstellt.</span><span class="sxs-lookup"><span data-stu-id="23a99-203">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="23a99-204">Sobald die Datenzuordnung erfolgt ist, können Sie den Status als **Abgeschlossen** und den Namen der zugeordneten Aktivitäten und Attribute anzeigen.</span><span class="sxs-lookup"><span data-stu-id="23a99-204">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Screenshot einer abgeschlossenen Kennzahlvorlagenkonfiguration.":::

1. <span data-ttu-id="23a99-206">Sie können jetzt **Ausführen** auswählen, um die Ergebnisse der Messung zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="23a99-206">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="23a99-207">Um dies später zu verfeinern, wählen Sie **Entwurf speichern**.</span><span class="sxs-lookup"><span data-stu-id="23a99-207">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="23a99-208">Verwalten von Kennzahlen</span><span class="sxs-lookup"><span data-stu-id="23a99-208">Manage your measures</span></span>

<span data-ttu-id="23a99-209">Die Liste der Kennzahlen finden Sie auf der Seite **Kennzahlen**.</span><span class="sxs-lookup"><span data-stu-id="23a99-209">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="23a99-210">Sie finden Informationen zu Kennzahlentyp, Ersteller, Erstellungsdatum, Status und Zustand.</span><span class="sxs-lookup"><span data-stu-id="23a99-210">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="23a99-211">Wenn Sie eine Kennzahl aus der Liste auswählen, können Sie eine Vorschau der Ausgabe anzeigen und eine CSV-Datei herunterladen.</span><span class="sxs-lookup"><span data-stu-id="23a99-211">When you select a measure from the list, you can preview the output and download a CSV file.</span></span>

<span data-ttu-id="23a99-212">Um alle Ihre Kennzahlen gleichzeitig zu aktualisieren, wählen Sie **Alle aktualisieren** aus, ohne eine bestimmte Kennzahl auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="23a99-212">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="23a99-213">![Maßnahmen zur Verwaltung einzelner Kennzahlen.](media/measure-actions.png "Maßnahmen zur Verwaltung einzelner Kennzahlen.")</span><span class="sxs-lookup"><span data-stu-id="23a99-213">![Actions to manage single measures.](media/measure-actions.png "Actions to manage single measures.")</span></span>

<span data-ttu-id="23a99-214">Wählen Sie eine Kennzahl aus den folgenden Optionen in der Liste aus:</span><span class="sxs-lookup"><span data-stu-id="23a99-214">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="23a99-215">Wählen Sie den Kennzahlnamen aus, um dessen Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="23a99-215">Select the measure name to see its details.</span></span>
- <span data-ttu-id="23a99-216">**Bearbeiten** der Konfiguration der Kennzahl.</span><span class="sxs-lookup"><span data-stu-id="23a99-216">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="23a99-217">**Aktualisieren** Sie die Maßnahme basierend auf den neuesten Daten.</span><span class="sxs-lookup"><span data-stu-id="23a99-217">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="23a99-218">**Umbenennen** der Kennzahl.</span><span class="sxs-lookup"><span data-stu-id="23a99-218">**Rename** the measure.</span></span>
- <span data-ttu-id="23a99-219">**Löschen** der Kennzahl.</span><span class="sxs-lookup"><span data-stu-id="23a99-219">**Delete** the measure.</span></span>
- <span data-ttu-id="23a99-220">**Aktivieren** oder **Deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="23a99-220">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="23a99-221">Inaktive Maßnahmen werden während einer [geplanten Aktualisierung](system.md#schedule-tab) nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="23a99-221">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="23a99-222">Es gibt [sechs Arten von Status](system.md#status-types) für Aufgaben/Prozesse.</span><span class="sxs-lookup"><span data-stu-id="23a99-222">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="23a99-223">Darüber hinaus [hängen die meisten Prozesse von anderen nachfolgenden Prozessen ab](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="23a99-223">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="23a99-224">Sie können den Status eines Prozesses auswählen, um Details zum Fortschritt des gesamten Auftrags anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="23a99-224">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="23a99-225">Nach der Auswahl von **Siehe Einzelheiten** für eine der Aufgaben des Auftrags finden Sie zusätzliche Informationen: Bearbeitungszeit, das letzte Verarbeitungsdatum und alle mit der Aufgabe verbundenen Fehler und Warnungen.</span><span class="sxs-lookup"><span data-stu-id="23a99-225">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="23a99-226">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="23a99-226">Next step</span></span>

<span data-ttu-id="23a99-227">Sie können vorhandene Maßnahmen verwenden, um [ein Kundensegment](segments.md) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="23a99-227">You can use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
