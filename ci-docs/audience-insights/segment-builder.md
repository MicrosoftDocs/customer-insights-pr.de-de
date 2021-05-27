---
title: Segmente erstellen und verwalten
description: Erstellen Sie Kundensegmente, um sie auf der Grundlage verschiedener Attribute zu gruppieren.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064936"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="86eb2-103">Segmente erstellen und verwalten</span><span class="sxs-lookup"><span data-stu-id="86eb2-103">Create and manage segments</span></span>

<span data-ttu-id="86eb2-104">Sie können komplexe Filter mit Bezug zur einheitlichen Kundenentität und den verwandten Entitäten festlegen.</span><span class="sxs-lookup"><span data-stu-id="86eb2-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="86eb2-105">Jedes Segment erstellt nach der Verarbeitung eine Reihe von Kundendatensätzen, die Sie exportieren und für die Sie Maßnahmen ergreifen können.</span><span class="sxs-lookup"><span data-stu-id="86eb2-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="86eb2-106">Segmente werden auf der Seite **Segmente** verwaltet.</span><span class="sxs-lookup"><span data-stu-id="86eb2-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="86eb2-107">Das folgende Beispiel veranschaulicht die Funktionalität der Segmentierung.</span><span class="sxs-lookup"><span data-stu-id="86eb2-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="86eb2-108">Wir haben ein Segment für Kunden definiert, die in den letzten 90 Tagen Waren im Wert von mindestens 500 US-Dollar bestellt haben *und* die an einem Kundenserviceanruf beteiligt waren, der eskaliert wurde.</span><span class="sxs-lookup"><span data-stu-id="86eb2-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Screenshot der Segment Builder-Benutzeroberfläche mit zwei Gruppen, die ein Kundensegment angeben.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="86eb2-110">Ein neues Segment erstellen</span><span class="sxs-lookup"><span data-stu-id="86eb2-110">Create a new segment</span></span>

<span data-ttu-id="86eb2-111">Es gibt mehrere Wege, ein neues Segment zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="86eb2-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="86eb2-112">In diesem Abschnitt wird beschrieben, wie Sie ein *leeres Segment* von Grund auf neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="86eb2-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="86eb2-113">Sie können auch ein *schnelles Segment* basierend auf vorhandenen Entitäten erstellen oder Maschinelles Lernen-Modelle verwenden, um *vorgeschlagene Segmente* zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="86eb2-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="86eb2-114">Weitere Informationen: [Segmentübersicht](segments.md).</span><span class="sxs-lookup"><span data-stu-id="86eb2-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="86eb2-115">Während Sie ein Segment erstellen, können Sie einen Entwurf speichern.</span><span class="sxs-lookup"><span data-stu-id="86eb2-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="86eb2-116">Es wird als inaktives Segment gespeichert und kann nicht aktiviert werden, wenn eine gültige Konfiguration vorliegt.</span><span class="sxs-lookup"><span data-stu-id="86eb2-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="86eb2-117">Gehen Sie zur Seite **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="86eb2-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="86eb2-118">Wählen Sie **Neu** > **Leeres Segment** aus.</span><span class="sxs-lookup"><span data-stu-id="86eb2-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="86eb2-119">In dem Bereich **Neues Segment** wählen Sie einen Segmenttyp aus.</span><span class="sxs-lookup"><span data-stu-id="86eb2-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="86eb2-120">**Dynamische Segmente** nach einem wiederkehrenden Zeitplan [aktualisieren](segments.md#refresh-segments).</span><span class="sxs-lookup"><span data-stu-id="86eb2-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="86eb2-121">**Statische Segmente** einmal ausführen, wenn Sie sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="86eb2-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="86eb2-122">Stellen Sie einen **Name der Ausgabeentität** für das Segment bereit.</span><span class="sxs-lookup"><span data-stu-id="86eb2-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="86eb2-123">Geben Sie optional einen Anzeigenamen und eine Beschreibung an, die die Identifizierung des Segments erleichtert.</span><span class="sxs-lookup"><span data-stu-id="86eb2-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="86eb2-124">Wählen Sie **Weiter**, um zu der Seite **Segment-Builder** zu gelangen, auf der Sie eine Gruppe definieren.</span><span class="sxs-lookup"><span data-stu-id="86eb2-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="86eb2-125">Eine Gruppe ist eine Gruppe von Kunden.</span><span class="sxs-lookup"><span data-stu-id="86eb2-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="86eb2-126">Wählen Sie die Entität, die das Attribut enthält, nach dem Sie segmentieren möchten.</span><span class="sxs-lookup"><span data-stu-id="86eb2-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="86eb2-127">Wählen Sie das Attribut aus, nach dem segmentiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="86eb2-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="86eb2-128">Dieses Attribut kann einen von vier Werttypen haben: numerisch, Zeichenfolge, Datum oder boolesch.</span><span class="sxs-lookup"><span data-stu-id="86eb2-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="86eb2-129">Wählen Sie einen Operator und einen Wert für das ausgewählte Attribut.</span><span class="sxs-lookup"><span data-stu-id="86eb2-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="86eb2-130">![Benutzerdefinierter Gruppenfilter](media/customer-group-numbers.png "Kundengruppen-Filter")</span><span class="sxs-lookup"><span data-stu-id="86eb2-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="86eb2-131">Anzahl</span><span class="sxs-lookup"><span data-stu-id="86eb2-131">Number</span></span> |<span data-ttu-id="86eb2-132">Definition</span><span class="sxs-lookup"><span data-stu-id="86eb2-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="86eb2-133">1</span><span class="sxs-lookup"><span data-stu-id="86eb2-133">1</span></span>     |<span data-ttu-id="86eb2-134">Entity</span><span class="sxs-lookup"><span data-stu-id="86eb2-134">Entity</span></span>          |
   |<span data-ttu-id="86eb2-135">2</span><span class="sxs-lookup"><span data-stu-id="86eb2-135">2</span></span>     |<span data-ttu-id="86eb2-136">Attribut</span><span class="sxs-lookup"><span data-stu-id="86eb2-136">Attribute</span></span>          |
   |<span data-ttu-id="86eb2-137">3</span><span class="sxs-lookup"><span data-stu-id="86eb2-137">3</span></span>    |<span data-ttu-id="86eb2-138">Operator</span><span class="sxs-lookup"><span data-stu-id="86eb2-138">Operator</span></span>         |
   |<span data-ttu-id="86eb2-139">4</span><span class="sxs-lookup"><span data-stu-id="86eb2-139">4</span></span>    |<span data-ttu-id="86eb2-140">Wert</span><span class="sxs-lookup"><span data-stu-id="86eb2-140">Value</span></span>         |

   1. <span data-ttu-id="86eb2-141">Um weitere Bedingungen zu einer Gruppe hinzuzufügen, können Sie zwei logische Operatoren verwenden:</span><span class="sxs-lookup"><span data-stu-id="86eb2-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="86eb2-142">**AND** Operator: Beide Bedingungen müssen als Teil des Segmentierungsprozesses erfüllt sein.</span><span class="sxs-lookup"><span data-stu-id="86eb2-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="86eb2-143">Diese Option ist am nützlichsten, wenn Sie Bedingungen für verschiedene Entitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="86eb2-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="86eb2-144">**OR**-Operator: Jede der beiden Bedingungen muss als Teil des Segmentierungsprozesses erfüllt sein.</span><span class="sxs-lookup"><span data-stu-id="86eb2-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="86eb2-145">Diese Option ist am nützlichsten, wenn Sie mehrere Bedingungen für dieselbe Entität definieren.</span><span class="sxs-lookup"><span data-stu-id="86eb2-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="86eb2-146">![OR-Operator, wobei jede der beiden Bedingungen erfüllt sein muss](media/segmentation-either-condition.png "OR-Operator, wobei jede der beiden Bedingungen erfüllt sein muss")</span><span class="sxs-lookup"><span data-stu-id="86eb2-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="86eb2-147">Es ist derzeit möglich, einen **OR** Operator unter einem **AND** Operator zu verschachteln, aber nicht umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="86eb2-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="86eb2-148">Jede Gruppe entspricht einer Gruppe von Kunden.</span><span class="sxs-lookup"><span data-stu-id="86eb2-148">Each group matches set of customers.</span></span> <span data-ttu-id="86eb2-149">Sie können Gruppen kombinieren, um die Kunden einzuschließen, die für Ihren Geschäftsfall erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="86eb2-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="86eb2-150">Wählen Sie **Gruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="86eb2-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="86eb2-151">![Kundengruppe Gruppe hinzufügen](media/customer-group-add-group.png "Kundengruppe Gruppe hinzufügen")</span><span class="sxs-lookup"><span data-stu-id="86eb2-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="86eb2-152">Wählen Sie einen der eingestellten Operatoren aus: **Gesamtmenge**, **Überschneiden**, oder **Außer**.</span><span class="sxs-lookup"><span data-stu-id="86eb2-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="86eb2-153">![Kundengruppe Vereinigung hinzufügen](media/customer-group-union.png "Kundengruppe Vereinigung hinzufügen")</span><span class="sxs-lookup"><span data-stu-id="86eb2-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="86eb2-154">**Vereinigen** vereinigt die beiden Gruppen.</span><span class="sxs-lookup"><span data-stu-id="86eb2-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="86eb2-155">**Überschneiden** überschneidet die beiden Gruppen.</span><span class="sxs-lookup"><span data-stu-id="86eb2-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="86eb2-156">Nur Daten, die *beiden Gruppen gemeinsam* sind, werden in der vereinigten Gruppe beibehalten.</span><span class="sxs-lookup"><span data-stu-id="86eb2-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="86eb2-157">**Außer** kombiniert die beiden Gruppen.</span><span class="sxs-lookup"><span data-stu-id="86eb2-157">**Except** combines the two groups.</span></span> <span data-ttu-id="86eb2-158">Nur Daten in Gruppe A, die *nicht gemeinsam* mit Daten in Gruppe B sind, bleiben erhalten.</span><span class="sxs-lookup"><span data-stu-id="86eb2-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="86eb2-159">Wenn die Entität über [Beziehungen](relationships.md) mit der einheitlichen Kundenentität verbunden ist, müssen Sie den Beziehungspfad definieren, um ein gültiges Segment zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="86eb2-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="86eb2-160">Fügen Sie die Entitäten aus dem Beziehungspfad hinzu, bis Sie die Entität **Kunde: Customer Insights** aus der Dropdownliste auswählen können.</span><span class="sxs-lookup"><span data-stu-id="86eb2-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="86eb2-161">Dann wählen Sie **Alle Datensätze** für jeden Schritt aus.</span><span class="sxs-lookup"><span data-stu-id="86eb2-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="86eb2-162">![Beziehungspfad während der Segmenterstellung](media/segments-multiple-relationships.png "Beziehungspfad während der Segmenterstellung")</span><span class="sxs-lookup"><span data-stu-id="86eb2-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="86eb2-163">Standardmäßig generieren Segmente eine Ausgabeentität, die alle Attribute von Kundenprofilen enthält, die den definierten Filtern entsprechen.</span><span class="sxs-lookup"><span data-stu-id="86eb2-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="86eb2-164">Wenn ein Segment auf anderen Entitäten als der Entität *Kunde* basiert, können Sie der Ausgabeentität weitere Attribute dieser Entitäten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="86eb2-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="86eb2-165">Wählen Sie, **Projektattribute**, um die Attribute auszuwählen, die an die Ausgabeentität angehängt werden.</span><span class="sxs-lookup"><span data-stu-id="86eb2-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="86eb2-166">Beispiel: Ein Segment basiert auf einer Entität, die Kundenaktivitätsdaten enthält, die sich auf die Entität *Kunde* beziehen.</span><span class="sxs-lookup"><span data-stu-id="86eb2-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="86eb2-167">Das Segment sucht nach allen Kunden, die in den letzten 60 Tagen den Helpdesk angerufen haben.</span><span class="sxs-lookup"><span data-stu-id="86eb2-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="86eb2-168">Sie können die Anrufdauer und die Anzahl der Anrufe an alle übereinstimmenden Kundendatensätze in der Ausgabeentität anhängen.</span><span class="sxs-lookup"><span data-stu-id="86eb2-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="86eb2-169">Diese Informationen können hilfreich sein, um eine E-Mail mit hilfreichen Links zu Online-Hilfeartikeln und häufig gestellten Fragen an Kunden zu senden, die häufig angerufen haben.</span><span class="sxs-lookup"><span data-stu-id="86eb2-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="86eb2-170">Projizierte Attribute funktionieren nur für Entitäten, die eine Eins-zu-Viele-Beziehung zur Kundenentität haben.</span><span class="sxs-lookup"><span data-stu-id="86eb2-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="86eb2-171">Beispielsweise kann ein Kunde mehrere Abonnements haben.</span><span class="sxs-lookup"><span data-stu-id="86eb2-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="86eb2-172">Sie können nur Attribute einer Entität projizieren, die in jeder Gruppe von Segmentabfragen verwendet wird, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="86eb2-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="86eb2-173">Projizierte Attribute werden bei Verwendung von festgelegten Operatoren berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="86eb2-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="86eb2-174">Wählen Sie **Speichern**, um Ihr Segment zu speichern.</span><span class="sxs-lookup"><span data-stu-id="86eb2-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="86eb2-175">Ihr Segment wird gespeichert und verarbeitet, wenn alle Anforderungen validiert sind.</span><span class="sxs-lookup"><span data-stu-id="86eb2-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="86eb2-176">Andernfalls wird es als Entwurf gespeichert.</span><span class="sxs-lookup"><span data-stu-id="86eb2-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="86eb2-177">Wählen Sie **Zurück zu Segmenten**, um zur Seite **Segmente** zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="86eb2-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="86eb2-178">Schnelle Segmente</span><span class="sxs-lookup"><span data-stu-id="86eb2-178">Quick segments</span></span>

<span data-ttu-id="86eb2-179">Mit schnellen Segmenten können Sie schnell einfache Segmente mit einem einzigen Operator erstellen, um schnellere Einblicke zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="86eb2-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="86eb2-180">Wählen Sie auf der Seite **Segment** aus und wählen Sie **Neu** > **Erstellen aus**.</span><span class="sxs-lookup"><span data-stu-id="86eb2-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="86eb2-181">Wählen Sie die Option **Profile**, um ein Segment zu erstellen, das auf der *einheitlichen Kundenentität* basiert.</span><span class="sxs-lookup"><span data-stu-id="86eb2-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="86eb2-182">Wählen Sie die Option **Maßnahmen** zum Erstellen eines Segments um zuvor erstellte Kennzahlen.</span><span class="sxs-lookup"><span data-stu-id="86eb2-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="86eb2-183">Wählen Sie die Option **Intelligenz** zum Erstellen eines Segments für eine der Ausgabeentitäten aus, die Sie mit einer der beiden Funktionen **Vorhersagen** oder **Benutzerdefinierte Modelle** generiert haben.</span><span class="sxs-lookup"><span data-stu-id="86eb2-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="86eb2-184">Wählen Sie im Dialogfeld **Neues schnelles Segment** ein Attribut aus der Dropdownliste **Feld** aus.</span><span class="sxs-lookup"><span data-stu-id="86eb2-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="86eb2-185">Das System liefert einige zusätzliche Erkenntnisse, die Ihnen helfen, bessere Segmente Ihrer Kunden zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="86eb2-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="86eb2-186">Für kategoriale Felder werden 10 Top-Kundenzahlen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="86eb2-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="86eb2-187">Wählen Sie einen **Wert** und wählen Sie **Überprüfung**.</span><span class="sxs-lookup"><span data-stu-id="86eb2-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="86eb2-188">Bei einem numerischen Attribut zeigt das System an, welcher Attributwert unter das Perzentil des jeweiligen Kunden fällt.</span><span class="sxs-lookup"><span data-stu-id="86eb2-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="86eb2-189">Wählen Sie einen **Bediener** und einen **Wert**, dann wählen Sie **Review**.</span><span class="sxs-lookup"><span data-stu-id="86eb2-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="86eb2-190">Das System liefert Ihnen eine **geschätzte Segmentgröße**.</span><span class="sxs-lookup"><span data-stu-id="86eb2-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="86eb2-191">Sie können wählen, ob Sie das von Ihnen definierte Segment generieren oder es zunächst erneut aufrufen, um eine andere Segmentgröße zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="86eb2-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="86eb2-192">![Name und Schätzung für ein Quick-Segment](media/quick-segment-name.png "Name und Schätzung für ein schnelles Segment")</span><span class="sxs-lookup"><span data-stu-id="86eb2-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="86eb2-193">Geben Sie einen **Name** für Ihr Segment an.</span><span class="sxs-lookup"><span data-stu-id="86eb2-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="86eb2-194">Geben Sie optional einen **Anzeigename** ein.</span><span class="sxs-lookup"><span data-stu-id="86eb2-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="86eb2-195">Wählen Sie **Speichern**, um Ihr Segment zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="86eb2-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="86eb2-196">Nachdem das Segment fertig bearbeitet wurde, können Sie es wie jedes andere von Ihnen erstellte Segment anzeigen.</span><span class="sxs-lookup"><span data-stu-id="86eb2-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="86eb2-197">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="86eb2-197">Next steps</span></span>

<span data-ttu-id="86eb2-198">[Exportieren Sie ein Segment](export-destinations.md) und erkunden Sie die [Kundenkarte](customer-card-add-in.md) und [Connectors](export-power-bi.md), um Einblicke auf Kundenebene zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="86eb2-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
