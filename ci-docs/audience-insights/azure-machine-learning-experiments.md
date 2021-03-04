---
title: Azure Machine Learning Experimente
description: Verwenden Sie auf Azure Machine Learning basierende Modelle in Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: c166015b92596da0c6097e3d25e89579a5186ce0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267905"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="4a375-103">Verwenden Sie auf Azure Machine Learning basierende Modelle</span><span class="sxs-lookup"><span data-stu-id="4a375-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="4a375-104">Die vereinheitlichten Daten in Dynamics 365 Customer Insights sind eine Quelle für den Aufbau von Machine-Learning-Modellen, die zusätzliche Geschäftseinblicke generieren können.</span><span class="sxs-lookup"><span data-stu-id="4a375-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="4a375-105">Customer Insights lässt sich mit Machine Learning Studio (Classic) und Azure Machine Learning integrieren, um Ihre eigenen benutzerdefinierten Modelle zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a375-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="4a375-106">Beispiele für Experimente, die auf Machine Learning Studio (Classic) basieren, finden Sie unter [Machine Learning Studio (Classic) Experimente](machine-learning-studio-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="4a375-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="4a375-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4a375-107">Prerequisites</span></span>

- <span data-ttu-id="4a375-108">Zugriff auf Customer Insights</span><span class="sxs-lookup"><span data-stu-id="4a375-108">Access to Customer Insights</span></span>
- <span data-ttu-id="4a375-109">Ein aktives Azure-Enterprise-Abonnement</span><span class="sxs-lookup"><span data-stu-id="4a375-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="4a375-110">Vereinheitlichte Kundenprofile</span><span class="sxs-lookup"><span data-stu-id="4a375-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="4a375-111">[Entitäten-Export zu Azure Blob-Speicher](export-azure-blob-storage.md) konfiguriert</span><span class="sxs-lookup"><span data-stu-id="4a375-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="4a375-112">Azure Machine Learning Arbeitsbereich einrichten</span><span class="sxs-lookup"><span data-stu-id="4a375-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="4a375-113">Siehe [Erstellen eines Azure Machine Learning Arbeitsbereichs](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) für verschiedene Optionen zum Erstellen des Arbeitsbereichs.</span><span class="sxs-lookup"><span data-stu-id="4a375-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="4a375-114">Um die beste Leistung zu erzielen, erstellen Sie den Arbeitsbereich in einer Azure-Region, die Ihrer Customer Insights Umgebung geografisch am nächsten ist.</span><span class="sxs-lookup"><span data-stu-id="4a375-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="4a375-115">Zugriff auf Ihren Arbeitsbereich über das [Azure Machine Learning Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="4a375-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="4a375-116">Es gibt mehrere [Möglichkeiten, mit Ihrem Arbeitsbereich zu interagieren](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction).</span><span class="sxs-lookup"><span data-stu-id="4a375-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="4a375-117">Arbeiten Sie mit dem Azure Machine Learning Designer</span><span class="sxs-lookup"><span data-stu-id="4a375-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="4a375-118">Azure Machine Learning Designer bietet einen visuellen Canvas, in den Sie Datasets und Module ziehen können, ähnlich wie bei Machine Learning Studio (Classic).</span><span class="sxs-lookup"><span data-stu-id="4a375-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="4a375-119">Eine mit dem Designer erstellte Batch-Pipeline kann in Customer Insights integriert werden, wenn sie entsprechend konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="4a375-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="4a375-120">Arbeiten mit dem Azure Machine Learning SDK</span><span class="sxs-lookup"><span data-stu-id="4a375-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="4a375-121">Datenwissenschaftler und KI-Entwickler verwenden das [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true), um Machine Learning Workflows zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4a375-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="4a375-122">Zurzeit können Modelle, die mit dem SDK trainiert wurden, nicht direkt in Customer Insights integriert werden.</span><span class="sxs-lookup"><span data-stu-id="4a375-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="4a375-123">Für die Integration mit Customer Insights ist eine Batch-Inferenz-Pipeline erforderlich, die dieses Modell verwertet.</span><span class="sxs-lookup"><span data-stu-id="4a375-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="4a375-124">Anforderungen an die Batch-Pipeline zur Integration mit Customer Insights</span><span class="sxs-lookup"><span data-stu-id="4a375-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="4a375-125">Dataset-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="4a375-125">Dataset Configuration</span></span>

<span data-ttu-id="4a375-126">Sie müssen Datasets erstellen, um Entitätsdaten aus Customer Insights für Ihre Batch-Inferenz-Pipeline zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a375-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="4a375-127">Diese Datasets müssen im Arbeitsbereich registriert werden.</span><span class="sxs-lookup"><span data-stu-id="4a375-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="4a375-128">Zurzeit werden nur [tabellarische Datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) im .csv-Format unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4a375-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="4a375-129">Die Datasets, die den Daten der Entitäten entsprechen, müssen als Pipeline-Parameter parametrisiert werden.</span><span class="sxs-lookup"><span data-stu-id="4a375-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="4a375-130">Dataset-Parameter im Designer</span><span class="sxs-lookup"><span data-stu-id="4a375-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="4a375-131">Öffnen Sie im Designer **Spalten in Dataset auswählen** und wählen Sie **Als Pipeline-Parameter festlegen**, wo Sie einen Namen für den Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="4a375-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="4a375-132">![Dataset-Parametrisierung im Designer](media/intelligence-designer-dataset-parameters.png "Dataset-Parametrisierung im Designer")</span><span class="sxs-lookup"><span data-stu-id="4a375-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="4a375-133">Dataset-Parameter im SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="4a375-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="4a375-134">Batch-Inferenz-Pipeline</span><span class="sxs-lookup"><span data-stu-id="4a375-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="4a375-135">Im Designer kann eine Trainings-Pipeline verwendet werden, um eine Inferenz-Pipeline zu erstellen oder zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4a375-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="4a375-136">Zurzeit werden nur Batch-Inferenz-Pipelines unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4a375-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="4a375-137">Mit dem SDK können Sie die Pipeline an einen Endpunkt veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="4a375-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="4a375-138">Derzeit integriert sich Customer Insights mit der Standard-Pipeline in einem Batch-Pipeline-Endpunkt im Arbeitsbereich für maschinelles Lernen.</span><span class="sxs-lookup"><span data-stu-id="4a375-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="4a375-139">Pipeline-Daten in Customer Insights importieren</span><span class="sxs-lookup"><span data-stu-id="4a375-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="4a375-140">Der Designer bietet das Modul [Daten exportieren](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data), mit dem die Ausgabe einer Pipeline in den Azure-Speicher exportiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="4a375-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="4a375-141">Derzeit muss das Modul den Datenspeichertyp **Azure Blob Storage** verwenden und den **Datastore** und den relativen **Pfad** parametrisieren.</span><span class="sxs-lookup"><span data-stu-id="4a375-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="4a375-142">Customer Insights überschreibt diese beiden Parameter während der Pipeline-Ausführung mit einem Datenspeicher und Pfad, auf den das Produkt Zugriff hat.</span><span class="sxs-lookup"><span data-stu-id="4a375-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4a375-143">![Datenmodul-Konfiguration exportieren](media/intelligence-designer-importdata.png "Daten exportieren Modul-Konfiguration")</span><span class="sxs-lookup"><span data-stu-id="4a375-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="4a375-144">Wenn Sie die Inferenzausgabe mit Code schreiben, können Sie die Ausgabe in den Pfad innerhalb eines *registrierten Datenspeichers* im Arbeitsbereich hochladen.</span><span class="sxs-lookup"><span data-stu-id="4a375-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="4a375-145">Wenn der Pfad und der Datenspeicher in der Pipeline parametrisiert sind, kann Customer Insights die Inferenzausgabe lesen und importieren.</span><span class="sxs-lookup"><span data-stu-id="4a375-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="4a375-146">Derzeit wird eine einfache tabellarische Ausgabe im csv-Format unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4a375-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="4a375-147">Der Pfad muss das Verzeichnis und den Dateinamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="4a375-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]