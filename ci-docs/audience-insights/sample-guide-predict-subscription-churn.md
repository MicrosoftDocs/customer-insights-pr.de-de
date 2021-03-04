---
title: Beispielanleitung für die Abo-Abwanderungsvorhersage
description: Verwenden Sie diese Beispielanleitung, um das Out-of-Box-Modell zur Vorhersage der Abonnement-Abwanderung auszuprobieren.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3f1019ace424f89320c5a0d5058e928f4cbc7e62
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269835"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="1e604-103">Anleitung zur Vorhersage von Abonnement-Abwanderung (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="1e604-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="1e604-104">Wir führen Sie durch ein End-to-End-Beispiel für die Vorhersage der Abwanderung von Abonnenten anhand der unten bereitgestellten Beispieldaten.</span><span class="sxs-lookup"><span data-stu-id="1e604-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="1e604-105">Szenario</span><span class="sxs-lookup"><span data-stu-id="1e604-105">Scenario</span></span>

<span data-ttu-id="1e604-106">Contoso ist ein Unternehmen, das hochwertigen Kaffee und Kaffeemaschinen herstellt, die es über seine Website Contoso Coffee verkauft.</span><span class="sxs-lookup"><span data-stu-id="1e604-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="1e604-107">Sie haben kürzlich ein Abo-Geschäft für Ihre Kunden gestartet, um regelmäßig Kaffee zu bekommen.</span><span class="sxs-lookup"><span data-stu-id="1e604-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="1e604-108">Ihr Ziel ist es, zu verstehen, welche abonnierten Kunden ihr Abonnement in den nächsten Monaten kündigen könnten.</span><span class="sxs-lookup"><span data-stu-id="1e604-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="1e604-109">Zu wissen, welche ihrer Kunden **wahrscheinlich abwandern**, kann ihnen helfen, Marketingaufwand zu sparen, indem sie sich darauf konzentrieren, diese Kunden zu halten.</span><span class="sxs-lookup"><span data-stu-id="1e604-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1e604-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1e604-110">Prerequisites</span></span>

- <span data-ttu-id="1e604-111">Mindestens die [Berechtigung "Mitwirkender"](permissions.md) in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1e604-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="1e604-112">Wir empfehlen, dass Sie die folgenden Schritte [in einer neuen Umgebung](manage-environments.md) implementieren.</span><span class="sxs-lookup"><span data-stu-id="1e604-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="1e604-113">Aufgabe 1 - Datenerfassung</span><span class="sxs-lookup"><span data-stu-id="1e604-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="1e604-114">Lesen Sie speziell die Artikel [über die Datenerfassung](data-sources.md) und [Importieren von Datenquellen mit Power Query Konnektoren](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="1e604-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="1e604-115">Die folgenden Informationen setzen voraus, dass Sie mit der Datenerfassung im Allgemeinen vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="1e604-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="1e604-116">Datenerfassung von Kundendaten aus der eCommerce-Plattform</span><span class="sxs-lookup"><span data-stu-id="1e604-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="1e604-117">Erstellen Sie eine Datenquelle mit dem Namen **eCommerce**, wählen Sie die Importoption und wählen Sie den **Text/CSV** Konnektor.</span><span class="sxs-lookup"><span data-stu-id="1e604-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1e604-118">Geben Sie die URL für eCommerce-Kontakte https://aka.ms/ciadclasscontacts ein.</span><span class="sxs-lookup"><span data-stu-id="1e604-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="1e604-119">Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.</span><span class="sxs-lookup"><span data-stu-id="1e604-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1e604-120">Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:</span><span class="sxs-lookup"><span data-stu-id="1e604-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1e604-121">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="1e604-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="1e604-122">**CreatedOn**: Datum/Uhrzeit/Zone</span><span class="sxs-lookup"><span data-stu-id="1e604-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Geburtsdatum in Datum umwandeln":::

1. <span data-ttu-id="1e604-124">Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle von **Abfrage** in **eCommerceContacts** um</span><span class="sxs-lookup"><span data-stu-id="1e604-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="1e604-125">Speichern Sie die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="1e604-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="1e604-126">Kundendaten aus dem Treueschema einlesen</span><span class="sxs-lookup"><span data-stu-id="1e604-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="1e604-127">Erstellen Sie eine Datenquelle mit dem Namen **LoyaltyScheme**, wählen Sie die Importoption und wählen Sie den Konnektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="1e604-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1e604-128">Geben Sie die URL für eCommerce-Kontakte https://aka.ms/ciadclasscustomerloyalty ein.</span><span class="sxs-lookup"><span data-stu-id="1e604-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="1e604-129">Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.</span><span class="sxs-lookup"><span data-stu-id="1e604-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1e604-130">Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:</span><span class="sxs-lookup"><span data-stu-id="1e604-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1e604-131">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="1e604-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="1e604-132">**RewardsPoints**: Ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="1e604-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="1e604-133">**CreatedOn**: Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="1e604-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="1e604-134">Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle von **Query** in **loyCustomers** um.</span><span class="sxs-lookup"><span data-stu-id="1e604-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="1e604-135">Speichern Sie die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="1e604-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="1e604-136">Einlesen von Abonnement-Informationen</span><span class="sxs-lookup"><span data-stu-id="1e604-136">Ingest subscription information</span></span>

1. <span data-ttu-id="1e604-137">Erstellen Sie eine Datenquelle mit dem Namen **SubscriptionHistory**, wählen Sie die Importoption und wählen Sie den Konnektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="1e604-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1e604-138">Geben Sie die URL für eCommerce-Kontakte https://aka.ms/ciadchurnsubscriptionhistory ein.</span><span class="sxs-lookup"><span data-stu-id="1e604-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="1e604-139">Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.</span><span class="sxs-lookup"><span data-stu-id="1e604-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1e604-140">Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:</span><span class="sxs-lookup"><span data-stu-id="1e604-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1e604-141">**SubscriptioID**: Ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="1e604-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="1e604-142">**SubscriptionAmount**: Währung</span><span class="sxs-lookup"><span data-stu-id="1e604-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="1e604-143">**SubscriptionEndDate**: Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="1e604-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="1e604-144">**SubscriptionStartDate**: Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="1e604-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="1e604-145">**TransactionDate**: Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="1e604-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="1e604-146">**IsRecurring**: Wahr/Falsch</span><span class="sxs-lookup"><span data-stu-id="1e604-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="1e604-147">**Is_auto_renew**: Wahr/Falsch</span><span class="sxs-lookup"><span data-stu-id="1e604-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="1e604-148">**RecurringFrequencyInMonths**: Ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="1e604-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="1e604-149">Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle von **Query** in **SubscriptionHistory** um.</span><span class="sxs-lookup"><span data-stu-id="1e604-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="1e604-150">Speichern Sie die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="1e604-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="1e604-151">Einlesen von Kundendaten aus Website-Bewertungen</span><span class="sxs-lookup"><span data-stu-id="1e604-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="1e604-152">Erstellen Sie eine Datenquelle mit dem Namen **Website**, wählen Sie die Importoption und wählen Sie den **Text/CSV**-Konnektor.</span><span class="sxs-lookup"><span data-stu-id="1e604-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1e604-153">Geben Sie die URL für eCommerce-Kontakte https://aka.ms/ciadclasswebsite ein.</span><span class="sxs-lookup"><span data-stu-id="1e604-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="1e604-154">Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.</span><span class="sxs-lookup"><span data-stu-id="1e604-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1e604-155">Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:</span><span class="sxs-lookup"><span data-stu-id="1e604-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1e604-156">**ReviewRating**: Ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="1e604-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="1e604-157">**ReviewDate**: Datum</span><span class="sxs-lookup"><span data-stu-id="1e604-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="1e604-158">Benennen Sie im Feld „Name“ im rechten Fensterbereich Ihre Datenquelle von **Query** in **WebReviews** um.</span><span class="sxs-lookup"><span data-stu-id="1e604-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="1e604-159">Aufgabe 2 - Daten vereinheitlichen</span><span class="sxs-lookup"><span data-stu-id="1e604-159">Task 2 - Data unification</span></span>

<span data-ttu-id="1e604-160">Nach der Datenerfassung beginnen wir nun mit dem **Zuordnen, Abgleichen, Zusammenführen** Prozess, um ein einheitliches Kundenprofil zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1e604-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="1e604-161">Weitere Informationen finden Sie unter [Datenvereinheitlichung](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="1e604-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="1e604-162">Zuordnung</span><span class="sxs-lookup"><span data-stu-id="1e604-162">Map</span></span>

1. <span data-ttu-id="1e604-163">Nach der Datenerfassung ordnen Sie die Kontakte aus den eCommerce- und Loyalty-Daten den gemeinsamen Datentypen zu.</span><span class="sxs-lookup"><span data-stu-id="1e604-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="1e604-164">Gehen Sie zu **Daten** > **Vereinheitlichen** > **Karten**.</span><span class="sxs-lookup"><span data-stu-id="1e604-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="1e604-165">Wählen Sie die Entitäten, die das Kundenprofil darstellen - **eCommerceContacts** und **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1e604-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="Vereinheitlichen Sie E-Commerce- und Treue-Datenquellen.":::

1. <span data-ttu-id="1e604-167">Wählen Sie **KontaktId** als Primärschlüssel für **eCommerceKontakte** und **LoyaltyID** als Primärschlüssel für **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1e604-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Vereinheitlichen Sie LoyaltyId als Primärschlüssel.":::

### <a name="match"></a><span data-ttu-id="1e604-169">Abgleichen</span><span class="sxs-lookup"><span data-stu-id="1e604-169">Match</span></span>

1. <span data-ttu-id="1e604-170">Gehen Sie auf die Registerkarte **Abgleichen** und wählen Sie **Reihenfolge festlegen**.</span><span class="sxs-lookup"><span data-stu-id="1e604-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="1e604-171">In der Dropdown-Liste **Primär** wählen Sie **eCommerceContacts : eCommerce** als primäre Quelle und schließen alle Datensätze ein.</span><span class="sxs-lookup"><span data-stu-id="1e604-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="1e604-172">Wählen Sie in der Dropdown-Liste **Entität 2** die Option **loyCustomers : LoyaltyScheme** und schließen Sie alle Datensätze ein.</span><span class="sxs-lookup"><span data-stu-id="1e604-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Abgleich eCommerce und Loyalty vereinheitlichen.":::

1. <span data-ttu-id="1e604-174">Wählen Sie **Eine neue Regel erstellen**</span><span class="sxs-lookup"><span data-stu-id="1e604-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="1e604-175">Fügen Sie Ihre erste Bedingung mit FullName hinzu.</span><span class="sxs-lookup"><span data-stu-id="1e604-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="1e604-176">Für eCommerceContacts wählen Sie **FullName** in der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="1e604-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="1e604-177">Für loyCustomers wählen Sie **FullName** im Dropdown.</span><span class="sxs-lookup"><span data-stu-id="1e604-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="1e604-178">Wählen Sie das Dropdown-Menü **Normalisieren** und wählen Sie **Typ (Telefon, Name, Adresse, ...)**.</span><span class="sxs-lookup"><span data-stu-id="1e604-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="1e604-179">Setzen Sie **Präzisionsstufe**: **Basis** und **Wert**: **Hoch**.</span><span class="sxs-lookup"><span data-stu-id="1e604-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="1e604-180">Geben Sie als Regelname **FullName, Email** ein.</span><span class="sxs-lookup"><span data-stu-id="1e604-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="1e604-181">Fügen Sie eine zweite Bedingung für E-Mail-Adressen hinzu, indem Sie **Bedingung hinzufügen** wählen.</span><span class="sxs-lookup"><span data-stu-id="1e604-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="1e604-182">Für die Entität eCommerceContacts wählen Sie **EMail** im Dropdown.</span><span class="sxs-lookup"><span data-stu-id="1e604-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="1e604-183">Für die Entität loyCustomers wählen Sie **EMail** im Drop-Down.</span><span class="sxs-lookup"><span data-stu-id="1e604-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="1e604-184">Lassen Sie Normalisieren leer.</span><span class="sxs-lookup"><span data-stu-id="1e604-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="1e604-185">Setzen Sie **Präzisionsstufe**: **Basis** und **Wert**: **Hoch**.</span><span class="sxs-lookup"><span data-stu-id="1e604-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Übereinstimmungsregel für Name und E-Mail vereinheitlichen.":::

7. <span data-ttu-id="1e604-187">Wählen Sie **Speichern** und **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1e604-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="1e604-188">Mergen</span><span class="sxs-lookup"><span data-stu-id="1e604-188">Merge</span></span>

1. <span data-ttu-id="1e604-189">Gehen Sie auf die Registerkarte **Zusammenführen**.</span><span class="sxs-lookup"><span data-stu-id="1e604-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="1e604-190">Ändern Sie auf der **ContactId** für die Entität **loyCustomers** den Anzeigenamen in **ContactIdLOYALTY**, um sie von den anderen aufgenommenen IDs zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="1e604-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Contactid aus Treue-ID umbenennen:":::

1. <span data-ttu-id="1e604-192">Wählen Sie **Speichern** und **Ausführen**, um den Zusammenführungsprozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="1e604-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="1e604-193">Aufgabe 3 - Konfigurieren der Abonnement-Abwanderungsprognose</span><span class="sxs-lookup"><span data-stu-id="1e604-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="1e604-194">Mit den vereinheitlichten Kundenprofilen können wir nun die Abwanderungsvorhersage für Abonnements durchführen.</span><span class="sxs-lookup"><span data-stu-id="1e604-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="1e604-195">Detaillierte Schritte finden Sie im Artikel [Abonnement-Abwanderungsvorhersage (Vorschau)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="1e604-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="1e604-196">Gehen Sie zu **Intelligenz** > **Erkennen** und wählen Sie das Modell **Kundenabwanderung**.</span><span class="sxs-lookup"><span data-stu-id="1e604-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="1e604-197">Wählen Sie die Option **Abonnement** und wählen Sie **Beginnen**.</span><span class="sxs-lookup"><span data-stu-id="1e604-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="1e604-198">Nennen Sie das Modell **OOB-Abonnementsabwanderungsvorhersage** und die Ausgabe-Entität **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="1e604-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="1e604-199">Definieren Sie zwei Bedingungen für das Churn-Modell:</span><span class="sxs-lookup"><span data-stu-id="1e604-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="1e604-200">**Tage seit Ende des Abonnements**: **mindestens 60** Tage.</span><span class="sxs-lookup"><span data-stu-id="1e604-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="1e604-201">Wenn ein Kunde nach Ablauf seines Abonnements das Abonnement in diesem Zeitraum nicht erneuert, wird er als abgewandert betrachtet.</span><span class="sxs-lookup"><span data-stu-id="1e604-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="1e604-202">**Abwanderungsdefinition**: **mindestens 93** Tage.</span><span class="sxs-lookup"><span data-stu-id="1e604-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="1e604-203">Die Dauer, die das Modell vorhersagt, nach der Kunden abwandern könnten.</span><span class="sxs-lookup"><span data-stu-id="1e604-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="1e604-204">Je weiter Sie in die Zukunft schauen, desto ungenauer werden die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="1e604-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Wählen Sie die Modellhebel Vorhersage-Fenster und Abwanderungs-Definition.":::

1. <span data-ttu-id="1e604-206">Wählen Sie **Erforderliche Daten hinzufügen** und wählen Sie **Daten hinzufügen** für die Abo-Historie.</span><span class="sxs-lookup"><span data-stu-id="1e604-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="1e604-207">Fügen Sie die Entität **Subscription : SubscriptionHistory** hinzu und ordnen Sie die Felder von eCommerce den entsprechenden, vom Modell benötigten Feldern zu.</span><span class="sxs-lookup"><span data-stu-id="1e604-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="1e604-208">Verbinden Sie die Entität **Subscription : SubscriptionHistory** mit **eCommerceContacts : eCommerce**, nennen Sie die Beziehung **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="1e604-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Join von eCommerce-Entitäten.":::

1. <span data-ttu-id="1e604-210">Fügen Sie unter Kundenaktivitäten die Entität **webReviews : Website** hinzu und ordnen Sie die Felder von webReviews den entsprechenden vom Modell benötigten Feldern zu.</span><span class="sxs-lookup"><span data-stu-id="1e604-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="1e604-211">Primärschlüssel: ReviewId</span><span class="sxs-lookup"><span data-stu-id="1e604-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="1e604-212">Zeitstempel: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="1e604-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="1e604-213">Ereignis: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="1e604-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="1e604-214">Konfigurieren Sie eine Aktivität für Website-Bewertungen.</span><span class="sxs-lookup"><span data-stu-id="1e604-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="1e604-215">Wählen Sie die Aktivität **Review** und verbinden Sie die Entität **webReviews : Website** mit **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="1e604-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="1e604-216">Wählen Sie **Weiter**, um den Modellplan einzustellen.</span><span class="sxs-lookup"><span data-stu-id="1e604-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="1e604-217">Das Modell muss regelmäßig trainieren, um neue Muster zu lernen, wenn neue Daten erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="1e604-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="1e604-218">Wählen Sie für dieses Beispiel **Monatlich**.</span><span class="sxs-lookup"><span data-stu-id="1e604-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="1e604-219">Nachdem Sie alle Details überprüft haben, wählen Sie **Speichern und Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1e604-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="1e604-220">Aufgabe 4 - Überprüfung der Modellergebnisse und Erklärungen</span><span class="sxs-lookup"><span data-stu-id="1e604-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="1e604-221">Lassen Sie das Modell das Training und das Scoring der Daten abschließen.</span><span class="sxs-lookup"><span data-stu-id="1e604-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="1e604-222">Sie können nun die Erklärungen zum Abonnement-Abwanderungsmodell überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1e604-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="1e604-223">Weitere Informationen finden Sie unter [Überprüfen eines Vorhersagestatus und der Ergebnisse](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="1e604-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="1e604-224">Aufgabe 5 - Erzeugen eines Segments von Kunden mit hohem Abwanderungsrisiko</span><span class="sxs-lookup"><span data-stu-id="1e604-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="1e604-225">Das Ausführen des Produktionsmodells erstellt eine neue Entität, die Sie in **Daten** > **Entitäten** sehen können.</span><span class="sxs-lookup"><span data-stu-id="1e604-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="1e604-226">Sie können ein neues Segment basierend auf der vom Modell erstellten Entität erstellen.</span><span class="sxs-lookup"><span data-stu-id="1e604-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="1e604-227">Gehen Sie zu **Segmente**.</span><span class="sxs-lookup"><span data-stu-id="1e604-227">Go to **Segments**.</span></span> <span data-ttu-id="1e604-228">Wählen Sie **Neu** und wählen Sie **Erstellen aus** > **Intelligenz**.</span><span class="sxs-lookup"><span data-stu-id="1e604-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Erstellen eines Segments mit der Modellausgabe.":::

1. <span data-ttu-id="1e604-230">Wählen Sie den Endpunkt **OOBSubscriptionChurnPrediction** und definieren Sie das Segment:</span><span class="sxs-lookup"><span data-stu-id="1e604-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="1e604-231">Feld: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="1e604-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="1e604-232">Operator: größer als</span><span class="sxs-lookup"><span data-stu-id="1e604-232">Operator: greater than</span></span>
   - <span data-ttu-id="1e604-233">Wert: 0,6</span><span class="sxs-lookup"><span data-stu-id="1e604-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Abonnement-Abwanderungssegment einrichten.":::

<span data-ttu-id="1e604-235">Sie haben jetzt ein Segment, das dynamisch aktualisiert wird und Kunden mit hohem Abwanderungsrisiko für dieses Abo-Geschäft identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1e604-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="1e604-236">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Segmenten](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1e604-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]