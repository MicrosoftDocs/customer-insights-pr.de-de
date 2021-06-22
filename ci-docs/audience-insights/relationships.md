---
title: Beziehungen zwischen Entitäten und Entitätspfaden
description: Erstellen und verwalten Sie Beziehungen zwischen Entitäten aus mehreren Datenquellen.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171163"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="d4cd9-103">Beziehungen zwischen Entitäten</span><span class="sxs-lookup"><span data-stu-id="d4cd9-103">Relationships between entities</span></span>

<span data-ttu-id="d4cd9-104">Beziehungen verbinden Entitäten und definieren einen Graphen Ihrer Daten, wenn Entitäten einen gemeinsamen Bezeichner, einen Fremdschlüssel, teilen.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="d4cd9-105">Dieser Fremdschlüssel kann von einer Entität zu einer anderen referenziert werden.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="d4cd9-106">Verbundene Entitäten ermöglichen die Definition von Segmenten und Kennzahlen auf der Grundlage mehrerer Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="d4cd9-107">Es gibt drei Arten von Beziehungen:</span><span class="sxs-lookup"><span data-stu-id="d4cd9-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="d4cd9-108">Nicht bearbeitbare Systembeziehungen, die vom System im Rahmen der Datenvereinheitlichung erstellt werden</span><span class="sxs-lookup"><span data-stu-id="d4cd9-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="d4cd9-109">Nicht bearbeitbare, geerbte Beziehungen, die automatisch aus der Erfassung von Datenquellen erstellt werden</span><span class="sxs-lookup"><span data-stu-id="d4cd9-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="d4cd9-110">Bearbeitbare benutzerdefinierte Beziehungen, die von Benutzern erstellt und konfiguriert werden</span><span class="sxs-lookup"><span data-stu-id="d4cd9-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="d4cd9-111">Nicht bearbeitbare Systembeziehungen</span><span class="sxs-lookup"><span data-stu-id="d4cd9-111">Non-editable system relationships</span></span>

<span data-ttu-id="d4cd9-112">Während der Datenvereinheitlichung werden basierend auf intelligenten Abgleichen automatisch Systembeziehungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="d4cd9-113">Diese Beziehungen helfen dabei, die Datensätze zum Kundenprofil mit entsprechenden Datensätzen in Beziehung zu setzen.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="d4cd9-114">Das folgende Diagramm veranschaulicht die Erstellung von drei systembasierten Beziehungen.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="d4cd9-115">Die Kundenentität wird mit anderen Entitäten abgeglichen, um die vereinheitlichte Entität *Kunde* zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagramm mit Beziehungspfaden für die Kundenentität mit drei 1-n-Beziehungen.":::

- <span data-ttu-id="d4cd9-117">Die \***CustomerToContact\*-Beziehung** wurde zwischen der Entität *Kunde* und der Entität *Kontakt* erstellt.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="d4cd9-118">Die Entität *Kunde* erhält das Schlüsselfeld **Contact_contactID**, das sich auf das Schlüsselfeld **contactID** der Entität *Contact* bezieht.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="d4cd9-119">Die \***CustomerToAccount\*-Beziehung** wurde zwischen der Entität *Kunde* und der Entität *Konto* erstellt.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="d4cd9-120">Die Entität *Kunde* erhält das Schlüsselfeld **Account_accountID**, das sich auf das Schlüsselfeld **accountID** der Entität *Konto* bezieht.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="d4cd9-121">Die \***CustomerToWebAccount\*-Beziehung** wurde zwischen der Entität *Kunde* und der Entität *WebAccount* erstellt.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="d4cd9-122">Die Entität *Kunde* erhält das Schlüsselfeld **WebAccount_webaccountID**, das sich auf das Schlüsselfeld **webaccountID** der Entität *WebAccount* bezieht.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="d4cd9-123">Nicht bearbeitbare, geerbte Beziehungen</span><span class="sxs-lookup"><span data-stu-id="d4cd9-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="d4cd9-124">Während der Datenerfassung überprüft das System Datenquellen auf vorhandene Beziehungen.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="d4cd9-125">Wenn keine Beziehung besteht, legt sie das System automatisch an.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="d4cd9-126">Diese Beziehungen werden auch in nachgeschalteten Prozessen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="d4cd9-127">Erstellen einer benutzerdefinierten Beziehung</span><span class="sxs-lookup"><span data-stu-id="d4cd9-127">Create a custom relationship</span></span>

<span data-ttu-id="d4cd9-128">Die Beziehung besteht aus einer *Quellentität* mit dem Fremdschlüssel und einer *Zielentität*, auf die der Fremdschlüssel der Quellentität verweist.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="d4cd9-129">Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Beziehungen**.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="d4cd9-130">Wählen Sie **Neue Beziehung**.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="d4cd9-131">Im Bereich **Neue Beziehung** geben Sie die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="d4cd9-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Seitenbereich der neuen Beziehung mit leeren Eingabefeldern.":::

   - <span data-ttu-id="d4cd9-133">**Beziehungsname**: Der Name, der den Zweck der Beziehung widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="d4cd9-134">Beispiel: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="d4cd9-135">**Beschreibung:**: Beschreibung der Beziehung.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="d4cd9-136">**Quellentität**: Die Entität, die in der Beziehung als Quelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="d4cd9-137">Beispiel: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="d4cd9-138">**Zielentität**: Die Entität, die in der Beziehung als Ziel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="d4cd9-139">Beispiel: Customer.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-139">Example: Customer.</span></span>
   - <span data-ttu-id="d4cd9-140">**Quellkardinalität**: Geben Sie die Kardinalität der Quellentität an.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="d4cd9-141">Die Kardinalität beschreibt die Anzahl der möglichen Elemente in einer Menge.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="d4cd9-142">Sie bezieht sich immer auf die Zielkardinalität.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="d4cd9-143">Sie können zwischen **Einer** und **Viele** wählen.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="d4cd9-144">Es werden nur Viele-zu-Eins und Eins-zu-Eins-Beziehungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="d4cd9-145">n:1: Mehrere Quelldatensätze können sich auf einen Zieldatensatz beziehen.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="d4cd9-146">Beispiel: Mehrere Supportfälle eines einzigen Kunden.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="d4cd9-147">1:1: Ein einzelner Quelldatensatz bezieht sich auf einen einzelnen Zieldatensatz.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="d4cd9-148">Beispiel: Eine Treue-ID für einen einzelnen Kunden.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="d4cd9-149">m:n-Beziehungen können erstellt werden, indem Sie zwei n:1-Beziehungen verwenden und dann eine verknüpfende Entität erstellen, die die Quellentität und die Zielentität verbindet.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="d4cd9-150">**Zielkardinalität**: Wählen Sie die Kardinalität der Zielentitätsdatensätze aus.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="d4cd9-151">**Quellschlüsselfeld**: Das Fremdschlüsselfeld in der Quellentität.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="d4cd9-152">Beispiel: SupportCase könnte CaseID als Fremdschlüsselfeld verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="d4cd9-153">**Zielschlüsselfeld**: Das Schlüsselfeld der Zielentität.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="d4cd9-154">Beispiel: Customer könnte das Schlüsselfeld **CustomerID** verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="d4cd9-155">Wählen Sie **Speichern** aus, um die benutzerdefinierte Beziehung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="d4cd9-156">Anzeigen von Beziehungen</span><span class="sxs-lookup"><span data-stu-id="d4cd9-156">View relationships</span></span>

<span data-ttu-id="d4cd9-157">Die Seite „Beziehungen“ listet alle erstellten Beziehungen auf.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="d4cd9-158">Jede Zeile steht für eine Beziehung, die auch Details zur Quellentität, Zielentität und Kardinalität enthält.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Liste von Beziehungen und Optionen in der Aktionsleiste der Seite „Beziehungen“.":::

<span data-ttu-id="d4cd9-160">Diese Seite bietet eine Reihe von Optionen für bestehende und neue Beziehungen:</span><span class="sxs-lookup"><span data-stu-id="d4cd9-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="d4cd9-161">**Neue Beziehung**: [Erstellen Sie eine neue Beziehung](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="d4cd9-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="d4cd9-162">**Visualisierer**: [Entdecken Sie den Beziehungsvisualisierer](#explore-the-relationship-visualizer), um ein Netzwerkdiagramm der bestehenden Beziehungen und ihrer Kardinalität anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="d4cd9-163">**Filtern nach**: Wählen Sie den Typ von Beziehungen aus, der in der Liste angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="d4cd9-164">**Beziehungen durchsuchen**: Verwenden Sie eine textbasierte Suche nach Eigenschaften von Beziehungen.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="d4cd9-165">Der Beziehungsvisualisierer</span><span class="sxs-lookup"><span data-stu-id="d4cd9-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="d4cd9-166">Der Beziehungsvisualisierer zeigt ein Netzwerkdiagramm der bestehenden Beziehungen zwischen verbundenen Entitäten und ihrer Kardinalität an.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="d4cd9-167">Um die Ansicht anzupassen, können Sie die Position der Felder ändern, indem Sie sie auf das Canvas ziehen.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Screenshot des Netzwerkdiagramms des Beziehungsvisualisierers mit Verbindungen zwischen verwandten Entitäten.":::

<span data-ttu-id="d4cd9-169">Verfügbare Optionen:</span><span class="sxs-lookup"><span data-stu-id="d4cd9-169">Available options:</span></span> 
- <span data-ttu-id="d4cd9-170">**Als Bild exportieren**: Speichern Sie die aktuelle Ansicht als Bilddatei.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="d4cd9-171">**Zum horizontalen/vertikalen Layout wechseln**: Ändern Sie die Ausrichtung der Entitäten und Beziehungen.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="d4cd9-172">**Bearbeiten**: Aktualisieren Sie die Eigenschaften von benutzerdefinierten Beziehungen im Bearbeitungsbereich und speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="d4cd9-173">Verwalten bestehender Beziehungen</span><span class="sxs-lookup"><span data-stu-id="d4cd9-173">Manage existing relationships</span></span> 

<span data-ttu-id="d4cd9-174">Auf der Seite „Beziehungen“ wird jede Beziehung durch eine Zeile dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="d4cd9-175">Wählen Sie eine Beziehung aus und wählen Sie dann eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="d4cd9-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="d4cd9-176">**Bearbeiten**: Aktualisieren Sie die Eigenschaften von benutzerdefinierten Beziehungen im Bearbeitungsbereich und speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="d4cd9-177">**Löschen**: Löschen Sie benutzerdefinierte Beziehungen.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="d4cd9-178">**Anzeigen**: Zeigen Sie vom System erstellte und geerbte Beziehungen an.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="d4cd9-179">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d4cd9-179">Next step</span></span>

<span data-ttu-id="d4cd9-180">System- und benutzerdefinierte Beziehungen werden zur [Erstellung von Segmenten](segments.md) auf der Grundlage mehrerer Datenquellen verwendet, die nicht mehr in einem Silo gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="d4cd9-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
