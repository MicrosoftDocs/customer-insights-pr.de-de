---
title: Beispielanleitung für Produktempfehlungsvorhersage
description: Verwenden Sie diese , um das Out-of-Box-Modell zur Vorhersage von Produktempfehlungen auszuprobieren.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 20072d14b160e54f5ad044adc1de6c079bf790e4
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595272"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="7334d-103">Beispielanleitung für Produktempfehlungsvorhersage (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="7334d-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="7334d-104">Wir führen Sie durch ein End-to-End-Beispiel für die Vorhersage von Produktempfehlungen anhand der unten bereitgestellten Beispieldaten.</span><span class="sxs-lookup"><span data-stu-id="7334d-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="7334d-105">Szenario</span><span class="sxs-lookup"><span data-stu-id="7334d-105">Scenario</span></span>

<span data-ttu-id="7334d-106">Contoso ist ein Unternehmen, das hochwertigen Kaffee und Kaffeemaschinen herstellt, die es über seine Website Contoso Coffee verkauft.</span><span class="sxs-lookup"><span data-stu-id="7334d-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="7334d-107">Ihr Ziel ist es zu verstehen, welche Produkte sie ihren wiederkehrenden Kunden empfehlen sollten.</span><span class="sxs-lookup"><span data-stu-id="7334d-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="7334d-108">Das Wissen darüber, was Kunden **wahrscheinlich eher kaufen**, kann ihnen helfen, Marketingbemühungen zu sparen, indem sie sich auf bestimmte Elemente konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="7334d-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7334d-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7334d-109">Prerequisites</span></span>

- <span data-ttu-id="7334d-110">Mindestens die [Berechtigung "Mitwirkender"](permissions.md) in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7334d-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="7334d-111">Wir empfehlen, dass Sie die folgenden Schritte [in einer neuen Umgebung](manage-environments.md) implementieren.</span><span class="sxs-lookup"><span data-stu-id="7334d-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="7334d-112">Aufgabe 1 - Datenerfassung</span><span class="sxs-lookup"><span data-stu-id="7334d-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="7334d-113">Lesen Sie speziell die Artikel [über die Datenerfassung](data-sources.md) und [Importieren von Datenquellen mit Power Query Konnektoren](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="7334d-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="7334d-114">Die folgenden Informationen setzen voraus, dass Sie mit der Datenerfassung im Allgemeinen vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="7334d-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="7334d-115">Datenerfassung von Kundendaten aus der eCommerce-Plattform</span><span class="sxs-lookup"><span data-stu-id="7334d-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="7334d-116">Erstellen Sie eine Datenquelle mit dem Namen **eCommerce**, wählen Sie die Importoption und wählen Sie den **Text/CSV** Konnektor.</span><span class="sxs-lookup"><span data-stu-id="7334d-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="7334d-117">Geben Sie die URL für eCommerce-Kontakte https://aka.ms/ciadclasscontacts ein.</span><span class="sxs-lookup"><span data-stu-id="7334d-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="7334d-118">Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.</span><span class="sxs-lookup"><span data-stu-id="7334d-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="7334d-119">Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:</span><span class="sxs-lookup"><span data-stu-id="7334d-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="7334d-120">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="7334d-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="7334d-121">**CreatedOn**: Datum/Uhrzeit/Zone</span><span class="sxs-lookup"><span data-stu-id="7334d-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Geburtsdatum in Datum umwandeln":::

5. <span data-ttu-id="7334d-123">Benennen Sie im Feld 'Name' im rechten Fensterbereich Ihre Datenquelle von **Abfrage** in **eCommerceContacts** um</span><span class="sxs-lookup"><span data-stu-id="7334d-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="7334d-124">**Speichern** Sie die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="7334d-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="7334d-125">Datenerfassung von Online-Kaufdaten</span><span class="sxs-lookup"><span data-stu-id="7334d-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="7334d-126">Fügen Sie einen weiteren Datensatz zur gleichen **eCommerce** Datenquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="7334d-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="7334d-127">Wählen Sie erneut den **Text/CSV** Konnektor.</span><span class="sxs-lookup"><span data-stu-id="7334d-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="7334d-128">Geben Sie die URL für **Online-Einkäufe** Daten https://aka.ms/ciadclassonline ein.</span><span class="sxs-lookup"><span data-stu-id="7334d-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="7334d-129">Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.</span><span class="sxs-lookup"><span data-stu-id="7334d-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="7334d-130">Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:</span><span class="sxs-lookup"><span data-stu-id="7334d-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="7334d-131">**Gekauft am**: Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="7334d-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="7334d-132">**GesamtPreis**: Währung</span><span class="sxs-lookup"><span data-stu-id="7334d-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="7334d-133">Benennen Sie im Feld **Name** im rechten Seitenbereich Ihre Datenquelle von **Abfrage** in **eCommercePurchases** um.</span><span class="sxs-lookup"><span data-stu-id="7334d-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="7334d-134">Speichern Sie die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="7334d-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="7334d-135">Kundendaten aus dem Treueschema einlesen</span><span class="sxs-lookup"><span data-stu-id="7334d-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="7334d-136">Erstellen Sie eine Datenquelle mit dem Namen **LoyaltyScheme**, wählen Sie die Importoption und wählen Sie den Konnektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="7334d-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="7334d-137">Geben Sie die URL für eCommerce-Kontakte https://aka.ms/ciadclasscustomerloyalty ein.</span><span class="sxs-lookup"><span data-stu-id="7334d-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="7334d-138">Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.</span><span class="sxs-lookup"><span data-stu-id="7334d-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="7334d-139">Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:</span><span class="sxs-lookup"><span data-stu-id="7334d-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="7334d-140">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="7334d-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="7334d-141">**RewardsPoints**: Ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="7334d-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="7334d-142">**CreatedOn**: Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="7334d-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="7334d-143">Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle von **Query** in **loyCustomers** um.</span><span class="sxs-lookup"><span data-stu-id="7334d-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="7334d-144">Speichern Sie die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="7334d-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="7334d-145">Aufgabe 2 - Daten vereinheitlichen</span><span class="sxs-lookup"><span data-stu-id="7334d-145">Task 2 - Data unification</span></span>

<span data-ttu-id="7334d-146">Nach der Datenerfassung beginnen wir nun mit dem **Zuordnen, Abgleichen, Zusammenführen** Prozess, um ein einheitliches Kundenprofil zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7334d-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="7334d-147">Weitere Informationen finden Sie unter [Datenvereinheitlichung](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="7334d-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="7334d-148">Zuordnung</span><span class="sxs-lookup"><span data-stu-id="7334d-148">Map</span></span>

1. <span data-ttu-id="7334d-149">Nach der Datenerfassung ordnen Sie die Kontakte aus den eCommerce- und Loyalty-Daten den gemeinsamen Datentypen zu.</span><span class="sxs-lookup"><span data-stu-id="7334d-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="7334d-150">Gehen Sie zu **Daten** > **Vereinheitlichen** > **Karten**.</span><span class="sxs-lookup"><span data-stu-id="7334d-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="7334d-151">Wählen Sie die Entitäten, die das Kundenprofil darstellen - **eCommerceContacts** und **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="7334d-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![Vereinheitlichen Sie E-Commerce- und Treue-Datenquellen.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="7334d-153">Wählen Sie **KontaktId** als Primärschlüssel für **eCommerceKontakte** und **LoyaltyID** als Primärschlüssel für **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="7334d-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Vereinheitlichen Sie LoyaltyId als Primärschlüssel.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="7334d-155">Abgleichen</span><span class="sxs-lookup"><span data-stu-id="7334d-155">Match</span></span>

1. <span data-ttu-id="7334d-156">Gehen Sie auf die Registerkarte **Abgleichen** und wählen Sie **Reihenfolge festlegen**.</span><span class="sxs-lookup"><span data-stu-id="7334d-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="7334d-157">In der Dropdown-Liste **Primär** wählen Sie **eCommerceContacts : eCommerce** als primäre Quelle und schließen alle Datensätze ein.</span><span class="sxs-lookup"><span data-stu-id="7334d-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="7334d-158">Wählen Sie in der Dropdown-Liste **Entität 2** die Option **loyCustomers : LoyaltyScheme** und schließen Sie alle Datensätze ein.</span><span class="sxs-lookup"><span data-stu-id="7334d-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Abgleich eCommerce und Loyalty vereinheitlichen.](media/unify-match-order.png)

4. <span data-ttu-id="7334d-160">Wählen Sie **Eine neue Regel erstellen**</span><span class="sxs-lookup"><span data-stu-id="7334d-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="7334d-161">Fügen Sie Ihre erste Bedingung mit FullName hinzu.</span><span class="sxs-lookup"><span data-stu-id="7334d-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="7334d-162">Für eCommerceContacts wählen Sie **FullName** in der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="7334d-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="7334d-163">Für loyCustomers wählen Sie **FullName** im Dropdown.</span><span class="sxs-lookup"><span data-stu-id="7334d-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="7334d-164">Wählen Sie das Dropdown-Menü **Normalisieren** und wählen Sie **Typ (Telefon, Name, Adresse, ...)**.</span><span class="sxs-lookup"><span data-stu-id="7334d-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="7334d-165">Setzen Sie **Präzisionsstufe**: **Basis** und **Wert**: **Hoch**.</span><span class="sxs-lookup"><span data-stu-id="7334d-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="7334d-166">Geben Sie als Regelname **FullName, Email** ein.</span><span class="sxs-lookup"><span data-stu-id="7334d-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="7334d-167">Fügen Sie eine zweite Bedingung für E-Mail-Adressen hinzu, indem Sie **Bedingung hinzufügen** wählen.</span><span class="sxs-lookup"><span data-stu-id="7334d-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="7334d-168">Für die Entität eCommerceContacts wählen Sie **EMail** im Dropdown.</span><span class="sxs-lookup"><span data-stu-id="7334d-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="7334d-169">Für die Entität loyCustomers wählen Sie **EMail** im Drop-Down.</span><span class="sxs-lookup"><span data-stu-id="7334d-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="7334d-170">Lassen Sie Normalisieren leer.</span><span class="sxs-lookup"><span data-stu-id="7334d-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="7334d-171">Setzen Sie **Präzisionsstufe**: **Basis** und **Wert**: **Hoch**.</span><span class="sxs-lookup"><span data-stu-id="7334d-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Übereinstimmungsregel für Name und E-Mail vereinheitlichen.](media/unify-match-rule.png)

7. <span data-ttu-id="7334d-173">Wählen Sie **Speichern** und **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7334d-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="7334d-174">Mergen</span><span class="sxs-lookup"><span data-stu-id="7334d-174">Merge</span></span>

1. <span data-ttu-id="7334d-175">Gehen Sie auf die Registerkarte **Zusammenführen**.</span><span class="sxs-lookup"><span data-stu-id="7334d-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="7334d-176">Ändern Sie auf der **ContactId** für die Entität **loyCustomers** den Anzeigenamen in **ContactIdLOYALTY**, um sie von den anderen aufgenommenen IDs zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="7334d-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![Contactid aus Treue-ID umbenennen:](media/unify-merge-contactid.png)

1. <span data-ttu-id="7334d-178">Wählen Sie **Speichern** und **Ausführen**, um den Zusammenführungsprozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="7334d-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="7334d-179">Aufgabe 3 – Konfigurieren Sie die Produktempfehlungsvorhersage</span><span class="sxs-lookup"><span data-stu-id="7334d-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="7334d-180">Mit den vereinheitlichten Kundenprofilen können wir nun die Abwanderungsvorhersage für Abonnements durchführen.</span><span class="sxs-lookup"><span data-stu-id="7334d-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="7334d-181">Gehen Sie zu **Intelligenz** > **Vorhersage** und wählen Sie **Produktempfehlung** aus.</span><span class="sxs-lookup"><span data-stu-id="7334d-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="7334d-182">Wählen Sie **Erste Schritte** aus.</span><span class="sxs-lookup"><span data-stu-id="7334d-182">Select **Get started**.</span></span>

1. <span data-ttu-id="7334d-183">Nennen Sie das Modell **OOB-Produktempfehlungsmodell-Vorhersage** und die Ausgabeentität **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="7334d-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="7334d-184">Definieren Sie drei Bedingungen für das Modell:</span><span class="sxs-lookup"><span data-stu-id="7334d-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="7334d-185">**Anzahl der Produkte**: Setzen Sie diesen Wert auf **5**.</span><span class="sxs-lookup"><span data-stu-id="7334d-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="7334d-186">Diese Einstellung definiert, wie viele Produkte Sie Ihren Kunden empfehlen möchten.</span><span class="sxs-lookup"><span data-stu-id="7334d-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="7334d-187">**Produkte vorschlagen, die Kunden kürzlich gekauft haben?**: Wählen **Ja**, um anzuzeigen, dass Sie Produkte in die Empfehlung aufnehmen möchten, die Ihre Kunden zuvor gekauft haben.</span><span class="sxs-lookup"><span data-stu-id="7334d-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="7334d-188">**Fenster für Vergangenheitsdaten:** Wählen Sie mindestens **365 Tage**.</span><span class="sxs-lookup"><span data-stu-id="7334d-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="7334d-189">Diese Einstellung legt fest, wie weit das Modell die Aktivität des Kunden zurückverfolgt, um sie als Eingabe für Empfehlungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7334d-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modelleinstellungen für das Produktempfehlungsmodell":::

1. <span data-ttu-id="7334d-191">Wählen Sie **Erforderliche Daten** und wählen Sie **Daten hinzufügen** für die Einkaufshistorie.</span><span class="sxs-lookup"><span data-stu-id="7334d-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="7334d-192">Fügen Sie die Entität **eCommercePurchases : eCommerce** hinzu und ordnen Sie die Felder von eCommerce den entsprechenden vom Modell benötigten Feldern zu.</span><span class="sxs-lookup"><span data-stu-id="7334d-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="7334d-193">Verbinden Sie die Entität **eCommercePurchases : eCommerce** mit **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="7334d-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Join von eCommerce-Entitäten.](media/model-purchase-join.png)

1. <span data-ttu-id="7334d-195">Wählen Sie **Weiter**, um den Modellplan einzustellen.</span><span class="sxs-lookup"><span data-stu-id="7334d-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="7334d-196">Das Modell muss regelmäßig trainieren, um neue Muster zu lernen, wenn neue Daten erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="7334d-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="7334d-197">Wählen Sie für dieses Beispiel **Monatlich**.</span><span class="sxs-lookup"><span data-stu-id="7334d-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="7334d-198">Nachdem Sie alle Details überprüft haben, wählen Sie **Speichern und Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7334d-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="7334d-199">Aufgabe 4 - Überprüfung der Modellergebnisse und Erklärungen</span><span class="sxs-lookup"><span data-stu-id="7334d-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="7334d-200">Lassen Sie das Modell das Training und das Scoring der Daten abschließen.</span><span class="sxs-lookup"><span data-stu-id="7334d-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="7334d-201">Sie können nun die Erklärungen zum Produktempfehlungsmodell überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7334d-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="7334d-202">Weitere Informationen finden Sie unter [Überprüfen eines Vorhersagestatus und der Ergebnisse](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="7334d-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="7334d-203">Aufgabe 5 – Erstellen Sie ein Segment mit häufig gekauften Produkten</span><span class="sxs-lookup"><span data-stu-id="7334d-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="7334d-204">Das Ausführen des Produktionsmodells erstellt eine neue Entität, die Sie in **Daten** > **Entitäten** sehen können.</span><span class="sxs-lookup"><span data-stu-id="7334d-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="7334d-205">Sie können ein neues Segment basierend auf der vom Modell erstellten Entität erstellen.</span><span class="sxs-lookup"><span data-stu-id="7334d-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="7334d-206">Gehen Sie zu **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="7334d-206">Go to **Segments**.</span></span> <span data-ttu-id="7334d-207">Wählen Sie **Neu** und wählen Sie **Erstellen aus** > **Intelligenz**.</span><span class="sxs-lookup"><span data-stu-id="7334d-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Erstellen eines Segments mit der Modellausgabe.](media/segment-intelligence.png)

1. <span data-ttu-id="7334d-209">Wählen Sie den Endpunkt **OOBProductRecommendationModelPrediction** und definieren Sie das Segment:</span><span class="sxs-lookup"><span data-stu-id="7334d-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="7334d-210">Feld: ProductID</span><span class="sxs-lookup"><span data-stu-id="7334d-210">Field: ProductID</span></span>
   - <span data-ttu-id="7334d-211">Operator: Wert</span><span class="sxs-lookup"><span data-stu-id="7334d-211">Operator: Value</span></span>
   - <span data-ttu-id="7334d-212">Wert: Wählen Sie die drei wichtigsten Produkt-IDs aus</span><span class="sxs-lookup"><span data-stu-id="7334d-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Erstellen Sie ein Segment aus den Modellergebnissen.":::

<span data-ttu-id="7334d-214">Sie haben jetzt ein Segment, das dynamisch aktualisiert wird und die Kunden identifiziert, die eher bereit sind, die drei am meisten empfohlenen Produkte zu kaufen</span><span class="sxs-lookup"><span data-stu-id="7334d-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="7334d-215">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Segmenten](segments.md).</span><span class="sxs-lookup"><span data-stu-id="7334d-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]