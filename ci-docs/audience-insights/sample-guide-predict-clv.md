---
title: Beispielanleitung für die Vorhersage des langfristigen Kundenwerts
description: Verwenden Sie diese Beispielanleitung, um das Modell zur Vorhersage des langfristigen Kundenwerts auszuprobieren.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129944"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="73c1d-103">Beispielanleitung für die Vorhersage des langfristigen Kundenwerts (Customer Lifetime Value, CLV)</span><span class="sxs-lookup"><span data-stu-id="73c1d-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="73c1d-104">In dieser Anleitung wird Ihnen ein End-to-End-Beispiel zur Vorhersage des CLV in Customer Insights anhand von Beispieldaten erläutert.</span><span class="sxs-lookup"><span data-stu-id="73c1d-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="73c1d-105">Szenario</span><span class="sxs-lookup"><span data-stu-id="73c1d-105">Scenario</span></span>

<span data-ttu-id="73c1d-106">Contoso ist ein Unternehmen, das hochwertigen Kaffee und Kaffeemaschinen herstellt.</span><span class="sxs-lookup"><span data-stu-id="73c1d-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="73c1d-107">Die Produkte werden über Website Contoso Coffee vertrieben.</span><span class="sxs-lookup"><span data-stu-id="73c1d-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="73c1d-108">Das Unternehmen möchte den Wert (Umsatz) verstehen, den seine Kunden in den nächsten 12 Monaten generieren können.</span><span class="sxs-lookup"><span data-stu-id="73c1d-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="73c1d-109">Wenn der erwartete Wert für die nächsten 12 Monaten bekannt ist, kann das Unternehmen seine Marketingbemühungen auf hochwertige Kunden ausrichten.</span><span class="sxs-lookup"><span data-stu-id="73c1d-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="73c1d-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="73c1d-110">Prerequisites</span></span>

- <span data-ttu-id="73c1d-111">Mindestens [Berechtigungen für Mitwirkende](permissions.md) für Zielgruppenerkenntnisse.</span><span class="sxs-lookup"><span data-stu-id="73c1d-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="73c1d-112">Wir empfehlen, dass Sie die folgenden Schritte [in einer neuen Umgebung](manage-environments.md) implementieren.</span><span class="sxs-lookup"><span data-stu-id="73c1d-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="73c1d-113">Aufgabe 1 - Datenerfassung</span><span class="sxs-lookup"><span data-stu-id="73c1d-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="73c1d-114">Lesen Sie die Artikel [zur Datenerfassung](data-sources.md) und zum [Importieren von Datenquellen mit Power Query-Konnektoren](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="73c1d-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="73c1d-115">Die folgenden Informationen setzen voraus, dass Sie mit der Datenerfassung im Allgemeinen vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="73c1d-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="73c1d-116">Datenerfassung von Kundendaten aus der eCommerce-Plattform</span><span class="sxs-lookup"><span data-stu-id="73c1d-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="73c1d-117">Erstellen Sie eine Datenquelle mit dem Namen **eCommerce**, wählen Sie die Importoption und wählen Sie den **Text/CSV** Konnektor.</span><span class="sxs-lookup"><span data-stu-id="73c1d-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="73c1d-118">Geben Sie die URL für eCommerce-Kontakte ein: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="73c1d-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="73c1d-119">Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.</span><span class="sxs-lookup"><span data-stu-id="73c1d-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="73c1d-120">Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:</span><span class="sxs-lookup"><span data-stu-id="73c1d-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="73c1d-121">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="73c1d-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="73c1d-122">**CreatedOn**: Datum/Uhrzeit/Zone</span><span class="sxs-lookup"><span data-stu-id="73c1d-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Geburtsdatum in Datum umwandeln":::

1. <span data-ttu-id="73c1d-124">Benennen Sie im Feld 'Name' im rechten Fensterbereich Ihre Datenquelle von **Abfrage** in **eCommerceContacts** um</span><span class="sxs-lookup"><span data-stu-id="73c1d-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="73c1d-125">**Speichern** Sie die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="73c1d-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="73c1d-126">Datenerfassung von Online-Kaufdaten</span><span class="sxs-lookup"><span data-stu-id="73c1d-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="73c1d-127">Fügen Sie einen weiteren Datensatz zur gleichen **eCommerce** Datenquelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="73c1d-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="73c1d-128">Wählen Sie erneut den **Text/CSV** Konnektor.</span><span class="sxs-lookup"><span data-stu-id="73c1d-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="73c1d-129">Geben Sie die URL für **Online-Einkäufe** Daten https://aka.ms/ciadclassonline ein.</span><span class="sxs-lookup"><span data-stu-id="73c1d-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="73c1d-130">Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.</span><span class="sxs-lookup"><span data-stu-id="73c1d-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="73c1d-131">Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:</span><span class="sxs-lookup"><span data-stu-id="73c1d-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="73c1d-132">**Gekauft am**: Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="73c1d-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="73c1d-133">**GesamtPreis**: Währung</span><span class="sxs-lookup"><span data-stu-id="73c1d-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="73c1d-134">Benennen Sie im Feld **Name** im rechten Seitenbereich Ihre Datenquelle von **Abfrage** in **eCommercePurchases** um.</span><span class="sxs-lookup"><span data-stu-id="73c1d-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="73c1d-135">**Speichern** Sie die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="73c1d-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="73c1d-136">Kundendaten aus dem Treueschema einlesen</span><span class="sxs-lookup"><span data-stu-id="73c1d-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="73c1d-137">Erstellen Sie eine Datenquelle mit dem Namen **LoyaltyScheme**, wählen Sie die Importoption und wählen Sie den Konnektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="73c1d-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="73c1d-138">Geben Sie die URL für eCommerce-Kontakte https://aka.ms/ciadclasscustomerloyalty ein.</span><span class="sxs-lookup"><span data-stu-id="73c1d-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="73c1d-139">Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.</span><span class="sxs-lookup"><span data-stu-id="73c1d-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="73c1d-140">Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:</span><span class="sxs-lookup"><span data-stu-id="73c1d-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="73c1d-141">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="73c1d-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="73c1d-142">**RewardsPoints**: Ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="73c1d-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="73c1d-143">**CreatedOn**: Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="73c1d-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="73c1d-144">Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle von **Query** in **loyCustomers** um.</span><span class="sxs-lookup"><span data-stu-id="73c1d-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="73c1d-145">**Speichern** Sie die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="73c1d-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="73c1d-146">Einlesen von Kundendaten aus Website-Bewertungen</span><span class="sxs-lookup"><span data-stu-id="73c1d-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="73c1d-147">Erstellen Sie eine Datenquelle mit dem Namen **Website**, wählen Sie die Importoption und wählen Sie den **Text/CSV**-Konnektor.</span><span class="sxs-lookup"><span data-stu-id="73c1d-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="73c1d-148">Geben Sie die URL für eCommerce-Kontakte https://aka.ms/CI-ILT/WebReviews ein.</span><span class="sxs-lookup"><span data-stu-id="73c1d-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="73c1d-149">Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.</span><span class="sxs-lookup"><span data-stu-id="73c1d-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="73c1d-150">Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:</span><span class="sxs-lookup"><span data-stu-id="73c1d-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="73c1d-151">**ReviewRating**: Dezimalzahl</span><span class="sxs-lookup"><span data-stu-id="73c1d-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="73c1d-152">**ReviewDate**: Datum</span><span class="sxs-lookup"><span data-stu-id="73c1d-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="73c1d-153">Benennen Sie Ihre Datenquelle im Feld „Name“ im rechten Bereich von **Abfrage** in **Überprüfungen** um.</span><span class="sxs-lookup"><span data-stu-id="73c1d-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="73c1d-154">**Speichern** Sie die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="73c1d-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="73c1d-155">Aufgabe 2 - Daten vereinheitlichen</span><span class="sxs-lookup"><span data-stu-id="73c1d-155">Task 2 - Data unification</span></span>

<span data-ttu-id="73c1d-156">Nach dem Erfassen der Daten beginnen wir nun mit der Datenvereinheitlichung, um ein vereinheitlichtes Kundenprofil zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="73c1d-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="73c1d-157">Weitere Informationen finden Sie unter [Datenvereinheitlichung](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="73c1d-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="73c1d-158">Zuordnung</span><span class="sxs-lookup"><span data-stu-id="73c1d-158">Map</span></span>

1. <span data-ttu-id="73c1d-159">Nach der Datenerfassung ordnen Sie die Kontakte aus den eCommerce- und Loyalty-Daten den gemeinsamen Datentypen zu.</span><span class="sxs-lookup"><span data-stu-id="73c1d-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="73c1d-160">Gehen Sie zu **Daten** > **Vereinheitlichen** > **Karten**.</span><span class="sxs-lookup"><span data-stu-id="73c1d-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="73c1d-161">Wählen Sie die Entitäten, die das Kundenprofil darstellen - **eCommerceContacts** und **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="73c1d-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="73c1d-162">Wählen Sie dann **Übernehmen** aus.</span><span class="sxs-lookup"><span data-stu-id="73c1d-162">Then, select **Apply**.</span></span>

   ![Vereinheitlichen Sie E-Commerce- und Treue-Datenquellen.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="73c1d-164">Wählen Sie **KontaktId** als Primärschlüssel für **eCommerceKontakte** und **LoyaltyID** als Primärschlüssel für **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="73c1d-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Vereinheitlichen Sie LoyaltyId als Primärschlüssel.](media/unify-loyaltyid.png)

1. <span data-ttu-id="73c1d-166">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="73c1d-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="73c1d-167">Abgleichen</span><span class="sxs-lookup"><span data-stu-id="73c1d-167">Match</span></span>

1. <span data-ttu-id="73c1d-168">Gehen Sie auf die Registerkarte **Abgleichen** und wählen Sie **Reihenfolge festlegen**.</span><span class="sxs-lookup"><span data-stu-id="73c1d-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="73c1d-169">In der Dropdown-Liste **Primär** wählen Sie **eCommerceContacts : eCommerce** als primäre Quelle und schließen alle Datensätze ein.</span><span class="sxs-lookup"><span data-stu-id="73c1d-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="73c1d-170">Wählen Sie in der Dropdown-Liste **Entität 2** die Option **loyCustomers : LoyaltyScheme** und schließen Sie alle Datensätze ein.</span><span class="sxs-lookup"><span data-stu-id="73c1d-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Abgleich eCommerce und Loyalty vereinheitlichen.](media/unify-match-order.png)

1. <span data-ttu-id="73c1d-172">Wählen Sie **Regel hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="73c1d-172">Select **Add rule**</span></span>

1. <span data-ttu-id="73c1d-173">Fügen Sie Ihre erste Bedingung mit FullName hinzu.</span><span class="sxs-lookup"><span data-stu-id="73c1d-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="73c1d-174">Für eCommerceContacts wählen Sie **FullName** in der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="73c1d-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="73c1d-175">Für loyCustomers wählen Sie **FullName** im Dropdown.</span><span class="sxs-lookup"><span data-stu-id="73c1d-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="73c1d-176">Wählen Sie in der Dropdownliste **Normalisieren** die Option **Typ (Telefon, Name, Adresse, ...)** aus.</span><span class="sxs-lookup"><span data-stu-id="73c1d-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="73c1d-177">Setzen Sie **Präzisionsstufe**: **Basis** und **Wert**: **Hoch**.</span><span class="sxs-lookup"><span data-stu-id="73c1d-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="73c1d-178">Geben Sie als Regelname **FullName, Email** ein.</span><span class="sxs-lookup"><span data-stu-id="73c1d-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="73c1d-179">Fügen Sie eine zweite Bedingung für E-Mail-Adressen hinzu, indem Sie **Bedingung hinzufügen** wählen.</span><span class="sxs-lookup"><span data-stu-id="73c1d-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="73c1d-180">Für die Entität eCommerceContacts wählen Sie **EMail** im Dropdown.</span><span class="sxs-lookup"><span data-stu-id="73c1d-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="73c1d-181">Für die Entität loyCustomers wählen Sie **EMail** im Drop-Down.</span><span class="sxs-lookup"><span data-stu-id="73c1d-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="73c1d-182">Lassen Sie Normalisieren leer.</span><span class="sxs-lookup"><span data-stu-id="73c1d-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="73c1d-183">Setzen Sie **Präzisionsstufe**: **Basis** und **Wert**: **Hoch**.</span><span class="sxs-lookup"><span data-stu-id="73c1d-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Übereinstimmungsregel für Name und E-Mail vereinheitlichen.](media/unify-match-rule.png)

1. <span data-ttu-id="73c1d-185">Wählen Sie **Fertig** aus.</span><span class="sxs-lookup"><span data-stu-id="73c1d-185">Select **Done**.</span></span>

1. <span data-ttu-id="73c1d-186">Wählen Sie **Speichern** und **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="73c1d-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="73c1d-187">Zusammenführen</span><span class="sxs-lookup"><span data-stu-id="73c1d-187">Merge</span></span>

1. <span data-ttu-id="73c1d-188">Gehen Sie auf die Registerkarte **Zusammenführen**.</span><span class="sxs-lookup"><span data-stu-id="73c1d-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="73c1d-189">Ändern Sie auf der **ContactId** für die Entität **loyCustomers** den Anzeigenamen in **ContactIdLOYALTY**, um sie von den anderen aufgenommenen IDs zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="73c1d-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![Contactid aus Treue-ID umbenennen:](media/unify-merge-contactid.png)

1. <span data-ttu-id="73c1d-191">Wählen Sie **Speichern** und **Merge- und Downstream-Prozesse ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="73c1d-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="73c1d-192">Aufgabe 3 – Konfigurieren der Vorhersage des langfristigen Kundenwerts</span><span class="sxs-lookup"><span data-stu-id="73c1d-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="73c1d-193">Mit den vereinheitlichten Kundenprofilen können wir jetzt die Vorhersage des langfristigen Kundenwerts ausführen.</span><span class="sxs-lookup"><span data-stu-id="73c1d-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="73c1d-194">Detaillierte Schritte finden Sie unter [Vorhersage des langfristigen Kundenwerts (Vorschau)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="73c1d-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="73c1d-195">Wechseln Sie zu **Intelligenz**  > **Vorhersagen** und wählen Sie **Kundenlebensdauerwert-Modell** aus.</span><span class="sxs-lookup"><span data-stu-id="73c1d-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="73c1d-196">Gehen Sie die Informationen im Seitenbereich durch und wählen Sie **Los geht's** aus.</span><span class="sxs-lookup"><span data-stu-id="73c1d-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="73c1d-197">Nennen Sie das Modell **OOB eCommerce CLV-Vorhersage** und die Ausgabeentität **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="73c1d-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="73c1d-198">Definieren Sie Modellpräferenzen für das CLV-Modell:</span><span class="sxs-lookup"><span data-stu-id="73c1d-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="73c1d-199">**Vorhersagezeitraum**:**12 Monate oder 1 Jahr**.</span><span class="sxs-lookup"><span data-stu-id="73c1d-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="73c1d-200">Diese Einstellung definiert, wie weit in die Zukunft der langfristige Kundenwert vorhergesagt werden soll.</span><span class="sxs-lookup"><span data-stu-id="73c1d-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="73c1d-201">**Aktive Kunden**: Geben Sie an, was aktive Kunden für Ihr Unternehmen bedeuten.</span><span class="sxs-lookup"><span data-stu-id="73c1d-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="73c1d-202">Legen Sie den historischen Zeitrahmen fest, in dem ein Kunde mindestens eine Transaktion durchgeführt haben muss, um als aktiv zu gelten.</span><span class="sxs-lookup"><span data-stu-id="73c1d-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="73c1d-203">Das Modell sagt CLV nur für aktive Kunden voraus.</span><span class="sxs-lookup"><span data-stu-id="73c1d-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="73c1d-204">Wählen Sie aus, ob das Modell den Zeitraum basierend auf historischen Transaktionsdaten berechnen soll oder ob Sie einen bestimmten Zeitrahmen angeben möchten.</span><span class="sxs-lookup"><span data-stu-id="73c1d-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="73c1d-205">In dieser Beispielanleitung **lassen wir das Kaufintervall vom Modell berechnen**, was die Standardoption ist.</span><span class="sxs-lookup"><span data-stu-id="73c1d-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="73c1d-206">**Kunden mit hohem Wert**: Definieren Sie hochwertige Kunden als Perzentil der am meisten bezahlenden Kunden.</span><span class="sxs-lookup"><span data-stu-id="73c1d-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="73c1d-207">Das Modell verwendet diese Eingabe, um Ergebnisse bereitzustellen, die Ihrer Geschäftsdefinition von Kunden mit hohem Wert entsprechen.</span><span class="sxs-lookup"><span data-stu-id="73c1d-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="73c1d-208">Sie können Kunden mit hohem Wert vom Modell definieren lassen.</span><span class="sxs-lookup"><span data-stu-id="73c1d-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="73c1d-209">Es verwendet eine heuristische Regel, die das Perzentil ableitet.</span><span class="sxs-lookup"><span data-stu-id="73c1d-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="73c1d-210">Sie können Kunden mit hohem Wert auch als Perzentil der zukünftig am meisten bezahlenden Kunden definieren.</span><span class="sxs-lookup"><span data-stu-id="73c1d-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="73c1d-211">In dieser Beispielanleitung definieren wir Kunden mit hohem Wert manuell als **Top 30 % der aktiv zahlenden Kunden** und wählen dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="73c1d-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Einstellungsschritt in der Anleitung für das CLV-Modell.":::

1. <span data-ttu-id="73c1d-213">Wählen Sie im Schritt **Erforderliche Daten** die Option **Daten hinzufügen** aus, um die Daten zum Transaktionsverlauf anzugeben.</span><span class="sxs-lookup"><span data-stu-id="73c1d-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="73c1d-214">Fügen Sie die Entität **eCommercePurchases : eCommerce** hinzu und ordnen Sie die Attribute zu, die für das Modell erforderlich sind:</span><span class="sxs-lookup"><span data-stu-id="73c1d-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="73c1d-215">Transaktions-ID: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="73c1d-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="73c1d-216">Transaktionsdatum: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="73c1d-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="73c1d-217">Transaktionsbetrag: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="73c1d-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="73c1d-218">Produkt-ID: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="73c1d-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="73c1d-219">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="73c1d-219">Select **Next**.</span></span>

1. <span data-ttu-id="73c1d-220">Richten Sie die Beziehung zwischen der Entität **eCommercePurchases : eCommerce** und **eCommerceContacts : eCommerce** ein.</span><span class="sxs-lookup"><span data-stu-id="73c1d-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="73c1d-221">Der Schritt **Zusätzliche Daten (optional)** ermöglicht das Hinzufügen weiterer Kundenaktivitätsdaten.</span><span class="sxs-lookup"><span data-stu-id="73c1d-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="73c1d-222">Diese Daten können dazu beitragen, mehr Erkenntnisse zu den Kundeninteraktionen mit Ihrem Unternehmen zu erhalten, die zum CLV beitragen können.</span><span class="sxs-lookup"><span data-stu-id="73c1d-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="73c1d-223">Das Hinzufügen wichtiger Kundeninteraktionen – wie Webprotokolle, Protokolle des Kundenservice oder der Verlauf des Prämienprogramms – kann die Genauigkeit der Vorhersagen verbessern.</span><span class="sxs-lookup"><span data-stu-id="73c1d-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="73c1d-224">Wählen Sie **Daten hinzufügen** aus, um mehr Kundenaktivitätsdaten aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="73c1d-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="73c1d-225">Fügen Sie die Kundenaktivitätsentität hinzu und ordnen Sie ihre Feldnamen den entsprechenden Feldern zu, die für das Modell erforderlich sind:</span><span class="sxs-lookup"><span data-stu-id="73c1d-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="73c1d-226">Kundenaktivitätsentität: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="73c1d-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="73c1d-227">Primärschlüssel: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="73c1d-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="73c1d-228">Zeitstempel: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="73c1d-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="73c1d-229">Ereignis (Aktivitätsname): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="73c1d-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="73c1d-230">Details (Betrag oder Wert): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="73c1d-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="73c1d-231">Wählen Sie **Weiter** aus und konfigurieren Sie die Aktivität und die Beziehung zwischen den Transaktionsdaten und den Kundendaten:</span><span class="sxs-lookup"><span data-stu-id="73c1d-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="73c1d-232">Aktivitätstyp: Vorhandene auswählen</span><span class="sxs-lookup"><span data-stu-id="73c1d-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="73c1d-233">Aktivitätsbeschriftung: Überprüfung</span><span class="sxs-lookup"><span data-stu-id="73c1d-233">Activity label: Review</span></span>
   - <span data-ttu-id="73c1d-234">Entsprechende Beschriftung: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="73c1d-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="73c1d-235">Kundenentität: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="73c1d-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="73c1d-236">Beziehung: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="73c1d-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="73c1d-237">Wählen Sie **Weiter**, um den Modellplan einzustellen.</span><span class="sxs-lookup"><span data-stu-id="73c1d-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="73c1d-238">Das Modell muss regelmäßig trainiert werden, um neue Muster zu lernen, wenn neue Daten erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="73c1d-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="73c1d-239">Wählen Sie für dieses Beispiel **Monatlich** aus.</span><span class="sxs-lookup"><span data-stu-id="73c1d-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="73c1d-240">Nachdem Sie alle Details überprüft haben, wählen Sie **Speichern und ausführen**.</span><span class="sxs-lookup"><span data-stu-id="73c1d-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="73c1d-241">Aufgabe 4 - Überprüfung der Modellergebnisse und Erklärungen</span><span class="sxs-lookup"><span data-stu-id="73c1d-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="73c1d-242">Lassen Sie das Modell das Training und das Scoring der Daten abschließen.</span><span class="sxs-lookup"><span data-stu-id="73c1d-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="73c1d-243">Als Nächstes können Sie die Ergebnisse und Erläuterungen des CLV-Modells überprüfen.</span><span class="sxs-lookup"><span data-stu-id="73c1d-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="73c1d-244">Weitere Informationen finden Sie unter [Überprüfen eines Vorhersagestatus und der Ergebnisse](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="73c1d-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="73c1d-245">Aufgabe 5 – Erstellen eines Segments mit Kunden mit hohem Wert</span><span class="sxs-lookup"><span data-stu-id="73c1d-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="73c1d-246">Beim Ausführen des Modells wird eine neue Entität erstellt, die unter **Daten** > **Entitäten** aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="73c1d-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="73c1d-247">Sie können ein neues Kundensegment basierend auf der vom Modell erstellten Entität erstellen.</span><span class="sxs-lookup"><span data-stu-id="73c1d-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="73c1d-248">Gehen Sie zu **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="73c1d-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="73c1d-249">Wählen Sie **Neu** aus und wechseln Sie dann zu **Erstellen aus** > **Intelligenz**.</span><span class="sxs-lookup"><span data-stu-id="73c1d-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Erstellen eines Segments mit der Modellausgabe.](media/segment-intelligence.png)

1. <span data-ttu-id="73c1d-251">Wählen Sie die Entität **OOBeCommerceCLVPrediction** aus und definieren Sie das Segment:</span><span class="sxs-lookup"><span data-stu-id="73c1d-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="73c1d-252">Feld: CLVScore</span><span class="sxs-lookup"><span data-stu-id="73c1d-252">Field: CLVScore</span></span>
  - <span data-ttu-id="73c1d-253">Operator: größer als</span><span class="sxs-lookup"><span data-stu-id="73c1d-253">Operator: greater than</span></span>
  - <span data-ttu-id="73c1d-254">Wert: 1500</span><span class="sxs-lookup"><span data-stu-id="73c1d-254">Value: 1500</span></span>

1. <span data-ttu-id="73c1d-255">Wählen Sie **Überprüfung** aus und wählen Sie dann für das Segment **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="73c1d-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="73c1d-256">Sie haben jetzt ein Segment, das Kunden identifiziert, die in den kommenden 12 Monaten voraussichtlich mehr als 1.500 US-Dollar Umsatz generieren werden.</span><span class="sxs-lookup"><span data-stu-id="73c1d-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="73c1d-257">Dieses Segment wird dynamisch aktualisiert, wenn mehr Daten erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="73c1d-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="73c1d-258">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Segmenten](segments.md).</span><span class="sxs-lookup"><span data-stu-id="73c1d-258">For more information, see [Create and manage segments](segments.md).</span></span>
