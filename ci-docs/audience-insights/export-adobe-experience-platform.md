---
title: Customer Insights-Daten in Adobe Experience Platform exportieren
description: Erfahren Sie, wie Sie Zielgruppen-Insights-Segmente in Adobe Experience Platform verwenden.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596268"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="d1f3d-103">Customer Insights-Segmente in Adobe Experience Platform verwenden (Verwenden)</span><span class="sxs-lookup"><span data-stu-id="d1f3d-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="d1f3d-104">Als Benutzer von Zielgruppen-Insights für Dynamics 365 Customer Insights haben Sie möglicherweise Segmente erstellt, um Ihre Marketingkampagnen effizienter zu gestalten, indem Sie relevante Zielgruppen ansprechen.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="d1f3d-105">Um ein Segment aus Zielgruppen-Insights in Adobe Experience Platform und Anwendungen wie Adobe Campaign Standard zu verwenden, müssen Sie einige in diesem Artikel beschriebene Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Prozessdiagramm der in diesem Artikel beschriebenen Schritte.":::

## <a name="prerequisites"></a><span data-ttu-id="d1f3d-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d1f3d-107">Prerequisites</span></span>

-   <span data-ttu-id="d1f3d-108">Dynamics 365 Customer Insights-Lizenz</span><span class="sxs-lookup"><span data-stu-id="d1f3d-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="d1f3d-109">Adobe Experience Platform-Lizenz</span><span class="sxs-lookup"><span data-stu-id="d1f3d-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="d1f3d-110">Adobe Campaign Standard-Lizenz</span><span class="sxs-lookup"><span data-stu-id="d1f3d-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="d1f3d-111">Azure Blob Storage-Konto</span><span class="sxs-lookup"><span data-stu-id="d1f3d-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="d1f3d-112">Kampagnenübersicht</span><span class="sxs-lookup"><span data-stu-id="d1f3d-112">Campaign Overview</span></span>

<span data-ttu-id="d1f3d-113">Schauen wir uns eine fiktive Beispielkampagne an, um besser zu verstehen, wie Sie Segmente aus Zielgruppen-Insights in Adobe Experience Platform verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="d1f3d-114">Nehmen wir an, Ihr Unternehmen bietet Ihren Kunden in den USA einen monatlichen, abonnementbasierten Service an.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="d1f3d-115">Sie möchten Kunden identifizieren, deren Abonnements in den Nächsten acht Tagen erneuert werden sollen, deren Abonnement jedoch noch nicht verlängert wurde.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="d1f3d-116">Um diese Kunden zu halten, möchten Sie ihnen mithilfe von Adobe Experience Platform ein Werbeangebot per E-Mail senden.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="d1f3d-117">In diesem Beispiel möchten wir die Werbe-E-Mail-Kampagne einmal ausführen.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="d1f3d-118">Dieser Artikel behandelt nicht den Anwendungsfall, die Kampagne mehr als einmal auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="d1f3d-119">Identifizieren Sie Ihre Zielgruppe</span><span class="sxs-lookup"><span data-stu-id="d1f3d-119">Identify your target audience</span></span>

<span data-ttu-id="d1f3d-120">In unserem Szenario gehen wir davon aus, dass die E-Mail-Adressen der Kunden in Zielgruppen-Insights verfügbar sind und ihre Werbepräferenzen analysiert wurden, um Mitglieder des Segments zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="d1f3d-121">Das [Segment, das Sie in Zielgruppen-Insights definiert haben](segments.md) wird **ChurnProneCustomers** genannt und Sie planen, diesen Kunden die E-Mail-Aktion zu senden.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot der Segmentseite mit dem erstellten ChurnProneCustomers-Segment.":::

<span data-ttu-id="d1f3d-123">Die Angebots-E-Mail, die Sie versenden möchten, enthält das Vorname, Nachname, und das Abonnement-Enddatum des Kunden.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="d1f3d-124">Es informiert die Kunden über den Rabatt, den sie erhalten, wenn sie ihr Abonnement vor Ablauf verlängern.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="d1f3d-125">Exportieren Sie Ihre Zielgruppe</span><span class="sxs-lookup"><span data-stu-id="d1f3d-125">Export your target audience</span></span>

<span data-ttu-id="d1f3d-126">Nachdem unsere Zielgruppe identifiziert wurde, können wir den Export von Zielgruppen-Insights in ein Azure Blob-Speicherkonto konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="d1f3d-127">Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Ziele exportieren**.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d1f3d-128">Wählen Sie in der Kachel **Azure Blob-Speicher** **Einrichten** aus.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfigurationskachel für Azure Blob-Speicher.":::

1. <span data-ttu-id="d1f3d-130">Geben Sie einen **Anzeigename** für dieses neue Exportziel ein und geben Sie dann **Kontoname**, **Kontoschlüssel**, und **Container** des Azure Blob-Speicherkontos ein, in das Sie das Segment exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot der Speicherkontokonfiguration. "::: 

   - <span data-ttu-id="d1f3d-132">Weitere Informationen zum Suchen des Azure-Blobspeicherkontonamens und des Kontoschlüssels finden Sie unter [Verwalten von Speicherkontoeinstellungen im Azure-Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="d1f3d-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="d1f3d-133">Informationen zum Erstellen eines Containers finden Sie unter [Erstellen eines Containers](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="d1f3d-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="d1f3d-134">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-134">Select **Next**.</span></span>

1. <span data-ttu-id="d1f3d-135">Wählen Sie die Segmente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="d1f3d-136">In diesem Beispiel ist es **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot der Benutzeroberfläche für die Segmentauswahl mit ausgewähltem ChurnProneCustomers-Segment.":::

1. <span data-ttu-id="d1f3d-138">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-138">Select **Save**.</span></span>

<span data-ttu-id="d1f3d-139">Nachdem Sie das Exportziel gespeichert haben, finden Sie es auf **Administrator** > **Exporte** > **Meine Exportziele**.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Screenshot mit hervorgehobener Exportliste und Beispielsegment.":::

<span data-ttu-id="d1f3d-141">Sie können jetzt [das Segment nach Bedarf exportieren](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d1f3d-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="d1f3d-142">Der Export wird auch bei jeder [geplanten Aktualisierung](system.md) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d1f3d-143">Stellen Sie sicher, dass die Anzahl der Datensätze im exportierten Segment innerhalb des zulässigen Grenzwerts Ihrer Adobe Campaign Standard-Lizenz liegt.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="d1f3d-144">Exportierte Daten werden in dem oben konfigurierten Azure Blob-Speichercontainer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="d1f3d-145">Der folgende Ordnerpfad wird automatisch in Ihrem Container erstellt:</span><span class="sxs-lookup"><span data-stu-id="d1f3d-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="d1f3d-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="d1f3d-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="d1f3d-147">Beispiel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="d1f3d-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="d1f3d-148">Das *model.json* für die exportierten Entitäten befindet sich auf der *%ExportDestinationName%*-Ebene.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="d1f3d-149">Beispiel Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="d1f3d-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="d1f3d-150">Definieren Sie das Experience Data Model (XDM) in Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="d1f3d-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="d1f3d-151">Bevor die aus Zielgruppe-Insights exportierten Daten in Adobe Experience Platform verwendet werden können, müssen Sie das Experience Data Model-Schema definieren und [die Daten für das Echtzeit-Kundenprofil konfigurieren](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="d1f3d-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="d1f3d-152">Lernen Sie, [was XDM ist](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) und verstehen Sie die [Grundlagen der Schemakomposition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="d1f3d-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="d1f3d-153">Importieren Sie Daten in die Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="d1f3d-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="d1f3d-154">Nachdem alles vorhanden ist, müssen wir die vorbereiteten Zielgruppen-Daten aus Zielgruppen-Insights in Adobe Experience Platform importieren, um Profile zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="d1f3d-155">Zuerst, [erstellen Sie eine Azure Blob Storage-Quellverbindung](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="d1f3d-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="d1f3d-156">Nachdem Sie die Quellverbindung definiert haben, [konfigurieren Sie einen Dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) für eine Cloud-Speicher-Batch-Verbindung zum Importieren der Segmentausgabe von Zielgruppen-Insights in Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="d1f3d-157">Erstellen Sie eine Zielgruppe in Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d1f3d-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="d1f3d-158">Um die E-Mail für diese Kampagne zu senden, verwenden wir Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="d1f3d-159">Nach dem Importieren der Daten in Adobe Experience Platform müssen wir [eine Zielgruppe erstellen](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard unter Verwendung der Daten in Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="d1f3d-160">Lernen wie man, [den Segment Builder verwendet](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard, um ein Publikum basierend auf den Daten in Adobe Experience Platform zu definieren.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="d1f3d-161">Erstellen und senden Sie die E-Mail mit Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d1f3d-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="d1f3d-162">Erstellen Sie den E-Mail-Inhalt und dann [testen und senden](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) Sie Ihre E-Mail.</span><span class="sxs-lookup"><span data-stu-id="d1f3d-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Beispiel-E-Mail mit Verlängerungsangebot von Adobe Campaign Standard.":::