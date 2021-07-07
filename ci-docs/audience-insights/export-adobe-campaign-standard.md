---
title: Customer Insights-Daten in Adobe Campaign Standard exportieren
description: Erfahren Sie, wie Sie Zielgruppen-Insights-Segmente in Adobe Campaign Standard verwenden.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 917ab9559416f3ee0ffd66e471e590e8da3faffc
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305385"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="a7cac-103">Customer Insights-Segmente in Adobe Campaign Standard verwenden (Verwenden)</span><span class="sxs-lookup"><span data-stu-id="a7cac-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="a7cac-104">Als Nutzer von Zielgruppeneinblicken in Dynamics 365 Customer Insights haben Sie möglicherweise Segmente erstellt, um Ihre Marketingkampagnen durch die Ausrichtung auf relevante Zielgruppen effizienter zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="a7cac-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="a7cac-105">Um ein Segment aus Zielgruppen-Insights in Adobe Experience Platform und Anwendungen wie Adobe Campaign Standard zu verwenden, müssen Sie einige in diesem Artikel beschriebene Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="a7cac-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Prozessdiagramm der in diesem Artikel beschriebenen Schritte.":::

## <a name="prerequisites"></a><span data-ttu-id="a7cac-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a7cac-107">Prerequisites</span></span>

-   <span data-ttu-id="a7cac-108">Dynamics 365 Customer Insights-Lizenz</span><span class="sxs-lookup"><span data-stu-id="a7cac-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="a7cac-109">Adobe Campaign Standard-Lizenz</span><span class="sxs-lookup"><span data-stu-id="a7cac-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="a7cac-110">Azure Blob Storage-Konto</span><span class="sxs-lookup"><span data-stu-id="a7cac-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="a7cac-111">Kampagnenübersicht</span><span class="sxs-lookup"><span data-stu-id="a7cac-111">Campaign overview</span></span>

<span data-ttu-id="a7cac-112">Schauen wir uns eine fiktive Beispielkampagne an, um besser zu verstehen, wie Sie Segmente aus Zielgruppen-Insights in Adobe Experience Platform verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a7cac-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="a7cac-113">Nehmen wir an, Ihr Unternehmen bietet Ihren Kunden in den USA einen monatlichen, abonnementbasierten Service an.</span><span class="sxs-lookup"><span data-stu-id="a7cac-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="a7cac-114">Sie möchten Kunden identifizieren, deren Abonnements in den Nächsten acht Tagen erneuert werden sollen, deren Abonnement jedoch noch nicht verlängert wurde.</span><span class="sxs-lookup"><span data-stu-id="a7cac-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="a7cac-115">Um diese Kunden zu halten, möchten Sie ihnen mithilfe von Adobe Campaign Standard ein Werbeangebot per E-Mail senden.</span><span class="sxs-lookup"><span data-stu-id="a7cac-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="a7cac-116">In diesem Beispiel möchten wir die Werbe-E-Mail-Kampagne einmal ausführen.</span><span class="sxs-lookup"><span data-stu-id="a7cac-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="a7cac-117">Dieser Artikel behandelt nicht den Anwendungsfall, die Kampagne mehr als einmal auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a7cac-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="a7cac-118">Zielgruppen-Insights und Adobe Campaign Standard können jedoch so konfiguriert werden, dass sie auch für ein wiederkehrendes Kampagnenszenario funktionieren.</span><span class="sxs-lookup"><span data-stu-id="a7cac-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="a7cac-119">Identifizieren Sie Ihre Zielgruppe</span><span class="sxs-lookup"><span data-stu-id="a7cac-119">Identify your target audience</span></span>

<span data-ttu-id="a7cac-120">In unserem Szenario gehen wir davon aus, dass die E-Mail-Adressen der Kunden in Zielgruppen-Insights verfügbar sind und ihre Werbepräferenzen analysiert wurden, um Mitglieder des Segments zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="a7cac-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="a7cac-121">Das [Segment, das Sie in Zielgruppen-Insights definiert haben](segments.md) wird **ChurnProneCustomers** genannt und Sie planen, diesen Kunden die E-Mail-Aktion zu senden.</span><span class="sxs-lookup"><span data-stu-id="a7cac-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot der Segmentseite mit dem erstellten ChurnProneCustomers-Segment.":::

<span data-ttu-id="a7cac-123">Die Angebots-E-Mail, die Sie versenden möchten, enthält das Vorname, Nachname, und das Abonnement-Enddatum des Kunden.</span><span class="sxs-lookup"><span data-stu-id="a7cac-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="a7cac-124">Es informiert die Kunden über den Rabatt, den sie erhalten, wenn sie ihr Abonnement vor Ablauf verlängern.</span><span class="sxs-lookup"><span data-stu-id="a7cac-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="a7cac-125">Exportieren Sie Ihre Zielgruppe</span><span class="sxs-lookup"><span data-stu-id="a7cac-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="a7cac-126">Verbindung konfigurieren</span><span class="sxs-lookup"><span data-stu-id="a7cac-126">Configure a connection</span></span>

<span data-ttu-id="a7cac-127">Nachdem unsere Zielgruppe identifiziert wurde, können wir den Export von Zielgruppen-Insights in ein Azure Blob-Speicherkonto konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a7cac-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="a7cac-128">Gehen Sie in Zielgruppenerkenntnissen zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="a7cac-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a7cac-129">Wählen Sie **Verbindung hinzufügen** und dann **Adobe Campaign** aus, um die Verbindung zu konfigurieren, oder wählen Sie **Einrichten** in der Kachel **Adobe Campaign** aus.</span><span class="sxs-lookup"><span data-stu-id="a7cac-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigurationskachel für Adobe Campaign Standard.":::

1. <span data-ttu-id="a7cac-131">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="a7cac-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a7cac-132">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="a7cac-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a7cac-133">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="a7cac-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a7cac-134">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="a7cac-134">Choose who can use this connection.</span></span> <span data-ttu-id="a7cac-135">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="a7cac-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a7cac-136">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a7cac-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a7cac-137">Geben Sie die **Kontobezeichnung**, **Kontoschlüssel** und **Container** des Azure Blob Storage-Kontos ein, in das Sie das Segment exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a7cac-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot der Speicherkontokonfiguration. "::: 

   - <span data-ttu-id="a7cac-139">Weitere Informationen zum Suchen des Azure-Blob Storage Kontonamen und des Kontoschlüssels finden Sie unter [Verwalten von Speicherkontoeinstellungen im Azure-Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="a7cac-139">To learn more about how to find the Azure Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="a7cac-140">Informationen zum Erstellen eines Containers finden Sie unter [Erstellen eines Containers](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="a7cac-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="a7cac-141">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="a7cac-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="a7cac-142">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="a7cac-142">Configure an export</span></span>

<span data-ttu-id="a7cac-143">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="a7cac-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a7cac-144">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a7cac-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a7cac-145">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="a7cac-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a7cac-146">Um einen neuen Export zu erstellen, wählen Sie **Export hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="a7cac-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="a7cac-147">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Adobe Campaign-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="a7cac-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="a7cac-148">Wenn dieser Abschnittsname nicht angezeigt wird, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a7cac-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="a7cac-149">Wählen Sie die Segmente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a7cac-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="a7cac-150">In diesem Beispiel ist es **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="a7cac-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot der Benutzeroberfläche für die Segmentauswahl mit ausgewähltem ChurnProneCustomers-Segment.":::

1. <span data-ttu-id="a7cac-152">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a7cac-152">Select **Next**.</span></span>

1. <span data-ttu-id="a7cac-153">Jetzt kartieren wir die **Quelle**-Felder aus dem Segment Zielgruppen-Insights bis zu den **Ziel**-Feldnamen im Adobe Campaign Standard-Profilschema.</span><span class="sxs-lookup"><span data-stu-id="a7cac-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Feldzuordnung für den Adobe Campaign Standard-Connector.":::

   <span data-ttu-id="a7cac-155">Wenn Sie weitere Attribute hinzufügen möchten, wählen Sie **Attribut hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a7cac-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="a7cac-156">Der Zielname kann sich vom Namen des Quellfelds unterscheiden, sodass Sie die Segmentausgabe von Zielgruppen-Insights weiterhin Adobe Campaign Standard zuordnen können, wenn die Felder in beiden Systemen nicht denselben Namen haben.</span><span class="sxs-lookup"><span data-stu-id="a7cac-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a7cac-157">Die E-Mail-Adresse wird als Identitätsfeld verwendet. Sie können jedoch jede andere Kennung aus Ihrem Kundenprofil für Zielgruppen-Insights verwenden, um Daten Adobe Campaign Standard zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="a7cac-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="a7cac-158">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="a7cac-158">Select **Save**.</span></span>

<span data-ttu-id="a7cac-159">Nachdem Sie das Exportziel gespeichert haben, finden Sie in **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="a7cac-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="a7cac-160">Sie können jetzt [das Segment nach Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a7cac-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="a7cac-161">Der Export wird auch bei jeder [geplanten Aktualisierung](system.md) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="a7cac-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a7cac-162">Stellen Sie sicher, dass die Anzahl der Datensätze im exportierten Segment innerhalb des zulässigen Grenzwerts Ihrer Adobe Campaign Standard-Lizenz liegt.</span><span class="sxs-lookup"><span data-stu-id="a7cac-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="a7cac-163">Exportierte Daten werden in dem oben konfigurierten Azure Blob Storage Container gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a7cac-163">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="a7cac-164">Der folgende Ordnerpfad wird automatisch in Ihrem Container erstellt:</span><span class="sxs-lookup"><span data-stu-id="a7cac-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="a7cac-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="a7cac-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="a7cac-166">Beispiel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="a7cac-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="a7cac-167">Adobe Campaign Standard konfigurieren</span><span class="sxs-lookup"><span data-stu-id="a7cac-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="a7cac-168">Wenn ein Segment aus Zielgruppen-Insights exportiert wird, enthält es die Spalten, die Sie beim Definieren des Exportziels im vorherigen Schritt ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a7cac-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="a7cac-169">Diese Daten können verwendet werden, um [Profile in Adobe Campaign Standard zu erstellen](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="a7cac-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="a7cac-170">Um das Segment in Adobe Campaign Standard zu verwenden, müssen Sie das Profilschema in Adobe Campaign Standard um zwei zusätzliche Felder erweitern.</span><span class="sxs-lookup"><span data-stu-id="a7cac-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="a7cac-171">Lernen wie man [die Profilressource erweitert](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) mit neuen Feldern in Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="a7cac-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="a7cac-172">In unserem Beispiel sind diese Felder *Segmentname und Segmentdatum (optional)*.</span><span class="sxs-lookup"><span data-stu-id="a7cac-172">In our example, these fields are *Segment Name and Segment Date (optional)*.</span></span>

<span data-ttu-id="a7cac-173">Wir werden diese Felder verwenden, um die Profile in Adobe Campaign Standard zu identifizieren, auf die wir für diese Kampagne abzielen möchten.</span><span class="sxs-lookup"><span data-stu-id="a7cac-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="a7cac-174">Wenn in Adobe Campaign Standard keine anderen Datensätze als die zu importierenden vorhanden sind, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="a7cac-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="a7cac-175">Daten in Adobe Campaign Standard importieren</span><span class="sxs-lookup"><span data-stu-id="a7cac-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="a7cac-176">Nachdem alles vorhanden ist, müssen wir die vorbereiteten Zielgruppen-Daten aus Zielgruppen-Insights in Adobe Campaign Standard importieren, um Profile zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a7cac-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="a7cac-177">Lernen Sie, [wie Sie Profile in Adobe Campaign Standard importieren](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) mihilfe eines Workflows.</span><span class="sxs-lookup"><span data-stu-id="a7cac-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="a7cac-178">Der Importworkflow in der Abbildung unten wurde so konfiguriert, dass er alle acht Stunden ausgeführt wird und nach exportierten Zielgruppenerkenntnis-Segmenten (.csv-Datei in Azure Blob Storage) sucht.</span><span class="sxs-lookup"><span data-stu-id="a7cac-178">The import workflow in the image below has been configured to run every eight hours and look for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="a7cac-179">Der Workflow extrahiert den Inhalt der CSV-Datei in einer angegebenen Spaltenreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="a7cac-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="a7cac-180">Dieser Workflow wurde entwickelt, um eine grundlegende Fehlerbehandlung durchzuführen und sicherzustellen, dass jeder Datensatz eine E-Mail-Adresse hat, bevor die Daten in Adobe Campaign Standard hydratisiert werden.</span><span class="sxs-lookup"><span data-stu-id="a7cac-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="a7cac-181">Der Workflow extrahiert außerdem den Segmentnamen aus dem Dateinamen, bevor er in die Profildaten von Adobe Campaign Standard übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="a7cac-181">The workflow also extracts the segment name from the filename before upserting into Adobe Campaign Standard profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Screenshot eines Import-Workflows in der Benutzeroberfläche von Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="a7cac-183">Rufen Sie die Zielgruppe in Adobe Campaign Standard ab</span><span class="sxs-lookup"><span data-stu-id="a7cac-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="a7cac-184">Sobald die Daten in Adobe Campaign Standard importiert wurden, [können Sie einen Workflow erstellen](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) und Kunden [abfragen](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) basierend auf dem *Segmentname* und *Segmentdatum* um Profile auszuwählen, die für unsere Beispielkampagne identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="a7cac-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="a7cac-185">Erstellen und senden Sie die E-Mail mit Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="a7cac-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="a7cac-186">Erstellen Sie den E-Mail-Inhalt und dann [testen und senden](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) Sie Ihre E-Mail.</span><span class="sxs-lookup"><span data-stu-id="a7cac-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Beispiel-E-Mail mit Verlängerungsangebot von Adobe Campaign Standard.":::
