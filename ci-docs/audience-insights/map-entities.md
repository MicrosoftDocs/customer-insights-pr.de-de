---
title: Zuordnen von Entitäten zur Datenvereinheitlichung
description: Ordnen Sie Daten zu, um einheitliche Kundenprofile zu erstellen.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 0088daae0be0cb3e71f87387648430d2353081c9
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267034"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="50427-103">Entitäten und Attribute zuordnen</span><span class="sxs-lookup"><span data-stu-id="50427-103">Map entities and attributes</span></span>

<span data-ttu-id="50427-104">**Zuordnen** ist die erste Stufe im Datenvereinheitlichungsprozess von Zielgruppen-Insights.</span><span class="sxs-lookup"><span data-stu-id="50427-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="50427-105">Das Mapping besteht aus drei Phasen:</span><span class="sxs-lookup"><span data-stu-id="50427-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="50427-106">*Entitätsauswahl*: Identifizieren Sie die kombinierbaren Entitäten, die zu einem Datensatz mit vollständigeren Informationen über Ihre Kunden führen.</span><span class="sxs-lookup"><span data-stu-id="50427-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="50427-107">*Attributauswahl*: Identifizieren Sie für jede Entität die Spalten, die Sie in den Phasen *Abgleich* und *Zusammenführung* kombinieren und abstimmen möchten.</span><span class="sxs-lookup"><span data-stu-id="50427-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="50427-108">Diese Spalten werden *Attribute* genannt.</span><span class="sxs-lookup"><span data-stu-id="50427-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="50427-109">*Auswahl des Primärschlüssels und des semantischen Typs*: Identifizieren Sie für jede Entität ein Attribut, das Sie als Primärschlüssel für diese Entität definieren möchten, und identifizieren Sie für jedes Attribut einen semantischen Typ, der dieses Attribut am besten beschreibt.</span><span class="sxs-lookup"><span data-stu-id="50427-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="50427-110">Weitere Informationen über den allgemeinen Flow der Datenvereinheitlichung finden Sie unter [Vereinheitlichung](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="50427-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="50427-111">Wählen Sie die ersten Entitäten</span><span class="sxs-lookup"><span data-stu-id="50427-111">Select the first entities</span></span>

1. <span data-ttu-id="50427-112">Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Vereinheitlichen** > **Karte**.</span><span class="sxs-lookup"><span data-stu-id="50427-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="50427-113">Beginnen Sie die Mappingphase, indem Sie **Entitäten auswählen** wählen.</span><span class="sxs-lookup"><span data-stu-id="50427-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="50427-114">Wählen Sie die Entitäten und Attribute aus, die Sie in den Phasen *Abgleichen* und *Zusammenführen* verwenden wollen.</span><span class="sxs-lookup"><span data-stu-id="50427-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="50427-115">Sie können die erforderlichen Attribute einzeln aus einer Entität auswählen oder alle Attribute aus einer Entität einschließen, indem Sie das Kontrollkästchen **Alle Felder einschließen** auf Entitätsebene auswählen.</span><span class="sxs-lookup"><span data-stu-id="50427-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="50427-116">Wir empfehlen die Auswahl von mindestens zwei Entitäten, die von dem Datenvereinheitlichungsprozess profitieren.</span><span class="sxs-lookup"><span data-stu-id="50427-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="50427-117">![Beispiel für das Hinzufügen von Entitäten](media/data-manager-configure-map-add-entities-example.png "Beispiel für das Hinzufügen von Entitäten")</span><span class="sxs-lookup"><span data-stu-id="50427-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="50427-118">In diesem Beispiel fügen wir die Entitäten **eCommerceContacts** und **loyCustomers** hinzu.</span><span class="sxs-lookup"><span data-stu-id="50427-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="50427-119">Durch Auswahl dieser Entitäten können Sie Erkenntnisse darüber gewinnen, welche der Online-Geschäftskunden Mitglieder des Treueprogramms sind.</span><span class="sxs-lookup"><span data-stu-id="50427-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="50427-120">Sie können nach Schlüsselwörtern in allen Attributen und Entitäten suchen, um die erforderlichen Attribute auszuwählen, die Sie zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="50427-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="50427-121">![Beispiel für Suchfelder](media/data-manager-configure-map-search-fields-example.png "Beispiel für Suchfelder")</span><span class="sxs-lookup"><span data-stu-id="50427-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="50427-122">Wählen Sie **Anwenden**, um Ihre Auswahl zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="50427-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="50427-123">Wählen Sie den Primärschlüssel und den semantischen Typ für Attribute aus</span><span class="sxs-lookup"><span data-stu-id="50427-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="50427-124">Nach Auswahl Ihrer Entitäten wird die Seite **Karte** die ausgewählten Entitäten zu Ihrer Überprüfung auflisten.</span><span class="sxs-lookup"><span data-stu-id="50427-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="50427-125">Definieren Sie den Primärschlüssel für eine Entität und identifizieren Sie den semantischen Typ für ein Attribut in der Entität.</span><span class="sxs-lookup"><span data-stu-id="50427-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="50427-126">**Primärschlüssel**: Wählen Sie ein Attribut als Primärschlüssel für jede Ihrer Entitäten aus.</span><span class="sxs-lookup"><span data-stu-id="50427-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="50427-127">Damit ein Attribut ein gültiger Primärschlüssel ist, sollte es keine doppelten Werte, fehlenden Werte oder Nullwerte enthalten.</span><span class="sxs-lookup"><span data-stu-id="50427-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="50427-128">Zeichenfolgen-, Integer- und GUID-Datentypattribute werden als Primärschlüssel unterstützt und in einem Feld angezeigt, aus dem Sie auswählen können.</span><span class="sxs-lookup"><span data-stu-id="50427-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="50427-129">**Semantischer Attributtyp**: Kategorien Ihrer Attribute, wie z. B. E-Mail-Adresse oder Name.</span><span class="sxs-lookup"><span data-stu-id="50427-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="50427-130">Um KI-Modelle für intelligente Vorhersage der Semantik zu verwenden, Zeit zu sparen und die Genauigkeit zu verbessern, stellen Sie **Intelligentes Mapping** auf **AN**.</span><span class="sxs-lookup"><span data-stu-id="50427-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="50427-131">Intelligentes Mapping hebt die KI-basierte Semantikempfehlung im **Typ**-Feld hervor.</span><span class="sxs-lookup"><span data-stu-id="50427-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="50427-132">Wenn Sie es auf **AUS** stellen, sehen Sie unsere regulären Mappingempfehlungen.</span><span class="sxs-lookup"><span data-stu-id="50427-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="50427-133">Sie können einen beliebigen semantischen Typ aus der Liste verfügbarer Optionen auswählen und die vorgeschlagene Auswahl außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="50427-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="50427-134">![Attributtyp und Semantikvorhersage](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attributtyp und Semantikvorhersage")</span><span class="sxs-lookup"><span data-stu-id="50427-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="50427-135">Das Hinzufügen eines benutzerdefinierten semantischen Typs ist ebenfalls möglich.</span><span class="sxs-lookup"><span data-stu-id="50427-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="50427-136">Wählen Sie das Typ-Feld für dieses Attribut und geben Sie Ihren benutzerdefinierten Namen des semantischen Typs ein.</span><span class="sxs-lookup"><span data-stu-id="50427-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="50427-137">Auf diese Weise können Sie auch die Attributtypen ändern, die vom System identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="50427-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="50427-138">Alle Attribute, für die ein semantischer Typ automatisch identifiziert wird, sind im Abschnitt **Überprüfen zugeordneter Felder** zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="50427-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="50427-139">Überprüfen Sie diese Attribute und ihre semantischen Typen, da sie verwendet werden, um Ihre Entitäten im Zusammenführungsschritt der Datenvereinigung zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="50427-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="50427-140">Attribute, die nicht automatisch einem semantischen Typ zugeordnet werden, werden im Abschnitt **Definieren der Daten in den nicht zugeordneten Feldern** zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="50427-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="50427-141">Wählen Sie das Feld für den semantischen Typ für die nicht zugeordneten Attribute aus, oder geben Sie Ihren benutzerdefinierten Attributtypnamen ein.</span><span class="sxs-lookup"><span data-stu-id="50427-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="50427-142">![Primärschlüssel und Attributtyp](media/data-manager-configure-map-add-attributes.png "Primärschlüssel und Attributtyp")</span><span class="sxs-lookup"><span data-stu-id="50427-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="50427-143">Ein Feld sollte dem semantischen Typ Person.FullName zugeordnet sein, um den Kundennamen auf der Kundenkarte auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="50427-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="50427-144">Andernfalls erscheinen die Kundenkarten namenlos.</span><span class="sxs-lookup"><span data-stu-id="50427-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="50427-145">Hinzufügen und Entfernen von Attributen und Entitäten</span><span class="sxs-lookup"><span data-stu-id="50427-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="50427-146">Wählen -Sie auf **Vereinheitlichen** > **Karte** **Felder bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="50427-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="50427-147">In dem Bereich **Felder bearbeiten** fügen Sie Attribute oder Entitäten hinzu oder entfernen sie diese.</span><span class="sxs-lookup"><span data-stu-id="50427-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="50427-148">Verwenden Sie die Suche oder den Bildlauf, um Ihre Attribute und Objekte von Interesse zu finden und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="50427-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="50427-149">Sie können ein Attribut oder eine Entität nicht entfernen, wenn sie bereits übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="50427-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="50427-150">![Attribute hinzufügen oder entfernen](media/configure-data-map-edit.png "Attribute hinzufügen oder entfernen")</span><span class="sxs-lookup"><span data-stu-id="50427-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="50427-151">Wählen Sie **Übernehmen** aus.</span><span class="sxs-lookup"><span data-stu-id="50427-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="50427-152">Hinzufügen von Bildern zu Profilen</span><span class="sxs-lookup"><span data-stu-id="50427-152">Add images to profiles</span></span>

<span data-ttu-id="50427-153">Wenn eine Entität URLs zu öffentlich verfügbaren Profilbildern oder Logos enthält, können Sie diese dem einheitlichen Kundenprofil hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="50427-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="50427-154">Wählen Sie die Entität aus und suchen Sie das Feld, das die URL zum Profilbild enthält.</span><span class="sxs-lookup"><span data-stu-id="50427-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="50427-155">Geben Sie im Eingabefeld **Typ** manuell den folgenden Wert ein:</span><span class="sxs-lookup"><span data-stu-id="50427-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="50427-156">Für eine Person: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="50427-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="50427-157">Für eine Organisation: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="50427-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="50427-158">Fahren Sie mit den Vereinigungsschritten fort und stellen Sie sicher, dass das Attribut, das die Bild-URL enthält, auch im Schritt [Zusammenführen](merge-entities.md) zusammengeführt wird.</span><span class="sxs-lookup"><span data-stu-id="50427-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="50427-159">Setzen Sie Attribute für Organisationen</span><span class="sxs-lookup"><span data-stu-id="50427-159">Set attributes for organizations</span></span>

<span data-ttu-id="50427-160">Bei Organisationen (Vorschau) sollte der Attributtyp auf „Organization.Name“ abgebildet werden</span><span class="sxs-lookup"><span data-stu-id="50427-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="50427-161">![Primärschlüssel und Attributtyp B2B](media/configure-data-map-edit-b2b.png "Primärschlüssel und Attributtyp B2B")</span><span class="sxs-lookup"><span data-stu-id="50427-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="50427-162">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="50427-162">Next step</span></span>

<span data-ttu-id="50427-163">Als Teil des Datenvereinheitlichungsprozesses gehen Sie auf die Seite **Abgleich**.</span><span class="sxs-lookup"><span data-stu-id="50427-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="50427-164">Besuchen Sie [**Abgleichen**](match-entities.md) um mehr über diese Phase zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="50427-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="50427-165">Sehen Sie sich das folgende Video an: [Einstieg: Erstellen eines einheitlichen Kundenprofils](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="50427-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]