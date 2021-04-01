---
title: Vervollständigen Sie Teildaten mithilfe von Vorhersagen
description: Verwenden Sie Vorhersagen, um unvollständige Kundendaten aufzufüllen.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3342328b9eead9bdcb8b41f119a1d0a5823001c8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595900"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="94be6-103">Ergänzen von Teildaten mit Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="94be6-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="94be6-104">Mit Vorhersagen können Sie auf einfache Weise Werte vorhersagen, die Ihr Verständnis für einen Kunden verbessern können.</span><span class="sxs-lookup"><span data-stu-id="94be6-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="94be6-105">Auf der Seite **Intelligenz** > **Vorhersagen** können Sie **Meine Vorhersagen** auswählen, um Vorhersagen zu sehen, die Sie in anderen Teilen von Zielgruppen-Insights konfiguriert haben, und die Sie weiter anpassen können.</span><span class="sxs-lookup"><span data-stu-id="94be6-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="94be6-106">Sie können diese Funktion nicht verwenden, wenn Ihre Umgebung Azure Data Lake Gen 2-Speicher verwendet.</span><span class="sxs-lookup"><span data-stu-id="94be6-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="94be6-107">Die Vorhersagenfunktion verwendet automatisierte Mittel zur Auswertung von Daten und zur Erstellung von Vorhersagen auf der Grundlage dieser Daten und kann daher als Methode zur Erstellung von Profilen verwendet werden, da dieser Begriff in der Datenschutz-Grundverordnung („DSGVO“) definiert ist.</span><span class="sxs-lookup"><span data-stu-id="94be6-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="94be6-108">Die Nutzung dieser Funktion durch den Kunden zur Datenverarbeitung kann der DSGVO oder anderen Gesetzen oder Vorschriften unterliegen.</span><span class="sxs-lookup"><span data-stu-id="94be6-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="94be6-109">Sie sind dafür verantwortlich, dass Ihre Dynamics 365 Customer Insights-Nutzung, einschließlich der Vorhersagen, allen geltenden Gesetzen und Vorschriften entspricht, einschließlich Gesetzen in Bezug auf Privatsphäre, personenbezogene Daten, biometrische Daten, Datenschutz und Vertraulichkeit der Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="94be6-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="94be6-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="94be6-110">Prerequisites</span></span>

<span data-ttu-id="94be6-111">Bevor Ihre Organisation die Vorhersagefunktion verwenden kann, müssen die folgenden Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="94be6-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="94be6-112">Ihre Organisation hat eine Instanz [ in der Common Data Service](/ai-builder/build-model#prerequisites) eingerichtet und sie befindet sich in der gleichen Organisation wie Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="94be6-112">Your organization has an instance [set up in the Common Data Service](/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="94be6-113">Ihre Umgebung ist mit Ihrer Common Data Service-Instanz verbunden.</span><span class="sxs-lookup"><span data-stu-id="94be6-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="94be6-114">Wenn Sie eine [neue Umgebung schaffen](manage-environments.md), konfigurieren Sie sie im Dialogfeld **Erstellen Sie eine Umgebung** und wählen **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="94be6-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="94be6-115">Wenn Sie bereits eine Umgebung erstellt haben, gehen Sie zu deren Einstellungen und wählen Sie **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="94be6-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="94be6-116">So oder so, geben Sie im Abschnitt **Vorhersagen verwenden** die Common Data Service-Instanz-URL ein, an die Sie Ihre Umgebung anhängen möchten.</span><span class="sxs-lookup"><span data-stu-id="94be6-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="94be6-117">Erstellen Sie eine Vorhersage in der Kunde-Entität</span><span class="sxs-lookup"><span data-stu-id="94be6-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="94be6-118">Gehen Sie in Zielgruppen-Insights zu **Daten** > **Entitäten**.</span><span class="sxs-lookup"><span data-stu-id="94be6-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="94be6-119">Wählen Sie die Entität **Kunde** aus.</span><span class="sxs-lookup"><span data-stu-id="94be6-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="94be6-120">Im Bereich **Kunde: CustomerInsights**-Entität, wählen Sie auf dem Register **Felder**.</span><span class="sxs-lookup"><span data-stu-id="94be6-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="94be6-121">Suchen Sie den Attributnamen, für den Sie Werte vorhersagen möchten, und wählen Sie dann das Symbol **Übersicht** in der Spalte **Zusammenfassung**.</span><span class="sxs-lookup"><span data-stu-id="94be6-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="94be6-122">![Übersichtssymbol](media/intelligence-overviewicon.png "Übersicht über das Symbol")</span><span class="sxs-lookup"><span data-stu-id="94be6-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="94be6-123">Wenn es eine hohe Rate fehlender Werte für Ihr Attribut gibt, wählen Sie **Fehlende Werte vorhersagen** aus, um mit Ihrer Vorhersage fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="94be6-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="94be6-124">![Übersichtsstatus mit angezeigter Schaltfläche zur Vorhersage fehlender Werte](media/intelligence-overviewpredictmissingvalues.png "Überblicksstatus mit angezeigter Schaltfläche zur Vorhersage fehlender Werte")</span><span class="sxs-lookup"><span data-stu-id="94be6-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="94be6-125">Stellen Sie einen **Anzeigename** und einen **Name der Ausgabeentität** für die Ergebnisse der Vorhersage bereit.</span><span class="sxs-lookup"><span data-stu-id="94be6-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="94be6-126">Eine vorbelegte Liste von Optionen zeigt an, wo Sie die Werte einer vorhergesagten Kategorie zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="94be6-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="94be6-127">In diesem Fall sind Ihre einzigen Kategorie-Optionen 0 oder 1, da sie der Wahr/Falsch- oder Binär-Natur der Vorhersage entsprechen.</span><span class="sxs-lookup"><span data-stu-id="94be6-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="94be6-128">Ordnen Sie in der Kategorie-Spalte die Feldwerte, die in der endgültigen Vorhersage als 0 klassifiziert werden sollen, als 0 und die Elemente, die Sie in der endgültigen Vorhersage als 1 klassifizieren möchten, als 1 zu.</span><span class="sxs-lookup"><span data-stu-id="94be6-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="94be6-129">![Beispiel mit zugeordneten Feldwerten zu Kategorien](media/intelligence-categorymapping.png "Beispiel für die Zuordnung von Feldwerten zu Kategorien")</span><span class="sxs-lookup"><span data-stu-id="94be6-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="94be6-130">Wählen Sie **Abgeschlossen**, und die Vorhersage wird verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="94be6-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="94be6-131">Die Bearbeitung wird je nach Umfang und Komplexität der Daten einige Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="94be6-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="94be6-132">Die Ergebnisse werden in einer neuen Entität basierend auf dem **Name der Ausgabeentität** der Vorhersage bereitgestellt, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="94be6-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="94be6-133">Erstellen einer Vorhersage beim Erstellen eines Segments</span><span class="sxs-lookup"><span data-stu-id="94be6-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="94be6-134">Die Vorhersage fehlender Werte für ein bestimmtes Attribut der Wahl ist auch bei der Erstellung eines Segments möglich.</span><span class="sxs-lookup"><span data-stu-id="94be6-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="94be6-135">Insbesondere, wenn Sie schnell ein Segment erstellen, das entweder auf Ihrer vereinheitlichten Kunden-Entität oder Ihrer Customer_Measure-Entität basiert.</span><span class="sxs-lookup"><span data-stu-id="94be6-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="94be6-136">Als Teil dieses Ablaufs wählen Sie ein bestimmtes Attribut aus, auf dem Ihr Segment basiert, z. B. Kundenzufriedenheit oder Kaufbetrag.</span><span class="sxs-lookup"><span data-stu-id="94be6-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="94be6-137">Bei der Segmenterstellung schlägt das System eine Methode zur Vorhersage fehlender Werte für dieses Attribut vor.</span><span class="sxs-lookup"><span data-stu-id="94be6-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="94be6-138">Gehen Sie in den Zielgruppen-Insights zu **Segmente** und wählen Sie die Kachel **Profile**.</span><span class="sxs-lookup"><span data-stu-id="94be6-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="94be6-139">Wählen Sie ein **Feld**, um ein Segment zu erstellen, und wählen Sie ein **Bediener**, dann wählen Sie **Überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="94be6-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="94be6-140">Geben Sie einen **Name** und einen **Anzeigename** für das Segment an.</span><span class="sxs-lookup"><span data-stu-id="94be6-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="94be6-141">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="94be6-141">Select **Save**.</span></span>

5. <span data-ttu-id="94be6-142">Wenn das von Ihnen erstellte Segment unvollständige Daten im Quellfeld enthält, können Sie die fehlenden Werte vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="94be6-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="94be6-143">![Schaltfläche Vorhersage](media/segments-predictoption.png "Schaltfläche Vorhersage")</span><span class="sxs-lookup"><span data-stu-id="94be6-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="94be6-144">Stellen Sie einen **Anzeigename** und einen **Name der Ausgabeentität** für die Ergebnisse der Vorhersage bereit.</span><span class="sxs-lookup"><span data-stu-id="94be6-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="94be6-145">**Fertig** auswählen</span><span class="sxs-lookup"><span data-stu-id="94be6-145">Select **Done**.</span></span> <span data-ttu-id="94be6-146">Ihre Vorhersage wird in Kürze in einer neuen Entität mit dem Namen generiert, den Sie für den **Namen der Ausgabeentität** angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="94be6-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="94be6-147">Eine Vorhersage anzeigen</span><span class="sxs-lookup"><span data-stu-id="94be6-147">View a prediction</span></span>

1. <span data-ttu-id="94be6-148">Gehen Sie in den Zielgruppen-Insights auf **Intelligenz** > **Vorhersagen** > **Meine Vorhersagen**.</span><span class="sxs-lookup"><span data-stu-id="94be6-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="94be6-149">Wählen Sie die Vorhersage aus, die Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="94be6-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="94be6-150">Markieren Sie die Auslassungspunkte in der Spalte **Aktionen** und wählen Sie **Ansicht**.</span><span class="sxs-lookup"><span data-stu-id="94be6-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="94be6-151">Sie sehen eine Reihe von Datenpunkten in der Ansicht Ihrer Vorhersage.</span><span class="sxs-lookup"><span data-stu-id="94be6-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="94be6-152">![Vorhersagen Seite](media/intelligence-predictionsviewpage.png "Seite Vorhersagen")</span><span class="sxs-lookup"><span data-stu-id="94be6-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="94be6-153">**Vorhergesagte Werte** zeigt die Zuordnung, die Sie während der Zuordnungsphase von Feldwert zu Kategorie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="94be6-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="94be6-154">Dies sind die Werte in Ihrem DataSet, die einer bestimmten Kategorie zugeordnet wurden.</span><span class="sxs-lookup"><span data-stu-id="94be6-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="94be6-155">-**Top-Einflussfaktoren** sind die Faktoren innerhalb Ihres Datensatzes, die am ehesten die Zuverlässigkeit der Vorhersage bezüglich der Zuordnung Ihres Feldwertes zu einer bestimmten Kategorie beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="94be6-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="94be6-156">**Leistung** zeigt an, wie sich die Vorhersagen entwickeln.</span><span class="sxs-lookup"><span data-stu-id="94be6-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="94be6-157">Wählen Sie den Link, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="94be6-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="94be6-158">**Vorschau** zeigt Beispiele des Ausgabedatensatzes Ihrer Vorhersage und die Wahrscheinlichkeit oder unser Vertrauen in den vorhergesagten Wert, wobei 0 unsicher und 1 sicher ist.</span><span class="sxs-lookup"><span data-stu-id="94be6-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="94be6-159">Aktualisieren einer Vorhersage</span><span class="sxs-lookup"><span data-stu-id="94be6-159">Update a prediction</span></span>

1. <span data-ttu-id="94be6-160">Gehen Sie in den Zielgruppen-Insights auf **Intelligenz** > **Vorhersagen** > **Meine Vorhersagen**.</span><span class="sxs-lookup"><span data-stu-id="94be6-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="94be6-161">Wählen Sie die Vorhersage, die Sie aktualisieren möchten, und wählen Sie das Symbol **Aktualisierung**.</span><span class="sxs-lookup"><span data-stu-id="94be6-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="94be6-162">Die Vorhersage wird für die Verarbeitung geplant.</span><span class="sxs-lookup"><span data-stu-id="94be6-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="94be6-163">Sie können den Zeitpunkt der letzten Aktualisierung in der Spalte **Aktualisiert** auf der Seite **Vorhersagen** sehen.</span><span class="sxs-lookup"><span data-stu-id="94be6-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="94be6-164">Bearbeiten einer Vorhersage</span><span class="sxs-lookup"><span data-stu-id="94be6-164">Edit a prediction</span></span>

<span data-ttu-id="94be6-165">Nachdem Sie eine Vorhersage erstellt haben, können Sie das Modell im AI Builder anpassen, um die Effektivität Ihres Modells zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="94be6-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="94be6-166">Gehen Sie in den Zielgruppen-Insights auf **Intelligenz** > **Vorhersagen** > **Meine Vorhersagen**.</span><span class="sxs-lookup"><span data-stu-id="94be6-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="94be6-167">Wählen Sie die Vorhersage aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="94be6-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="94be6-168">Markieren Sie die Auslassungspunkte in der Spalte **Aktionen** und wählen Sie **Ansicht**.</span><span class="sxs-lookup"><span data-stu-id="94be6-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="94be6-169">Wählen Sie **Anpassen in AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="94be6-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="94be6-170">Aktualisieren Sie Ihr Modell im AI Builder.</span><span class="sxs-lookup"><span data-stu-id="94be6-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="94be6-171">[Lernen Sie mehr über die Verwaltung von Modellen im AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="94be6-171">[Learn more about managing models in the AI builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="94be6-172">Der nächste Lauf Ihrer Vorhersage wird das von Ihnen erstellte aktualisierte Modell verwenden.</span><span class="sxs-lookup"><span data-stu-id="94be6-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="94be6-173">Neue Modelle, die in AI Builder erstellt wurden, werden nicht in Zielgruppen-Insights angezeigt, es sei denn, das Modell wurde aus den oben aufgeführten Erfahrungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="94be6-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="94be6-174">Eine Vorhersage entfernen</span><span class="sxs-lookup"><span data-stu-id="94be6-174">Remove a prediction</span></span>

1. <span data-ttu-id="94be6-175">Gehen Sie in den Zielgruppen-Insights auf **Intelligenz** > **Vorhersagen** > **Meine Vorhersagen**.</span><span class="sxs-lookup"><span data-stu-id="94be6-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="94be6-176">Wählen Sie die Vorhersage aus, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="94be6-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="94be6-177">Markieren Sie die Auslassungspunkte in der Spalte **Aktionen** und wählen Sie **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="94be6-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="94be6-178">Bestätigen Sie den Löschvorgang.</span><span class="sxs-lookup"><span data-stu-id="94be6-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="94be6-179">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="94be6-179">Troubleshooting</span></span>

<span data-ttu-id="94be6-180">Wenn Sie den Common Data Service-Anfügevorgang aufgrund eines Fehlers nicht abschließen können, können Sie versuchen, den Vorgang manuell abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="94be6-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="94be6-181">Es gibt zwei bekannte Probleme, die beim Anfügevorgang auftreten können:</span><span class="sxs-lookup"><span data-stu-id="94be6-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="94be6-182">Die Lösung Customer Card Add-in ist nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="94be6-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="94be6-183">Vervollständigen Sie die Anweisungen in Bezug auf [Installieren und Konfigurieren der Lösung](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="94be6-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="94be6-184">App-Berechtigungen werden nicht gewährt.</span><span class="sxs-lookup"><span data-stu-id="94be6-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="94be6-185">Wechseln Sie zu [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="94be6-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="94be6-186">**Umgebungen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="94be6-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="94be6-187">Wählen Sie die Auslassungspunkte neben der Umgebung aus, zu der Sie die Berechtigung hinzufügen möchten, und wählen Sie **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="94be6-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="94be6-188">Erweitern Sie **Benutzer + Berechtigungen** und wählen Sie **Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="94be6-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="94be6-189">Wählen Sie **+ Neu** und **Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="94be6-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="94be6-190">Wenn es noch nicht ausgewählt ist, wählen Sie **Anwendungsbenutzer** aus, und geben Sie die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="94be6-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="94be6-191">**Benutzername:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="94be6-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="94be6-192">**Anwendungs-ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="94be6-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="94be6-193">**Vorname:** Kunde</span><span class="sxs-lookup"><span data-stu-id="94be6-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="94be6-194">**Nachname:** Insights</span><span class="sxs-lookup"><span data-stu-id="94be6-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="94be6-195">**Primäre E-Mail-Adresse:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="94be6-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="94be6-196">Klicken Sie auf **Speichern und Schließen**.</span><span class="sxs-lookup"><span data-stu-id="94be6-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="94be6-197">Wählen Sie den gerade erstellten Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="94be6-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="94be6-198">Wählen Sie in der oberen Menüleiste **Rollen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="94be6-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="94be6-199">Wählen Sie **Systemadministrator** und dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="94be6-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]