---
title: Anreicherung der Adressverbesserung
description: Bereichern und normalisieren Sie Adressinformationen von Kundenprofilen mit Microsoft-Modellen.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305431"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="ec1dd-103">Anreicherung von Kundenprofilen mit erweiterten Adressen</span><span class="sxs-lookup"><span data-stu-id="ec1dd-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="ec1dd-104">Adressen in Ihren Daten können unstrukturiert, unvollständig oder falsch sein.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="ec1dd-105">Verwenden Sie die Modelle von Microsoft, um Ihre Adressen im [Common Data Model-Format](/common-data-model/schema/core/applicationcommon/address) für bessere Genauigkeit und Einsichten zu normalisieren und anzureichern.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="ec1dd-106">Wie wir Adressen verbessern</span><span class="sxs-lookup"><span data-stu-id="ec1dd-106">How we enhance addresses</span></span>

<span data-ttu-id="ec1dd-107">Unser Modell durchläuft einen zweistufigen Prozess, um eine Adresse zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="ec1dd-108">Zunächst wird die Adresse analysiert, um die Komponenten zu identifizieren und in ein strukturiertes Format gebracht.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="ec1dd-109">Dann verwenden wir KI, um die Werte in der Adresse zu korrigieren, zu vervollständigen und zu standardisieren.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-109">Then, we use AI to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="ec1dd-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec1dd-110">Example</span></span>

<span data-ttu-id="ec1dd-111">Adressinformationen können in einem nicht standardmäßigen Format vorliegen und Rechtschreibfehler enthalten.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-111">Address information might be in a nonstandard format and contain spelling errors.</span></span> <span data-ttu-id="ec1dd-112">Das Modell kann diese Probleme beheben und konsistente Adressen in einheitlichen Kundenprofilen erstellen.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="ec1dd-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="ec1dd-113">Limitations</span></span>

<span data-ttu-id="ec1dd-114">Erweiterte Adressen funktionieren nur mit den Werten, die bereits in Ihren aufgenommenen Adressdaten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="ec1dd-115">Das Modell wird nicht:</span><span class="sxs-lookup"><span data-stu-id="ec1dd-115">The model doesn't:</span></span> 

1. <span data-ttu-id="ec1dd-116">Überprüfen, ob die Adresse eine gültige Adresse ist.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="ec1dd-117">Überprüfen, ob einer der Werte wie Postleitzahlen oder Straßennamen gültig ist.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="ec1dd-118">Werte ändern, die nicht erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="ec1dd-119">Das Modell verwendet auf maschinellem Lernen basierende Techniken, um Adressen zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="ec1dd-120">Wir wenden zwar einen hohen Konfidenzschwellenwert an, wenn das Modell einen Eingabewert ändert, wie bei jedem auf maschinellem Lernen basierenden Modell, aber eine 100-prozentige Genauigkeit kann nicht garantiert werden.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-120">While we apply a high confidence threshold for when the model changes an input value, as with any machine learning-based model, 100 percent accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="ec1dd-121">Unterstützte Länder oder Regionen</span><span class="sxs-lookup"><span data-stu-id="ec1dd-121">Supported countries or regions</span></span>

<span data-ttu-id="ec1dd-122">Wir unterstützen derzeit bereichernde Adressen in diesen Ländern oder Regionen:</span><span class="sxs-lookup"><span data-stu-id="ec1dd-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="ec1dd-123">Australien</span><span class="sxs-lookup"><span data-stu-id="ec1dd-123">Australia</span></span>
- <span data-ttu-id="ec1dd-124">Kanada</span><span class="sxs-lookup"><span data-stu-id="ec1dd-124">Canada</span></span>
- <span data-ttu-id="ec1dd-125">Großbritannien</span><span class="sxs-lookup"><span data-stu-id="ec1dd-125">United Kingdom</span></span>
- <span data-ttu-id="ec1dd-126">Vereinigte Staaten</span><span class="sxs-lookup"><span data-stu-id="ec1dd-126">United States</span></span>

<span data-ttu-id="ec1dd-127">Adressen müssen einen Länder-/Regionswert enthalten.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="ec1dd-128">Wir verarbeiten keine Adressen für Länder oder Regionen, die nicht unterstützt werden, und Adressen, für die kein Land oder keine Region angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="ec1dd-129">Anreicherungskonfiguration</span><span class="sxs-lookup"><span data-stu-id="ec1dd-129">Configure the enrichment</span></span>

1. <span data-ttu-id="ec1dd-130">Gehen Sie zu **Daten** > **Anreicherung**.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="ec1dd-131">Wählen Sie **Meine Daten anreichern** auf der Kachel **Erweiterte Adressen** aus.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Screenshot der Kachel Erweiterte Adressen.":::

1. <span data-ttu-id="ec1dd-133">Wählen Sie **Kunden-Dataset** und wählen Sie die Entität mit den Adressen aus, die Sie anreichern möchten.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="ec1dd-134">Sie können die Entität *Kunde* auswählen, um Adressen in all Ihren Kundenprofilen anzureichern, oder wählen Sie eine Segmententität aus, um Adressen nur in Kundenprofilen anzureichern, die in diesem Segment enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="ec1dd-135">Wählen Sie aus, wie Adressen in Ihrem Datenset formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="ec1dd-136">Wählen Sie **Einzelattributadresse** aus, wenn Adressen in Ihren Daten ein einzelnes Feld verwenden.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="ec1dd-137">Wählen Sie **Mehrattributadresse** aus, wenn Adressen in Ihren Daten mehr als ein einzelnes Feld verwenden.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ec1dd-138">Land/Region ist sowohl in Einzelattribut- als auch in Mehrfachattributadressen obligatorisch.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-138">Country/Region is mandatory in both single-attribute and multiple-attribute addresses.</span></span> <span data-ttu-id="ec1dd-139">Adressen, die keine gültigen oder unterstützten Länder-/Regionswerte enthalten, werden nicht angereichert.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-139">Addresses that don't contain valid or supported country/region values won't be enriched.</span></span>

1.  <span data-ttu-id="ec1dd-140">Ordnen Sie die Adressfelder Ihrer einheitlichen Kundenentität zu.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Erweiterte Adressfeld-Zuordnungsseite.":::

1. <span data-ttu-id="ec1dd-142">Wählen Sie **Weiter** aus, um die Feldzuordnung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="ec1dd-143">Geben Sie einen Namen für die Anreicherung und einen Namen für die Ausgabeentität an.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="ec1dd-144">Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="ec1dd-145">Anreicherungsergebnisse</span><span class="sxs-lookup"><span data-stu-id="ec1dd-145">Enrichment results</span></span>

<span data-ttu-id="ec1dd-146">Wählen Sie **Ausführen** aus der Befehlsleiste aus, um den Anreicherungsprozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="ec1dd-147">Sie können das System die Anreicherung auch automatisch als Teil von einer [geplante Aktualisierung](system.md#schedule-tab) ausführen lassen.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ec1dd-148">Die Bearbeitungszeit hängt von der Größe Ihrer Kundendaten ab.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="ec1dd-149">Nach Abschluss des Anreicherungsprozesses können Sie die neu angereicherten Kundenprofildaten unter **Meine Anreicherungen** überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="ec1dd-150">Außerdem finden Sie den Zeitpunkt des letzten Updates und die Anzahl der angereicherten Profile.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="ec1dd-151">Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ec1dd-152">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ec1dd-152">Next steps</span></span>

<span data-ttu-id="ec1dd-153">Bauen Sie auf Ihren angereicherten Kundendaten auf.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="ec1dd-154">Erstellen von [Segmenten](segments.md) und [Maßnahmen](measures.md), und [Exportieren Sie die Daten](export-destinations.md),  um Ihren Kunden personalisierte Erlebnisse zu bieten.</span><span class="sxs-lookup"><span data-stu-id="ec1dd-154">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
