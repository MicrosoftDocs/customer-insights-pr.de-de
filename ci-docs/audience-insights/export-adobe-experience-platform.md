---
title: Customer Insights-Daten in Adobe Experience Platform exportieren
description: Erfahren Sie, wie Sie Zielgruppen-Insights-Segmente in Adobe Experience Platform verwenden.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760100"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="33bfe-103">Customer Insights-Segmente in Adobe Experience Platform verwenden (Verwenden)</span><span class="sxs-lookup"><span data-stu-id="33bfe-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="33bfe-104">Als Benutzer von Zielgruppen-Insights für Dynamics 365 Customer Insights haben Sie möglicherweise Segmente erstellt, um Ihre Marketingkampagnen effizienter zu gestalten, indem Sie relevante Zielgruppen ansprechen.</span><span class="sxs-lookup"><span data-stu-id="33bfe-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="33bfe-105">Um ein Segment aus Zielgruppen-Insights in Adobe Experience Platform und Anwendungen wie Adobe Campaign Standard zu verwenden, müssen Sie einige in diesem Artikel beschriebene Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="33bfe-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Prozessdiagramm der in diesem Artikel beschriebenen Schritte.":::

## <a name="prerequisites"></a><span data-ttu-id="33bfe-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="33bfe-107">Prerequisites</span></span>

-   <span data-ttu-id="33bfe-108">Dynamics 365 Customer Insights-Lizenz</span><span class="sxs-lookup"><span data-stu-id="33bfe-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="33bfe-109">Adobe Experience Platform-Lizenz</span><span class="sxs-lookup"><span data-stu-id="33bfe-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="33bfe-110">Adobe Campaign Standard-Lizenz</span><span class="sxs-lookup"><span data-stu-id="33bfe-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="33bfe-111">Azure Blob Storage-Konto</span><span class="sxs-lookup"><span data-stu-id="33bfe-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="33bfe-112">Kampagnenübersicht</span><span class="sxs-lookup"><span data-stu-id="33bfe-112">Campaign Overview</span></span>

<span data-ttu-id="33bfe-113">Schauen wir uns eine fiktive Beispielkampagne an, um besser zu verstehen, wie Sie Segmente aus Zielgruppen-Insights in Adobe Experience Platform verwenden können.</span><span class="sxs-lookup"><span data-stu-id="33bfe-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="33bfe-114">Nehmen wir an, Ihr Unternehmen bietet Ihren Kunden in den USA einen monatlichen, abonnementbasierten Service an.</span><span class="sxs-lookup"><span data-stu-id="33bfe-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="33bfe-115">Sie möchten Kunden identifizieren, deren Abonnements in den Nächsten acht Tagen erneuert werden sollen, deren Abonnement jedoch noch nicht verlängert wurde.</span><span class="sxs-lookup"><span data-stu-id="33bfe-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="33bfe-116">Um diese Kunden zu halten, möchten Sie ihnen mithilfe von Adobe Experience Platform ein Werbeangebot per E-Mail senden.</span><span class="sxs-lookup"><span data-stu-id="33bfe-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="33bfe-117">In diesem Beispiel möchten wir die Werbe-E-Mail-Kampagne einmal ausführen.</span><span class="sxs-lookup"><span data-stu-id="33bfe-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="33bfe-118">Dieser Artikel behandelt nicht den Anwendungsfall, die Kampagne mehr als einmal auszuführen.</span><span class="sxs-lookup"><span data-stu-id="33bfe-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="33bfe-119">Identifizieren Sie Ihre Zielgruppe</span><span class="sxs-lookup"><span data-stu-id="33bfe-119">Identify your target audience</span></span>

<span data-ttu-id="33bfe-120">In unserem Szenario gehen wir davon aus, dass die E-Mail-Adressen der Kunden in Zielgruppen-Insights verfügbar sind und ihre Werbepräferenzen analysiert wurden, um Mitglieder des Segments zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="33bfe-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="33bfe-121">Das [Segment, das Sie in Zielgruppen-Insights definiert haben](segments.md) wird **ChurnProneCustomers** genannt und Sie planen, diesen Kunden die E-Mail-Aktion zu senden.</span><span class="sxs-lookup"><span data-stu-id="33bfe-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot der Segmentseite mit dem erstellten ChurnProneCustomers-Segment.":::

<span data-ttu-id="33bfe-123">Die Angebots-E-Mail, die Sie versenden möchten, enthält das Vorname, Nachname, und das Abonnement-Enddatum des Kunden.</span><span class="sxs-lookup"><span data-stu-id="33bfe-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="33bfe-124">Es informiert die Kunden über den Rabatt, den sie erhalten, wenn sie ihr Abonnement vor Ablauf verlängern.</span><span class="sxs-lookup"><span data-stu-id="33bfe-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="33bfe-125">Exportieren Sie Ihre Zielgruppe</span><span class="sxs-lookup"><span data-stu-id="33bfe-125">Export your target audience</span></span>

<span data-ttu-id="33bfe-126">Nachdem unsere Zielgruppe identifiziert wurde, können wir den Export von Zielgruppen-Insights in ein Azure Blob-Speicherkonto konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="33bfe-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="33bfe-127">Verbindung konfigurieren</span><span class="sxs-lookup"><span data-stu-id="33bfe-127">Configure a connection</span></span>

1. <span data-ttu-id="33bfe-128">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="33bfe-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="33bfe-129">Wählen Sie **Verbindung hinzufügen** und dann **Azure Blob Storage**, oder wählen Sie **Einrichten** auf der Kachel **Azure Blob Storage**:</span><span class="sxs-lookup"><span data-stu-id="33bfe-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile:</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfigurationskachel für Azure Blob-Speicher."::: <span data-ttu-id="33bfe-131">um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="33bfe-131">to configure the connection.</span></span>

1. <span data-ttu-id="33bfe-132">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="33bfe-132">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="33bfe-133">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="33bfe-133">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="33bfe-134">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="33bfe-134">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="33bfe-135">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="33bfe-135">Choose who can use this connection.</span></span> <span data-ttu-id="33bfe-136">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="33bfe-136">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="33bfe-137">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="33bfe-137">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="33bfe-138">Geben Sie die **Kontobezeichnung**, **Kontoschlüssel** und **Container** des Azure Blob Storage-Kontos ein, in das Sie das Segment exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="33bfe-138">Enter **Account name**, **Account key**, and **Container** for your Blob storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot der Speicherkontokonfiguration. "::: 
   
    - <span data-ttu-id="33bfe-140">Weitere Informationen zum Ermitteln des Blob Storage-Kontonamens und des Kontoschlüssels finden Sie unter [Verwalten Sie die Speicherkontoeinstellungen im Azure-Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="33bfe-140">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="33bfe-141">Informationen zum Erstellen eines Containers finden Sie unter [Erstellen eines Containers](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="33bfe-141">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="33bfe-142">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="33bfe-142">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="33bfe-143">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="33bfe-143">Configure an export</span></span>

<span data-ttu-id="33bfe-144">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="33bfe-144">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="33bfe-145">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="33bfe-145">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="33bfe-146">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="33bfe-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="33bfe-147">Um einen neuen Export zu erstellen, wählen Sie **Export hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="33bfe-147">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="33bfe-148">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Azure Blob Storage-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="33bfe-148">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="33bfe-149">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="33bfe-149">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="33bfe-150">Wählen Sie die Segmente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="33bfe-150">Choose the segment that you want to export.</span></span> <span data-ttu-id="33bfe-151">In diesem Beispiel ist es **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="33bfe-151">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot der Benutzeroberfläche für die Segmentauswahl mit ausgewähltem ChurnProneCustomers-Segment.":::

1. <span data-ttu-id="33bfe-153">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="33bfe-153">Select **Save**.</span></span>

<span data-ttu-id="33bfe-154">Nachdem Sie das Exportziel gespeichert haben, finden Sie in **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="33bfe-154">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="33bfe-155">Sie können jetzt [das Segment nach Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="33bfe-155">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="33bfe-156">Der Export wird auch bei jeder [geplanten Aktualisierung](system.md) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="33bfe-156">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="33bfe-157">Stellen Sie sicher, dass die Anzahl der Datensätze im exportierten Segment innerhalb des zulässigen Grenzwerts Ihrer Adobe Campaign Standard-Lizenz liegt.</span><span class="sxs-lookup"><span data-stu-id="33bfe-157">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="33bfe-158">Exportierte Daten werden in dem oben konfigurierten Azure Blob-Speichercontainer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="33bfe-158">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="33bfe-159">Der folgende Ordnerpfad wird automatisch in Ihrem Container erstellt:</span><span class="sxs-lookup"><span data-stu-id="33bfe-159">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="33bfe-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="33bfe-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="33bfe-161">Beispiel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="33bfe-161">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="33bfe-162">Das *model.json* für die exportierten Entitäten befindet sich auf der *%ExportDestinationName%*-Ebene.</span><span class="sxs-lookup"><span data-stu-id="33bfe-162">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="33bfe-163">Beispiel Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="33bfe-163">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="33bfe-164">Definieren Sie das Experience Data Model (XDM) in Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="33bfe-164">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="33bfe-165">Bevor die aus Zielgruppe-Insights exportierten Daten in Adobe Experience Platform verwendet werden können, müssen Sie das Experience Data Model-Schema definieren und [die Daten für das Echtzeit-Kundenprofil konfigurieren](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="33bfe-165">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="33bfe-166">Lernen Sie, [was XDM ist](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) und verstehen Sie die [Grundlagen der Schemakomposition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="33bfe-166">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="33bfe-167">Importieren Sie Daten in die Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="33bfe-167">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="33bfe-168">Nachdem alles vorhanden ist, müssen wir die vorbereiteten Zielgruppen-Daten aus Zielgruppen-Insights in Adobe Experience Platform importieren, um Profile zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="33bfe-168">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="33bfe-169">Zuerst, [erstellen Sie eine Azure Blob Storage-Quellverbindung](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="33bfe-169">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="33bfe-170">Nachdem Sie die Quellverbindung definiert haben, [konfigurieren Sie einen Dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) für eine Cloud-Speicher-Batch-Verbindung zum Importieren der Segmentausgabe von Zielgruppen-Insights in Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="33bfe-170">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="33bfe-171">Erstellen Sie eine Zielgruppe in Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="33bfe-171">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="33bfe-172">Um die E-Mail für diese Kampagne zu senden, verwenden wir Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="33bfe-172">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="33bfe-173">Nach dem Importieren der Daten in Adobe Experience Platform müssen wir [eine Zielgruppe erstellen](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard unter Verwendung der Daten in Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="33bfe-173">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="33bfe-174">Lernen wie man, [den Segment Builder verwendet](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard, um ein Publikum basierend auf den Daten in Adobe Experience Platform zu definieren.</span><span class="sxs-lookup"><span data-stu-id="33bfe-174">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="33bfe-175">Erstellen und senden Sie die E-Mail mit Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="33bfe-175">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="33bfe-176">Erstellen Sie den E-Mail-Inhalt und dann [testen und senden](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) Sie Ihre E-Mail.</span><span class="sxs-lookup"><span data-stu-id="33bfe-176">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Beispiel-E-Mail mit Verlängerungsangebot von Adobe Campaign Standard.":::
