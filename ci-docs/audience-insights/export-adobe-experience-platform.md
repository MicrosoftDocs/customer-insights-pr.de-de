---
title: Customer Insights-Daten in Adobe Experience Platform exportieren
description: Erfahren Sie, wie Sie Zielgruppen-Einblick-Segmente in der Adobe Experience Platform verwenden.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305523"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="3d838-103">Customer Insights-Segmente in Adobe Experience Platform verwenden (Verwenden)</span><span class="sxs-lookup"><span data-stu-id="3d838-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="3d838-104">Als Nutzer von Zielgruppeneinblicken in Dynamics 365 Customer Insights haben Sie möglicherweise Segmente erstellt, um Ihre Marketingkampagnen durch die Ausrichtung auf relevante Zielgruppen effizienter zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="3d838-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="3d838-105">Um ein Segment aus Zielgruppen-Insights in Adobe Experience Platform und Anwendungen wie Adobe Campaign Standard zu verwenden, müssen Sie einige in diesem Artikel beschriebene Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="3d838-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Prozessdiagramm der in diesem Artikel beschriebenen Schritte.":::

## <a name="prerequisites"></a><span data-ttu-id="3d838-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3d838-107">Prerequisites</span></span>

-   <span data-ttu-id="3d838-108">Dynamics 365 Customer Insights-Lizenz</span><span class="sxs-lookup"><span data-stu-id="3d838-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="3d838-109">Adobe Experience Platform-Lizenz</span><span class="sxs-lookup"><span data-stu-id="3d838-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="3d838-110">Adobe Campaign Standard-Lizenz</span><span class="sxs-lookup"><span data-stu-id="3d838-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="3d838-111">Azure Blob Storage-Konto</span><span class="sxs-lookup"><span data-stu-id="3d838-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="3d838-112">Kampagnenübersicht</span><span class="sxs-lookup"><span data-stu-id="3d838-112">Campaign Overview</span></span>

<span data-ttu-id="3d838-113">Schauen wir uns eine fiktive Beispielkampagne an, um besser zu verstehen, wie Sie Segmente aus Zielgruppen-Insights in Adobe Experience Platform verwenden können.</span><span class="sxs-lookup"><span data-stu-id="3d838-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="3d838-114">Nehmen wir an, Ihr Unternehmen bietet Ihren Kunden in den USA einen monatlichen, abonnementbasierten Service an.</span><span class="sxs-lookup"><span data-stu-id="3d838-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="3d838-115">Sie möchten Kunden identifizieren, deren Abonnements in den Nächsten acht Tagen erneuert werden sollen, deren Abonnement jedoch noch nicht verlängert wurde.</span><span class="sxs-lookup"><span data-stu-id="3d838-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="3d838-116">Um diese Kunden zu halten, möchten Sie ihnen mithilfe von Adobe Experience Platform ein Werbeangebot per E-Mail senden.</span><span class="sxs-lookup"><span data-stu-id="3d838-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="3d838-117">In diesem Beispiel möchten wir die Werbe-E-Mail-Kampagne einmal ausführen.</span><span class="sxs-lookup"><span data-stu-id="3d838-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="3d838-118">Dieser Artikel behandelt nicht den Anwendungsfall, die Kampagne mehr als einmal auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3d838-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="3d838-119">Identifizieren Sie Ihre Zielgruppe</span><span class="sxs-lookup"><span data-stu-id="3d838-119">Identify your target audience</span></span>

<span data-ttu-id="3d838-120">In unserem Szenario gehen wir davon aus, dass die E-Mail-Adressen der Kunden in Zielgruppen-Insights verfügbar sind und ihre Werbepräferenzen analysiert wurden, um Mitglieder des Segments zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="3d838-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="3d838-121">Das [Segment, das Sie in Zielgruppen-Insights definiert haben](segments.md) wird **ChurnProneCustomers** genannt und Sie planen, diesen Kunden die E-Mail-Aktion zu senden.</span><span class="sxs-lookup"><span data-stu-id="3d838-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot der Segmentseite mit dem erstellten ChurnProneCustomers-Segment.":::

<span data-ttu-id="3d838-123">Die Angebots-E-Mail, die Sie versenden möchten, enthält das Vorname, Nachname, und das Abonnement-Enddatum des Kunden.</span><span class="sxs-lookup"><span data-stu-id="3d838-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="3d838-124">Es informiert die Kunden über den Rabatt, den sie erhalten, wenn sie ihr Abonnement vor Ablauf verlängern.</span><span class="sxs-lookup"><span data-stu-id="3d838-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="3d838-125">Exportieren Sie Ihre Zielgruppe</span><span class="sxs-lookup"><span data-stu-id="3d838-125">Export your target audience</span></span>

<span data-ttu-id="3d838-126">Nachdem unsere Zielgruppe identifiziert wurde, können wir den Export von Zielgruppen-Insights in ein Azure Blob-Speicherkonto konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3d838-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="3d838-127">Verbindung konfigurieren</span><span class="sxs-lookup"><span data-stu-id="3d838-127">Configure a connection</span></span>

1. <span data-ttu-id="3d838-128">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="3d838-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="3d838-129">Wählen Sie **Verbindung hinzufügen** und wählen Sie **Azure Blob Storage** oder wählen Sie **Einrichten** in der Kachel **Azure Blob Storage**, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3d838-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile to configure the connection.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfigurationskachel für Azure Blob-Speicher."::: 

1. <span data-ttu-id="3d838-131">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="3d838-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="3d838-132">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="3d838-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="3d838-133">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="3d838-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="3d838-134">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="3d838-134">Choose who can use this connection.</span></span> <span data-ttu-id="3d838-135">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="3d838-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="3d838-136">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="3d838-136">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="3d838-137">Geben Sie die **Kontobezeichnung**, **Kontoschlüssel** und **Container** für Ihr Blob Storage-Konto ein, in das Sie das Segment exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="3d838-137">Enter **Account name**, **Account key**, and **Container** for your Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot der Speicherkontokonfiguration. "::: 
   
    - <span data-ttu-id="3d838-139">Weitere Informationen zum Ermitteln des Blob Storage Kontonamens und des Kontoschlüssels finden Sie unter [Verwalten Sie die Speicherkontoeinstellungen im Azure-Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="3d838-139">To learn more about how to find the Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="3d838-140">Informationen zum Erstellen eines Containers finden Sie unter [Erstellen eines Containers](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="3d838-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="3d838-141">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="3d838-141">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="3d838-142">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="3d838-142">Configure an export</span></span>

<span data-ttu-id="3d838-143">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="3d838-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="3d838-144">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="3d838-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3d838-145">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="3d838-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3d838-146">Um einen neuen Export zu erstellen, wählen Sie **Export hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="3d838-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="3d838-147">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Azure Blob Storage-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="3d838-147">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="3d838-148">Wenn dieser Abschnittsname nicht angezeigt wird, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3d838-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="3d838-149">Wählen Sie die Segmente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="3d838-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="3d838-150">In diesem Beispiel ist es **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="3d838-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot der Benutzeroberfläche für die Segmentauswahl mit ausgewähltem ChurnProneCustomers-Segment.":::

1. <span data-ttu-id="3d838-152">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="3d838-152">Select **Save**.</span></span>

<span data-ttu-id="3d838-153">Nachdem Sie das Exportziel gespeichert haben, finden Sie in **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="3d838-153">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="3d838-154">Sie können jetzt [das Segment nach Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="3d838-154">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="3d838-155">Der Export wird auch bei jeder [geplanten Aktualisierung](system.md) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="3d838-155">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3d838-156">Stellen Sie sicher, dass die Anzahl der Datensätze im exportierten Segment innerhalb des zulässigen Grenzwerts Ihrer Adobe Campaign Standard-Lizenz liegt.</span><span class="sxs-lookup"><span data-stu-id="3d838-156">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="3d838-157">Exportierte Daten werden in dem oben konfigurierten Azure Blob Storage Container gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3d838-157">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="3d838-158">Der folgende Ordnerpfad wird automatisch in Ihrem Container erstellt:</span><span class="sxs-lookup"><span data-stu-id="3d838-158">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="3d838-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="3d838-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="3d838-160">Beispiel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="3d838-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="3d838-161">Das *model.json* für die exportierten Entitäten befindet sich auf der *%ExportDestinationName%*-Ebene.</span><span class="sxs-lookup"><span data-stu-id="3d838-161">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="3d838-162">Beispiel Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="3d838-162">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="3d838-163">Definieren Sie das Experience Data Model (XDM) in Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="3d838-163">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="3d838-164">Bevor die aus Zielgruppe-Insights exportierten Daten in Adobe Experience Platform verwendet werden können, müssen Sie das Experience Data Model-Schema definieren und [die Daten für das Echtzeit-Kundenprofil konfigurieren](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="3d838-164">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="3d838-165">Lernen Sie, [was XDM ist](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) und verstehen Sie die [Grundlagen der Schemakomposition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="3d838-165">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="3d838-166">Importieren Sie Daten in die Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="3d838-166">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="3d838-167">Nachdem alles vorhanden ist, müssen wir die vorbereiteten Zielgruppen-Daten aus Zielgruppen-Insights in Adobe Experience Platform importieren, um Profile zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3d838-167">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="3d838-168">Zuerst, [erstellen Sie eine Azure Blob Storage-Quellverbindung](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="3d838-168">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="3d838-169">Nachdem Sie die Quellverbindung definiert haben, [konfigurieren Sie einen Dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) für eine Cloud-Speicher-Batch-Verbindung zum Importieren der Segmentausgabe von Zielgruppen-Insights in Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="3d838-169">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="3d838-170">Erstellen Sie eine Zielgruppe in Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="3d838-170">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="3d838-171">Zum Senden der E-Mail für diese Kampagne verwenden wir Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="3d838-171">To send the email for this campaign, we'll use Adobe Campaign Standard.</span></span> <span data-ttu-id="3d838-172">Nach dem Importieren der Daten in Adobe Experience Platform müssen wir [eine Zielgruppe erstellen](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard unter Verwendung der Daten in Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="3d838-172">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>


<span data-ttu-id="3d838-173">Lernen wie man, [den Segment Builder verwendet](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard, um ein Publikum basierend auf den Daten in Adobe Experience Platform zu definieren.</span><span class="sxs-lookup"><span data-stu-id="3d838-173">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="3d838-174">Erstellen und senden Sie die E-Mail mit Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="3d838-174">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="3d838-175">Erstellen Sie den E-Mail-Inhalt und dann [testen und senden](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) Sie Ihre E-Mail.</span><span class="sxs-lookup"><span data-stu-id="3d838-175">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Beispiel-E-Mail mit Verlängerungsangebot von Adobe Campaign Standard.":::
