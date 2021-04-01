---
title: Verbinden Sie Common Data Model-Daten mit einem Azure Data Lake-Konto
description: Arbeiten Sie mit Common Data Model-Daten unter Verwendung von Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 385406b706890d741fec2694c190c0fada7809d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596544"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="543f0-103">Verbinden Sie den Ordner Common Data Model mithilfe einem Azure Data Lake-Konto</span><span class="sxs-lookup"><span data-stu-id="543f0-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="543f0-104">Dieser Artikel informiert Sie darüber, wie Sie Daten aus einem Common Data Model-Ordner mit Ihrem Azure Data Lake Storage Gen2-Konto aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="543f0-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="543f0-105">Wichtige Überlegungen</span><span class="sxs-lookup"><span data-stu-id="543f0-105">Important considerations</span></span>

- <span data-ttu-id="543f0-106">Daten in Azure Data Lake müssen dem Common Data Model-Standard entsprechen.</span><span class="sxs-lookup"><span data-stu-id="543f0-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="543f0-107">Andere Formate werden derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="543f0-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="543f0-108">Die Datenerfassung unterstützt ausschließlich Azure Data Lake *Gen2* Speicherkonten.</span><span class="sxs-lookup"><span data-stu-id="543f0-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="543f0-109">Sie können keine Azure Data Lake Gen1-Speicherkonten für die Datenerfassung verwenden.</span><span class="sxs-lookup"><span data-stu-id="543f0-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="543f0-110">Um sich mit einem Azure Service Prinzipal zu authentifizieren, stellen Sie sicher, dass es in Ihrem Mandanten konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="543f0-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="543f0-111">Weitere Informationen finden Sie unter [Verbinden Sie Zielgruppen-Insights mit einem Azure Data Lake Storage Gen2-Konto mit einem Azure-Dienstprinzipal](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="543f0-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="543f0-112">Der Azure Data Lake, mit dem Sie sich verbinden und von dem Sie Daten aufnehmen möchten, muss sich in derselben Azure-Region befinden wie die Dynamics 365 Customer Insights-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="543f0-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="543f0-113">Verbindungen zu einem Common Data Model-Ordner aus einem Data Lake in einer anderen Azure-Region werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="543f0-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="543f0-114">Um die Azure-Region der Umgebung zu kennen, gehen Sie zu **Admin** > **System** > **Über** in Zielgruppen-Insights.</span><span class="sxs-lookup"><span data-stu-id="543f0-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="543f0-115">Daten, die in Online-Diensten gespeichert sind, können an einem anderen Ort gespeichert werden als dort, wo die Daten verarbeitet oder in Dynamics 365 Customer Insights gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="543f0-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="543f0-116"> Durch das Importieren von oder Verbinden mit Daten, die in Online-Diensten gespeichert sind, erklären Sie sich damit einverstanden, dass Daten an das Microsoft Trust Center übertragen und dort mit Dynamics 365 Customer Insights gespeichert werden können. [Lernen Sie mehr im Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="543f0-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="543f0-117">Mit einem „Common Data Model“-Ordner verbinden</span><span class="sxs-lookup"><span data-stu-id="543f0-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="543f0-118">Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.</span><span class="sxs-lookup"><span data-stu-id="543f0-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="543f0-119">Wählen Sie **Datenquelle hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="543f0-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="543f0-120">Wählen Sie **Verbinden mit einem gemeinsamen Datenmodell-Ordner**, geben Sie einen **Name** für die Datenquelle ein und wählen Sie **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="543f0-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="543f0-121">Namensrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="543f0-121">Name guidelines:</span></span> 
   - <span data-ttu-id="543f0-122">Beginnen Sie mit einem Buchstaben.</span><span class="sxs-lookup"><span data-stu-id="543f0-122">Start with a letter.</span></span>
   - <span data-ttu-id="543f0-123">Verwenden Sie nur Buchstaben und Zahlen.</span><span class="sxs-lookup"><span data-stu-id="543f0-123">Use letters and numbers only.</span></span> <span data-ttu-id="543f0-124">Leerzeichen und Sonderzeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="543f0-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="543f0-125">Verwenden Sie zwischen 3 und 64 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="543f0-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="543f0-126">Sie können zwischen einer ressourcenbasierten Option und einer abonnementbasierten Option für die Authentifizierung wählen.</span><span class="sxs-lookup"><span data-stu-id="543f0-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="543f0-127">Weitere Informationen finden Sie unter [Verbinden Sie Zielgruppen-Insights mit einem Azure Data Lake Storage Gen2-Konto mit einem Azure-Dienstprinzipal](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="543f0-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="543f0-128">Geben Sie die **Container**-Informationen ein und wählen Sie **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="543f0-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="543f0-129">![Dialogfeld zum Eingeben neuer Verbindungsdetails für Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="543f0-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="543f0-130">Sie benötigen eine der folgenden Rollen entweder für den Container oder das oben genannte Speicherkonto, um eine Verbindung zu einem Datenquelle herstellen und einen solchen erstellen zu können:</span><span class="sxs-lookup"><span data-stu-id="543f0-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="543f0-131">Speicher-Blob-Datenleser</span><span class="sxs-lookup"><span data-stu-id="543f0-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="543f0-132">Speicher-Blob-Datenbesitzer</span><span class="sxs-lookup"><span data-stu-id="543f0-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="543f0-133">Storage-Blob-Daten-Mitwirkender</span><span class="sxs-lookup"><span data-stu-id="543f0-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="543f0-134">Wählen Sie im Dialog **Wählen Sie einen gemeinsamen Datenmodell-Ordner** die Datei manifest.json aus, aus der Daten importiert werden sollen, und wählen Sie **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="543f0-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="543f0-135">Jede model.json- oder manifest.json-Datei, die mit einer anderen Datenquelle in der Umgebung verbunden ist, wird nicht in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="543f0-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="543f0-136">Sie erhalten eine Liste der verfügbaren Entitäten in der ausgewählten model.json- oder manifest.json-Datei.</span><span class="sxs-lookup"><span data-stu-id="543f0-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="543f0-137">Sie können aus der Liste der verfügbaren Entitäten prüfen und auswählen und **Speichern** wählen.</span><span class="sxs-lookup"><span data-stu-id="543f0-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="543f0-138">Alle ausgewählten Entitäten werden von der neuen Datenquelle aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="543f0-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="543f0-139">![Dialogfeld mit einer Liste von Entitäten aus einer model.json-Datei](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="543f0-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="543f0-140">Geben Sie an, für welche Entitäten Sie die Datenprofilierung aktivieren möchten, und wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="543f0-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="543f0-141">Die Datenprofilerstellung ermöglicht Analysen und andere Funktionen.</span><span class="sxs-lookup"><span data-stu-id="543f0-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="543f0-142">Sie können die gesamte Entität auswählen, wodurch alle Attribute der Entität ausgewählt werden, oder Sie können bestimmte Attribute Ihrer Wahl auswählen.</span><span class="sxs-lookup"><span data-stu-id="543f0-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="543f0-143">Standardmäßig ist keine Entität für die Datenprofilierung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="543f0-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="543f0-144">![Dialogfeld, das eine Datenprofilierung zeigt](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="543f0-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="543f0-145">Nachdem Sie Ihre Auswahl gespeichert haben, wird die Seite **Datenquellen** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="543f0-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="543f0-146">Sie sollten nun die Ordnerverbindung Common Data Model als Datenquelle sehen.</span><span class="sxs-lookup"><span data-stu-id="543f0-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="543f0-147">Eine model.json- oder manifest.json-Datei kann nur mit einer Datenquelle in derselben Umgebung verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="543f0-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="543f0-148">Allerdings kann dieselbe model.json- oder manifest.json-Datei für Datenquellen in mehreren Umgebungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="543f0-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="543f0-149">Bearbeiten eines allgemeinen Datenmodellordners Datenquelle</span><span class="sxs-lookup"><span data-stu-id="543f0-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="543f0-150">Sie können den Zugriffsschlüssel für das Speicherkonto aktualisieren, das den Ordner Common Data Model enthält.</span><span class="sxs-lookup"><span data-stu-id="543f0-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="543f0-151">Sie können auch die model.json- oder manifest.json-Datei ändern.</span><span class="sxs-lookup"><span data-stu-id="543f0-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="543f0-152">Um eine Verbindung zu einem anderen Container als Ihrem Speicherkonto herzustellen oder den Kontonamen zu ändern, [erstellen Sie eine neue Datenquellenverbindung](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="543f0-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="543f0-153">Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.</span><span class="sxs-lookup"><span data-stu-id="543f0-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="543f0-154">Wählen Sie neben der Datenquelle, die Sie aktualisieren möchten, die Auslassungspunkte aus.</span><span class="sxs-lookup"><span data-stu-id="543f0-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="543f0-155">Wählen Sie eine Option **Bearbeiten** in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="543f0-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="543f0-156">Aktualisieren Sie optional den **Zugriffsschlüssel** und wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="543f0-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Dialog, um einen Zugriffsschlüssel für eine vorhandene Datenquelle zu bearbeiten und zu aktualisieren](media/edit-access-key.png)

5. <span data-ttu-id="543f0-158">Optional können Sie von einer Kontoschlüssel-Verbindung zu einer ressourcenbasierten oder abonnementbasierten Verbindung aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="543f0-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="543f0-159">Weitere Informationen finden Sie unter [Verbinden Sie Zielgruppen-Insights mit einem Azure Data Lake Storage Gen2-Konto mit einem Azure-Dienstprinzipal](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="543f0-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="543f0-160">Sie können die **Container**-Informationen beim Aktualisieren der Verbindung nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="543f0-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Dialogfeld zum Eingeben von Verbindungsdetails für Azure Data Lake zu einem vorhandenen Speicherkonto](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="543f0-162">Sie benötigen eine der folgenden Rollen entweder für den Container oder das oben genannte Speicherkonto, um eine Verbindung zu einem Datenquelle herstellen und einen solchen erstellen zu können:</span><span class="sxs-lookup"><span data-stu-id="543f0-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="543f0-163">Speicher-Blob-Datenleser</span><span class="sxs-lookup"><span data-stu-id="543f0-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="543f0-164">Speicher-Blob-Datenbesitzer</span><span class="sxs-lookup"><span data-stu-id="543f0-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="543f0-165">Storage-Blob-Daten-Mitwirkender</span><span class="sxs-lookup"><span data-stu-id="543f0-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="543f0-166">Wählen Sie optional eine andere model.json- oder manifest.json-Datei mit einer anderen Gruppe von Entitäten aus dem Container.</span><span class="sxs-lookup"><span data-stu-id="543f0-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="543f0-167">Optional können Sie zusätzliche Entitäten zum Einlesen auswählen.</span><span class="sxs-lookup"><span data-stu-id="543f0-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="543f0-168">Sie können auch bereits ausgewählte Entitäten entfernen, wenn es keine Abhängigkeiten gibt.</span><span class="sxs-lookup"><span data-stu-id="543f0-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="543f0-169">Wenn Abhängigkeiten von der vorhandenen model.json- oder manifest.json-Datei und der Gruppe von Entitäten bestehen, wird eine Fehlermeldung angezeigt und Sie können keine andere model.json- oder manifest.json-Datei auswählen.</span><span class="sxs-lookup"><span data-stu-id="543f0-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="543f0-170">Entfernen Sie diese Abhängigkeiten, bevor Sie die model.json- oder manifest.json-Datei ändern, oder erstellen Sie eine neue Datenquelle mit der model.json- oder manifest.json-Datei, die Sie verwenden möchten, um das Entfernen der Abhängigkeiten zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="543f0-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="543f0-171">Optional können Sie zusätzliche Attribute oder Entitäten auswählen, um die Datenprofilierung zu aktivieren oder bereits ausgewählte zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="543f0-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]