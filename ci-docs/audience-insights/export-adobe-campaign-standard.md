---
title: Customer Insights-Daten in Adobe Campaign Standard exportieren
description: Erfahren Sie, wie Sie Zielgruppen-Insights-Segmente in Adobe Campaign Standard verwenden.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596314"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="c7855-103">Customer Insights-Segmente in Adobe Campaign Standard verwenden (Verwenden)</span><span class="sxs-lookup"><span data-stu-id="c7855-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="c7855-104">Als Benutzer von Zielgruppen-Insights für Dynamics 365 Customer Insights haben Sie möglicherweise Segmente erstellt, um Ihre Marketingkampagnen effizienter zu gestalten, indem Sie relevante Zielgruppen ansprechen.</span><span class="sxs-lookup"><span data-stu-id="c7855-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="c7855-105">Um ein Segment aus Zielgruppen-Insights in Adobe Experience Platform und Anwendungen wie Adobe Campaign Standard zu verwenden, müssen Sie einige in diesem Artikel beschriebene Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="c7855-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Prozessdiagramm der in diesem Artikel beschriebenen Schritte.":::

## <a name="prerequisites"></a><span data-ttu-id="c7855-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c7855-107">Prerequisites</span></span>

-   <span data-ttu-id="c7855-108">Dynamics 365 Customer Insights-Lizenz</span><span class="sxs-lookup"><span data-stu-id="c7855-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="c7855-109">Adobe Campaign Standard-Lizenz</span><span class="sxs-lookup"><span data-stu-id="c7855-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="c7855-110">Azure Blob Storage-Konto</span><span class="sxs-lookup"><span data-stu-id="c7855-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="c7855-111">Kampagnenübersicht</span><span class="sxs-lookup"><span data-stu-id="c7855-111">Campaign Overview</span></span>

<span data-ttu-id="c7855-112">Schauen wir uns eine fiktive Beispielkampagne an, um besser zu verstehen, wie Sie Segmente aus Zielgruppen-Insights in Adobe Experience Platform verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c7855-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="c7855-113">Nehmen wir an, Ihr Unternehmen bietet Ihren Kunden in den USA einen monatlichen, abonnementbasierten Service an.</span><span class="sxs-lookup"><span data-stu-id="c7855-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="c7855-114">Sie möchten Kunden identifizieren, deren Abonnements in den Nächsten acht Tagen erneuert werden sollen, deren Abonnement jedoch noch nicht verlängert wurde.</span><span class="sxs-lookup"><span data-stu-id="c7855-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="c7855-115">Um diese Kunden zu halten, möchten Sie ihnen mithilfe von Adobe Campaign Standard ein Werbeangebot per E-Mail senden.</span><span class="sxs-lookup"><span data-stu-id="c7855-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="c7855-116">In diesem Beispiel möchten wir die Werbe-E-Mail-Kampagne einmal ausführen.</span><span class="sxs-lookup"><span data-stu-id="c7855-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="c7855-117">Dieser Artikel behandelt nicht den Anwendungsfall, die Kampagne mehr als einmal auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c7855-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="c7855-118">Zielgruppen-Insights und Adobe Campaign Standard können jedoch so konfiguriert werden, dass sie auch für ein wiederkehrendes Kampagnenszenario funktionieren.</span><span class="sxs-lookup"><span data-stu-id="c7855-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="c7855-119">Identifizieren Sie Ihre Zielgruppe</span><span class="sxs-lookup"><span data-stu-id="c7855-119">Identify your target audience</span></span>

<span data-ttu-id="c7855-120">In unserem Szenario gehen wir davon aus, dass die E-Mail-Adressen der Kunden in Zielgruppen-Insights verfügbar sind und ihre Werbepräferenzen analysiert wurden, um Mitglieder des Segments zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c7855-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="c7855-121">Das [Segment, das Sie in Zielgruppen-Insights definiert haben](segments.md) wird **ChurnProneCustomers** genannt und Sie planen, diesen Kunden die E-Mail-Aktion zu senden.</span><span class="sxs-lookup"><span data-stu-id="c7855-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot der Segmentseite mit dem erstellten ChurnProneCustomers-Segment.":::

<span data-ttu-id="c7855-123">Die Angebots-E-Mail, die Sie versenden möchten, enthält das Vorname, Nachname, und das Abonnement-Enddatum des Kunden.</span><span class="sxs-lookup"><span data-stu-id="c7855-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="c7855-124">Es informiert die Kunden über den Rabatt, den sie erhalten, wenn sie ihr Abonnement vor Ablauf verlängern.</span><span class="sxs-lookup"><span data-stu-id="c7855-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="c7855-125">Exportieren Sie Ihre Zielgruppe</span><span class="sxs-lookup"><span data-stu-id="c7855-125">Export your target audience</span></span>

<span data-ttu-id="c7855-126">Nachdem unsere Zielgruppe identifiziert wurde, können wir den Export von Zielgruppen-Insights in ein Azure Blob-Speicherkonto konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c7855-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="c7855-127">Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Ziele exportieren**.</span><span class="sxs-lookup"><span data-stu-id="c7855-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c7855-128">In der Kachel **Adobe Campaign** wählen Sie **Einrichten**.</span><span class="sxs-lookup"><span data-stu-id="c7855-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigurationskachel für Adobe Campaign Standard.":::

1. <span data-ttu-id="c7855-130">Geben Sie einen **Anzeigename** für dieses neue Exportziel ein und geben Sie dann **Kontoname**, **Kontoschlüssel**, und **Container** des Azure Blob-Speicherkontos ein, in das Sie das Segment exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="c7855-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot der Speicherkontokonfiguration. "::: 

   - <span data-ttu-id="c7855-132">Weitere Informationen zum Suchen des Azure-Blobspeicherkontonamens und des Kontoschlüssels finden Sie unter [Verwalten von Speicherkontoeinstellungen im Azure-Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="c7855-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="c7855-133">Informationen zum Erstellen eines Containers finden Sie unter [Erstellen eines Containers](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="c7855-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="c7855-134">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c7855-134">Select **Next**.</span></span>

1. <span data-ttu-id="c7855-135">Wählen Sie die Segmente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="c7855-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="c7855-136">In diesem Beispiel ist es **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="c7855-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot der Benutzeroberfläche für die Segmentauswahl mit ausgewähltem ChurnProneCustomers-Segment.":::

1. <span data-ttu-id="c7855-138">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c7855-138">Select **Next**.</span></span>

1. <span data-ttu-id="c7855-139">Jetzt kartieren wir die **Quelle**-Felder aus dem Segment Zielgruppen-Insights bis zu den **Ziel**-Feldnamen im Adobe Campaign Standard-Profilschema.</span><span class="sxs-lookup"><span data-stu-id="c7855-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Feldzuordnung für den Adobe Campaign Standard-Connector.":::

   <span data-ttu-id="c7855-141">Wenn Sie weitere Attribute hinzufügen möchten, wählen Sie **Attribut hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c7855-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="c7855-142">Der Zielname kann sich vom Namen des Quellfelds unterscheiden, sodass Sie die Segmentausgabe von Zielgruppen-Insights weiterhin Adobe Campaign Standard zuordnen können, wenn die Felder in beiden Systemen nicht denselben Namen haben.</span><span class="sxs-lookup"><span data-stu-id="c7855-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c7855-143">Die E-Mail-Adresse wird als Identitätsfeld verwendet. Sie können jedoch jede andere Kennung aus Ihrem Kundenprofil für Zielgruppen-Insights verwenden, um Daten Adobe Campaign Standard zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="c7855-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="c7855-144">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="c7855-144">Select **Save**.</span></span>

<span data-ttu-id="c7855-145">Nachdem Sie das Exportziel gespeichert haben, finden Sie es auf **Administrator** > **Exporte** > **Meine Exportziele**.</span><span class="sxs-lookup"><span data-stu-id="c7855-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Screenshot mit hervorgehobener Exportliste und Beispielsegment.":::

<span data-ttu-id="c7855-147">Sie können jetzt [das Segment nach Bedarf exportieren](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c7855-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="c7855-148">Der Export wird auch bei jeder [geplanten Aktualisierung](system.md) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="c7855-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c7855-149">Stellen Sie sicher, dass die Anzahl der Datensätze im exportierten Segment innerhalb des zulässigen Grenzwerts Ihrer Adobe Campaign Standard-Lizenz liegt.</span><span class="sxs-lookup"><span data-stu-id="c7855-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="c7855-150">Exportierte Daten werden in dem oben konfigurierten Azure Blob-Speichercontainer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c7855-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="c7855-151">Der folgende Ordnerpfad wird automatisch in Ihrem Container erstellt:</span><span class="sxs-lookup"><span data-stu-id="c7855-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="c7855-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="c7855-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="c7855-153">Beispiel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="c7855-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="c7855-154">Adobe Campaign Standard konfigurieren</span><span class="sxs-lookup"><span data-stu-id="c7855-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="c7855-155">Wenn ein Segment aus Zielgruppen-Insights exportiert wird, enthält es die Spalten, die Sie beim Definieren des Exportziels im vorherigen Schritt ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="c7855-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="c7855-156">Diese Daten können verwendet werden, um [Profile in Adobe Campaign Standard zu erstellen](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="c7855-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="c7855-157">Um das Segment in Adobe Campaign Standard zu verwenden, müssen Sie das Profilschema in Adobe Campaign Standard um zwei zusätzliche Felder erweitern.</span><span class="sxs-lookup"><span data-stu-id="c7855-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="c7855-158">Lernen wie man [die Profilressource erweitert](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) mit neuen Feldern in Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="c7855-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="c7855-159">In unserem Beispiel sind diese Felder *Segmentname und Segmentdatum (optional).*</span><span class="sxs-lookup"><span data-stu-id="c7855-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="c7855-160">Wir werden diese Felder verwenden, um die Profile in Adobe Campaign Standard zu identifizieren, auf die wir für diese Kampagne abzielen möchten.</span><span class="sxs-lookup"><span data-stu-id="c7855-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="c7855-161">Wenn in Adobe Campaign Standard keine anderen Datensätze als die zu importierenden vorhanden sind, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="c7855-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="c7855-162">Daten in Adobe Campaign Standard importieren</span><span class="sxs-lookup"><span data-stu-id="c7855-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="c7855-163">Nachdem alles vorhanden ist, müssen wir die vorbereiteten Zielgruppen-Daten aus Zielgruppen-Insights in Adobe Campaign Standard importieren, um Profile zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c7855-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="c7855-164">Lernen Sie, [wie Sie Profile in Adobe Campaign Standard importieren](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) mihilfe eines Workflows.</span><span class="sxs-lookup"><span data-stu-id="c7855-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="c7855-165">Der Import-Workflow in der Abbildung unten wurde so konfiguriert, dass er alle 8 Stunden ausgeführt wird. Er sucht nach exportierten Zielgruppen-Insights-Segmenten (CSV-Datei im Azure Blob-Speicher).</span><span class="sxs-lookup"><span data-stu-id="c7855-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="c7855-166">Der Workflow extrahiert den Inhalt der CSV-Datei in einer angegebenen Spaltenreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="c7855-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="c7855-167">Dieser Workflow wurde entwickelt, um eine grundlegende Fehlerbehandlung durchzuführen und sicherzustellen, dass jeder Datensatz eine E-Mail-Adresse hat, bevor die Daten in Adobe Campaign Standard hydratisiert werden.</span><span class="sxs-lookup"><span data-stu-id="c7855-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="c7855-168">Der Workflow extrahiert auch den Segmentnamen aus dem Dateinamen, bevor er in ACS-Profildaten aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="c7855-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Screenshot eines Import-Workflows in der Benutzeroberfläche von Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="c7855-170">Rufen Sie die Zielgruppe in Adobe Campaign Standard ab</span><span class="sxs-lookup"><span data-stu-id="c7855-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="c7855-171">Sobald die Daten in Adobe Campaign Standard importiert wurden, [können Sie einen Workflow erstellen](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) und Kunden [abfragen](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) basierend auf dem *Segmentname* und *Segmentdatum* um Profile auszuwählen, die für unsere Beispielkampagne identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="c7855-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="c7855-172">Erstellen und senden Sie die E-Mail mit Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c7855-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="c7855-173">Erstellen Sie den E-Mail-Inhalt und dann [testen und senden](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) Sie Ihre E-Mail.</span><span class="sxs-lookup"><span data-stu-id="c7855-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Beispiel-E-Mail mit Verlängerungsangebot von Adobe Campaign Standard.":::