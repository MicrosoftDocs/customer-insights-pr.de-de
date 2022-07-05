---
title: Verwenden Sie auf Azure Machine Learning basierende Modelle
description: Verwenden Sie auf Azure Machine Learning basierende Modelle in Dynamics 365 Customer Insights.
ms.date: 12/02/2021
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a1efad2887a02a92ee2960b07b066edc331f3665
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081021"
---
# <a name="use-azure-machine-learning-based-models"></a>Verwenden Sie auf Azure Machine Learning basierende Modelle

Die vereinheitlichten Daten in Dynamics 365 Customer Insights sind eine Quelle für den Aufbau von Machine-Learning-Modellen, die zusätzliche Geschäftseinblicke generieren können. Customer Insights lässt sich in Azure Machine Learning integrieren, um Ihre eigenen benutzerdefinierten Modelle zu verwenden.

## <a name="prerequisites"></a>Voraussetzungen

- Zugriff auf Customer Insights
- Ein aktives Azure-Enterprise-Abonnement
- [Vereinheitlichte Kundenprofile](data-unification.md)
- [Entitäten-Export zu Azure Blob-Speicher](export-azure-blob-storage.md) konfiguriert

## <a name="set-up-azure-machine-learning-workspace"></a>Azure Machine Learning Arbeitsbereich einrichten

1. Siehe [Erstellen eines Azure Machine Learning Arbeitsbereichs](/azure/machine-learning/concept-workspace#-create-a-workspace) für verschiedene Optionen zum Erstellen des Arbeitsbereichs. Um die beste Leistung zu erzielen, erstellen Sie den Arbeitsbereich in einer Azure-Region, die Ihrer Customer Insights Umgebung geografisch am nächsten ist.

1. Zugriff auf Ihren Arbeitsbereich über das [Azure Machine Learning Studio](https://ml.azure.com/). Es gibt mehrere [Möglichkeiten, mit Ihrem Arbeitsbereich zu interagieren](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction).

## <a name="work-with-azure-machine-learning-designer"></a>Arbeiten Sie mit dem Azure Machine Learning Designer

Der Azure Machine Learning-Designer stellt eine visuelle Canvas bereit, in die Sie Datasets und Module ziehen und ablegen können. Eine mit dem Designer erstellte Batch-Pipeline kann in Customer Insights integriert werden, wenn sie entsprechend konfiguriert ist. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Arbeiten mit dem Azure Machine Learning SDK

Datenwissenschaftler und KI-Entwickler verwenden das [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py), um Machine Learning Workflows zu erstellen. Zurzeit können Modelle, die mit dem SDK trainiert wurden, nicht direkt in Customer Insights integriert werden. Für die Integration mit Customer Insights ist eine Batch-Inferenz-Pipeline erforderlich, die dieses Modell verwertet.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Anforderungen an die Batch-Pipeline zur Integration mit Customer Insights

### <a name="dataset-configuration"></a>Dataset-Konfiguration

Sie müssen Datasets erstellen, um Entitätsdaten aus Customer Insights für Ihre Batch-Inferenz-Pipeline zu verwenden. Diese Datasets müssen im Arbeitsbereich registriert werden. Zurzeit werden nur [tabellarische Datasets](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) im .csv-Format unterstützt. Die Datasets, die den Daten der Entitäten entsprechen, müssen als Pipeline-Parameter parametrisiert werden.
   
* Dataset-Parameter im Designer
   
     Öffnen Sie im Designer **Spalten in Dataset auswählen** und wählen Sie **Als Pipeline-Parameter festlegen**, wo Sie einen Namen für den Parameter angeben.

     > [!div class="mx-imgBorder"]
     > ![Dataset-Parametrisierung im Designer.](media/intelligence-designer-dataset-parameters.png "Dataset-Parametrisierung im Designer")
   
* Dataset-Parameter im SDK (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Batch-Inferenz-Pipeline
  
* Im Designer kann eine Trainings-Pipeline verwendet werden, um eine Inferenz-Pipeline zu erstellen oder zu aktualisieren. Zurzeit werden nur Batch-Inferenz-Pipelines unterstützt.

* Mit dem SDK können Sie die Pipeline an einen Endpunkt veröffentlichen. Derzeit integriert sich Customer Insights mit der Standard-Pipeline in einem Batch-Pipeline-Endpunkt im Arbeitsbereich für maschinelles Lernen.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Pipeline-Daten in Customer Insights importieren

* Der Designer bietet das Modul [Daten exportieren](/azure/machine-learning/algorithm-module-reference/export-data), mit dem die Ausgabe einer Pipeline in den Azure-Speicher exportiert werden kann. Derzeit muss das Modul den Datenspeichertyp **Azure Blob Storage** verwenden und den **Datastore** und den relativen **Pfad** parametrisieren. Customer Insights überschreibt diese beiden Parameter während der Pipeline-Ausführung mit einem Datenspeicher und Pfad, auf den das Produkt Zugriff hat.
   > [!div class="mx-imgBorder"]
   > ![Datenmodul-Konfiguration exportieren.](media/intelligence-designer-importdata.png "Daten exportieren Modul-Konfiguration")
   
* Wenn Sie die Inferenzausgabe mit Code schreiben, können Sie die Ausgabe in den Pfad innerhalb eines *registrierten Datenspeichers* im Arbeitsbereich hochladen. Wenn der Pfad und der Datenspeicher in der Pipeline parametrisiert sind, kann Customer Insights die Inferenzausgabe lesen und importieren. Derzeit wird eine einfache tabellarische Ausgabe im csv-Format unterstützt. Der Pfad muss das Verzeichnis und den Dateinamen enthalten.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]