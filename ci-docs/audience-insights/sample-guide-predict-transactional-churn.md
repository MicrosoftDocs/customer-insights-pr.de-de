---
title: Transaktionsabwanderungsvorhersage Beispielanleitung
description: Verwenden Sie diese Anleitung, um das Out-of-Box-Modell zur Vorhersage von Transaktionsabwanderung auszuprobieren.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 251bc26246cee16952e8e4cb08e2ed7aa4d18488
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595425"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="1f94e-103">Anleitung zur Vorhersage der Transaktionsabwanderung (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="1f94e-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="1f94e-104">Diese Anleitung führt Sie durch ein End-to-End-Beispiel für die Vorhersage der Transaktionsabwanderung in Customer Insights unter Verwendung der unten angegebenen Daten.</span><span class="sxs-lookup"><span data-stu-id="1f94e-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="1f94e-105">Alle in dieser Anleitung verwendeten Daten sind keine echten Kundendaten und gehören zum Contoso Dataset, das sich in der *Demo* Umgebung innerhalb Ihres Customer Insights-Abonnements befindet.</span><span class="sxs-lookup"><span data-stu-id="1f94e-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="1f94e-106">Szenario</span><span class="sxs-lookup"><span data-stu-id="1f94e-106">Scenario</span></span>

<span data-ttu-id="1f94e-107">Contoso ist ein Unternehmen, das hochwertigen Kaffee und Kaffeemaschinen herstellt, die es über seine Website Contoso Coffee verkauft.</span><span class="sxs-lookup"><span data-stu-id="1f94e-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="1f94e-108">Ihr Ziel ist es, zu wissen, welche Kunden, die normalerweise regelmäßig ihre Produkte kaufen, in den nächsten 60 Tagen keine aktiven Kunden mehr sein werden.</span><span class="sxs-lookup"><span data-stu-id="1f94e-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="1f94e-109">Zu wissen, welche ihrer Kunden **wahrscheinlich abwandern**, kann ihnen helfen, Marketingaufwand zu sparen, indem sie sich darauf konzentrieren, diese Kunden zu halten.</span><span class="sxs-lookup"><span data-stu-id="1f94e-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1f94e-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1f94e-110">Prerequisites</span></span>

- <span data-ttu-id="1f94e-111">Mindestens die [Berechtigung "Mitwirkender"](permissions.md) in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1f94e-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="1f94e-112">Wir empfehlen, dass Sie die folgenden Schritte [in einer neuen Umgebung](manage-environments.md) implementieren.</span><span class="sxs-lookup"><span data-stu-id="1f94e-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="1f94e-113">Aufgabe 1 - Datenerfassung</span><span class="sxs-lookup"><span data-stu-id="1f94e-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="1f94e-114">Lesen Sie speziell die Artikel [über die Datenerfassung](data-sources.md) und [Importieren von Datenquellen mit Power Query Konnektoren](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="1f94e-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="1f94e-115">Die folgenden Informationen setzen voraus, dass Sie mit der Datenerfassung im Allgemeinen vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="1f94e-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="1f94e-116">Datenerfassung von Kundendaten aus der eCommerce-Plattform</span><span class="sxs-lookup"><span data-stu-id="1f94e-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="1f94e-117">Erstellen Sie eine Datenquelle mit dem Namen **eCommerce**, wählen Sie die Importoption und wählen Sie den **Text/CSV** Konnektor.</span><span class="sxs-lookup"><span data-stu-id="1f94e-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1f94e-118">Geben Sie die URL für eCommerce-Kontakte https://aka.ms/ciadclasscontacts ein.</span><span class="sxs-lookup"><span data-stu-id="1f94e-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="1f94e-119">Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.</span><span class="sxs-lookup"><span data-stu-id="1f94e-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1f94e-120">Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:</span><span class="sxs-lookup"><span data-stu-id="1f94e-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1f94e-121">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="1f94e-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="1f94e-122">**CreatedOn**: Datum/Uhrzeit/Zone</span><span class="sxs-lookup"><span data-stu-id="1f94e-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="1f94e-123">![DoB in Datum umwandeln](media/ecommerce-dob-date.PNG "Geburtsdatum in Datum umwandeln")</span><span class="sxs-lookup"><span data-stu-id="1f94e-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="1f94e-124">Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle von **Abfrage** in **eCommerceContacts** um</span><span class="sxs-lookup"><span data-stu-id="1f94e-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="1f94e-125">Speichern Sie die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="1f94e-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="1f94e-126">Datenerfassung von Online-Kaufdaten</span><span class="sxs-lookup"><span data-stu-id="1f94e-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="1f94e-127">Fügen Sie einen weiteren Datensatz zur gleichen **eCommerce** Datenquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="1f94e-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="1f94e-128">Wählen Sie erneut den **Text/CSV** Konnektor.</span><span class="sxs-lookup"><span data-stu-id="1f94e-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="1f94e-129">Geben Sie die URL für **Online-Einkäufe** Daten https://aka.ms/ciadclassonline ein.</span><span class="sxs-lookup"><span data-stu-id="1f94e-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="1f94e-130">Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.</span><span class="sxs-lookup"><span data-stu-id="1f94e-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1f94e-131">Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:</span><span class="sxs-lookup"><span data-stu-id="1f94e-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1f94e-132">**Gekauft am**: Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="1f94e-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="1f94e-133">**GesamtPreis**: Währung</span><span class="sxs-lookup"><span data-stu-id="1f94e-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="1f94e-134">Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle von **Abfrage** in **eCommercePurchases** um.</span><span class="sxs-lookup"><span data-stu-id="1f94e-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="1f94e-135">Speichern Sie die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="1f94e-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="1f94e-136">Kundendaten aus dem Treueschema einlesen</span><span class="sxs-lookup"><span data-stu-id="1f94e-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="1f94e-137">Erstellen Sie eine Datenquelle mit dem Namen **LoyaltyScheme**, wählen Sie die Importoption und wählen Sie den Konnektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="1f94e-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1f94e-138">Geben Sie die URL für eCommerce-Kontakte https://aka.ms/ciadclasscustomerloyalty ein.</span><span class="sxs-lookup"><span data-stu-id="1f94e-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="1f94e-139">Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.</span><span class="sxs-lookup"><span data-stu-id="1f94e-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1f94e-140">Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:</span><span class="sxs-lookup"><span data-stu-id="1f94e-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1f94e-141">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="1f94e-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="1f94e-142">**RewardsPoints**: Ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="1f94e-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="1f94e-143">**CreatedOn**: Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="1f94e-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="1f94e-144">Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle von **Query** in **loyCustomers** um.</span><span class="sxs-lookup"><span data-stu-id="1f94e-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="1f94e-145">Speichern Sie die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="1f94e-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="1f94e-146">Aufgabe 2 - Daten vereinheitlichen</span><span class="sxs-lookup"><span data-stu-id="1f94e-146">Task 2 - Data unification</span></span>

<span data-ttu-id="1f94e-147">Nach der Datenerfassung beginnen wir nun mit dem **Zuordnen, Abgleichen, Zusammenführen** Prozess, um ein einheitliches Kundenprofil zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f94e-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="1f94e-148">Weitere Informationen finden Sie unter [Datenvereinheitlichung](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="1f94e-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="1f94e-149">Zuordnung</span><span class="sxs-lookup"><span data-stu-id="1f94e-149">Map</span></span>

1. <span data-ttu-id="1f94e-150">Nach der Datenerfassung ordnen Sie die Kontakte aus den eCommerce- und Loyalty-Daten den gemeinsamen Datentypen zu.</span><span class="sxs-lookup"><span data-stu-id="1f94e-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="1f94e-151">Gehen Sie zu **Daten** > **Vereinheitlichen** > **Karten**.</span><span class="sxs-lookup"><span data-stu-id="1f94e-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="1f94e-152">Wählen Sie die Entitäten, die das Kundenprofil darstellen - **eCommerceContacts** und **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1f94e-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="Vereinheitlichen Sie E-Commerce- und Treue-Datenquellen.":::

1. <span data-ttu-id="1f94e-154">Wählen Sie **KontaktId** als Primärschlüssel für **eCommerceKontakte** und **LoyaltyID** als Primärschlüssel für **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1f94e-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Vereinheitlichen Sie LoyaltyId als Primärschlüssel.":::

### <a name="match"></a><span data-ttu-id="1f94e-156">Abgleichen</span><span class="sxs-lookup"><span data-stu-id="1f94e-156">Match</span></span>

1. <span data-ttu-id="1f94e-157">Gehen Sie auf die Registerkarte **Abgleichen** und wählen Sie **Reihenfolge festlegen**.</span><span class="sxs-lookup"><span data-stu-id="1f94e-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="1f94e-158">In der Dropdown-Liste **Primär** wählen Sie **eCommerceContacts : eCommerce** als primäre Quelle und schließen alle Datensätze ein.</span><span class="sxs-lookup"><span data-stu-id="1f94e-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="1f94e-159">Wählen Sie in der Dropdown-Liste **Entität 2** die Option **loyCustomers : LoyaltyScheme** und schließen Sie alle Datensätze ein.</span><span class="sxs-lookup"><span data-stu-id="1f94e-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Abgleich eCommerce und Loyalty vereinheitlichen.":::

1. <span data-ttu-id="1f94e-161">Wählen Sie **Eine neue Regel erstellen**</span><span class="sxs-lookup"><span data-stu-id="1f94e-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="1f94e-162">Fügen Sie Ihre erste Bedingung mit FullName hinzu.</span><span class="sxs-lookup"><span data-stu-id="1f94e-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="1f94e-163">Für eCommerceContacts wählen Sie **FullName** in der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="1f94e-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="1f94e-164">Für loyCustomers wählen Sie **FullName** im Dropdown.</span><span class="sxs-lookup"><span data-stu-id="1f94e-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="1f94e-165">Wählen Sie das Dropdown-Menü **Normalisieren** und wählen Sie **Typ (Telefon, Name, Adresse, ...)**.</span><span class="sxs-lookup"><span data-stu-id="1f94e-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="1f94e-166">Setzen Sie **Präzisionsstufe**: **Basis** und **Wert**: **Hoch**.</span><span class="sxs-lookup"><span data-stu-id="1f94e-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="1f94e-167">Geben Sie als Regelname **FullName, Email** ein.</span><span class="sxs-lookup"><span data-stu-id="1f94e-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="1f94e-168">Fügen Sie eine zweite Bedingung für E-Mail-Adressen hinzu, indem Sie **Bedingung hinzufügen** wählen.</span><span class="sxs-lookup"><span data-stu-id="1f94e-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="1f94e-169">Für die Entität eCommerceContacts wählen Sie **EMail** im Dropdown.</span><span class="sxs-lookup"><span data-stu-id="1f94e-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="1f94e-170">Für die Entität loyCustomers wählen Sie **EMail** im Drop-Down.</span><span class="sxs-lookup"><span data-stu-id="1f94e-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="1f94e-171">Lassen Sie Normalisieren leer.</span><span class="sxs-lookup"><span data-stu-id="1f94e-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="1f94e-172">Setzen Sie **Präzisionsstufe**: **Basis** und **Wert**: **Hoch**.</span><span class="sxs-lookup"><span data-stu-id="1f94e-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Übereinstimmungsregel für Name und E-Mail vereinheitlichen.":::

7. <span data-ttu-id="1f94e-174">Wählen Sie **Speichern** und **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1f94e-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="1f94e-175">Mergen</span><span class="sxs-lookup"><span data-stu-id="1f94e-175">Merge</span></span>

1. <span data-ttu-id="1f94e-176">Gehen Sie auf die Registerkarte **Zusammenführen**.</span><span class="sxs-lookup"><span data-stu-id="1f94e-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="1f94e-177">Ändern Sie auf der **ContactId** für die Entität **loyCustomers** den Anzeigenamen in **ContactIdLOYALTY**, um sie von den anderen aufgenommenen IDs zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="1f94e-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Contactid aus Treue-ID umbenennen:":::

1. <span data-ttu-id="1f94e-179">Wählen Sie **Speichern** und **Ausführen**, um den Zusammenführungsprozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="1f94e-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="1f94e-180">Aufgabe 3 - Konfigurieren der Vorhersage der Transaktionsabwanderung</span><span class="sxs-lookup"><span data-stu-id="1f94e-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="1f94e-181">Mit den vereinheitlichten Kundenprofilen können wir nun die Abwanderungsvorhersage für Abonnements durchführen.</span><span class="sxs-lookup"><span data-stu-id="1f94e-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="1f94e-182">Detaillierte Schritte finden Sie im Artikel [Abonnement-Abwanderungsvorhersage (Vorschau)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="1f94e-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="1f94e-183">Gehen Sie zu **Intelligenz** > **Erkennen** und wählen Sie das Modell **Kundenabwanderung**.</span><span class="sxs-lookup"><span data-stu-id="1f94e-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="1f94e-184">Wählen Sie die Option **Transaktional** und wählen Sie **Anfangen**.</span><span class="sxs-lookup"><span data-stu-id="1f94e-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="1f94e-185">Benennen Sie das Modell **OOB-E-Commerce-Abonnementsabwanderungsvorhersage** und die Ausgabe-Entität **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="1f94e-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="1f94e-186">Definieren Sie zwei Bedingungen für das Churn-Modell:</span><span class="sxs-lookup"><span data-stu-id="1f94e-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="1f94e-187">**Vorhersagefenster**: **mindestens 60** Tage.</span><span class="sxs-lookup"><span data-stu-id="1f94e-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="1f94e-188">Diese Einstellung legt fest, wie weit in die Zukunft wir die Kundenabwanderung vorhersagen wollen.</span><span class="sxs-lookup"><span data-stu-id="1f94e-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="1f94e-189">**Abwanderungsdefinition**: **mindestens 60** Tage.</span><span class="sxs-lookup"><span data-stu-id="1f94e-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="1f94e-190">Die Dauer ohne Kauf, nach der ein Kunde als abgewandert gilt.</span><span class="sxs-lookup"><span data-stu-id="1f94e-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Wählen Sie die Modellhebel Vorhersagefenster und Abwanderungsdefinition.":::

1. <span data-ttu-id="1f94e-192">Wählen Sie **Kaufhistorie (erforderlich)** und wählen Sie **Daten hinzufügen** für die Kaufhistorie.</span><span class="sxs-lookup"><span data-stu-id="1f94e-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="1f94e-193">Fügen Sie die Entität **eCommercePurchases : eCommerce** hinzu und ordnen Sie die Felder von eCommerce den entsprechenden vom Modell benötigten Feldern zu.</span><span class="sxs-lookup"><span data-stu-id="1f94e-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="1f94e-194">Verbinden Sie die Entität **eCommercePurchases : eCommerce** mit **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="1f94e-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Join von eCommerce-Entitäten.":::

1. <span data-ttu-id="1f94e-196">Wählen Sie **Weiter**, um den Modellplan einzustellen.</span><span class="sxs-lookup"><span data-stu-id="1f94e-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="1f94e-197">Das Modell muss regelmäßig trainieren, um neue Muster zu lernen, wenn neue Daten erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="1f94e-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="1f94e-198">Wählen Sie für dieses Beispiel **Monatlich**.</span><span class="sxs-lookup"><span data-stu-id="1f94e-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="1f94e-199">Nachdem Sie alle Details überprüft haben, wählen Sie **Speichern und Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1f94e-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="1f94e-200">Aufgabe 4 - Überprüfung der Modellergebnisse und Erklärungen</span><span class="sxs-lookup"><span data-stu-id="1f94e-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="1f94e-201">Lassen Sie das Modell das Training und das Scoring der Daten abschließen.</span><span class="sxs-lookup"><span data-stu-id="1f94e-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="1f94e-202">Sie können nun die Erklärungen zum Abonnement-Abwanderungsmodell überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1f94e-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="1f94e-203">Weitere Informationen finden Sie unter [Überprüfen eines Vorhersagestatus und der Ergebnisse](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="1f94e-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="1f94e-204">Aufgabe 5 - Erzeugen eines Segments von Kunden mit hohem Abwanderungsrisiko</span><span class="sxs-lookup"><span data-stu-id="1f94e-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="1f94e-205">Das Ausführen des Produktionsmodells erstellt eine neue Entität, die Sie in **Daten** > **Entitäten** sehen können.</span><span class="sxs-lookup"><span data-stu-id="1f94e-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="1f94e-206">Sie können ein neues Segment basierend auf der vom Modell erstellten Entität erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f94e-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="1f94e-207">Gehen Sie zu **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="1f94e-207">Go to **Segments**.</span></span> <span data-ttu-id="1f94e-208">Wählen Sie **Neu** und wählen Sie **Erstellen aus** > **Intelligenz**.</span><span class="sxs-lookup"><span data-stu-id="1f94e-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Erstellen eines Segments mit der Modellausgabe.":::

1. <span data-ttu-id="1f94e-210">Wählen Sie den Endpunkt **OOBSubscriptionChurnPrediction** und definieren Sie das Segment:</span><span class="sxs-lookup"><span data-stu-id="1f94e-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="1f94e-211">Feld: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="1f94e-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="1f94e-212">Operator: größer als</span><span class="sxs-lookup"><span data-stu-id="1f94e-212">Operator: greater than</span></span>
   - <span data-ttu-id="1f94e-213">Wert: 0,6</span><span class="sxs-lookup"><span data-stu-id="1f94e-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Abonnement-Abwanderungssegment einrichten.":::

<span data-ttu-id="1f94e-215">Sie haben jetzt ein Segment, das dynamisch aktualisiert wird und Kunden mit hohem Abwanderungsrisiko für dieses Abo-Geschäft identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1f94e-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="1f94e-216">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Segmenten](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1f94e-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]