---
title: Beziehungen zwischen Entitäten und Entitätspfaden
description: Erstellen und verwalten Sie Beziehungen zwischen Entitäten aus mehreren Datenquellen.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 292da986faa7f62d8aa73ed7214075612178e2e1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269875"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="c235d-103">Beziehungen zwischen Entitäten</span><span class="sxs-lookup"><span data-stu-id="c235d-103">Relationships between entities</span></span>

<span data-ttu-id="c235d-104">Beziehungen helfen Ihnen, Entitäten zu verbinden und ein Diagramm Ihrer Daten zu erstellen, wenn Entitäten einen gemeinsamen Identifikator (Fremdschlüssel) haben, auf den von einer Entität zu einer anderen verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c235d-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="c235d-105">Verbundene Entitäten ermöglichen Ihnen die Definition von Segmenten und Maßen auf der Grundlage mehrerer Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="c235d-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="c235d-106">Es gibt zwei Arten von Beziehungen.</span><span class="sxs-lookup"><span data-stu-id="c235d-106">There are two types of relationships.</span></span> <span data-ttu-id="c235d-107">Nicht editierbare Systembeziehungen, die automatisch erstellt werden, und benutzerdefinierte Beziehungen, die von Benutzern erstellt und konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="c235d-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="c235d-108">Während der Abgleich- und Zusammenführungsprozesse werden hinter den Kulissen Systembeziehungen auf der Grundlage eines intelligenten Abgleichs erstellt.</span><span class="sxs-lookup"><span data-stu-id="c235d-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="c235d-109">Diese Beziehungen helfen dabei, die Kundenprofilsätze mit den Datensätzen anderer entsprechender Entitäten in Beziehung zu setzen.</span><span class="sxs-lookup"><span data-stu-id="c235d-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="c235d-110">Das folgende Diagramm veranschaulicht die Erstellung von drei Systembeziehungen, wenn die Kundenentität mit zusätzlichen Entitäten abgeglichen wird, um die endgültige Entität Kundenprofil zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="c235d-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c235d-111">![Beziehungserstellung](media/relationships-entities-merge.png "Erstellung von Beziehungen")</span><span class="sxs-lookup"><span data-stu-id="c235d-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="c235d-112">\***CustomerToContact\*-Beziehung** wurde zwischen der Entität Kunde und der Entität Kontakt erstellt.</span><span class="sxs-lookup"><span data-stu-id="c235d-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="c235d-113">Die Entität Kunde erhält das Schlüsselfeld **Contact_contactId**, das sich auf das Schlüsselfeld Kontakt-Entität **contactId** bezieht.</span><span class="sxs-lookup"><span data-stu-id="c235d-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="c235d-114">\***CustomerToAccount\*-Beziehung** wurde zwischen der Entität Kunde und der Entität Konto erstellt.</span><span class="sxs-lookup"><span data-stu-id="c235d-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="c235d-115">Die Entität Kunde erhält das Schlüsselfeld **Account_accountId**, das sich auf das Schlüsselfeld Kontoentität **AccountId** bezieht.</span><span class="sxs-lookup"><span data-stu-id="c235d-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="c235d-116">\***CustomerToWebAccount\*-Beziehung** wurde zwischen der Entität Kunde und der Entität WebAccount angelegt.</span><span class="sxs-lookup"><span data-stu-id="c235d-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="c235d-117">Die Entität Kunde erhält das Schlüsselfeld **WebAccount_webaccountId**, das sich auf das Schlüsselfeld der Entität WebAccount **webaccountId** bezieht.</span><span class="sxs-lookup"><span data-stu-id="c235d-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="c235d-118">Erstellen einer Beziehung</span><span class="sxs-lookup"><span data-stu-id="c235d-118">Create a relationship</span></span>

<span data-ttu-id="c235d-119">Definieren Sie benutzerdefinierte Beziehungen auf der Seite **Beziehungen**.</span><span class="sxs-lookup"><span data-stu-id="c235d-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="c235d-120">Jede Beziehung besteht aus einer Quell-Entität (die Entität, die den Fremdschlüssel enthält) und einer Ziel-Entität (die Entität, auf die der Fremdschlüssel der Quell-Entität zeigt).</span><span class="sxs-lookup"><span data-stu-id="c235d-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="c235d-121">Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Beziehungen**.</span><span class="sxs-lookup"><span data-stu-id="c235d-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="c235d-122">Wählen Sie **Neue Beziehung**.</span><span class="sxs-lookup"><span data-stu-id="c235d-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="c235d-123">Geben Sie im Fensterbereich **Beziehung hinzufügen** die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="c235d-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c235d-124">![Beziehungsdetails eingeben](media/relationships-add.png "Beziehungsdetails eingeben")</span><span class="sxs-lookup"><span data-stu-id="c235d-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="c235d-125">**Beziehungsname**: Name, der den Zweck der Beziehung widerspiegelt (z. B. **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="c235d-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="c235d-126">**Beschreibung:**: Beschreibung der Beziehung.</span><span class="sxs-lookup"><span data-stu-id="c235d-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="c235d-127">**Quellentität**: Wählen Sie die Entität aus, die als Quelle in der Beziehung verwendet wird (z. B. WebLog).</span><span class="sxs-lookup"><span data-stu-id="c235d-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="c235d-128">**Kardinalität**: Wählen Sie die Kardinalität der Quell-Entitätsdatensätze aus.</span><span class="sxs-lookup"><span data-stu-id="c235d-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="c235d-129">Beispielsweise bedeutet „viele“, dass mehrere Weblog-Einträge mit einem WebAccount verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="c235d-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="c235d-130">**Quellschlüsselfeld**: Dies stellt das Fremdschlüsselfeld in der Quellentität dar.</span><span class="sxs-lookup"><span data-stu-id="c235d-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="c235d-131">Beispielsweise hat WebLog das Schlüsselfeld **KontoId**-Fremdschlüssel.</span><span class="sxs-lookup"><span data-stu-id="c235d-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="c235d-132">**Zielentität**: Wählen Sie die Entität, die als Ziel in der Beziehung verwendet wird (z. B. WebAccount).</span><span class="sxs-lookup"><span data-stu-id="c235d-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="c235d-133">**Zielkardinalität**: Wählen Sie die Kardinalität der Zielentitätsdatensätze aus.</span><span class="sxs-lookup"><span data-stu-id="c235d-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="c235d-134">Beispielsweise bedeutet „einer“, dass mehrere Weblog-Einträge mit einem WebAccount verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="c235d-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="c235d-135">**Zielschlüsselfeld**: Dieses Feld stellt das Schlüsselfeld der Zielentität dar.</span><span class="sxs-lookup"><span data-stu-id="c235d-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="c235d-136">Beispielsweise hat WebAccount das Schlüsselfeld **KontoId**.</span><span class="sxs-lookup"><span data-stu-id="c235d-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="c235d-137">Es werden nur Viele-zu-Eins und Eins-zu-Eins-Beziehungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c235d-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="c235d-138">Many-to-Many-Beziehungen können mit Hilfe von zwei Many-to-One-Beziehungen und einer Link-Entität (eine Entität, die zur Verbindung zwischen der Quell- und der Ziel-Entität verwendet wird) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c235d-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="c235d-139">Beziehung löschen</span><span class="sxs-lookup"><span data-stu-id="c235d-139">Delete a relationship</span></span>

1. <span data-ttu-id="c235d-140">Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Beziehungen**.</span><span class="sxs-lookup"><span data-stu-id="c235d-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="c235d-141">Markieren Sie die Ankreuzfelder für die Beziehungen, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="c235d-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="c235d-142">Wählen Sie **Löschen** oben in der Tabelle **Beziehungen**.</span><span class="sxs-lookup"><span data-stu-id="c235d-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="c235d-143">Bestätigen Sie den Löschvorgang.</span><span class="sxs-lookup"><span data-stu-id="c235d-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="c235d-144">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="c235d-144">Next step</span></span>

<span data-ttu-id="c235d-145">System- und benutzerdefinierte Beziehungen werden verwendet, um Segmente auf der Grundlage mehrerer Datenquellen zu erstellen, die nicht mehr in einem Silo gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c235d-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="c235d-146">Weitere Informationen finden Sie unter [Segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="c235d-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]