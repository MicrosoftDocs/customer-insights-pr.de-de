---
title: Segment Insights für bestehende Segmente
description: Erhalten Sie Insights zu bestehenden Segmenten, um Unterschiede und Gemeinsamkeiten zu erkennen.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: d731d21462b5a31aba0653f87e299d98373bbf49
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270019"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="bd2e8-103">Segment-Insights (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="bd2e8-103">Segment insights (preview)</span></span>

<span data-ttu-id="bd2e8-104">Entdecken Sie zusätzliche Informationen und Einblicke in Ihre vorhandenen Segmente.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="bd2e8-105">Finden Sie heraus, was zwei Segmente unterscheidet oder was sie gemeinsam haben.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="bd2e8-106">Segment-Überschneidung</span><span class="sxs-lookup"><span data-stu-id="bd2e8-106">Segment overlap</span></span>

<span data-ttu-id="bd2e8-107">Die Segmentüberlappungsanalyse zeigt, wie viele und welche Kunden zwei oder mehr Segmenten gemeinsam haben.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="bd2e8-108">Zum Beispiel, wie sich ein Segment häufiger Kunden mit einem Segment überschneidet, das Kunden enthält, die mit Ihrem Service oder Produkt zufrieden sind.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="bd2e8-109">Sie können auch analysieren, wie sich die Überlappung für bestimmte Attribute ändert.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="bd2e8-110">Führen Sie eine Überlappungsanalyse durch</span><span class="sxs-lookup"><span data-stu-id="bd2e8-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="bd2e8-111">Gehen Sie zu **Segmente** und wählen Sie die Registerkarte **Einblicke (Vorschau)**.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="bd2e8-112">Wählen **Neu** und wählen Sie die Option **Überlappung** im Feld **Wählen Sie Insights-Typ**.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="bd2e8-113">Wählen Sie die gewünschten Segmente aus und wählen Sie **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="bd2e8-114">Wählen Sie optional ein oder mehrere interessierende Felder aus, um Überlappungen für jeden möglichen Feldwert zu analysieren, und wählen Sie **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="bd2e8-115">Geben Sie einen Namen für Ihre Überlappungsanalyse, ein optionales Anzeigename und eine Beschreibung an.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="bd2e8-116">Wählen Sie **Speichern**, um die Analyse zu starten.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="bd2e8-117">Die Überlappungsanalyse ist fertig, wenn sich der Status von Aktualisieren zu Erfolgreich ändert.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="bd2e8-118">Anzeigen und Optimieren einer Überlappungsanalyse</span><span class="sxs-lookup"><span data-stu-id="bd2e8-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="bd2e8-119">Nach Abschluss der Analyse finden Sie Details zu diesem Einblick unter **Segmente** > **Erkenntnisse (Vorschau)**.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Erkenntnisdetails zur Segmentüberlappung":::

<span data-ttu-id="bd2e8-121">Wählen Sie eine Erkenntnis aus, um die Analyseergebnisse anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="bd2e8-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="bd2e8-122">Die Anzahl der Mitglieder, die die für die Analyse ausgewählten Segmente überlappen.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="bd2e8-123">Die Anzahl der Mitglieder, die in einem der Segmente enthalten sind, jedoch nicht in den übrigen Segmenten.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="bd2e8-124">Wenn Sie beim Konfigurieren der Überlappungsanalyse Felder ausgewählt haben, finden Sie diese auf den entsprechenden Registerkarten.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="bd2e8-125">Sie können das Filter-Dropdown-Menü verwenden, um eine beliebige interessierende Attributebene auszuwählen. In der Tabelle unten werden die entsprechenden Daten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="bd2e8-126">Segment-Unterscheidungsmerkmale</span><span class="sxs-lookup"><span data-stu-id="bd2e8-126">Segment differentiators</span></span>

<span data-ttu-id="bd2e8-127">Mithilfe von Segmentunterscheidungsmerkmalen können Sie herausfinden, was ein Segment vom Rest Ihrer Kunden oder von einem anderen Segment unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="bd2e8-128">Sie müssen nur ein Segment auswählen, und das System identifiziert Profilattribute und Kennzahlen, die das ausgewählte Segment unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="bd2e8-129">Führen Sie eine Differenzierungsanalyse durch</span><span class="sxs-lookup"><span data-stu-id="bd2e8-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="bd2e8-130">Gehen Sie zu **Segmente** und wählen Sie die Registerkarte **Einblicke (Vorschau)**.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="bd2e8-131">Wählen **Neu** und wählen Sie die Option **Überlappung** im Feld **Wählen Sie Insights-Typ**.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="bd2e8-132">Wählen Sie das Segment aus, das Sie analysieren möchten als **Primärsegment** aus und wählen Sie **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="bd2e8-133">Wählen Sie **Alle Kunden** oder ein **Sekundärsegment**, um Ihr primäres Segment mit zu vergleichen und wählen Sie **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="bd2e8-134">Wählen Sie optional ein oder mehrere interessierende Felder aus, um die Analyse auf bestimmte Attribute zu konzentrieren, und wählen Sie **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="bd2e8-135">Geben Sie einen Namen für Ihre Überlappungsanalyse, ein optionales Anzeigename und eine Beschreibung an.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="bd2e8-136">Wählen Sie **Speichern**, um die Analyse zu starten.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="bd2e8-137">Die Überlappungsanalyse ist fertig, wenn sich der Status von Aktualisieren zu Erfolgreich ändert.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="bd2e8-138">Anzeigen und Optimieren einer Differenzierungsanalyse</span><span class="sxs-lookup"><span data-stu-id="bd2e8-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="bd2e8-139">Nach Abschluss der Analyse finden Sie Details zu diesem Einblick unter **Segmente** > **Erkenntnisse (Vorschau)**.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Segmentdifferenziator Erkenntnisdetails":::

<span data-ttu-id="bd2e8-141">Wählen Sie eine Erkenntnis aus, um die Analyseergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="bd2e8-142">Eine Differenzierungsanalyse umfasst zwei Registerkarten.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="bd2e8-143">Die Registerkarte **Attribute** listet Profilattribute auf, die als Unterscheidungsmerkmale betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="bd2e8-144">Die Registerkarte **Maßnahmen** listet Unterscheidungsmerkmale auf.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="bd2e8-145">Jede Registerkarte enthält die folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="bd2e8-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="bd2e8-146">Rangliste der Unterscheidungsmerkmale, sortiert nach Differenzwerten.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="bd2e8-147">Das **Differenzwert** für jedes Unterscheidungsmerkmal.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="bd2e8-148">Die Differenzbewertung gibt den Differenzgrad eines Attributs zwischen zwei Segmenten an.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="bd2e8-149">Je höher die Differenzbewertung ist, desto stärker unterscheiden sich die Attribute zwischen den beiden Segmenten.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="bd2e8-150">Wählen Sie einen Wert aus, um den Bereich **Differenzwert** mit den Werteverteilungen für dieses Attribut zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bd2e8-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="bd2e8-151">Segmenterkenntnisse verwalten</span><span class="sxs-lookup"><span data-stu-id="bd2e8-151">Manage segment insights</span></span>

<span data-ttu-id="bd2e8-152">In der Befehlsleiste können Sie die folgenden Optionen für Ihre Erkenntnisse verwenden:</span><span class="sxs-lookup"><span data-stu-id="bd2e8-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="bd2e8-153">**Zurück**, um die Liste der Erkenntnisse zurückzugeben</span><span class="sxs-lookup"><span data-stu-id="bd2e8-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="bd2e8-154">**Aktualisierung**, um die Analyse erneut auszuführen</span><span class="sxs-lookup"><span data-stu-id="bd2e8-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="bd2e8-155">**Löschen**, um diese Erkenntnisse zu entfernen</span><span class="sxs-lookup"><span data-stu-id="bd2e8-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]