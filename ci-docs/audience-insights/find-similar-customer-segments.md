---
title: Ähnliche Kunden mit KI finden
description: Finden Sie ähnliche Kundensegmente mit künstlicher Intelligenz.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 8cdec4edd599b0249fcf144b5e5c0124504e1e14
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405782"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="43edd-103">Ähnliche Kunden (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="43edd-103">Similar Customers (preview)</span></span>

<span data-ttu-id="43edd-104">Mit dieser Funktion können Sie mithilfe künstlicher Intelligenz ähnliche Kunden in Ihrem Kundenstamm finden.</span><span class="sxs-lookup"><span data-stu-id="43edd-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="43edd-105">Sie müssen mindestens ein Segment erstellt haben, um diese Funktion nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="43edd-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="43edd-106">Durch Erweitern der Kriterien eines vorhandenen Segments können Sie Kunden finden, die diesem Segment ähnlich sind.</span><span class="sxs-lookup"><span data-stu-id="43edd-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="43edd-107">*Finden Sie ähnliche Kunden* verwendet automatisierte Mittel, um Daten auszuwerten und Vorhersagen auf der Grundlage dieser Daten zu treffen, und kann daher als Methode zur Profilerstellung verwendet werden, wie dieser Begriff in der allgemeinen Datenschutzverordnung (DSGVO) definiert ist.</span><span class="sxs-lookup"><span data-stu-id="43edd-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="43edd-108">Die Nutzung dieser Funktion durch den Kunden zur Datenverarbeitung kann der DSGVO oder anderen Gesetzen oder Vorschriften unterliegen.</span><span class="sxs-lookup"><span data-stu-id="43edd-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="43edd-109">Sie sind dafür verantwortlich, dass Ihre Dynamics 365 Customer Insights-Nutzung, einschließlich der Vorhersagen, allen geltenden Gesetzen und Vorschriften entspricht, einschließlich Gesetzen in Bezug auf Privatsphäre, personenbezogene Daten, biometrische Daten, Datenschutz und Vertraulichkeit der Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="43edd-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="43edd-110">Ähnliche Kunden finden</span><span class="sxs-lookup"><span data-stu-id="43edd-110">Finding similar customers</span></span>

1. <span data-ttu-id="43edd-111">Gehen Sie in Zielgruppen-Insights zu **Segmente** und wählen Sie das Segment, auf dem Ihr neues Segment basieren soll.</span><span class="sxs-lookup"><span data-stu-id="43edd-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="43edd-112">Das ist Ihr *Quellensegment*.</span><span class="sxs-lookup"><span data-stu-id="43edd-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="43edd-113">Wählen Sie in der Aktionsleiste aus **Finden Sie ähnliche Kunden**.</span><span class="sxs-lookup"><span data-stu-id="43edd-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="43edd-114">Überprüfen Sie den vorgeschlagenen Namen für Ihr neues Segment und ändern Sie ihn gegebenenfalls.</span><span class="sxs-lookup"><span data-stu-id="43edd-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="43edd-115">Überprüfen Sie die Felder, die Ihr neues Segment definieren.</span><span class="sxs-lookup"><span data-stu-id="43edd-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="43edd-116">Diese Felder definieren die Basis, auf der das System versucht, ähnliche Kunden wie Ihr Quellsegment zu finden.</span><span class="sxs-lookup"><span data-stu-id="43edd-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="43edd-117">Das System wählt standardmäßig empfohlene Felder aus.</span><span class="sxs-lookup"><span data-stu-id="43edd-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="43edd-118">Felder, die die Modellleistung erheblich reduzieren können, werden automatisch ausgeschlossen:</span><span class="sxs-lookup"><span data-stu-id="43edd-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="43edd-119">Felder mit den folgenden Datentypen: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="43edd-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="43edd-120">Felder mit einer Kardinalität (Anzahl der Elemente in einem Feld) von weniger als 2 oder mehr als 30</span><span class="sxs-lookup"><span data-stu-id="43edd-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="43edd-121">Wählen Sie aus, ob Sie **Alle Kunden** einschließen möchten oder nur Kunden in einem **Spezifisch vorhandenen Segment** in Ihrem neuen Segment.</span><span class="sxs-lookup"><span data-stu-id="43edd-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="43edd-122">Schließen Sie Kunden in Ihrem Quellensegment aus, indem Sie das Kontrollkästchen auswählen **Alle im Quellensegment ausschließen**.</span><span class="sxs-lookup"><span data-stu-id="43edd-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="43edd-123">Standardmäßig schlägt das System vor, nur 20 % der Zielgruppe in Ihre Ausgabe aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="43edd-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="43edd-124">Bearbeiten Sie diesen Schwellenwert nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="43edd-124">Edit this threshold as needed.</span></span> <span data-ttu-id="43edd-125">Durch Erhöhen des Schwellenwerts wird die Genauigkeit verringert.</span><span class="sxs-lookup"><span data-stu-id="43edd-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="43edd-126">Wählen Sie **Ausführen** am Ende der Seite, um eine binäre Klassifizierungsaufgabe (eine Methode von Maschinellem Lernen) zu starten, die das DataSet analysiert.</span><span class="sxs-lookup"><span data-stu-id="43edd-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="43edd-127">Sehen Sie sich das ähnliche Segment an</span><span class="sxs-lookup"><span data-stu-id="43edd-127">View the similar segment</span></span>

<span data-ttu-id="43edd-128">Nach der Verarbeitung des ähnlichen Segments finden Sie das neue Segment auf der Seite **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="43edd-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43edd-129">![Ähnliche Kundensegmente](media/expanded-segment.png "Ähnliche Kundensegmente")</span><span class="sxs-lookup"><span data-stu-id="43edd-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="43edd-130">Wählen Sie **Ansicht** in der Aktionsleiste, um das Segmentdetail zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="43edd-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="43edd-131">Diese Ansicht enthält Informationen zur Ergebnisverteilung über [Ähnlichkeitswerte](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="43edd-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="43edd-132">Die Ähnlichkeitswerte finden Sie auch in der **Vorschau der Segmentmitglieder**.</span><span class="sxs-lookup"><span data-stu-id="43edd-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="43edd-133">Verwenden Sie die Ausgabe eines ähnlichen Segments</span><span class="sxs-lookup"><span data-stu-id="43edd-133">Use the output of a similar segment</span></span>

<span data-ttu-id="43edd-134">Sie können [mit der Ausgabe eines ähnlichen Segments arbeiten](segments.md), wie Sie es mit anderen Segmenten tun.</span><span class="sxs-lookup"><span data-stu-id="43edd-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="43edd-135">Exportieren Sie beispielsweise das Segment oder erstellen Sie eine Kennzahl.</span><span class="sxs-lookup"><span data-stu-id="43edd-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="43edd-136">Aktualisieren und bearbeiten Sie ein ähnliches Segment</span><span class="sxs-lookup"><span data-stu-id="43edd-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="43edd-137">Um ein ähnliches Segment zu aktualisieren, wählen Sie es auf der Seite **Segmente** aus und wählen Sie **Aktualisierung** in der Aktionsleiste.</span><span class="sxs-lookup"><span data-stu-id="43edd-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="43edd-138">Durch Bearbeiten eines ähnlichen Segments werden Ihre Daten erneut verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="43edd-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="43edd-139">Das zuvor erstellte Segment wird mit aktualisierten Daten aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="43edd-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="43edd-140">Um ein ähnliches Segment zu bearbeiten, wählen Sie es auf der Seite **Segmente** aus und wählen Sie **Bearbeitung** in der Aktionsleiste.</span><span class="sxs-lookup"><span data-stu-id="43edd-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="43edd-141">Übernehmen Sie Ihre Änderungen und wählen Sie **Ausführen**, um die Verarbeitung zu starten.</span><span class="sxs-lookup"><span data-stu-id="43edd-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="43edd-142">Löschen Sie ein ähnliches Segment</span><span class="sxs-lookup"><span data-stu-id="43edd-142">Delete a similar segment</span></span>

<span data-ttu-id="43edd-143">Wählen Sie das Segment auf der Seite **Segmente** aus und wählen Sie **Löschen** in der Aktionsleiste.</span><span class="sxs-lookup"><span data-stu-id="43edd-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="43edd-144">Bestätigen Sie dann den Löschvorgang.</span><span class="sxs-lookup"><span data-stu-id="43edd-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="43edd-145">Über die Ähnlichkeitsbewertung</span><span class="sxs-lookup"><span data-stu-id="43edd-145">About similarity scores</span></span>

<span data-ttu-id="43edd-146">Das Modell der binären Klassifizierung Maschinelles Lernen weist Kunden im ähnlichen Segment eine Bewertung zu.</span><span class="sxs-lookup"><span data-stu-id="43edd-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="43edd-147">Die Bewertung basiert auf der Ähnlichkeit mit Kunden im Quellensegment.</span><span class="sxs-lookup"><span data-stu-id="43edd-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="43edd-148">Ähnlichkeitswerte unter 0,55 sind Kunden, die das System klassifiziert als *nicht ähnlich* an Kunden im Quellensegment</span><span class="sxs-lookup"><span data-stu-id="43edd-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="43edd-149">Ähnlichkeitswerte zwischen 0,55 und 0,7 werden klassifiziert als *etwas ähnlich*</span><span class="sxs-lookup"><span data-stu-id="43edd-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="43edd-150">Ähnlichkeitswerte zwischen 0,7 und 0,85 werden klassifiziert als *ähnlich*</span><span class="sxs-lookup"><span data-stu-id="43edd-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="43edd-151">Ähnlichkeitswerte zwischen 0,85 – 1 sind Kunden, die das System klassifiziert als *sehr ähnlich*</span><span class="sxs-lookup"><span data-stu-id="43edd-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="43edd-152">Kunden mit Ähnlichkeitswerten unter 0,4 werden nicht in die Modellausgabe einbezogen.</span><span class="sxs-lookup"><span data-stu-id="43edd-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="43edd-153">Das System betrachtet sie nicht als ähnlich genug für das Quellensegment.</span><span class="sxs-lookup"><span data-stu-id="43edd-153">The system doesn't consider them similar enough to the source segment.</span></span>
