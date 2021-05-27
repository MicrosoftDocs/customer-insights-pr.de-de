---
title: Aktivitätsbasierte Segmentvorschläge.
description: Mit Maschinellem Lernen können Sie anhand der Kundenaktivität neue und interessante Segmente finden.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034073"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="50ce3-103">Segmentvorschläge basierend auf Aktivitätsdaten (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="50ce3-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="50ce3-104">Entdecken Sie interessante Segmente Ihrer Kunden anhand von Kundenaktivitätsdaten, die in Customer Insights erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="50ce3-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="50ce3-105">Beispiele für Aktivitätsdaten sind Transaktionen, Support-Anrufdauer, Käufe oder Rückgaben.</span><span class="sxs-lookup"><span data-stu-id="50ce3-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="50ce3-106">Um Segmente vorzuschlagen, werden Aktivitätsdaten auf Aktualität, Häufigkeit und Geldwert (oder Dauer) analysiert.</span><span class="sxs-lookup"><span data-stu-id="50ce3-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="50ce3-107">Alternativ können Sie [vorgeschlagene Segmente generieren, um eine Kennzahl zu verbessern oder besser zu verstehen, was ein Attribut beeinflusst](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="50ce3-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Registerkarte Vorgeschlagene Segmente mit Segmentvorschlägen für aktivitätsbasierte und attributbasierte Segmente.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="50ce3-109">Kategorisieren Sie Kunden nach Aktivität</span><span class="sxs-lookup"><span data-stu-id="50ce3-109">Categorize customers by activity</span></span>

<span data-ttu-id="50ce3-110">Mit [Aktivitätsdaten](activities.md) in Customer Insights können wir Vorschläge generieren, die Kundengruppen repräsentieren:</span><span class="sxs-lookup"><span data-stu-id="50ce3-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="50ce3-111">aktivsten Kunden</span><span class="sxs-lookup"><span data-stu-id="50ce3-111">most active customers</span></span> 
- <span data-ttu-id="50ce3-112">Kunden, die die meisten Einkäufe getätigt haben</span><span class="sxs-lookup"><span data-stu-id="50ce3-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="50ce3-113">Kunden, die den größten Umsatz erzielt haben</span><span class="sxs-lookup"><span data-stu-id="50ce3-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="50ce3-114">Kunden, die in letzter Zeit nicht aktiv waren</span><span class="sxs-lookup"><span data-stu-id="50ce3-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="50ce3-115">Kunden, die häufig mit Ihrem Unternehmen interagieren</span><span class="sxs-lookup"><span data-stu-id="50ce3-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="50ce3-116">Wenn Sie ein Einzelhandelsgeschäft haben, können Sie herausfinden, welche Kunden die meisten Einnahmen erzielen, und sie mit einem Gutschein belohnen.</span><span class="sxs-lookup"><span data-stu-id="50ce3-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="50ce3-117">Oder Sie können gelegentliche Kunden identifizieren und ihnen anbieten, an einem Prämienprogramm teilzunehmen, damit sie Ihr Unternehmen häufiger besuchen.</span><span class="sxs-lookup"><span data-stu-id="50ce3-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="50ce3-118">Wenn Sie im Gesundheitswesen tätig sind und öffentliche Gesundheitsversorgung anbieten, ist es Ihr Ziel, die Kosten für einzelne Patienten zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="50ce3-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="50ce3-119">Eine Möglichkeit, dies zu tun, könnte darin bestehen, wiederkehrende Besuche zu reduzieren, indem bei möglichst wenigen Besuchen die bestmögliche Pflege bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="50ce3-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="50ce3-120">In diesem Fall ist es Ihr Ziel, die Besuchshäufigkeit niedrig zu halten und die wiederkehrenden Kosten für die Patienten zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="50ce3-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="50ce3-121">Oder Sie können Segmente von Patienten identifizieren, die häufige Termine und hohe wiederkehrende Kosten haben, und diese Fälle analysieren, um die Behandlung des Patienten zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="50ce3-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="50ce3-122">Erforderliche Daten</span><span class="sxs-lookup"><span data-stu-id="50ce3-122">Required data</span></span>

<span data-ttu-id="50ce3-123">Vorschläge werden basierend auf den ausgewählten Eingabedaten generiert.</span><span class="sxs-lookup"><span data-stu-id="50ce3-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="50ce3-124">Kundenprofile: Alle Kunden oder Mitglieder eines bestimmten Segments.</span><span class="sxs-lookup"><span data-stu-id="50ce3-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="50ce3-125">Zeitraum: Letzter Monat, letztes Jahr oder ein benutzerdefiniertes Zeitrahmen.</span><span class="sxs-lookup"><span data-stu-id="50ce3-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="50ce3-126">Aktivitätsart: Einkäufe, Einzelhandelsgeschäfte, Online-Transaktionen, Kundenunterstützungsfälle, Abonnements usw.</span><span class="sxs-lookup"><span data-stu-id="50ce3-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="50ce3-127">Entität in Customer Insights, die die Aktivitätsdaten enthält: Die UnifiedActivity-Entität oder die Entität für eine bestimmte Aktivität.</span><span class="sxs-lookup"><span data-stu-id="50ce3-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="50ce3-128">Zu berücksichtigende Dimensionen: Aktualität, Häufigkeit oder monetäre Dimension, abhängig von Ihren Geschäftsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="50ce3-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="50ce3-129">Generieren Sie vorgeschlagene Segmente</span><span class="sxs-lookup"><span data-stu-id="50ce3-129">Generate suggested segments</span></span>

1. <span data-ttu-id="50ce3-130">Gehen Sie zu **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="50ce3-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="50ce3-131">Wählen Sie die Registerkarte **Vorschläge (Vorschau)** aus.</span><span class="sxs-lookup"><span data-stu-id="50ce3-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="50ce3-132">Wählen Sie **Neue Vorschläge suchen** und wählen Sie **Kundenverhalten sehen oder antizipieren** aus.</span><span class="sxs-lookup"><span data-stu-id="50ce3-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="50ce3-133">Wählen Sie **Start** um die Anleitung zu befolgen.</span><span class="sxs-lookup"><span data-stu-id="50ce3-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Erster Schritt des Konfigurationsassistenten für ein vorgeschlagenes Segment basierend auf der Aktivität.":::

1. <span data-ttu-id="50ce3-135">Geben Sie die erforderlichen Eingabedaten ein und wählen Sie **Weiter** zum Fortfahren.</span><span class="sxs-lookup"><span data-stu-id="50ce3-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="50ce3-136">Kunden auswählen: Alle Kunden oder ein bestimmtes Segment einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="50ce3-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="50ce3-137">Aktivität auswählen: Wählen Sie den Aktivitätstyp und die Entitäten aus, die die Aktivität beschreiben.</span><span class="sxs-lookup"><span data-stu-id="50ce3-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="50ce3-138">Einstellungen: Legen Sie den zu berücksichtigenden Zeitraum und die Faktoren für Vorschläge fest und ordnen Sie die Attribute zu.</span><span class="sxs-lookup"><span data-stu-id="50ce3-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="50ce3-139">Überprüfen Sie Ihre Eingabe und wählen Sie **Ausführen**, um das Modell auszuführen und Vorschläge zu generieren.</span><span class="sxs-lookup"><span data-stu-id="50ce3-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="50ce3-140">Abhängig von der Anzahl der Kundenprofile und ausgewählten Aktivitäten kann der Vorgang einige Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="50ce3-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="50ce3-141">Nachdem Sie die Vorschläge generiert haben, können Sie sie nach der Dimension oder dem Wert filtern, an dem Sie am meisten interessiert sind.</span><span class="sxs-lookup"><span data-stu-id="50ce3-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="50ce3-142">Vorgeschlagene Segmentdetails anzeigen</span><span class="sxs-lookup"><span data-stu-id="50ce3-142">View details of a suggested segment</span></span>

<span data-ttu-id="50ce3-143">Sobald die Vorschläge generiert wurden, finden Sie sie unter **Segmente** > **Vorschläge (Vorschau)** in dem Bereich **Aktivitätsbasierte Vorschläge**.</span><span class="sxs-lookup"><span data-stu-id="50ce3-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Erweiterter Seitenbereich mit detaillierten Daten eines vorgeschlagenen Segments.":::

<span data-ttu-id="50ce3-145">Wählen Sie **Siehe Vorschlag** auf einem vorgeschlagenen Segment, um die Details dieses Segments anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="50ce3-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="50ce3-146">Der Seitenbereich enthält Details wie die Ausdehnung jeder Dimension im Vergleich zur Zielgruppe.</span><span class="sxs-lookup"><span data-stu-id="50ce3-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="50ce3-147">Außerdem werden die Anzahl der potenziellen Mitglieder im Segment und der entsprechende Prozentsatz der Gesamtkunden hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="50ce3-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="50ce3-148">Wenn Sie den Vorschlag als Segment behalten möchten, wählen Sie **Segment erstellen**.</span><span class="sxs-lookup"><span data-stu-id="50ce3-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="50ce3-149">Speichern Sie einen Vorschlag als Segment</span><span class="sxs-lookup"><span data-stu-id="50ce3-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="50ce3-150">Gehe Sie zu **Segmente** > **Vorschläge (Vorschau)**.</span><span class="sxs-lookup"><span data-stu-id="50ce3-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="50ce3-151">Wählen Sie das Segment aus, das Sie speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="50ce3-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="50ce3-152">Wählen Sie im Seitenbereich **Segment erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="50ce3-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="50ce3-153">Nach dem Speichern des Segments wird es in der Liste der Segmente auf der Registerkarte **Alle Segmente** angezeigt. Es kann jetzt [wie jedes andere Segment aktualisiert oder gelöscht werden](segments.md).</span><span class="sxs-lookup"><span data-stu-id="50ce3-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="50ce3-154">Sie können die Segmentdetails nicht bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="50ce3-154">You can't edit the segment details.</span></span> <span data-ttu-id="50ce3-155">Sie können jedoch die Eingabekriterien für die Vorschläge ändern und verschiedene Vorschläge generieren.</span><span class="sxs-lookup"><span data-stu-id="50ce3-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="50ce3-156">Aktualisieren oder bearbeiten Sie eine Reihe von Vorschlägen</span><span class="sxs-lookup"><span data-stu-id="50ce3-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="50ce3-157">Gehen Sie zu **Segmente** > **Vorschläge (Vorschau)** und suchen Sie nach dem Segment in dem Bereich **Aktivitätsbasierte Vorschläge**.</span><span class="sxs-lookup"><span data-stu-id="50ce3-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="50ce3-158">Wählen Sie **Vorschläge aktualisieren**, um die Vorschläge zu aktualisieren und gleichzeitig die konfigurierten Attribute beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="50ce3-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="50ce3-159">Oder wählen Sie **Vorschläge bearbeiten**, um die konfigurierten Attribute zu ändern.</span><span class="sxs-lookup"><span data-stu-id="50ce3-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="50ce3-160">Das System führt den Prozess erneut aus, generiert Segmentvorschläge basierend auf den neuesten Daten und ersetzt die aktuellen Vorschläge.</span><span class="sxs-lookup"><span data-stu-id="50ce3-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
