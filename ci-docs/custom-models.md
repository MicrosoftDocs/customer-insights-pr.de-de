---
title: Benutzerdefinierte Maschinelles Lernen Modelle | Microsoft Docs
description: Arbeiten Sie mit benutzerdefinierten Modellen aus Azure Machine Learning in Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609745"
---
# <a name="custom-machine-learning-models"></a>Benutzerdefinierte Maschinelles Lernen Modelle

> [!NOTE]
> Der Support für Machine Learning Studio (klassisch) endet am 31. August 2024. Wir empfehlen den Umstieg auf [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning) bis zu diesem Datum.
>
> Ab dem 1. Dezember 2021 können Sie keine neuen Machine Learning Studio-Ressourcen (klassisch) erstellen. Bis zum 31. August 2024 können Sie weiterhin die bestehenden Ressourcen von Machine Learning Studio (klassisch) verwenden. Weitere Informationen finden Sie unter [Zu Azure Machine Learning migrieren](/azure/machine-learning/migrate-overview).

Durch benutzerdefinierte Modelle können Sie Workflows verwalten, die auf Azure Machine Learning-Modellen basieren. Workflows helfen Ihnen bei der Auswahl der Daten, aus denen Sie Insights generieren möchten, und bei der Zuordnung der Ergebnisse zu Ihren vereinheitlichten Kundendaten. Weitere Informationen zum Erstellen von benutzerdefinierten ML-Modellen finden Sie unter [Verwenden von Azure Machine Learning-basierten Modellen](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Anforderungen

- Webdienste, die über [Azure Machine Learning-Batchpipelines](/azure/machine-learning/concept-ml-pipelines) veröffentlicht wurden.
- Pipeline muss unter einem [Pipeline-Endpunkt](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) veröffentlicht werden.
- Ein [Azure Data Lake Gen2-Speicherkonto](/azure/storage/blobs/data-lake-storage-quickstart-create-account), das mit Ihrer Azure Studio-Instanz verbunden ist.
- Für Azure Machine Learning-Arbeitsbereiche mit Pipelines Besitzer- oder Benutzerzugriffs-Administratorberechtigungen auf den Azure Machine Learning-Arbeitsbereich.

  > [!NOTE]
  > Daten werden zwischen Ihren Customer Insights-Instanzen und den ausgewählten Azure-Webdiensten oder -Pipelines im Workflow übertragen. Wenn Sie Daten an einen Azure-Service übertragen, stellen Sie sicher, dass der Service für die Verarbeitung von Daten auf die Weise und für den Standort konfiguriert ist, die erforderlich ist, um die rechtlichen Anforderungen für diese Daten für Ihr Unternehmen zu erfüllen.

## <a name="add-a-new-workflow"></a>Einen neuen Workflow hinzufügen

1. Gehen Sie zu **Intelligenz** > **Benutzerdefinierte Modelle** und wählen Sie **Neuer Workflow**.

1. Geben Sie einen erkennbaren **Namen** an.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Screenshot des Fensters „Neuer Workflow“.":::

1. Wählen Sie die Organisation, die den Webdienst enthält, unter **Mandant, der Ihren Webdienst enthält**.

1. Wenn Ihr Azure Machine Learning-Abonnement einen anderen Mandant als Customer Insights hat, wählen Sie **Anmelden** mit Ihren Anmeldedaten für die ausgewählte Organisation.

1. Wählen Sie die **Arbeitsbereiche**, die mit Ihrem Webdienst verbunden sind.

1. Wählen Sie die Azure Machine Learning-Pipeline aus der Dropdownliste **Webdienst, der Ihr Modell enthält** aus. Wählen Sie anschließend **Weiter** aus.
   Erfahren Sie mehr über [Veröffentlichen einer Pipeline in Azure Machine Learning mithilfe des Designers](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) oder [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. Für jede **Webdienst-Eingabe** wählen Sie die passende **Entität** aus von Customer Insights. Wählen Sie anschließend **Weiter** aus.
   > [!NOTE]
   > Der benutzerdefinierte Modellworkflow wendet Heuristiken an, um die Webdienst-Eingabefelder den Entitätsattributen basierend auf dem Namen und dem Datentyp des Felds zuzuordnen. Es wird ein Fehler angezeigt, wenn ein Webdienstfeld keiner Entität zugeordnet werden kann.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Workflow konfigurieren.":::

1. Legen Sie für **Modellausgabeparameter** folgenden Eigenschaften fest:
   - **Entitätsname** für die Pipeline-Ausgabeergebnisse
   - **Parameternamen des Ausgabedatenspeichers** Ihrer Batch-Pipeline
   - **Parameternamen des Ausgabepfads** Ihrer Batch-Pipeline

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Modellausgabe-Parameterbereich.":::

1. Wählen Sie das passende Attribut aus **Kunden-ID in den Ergebnissen**, das ihren Kunden identifiziert, und wählen Sie **Speichern**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Ergebnisse in den Kundendatenbereich überführen.":::

   Auf dem Bildschirm **Workflow gespeichert** werden Details zum Workflow angezeigt. Wenn Sie einen Workflow für eine Azure Machine Learning Pipeline konfiguriert haben, verbindet sich Customer Insights mit dem Arbeitsbereich, der die Pipeline enthält. Customer Insights erhält eine **Mitwirkende** Rolle im Azure Arbeitsbereich.

1. Wählen Sie **Fertig** aus. Die Seite **Benutzerdefinierte Modelle** wird angezeigt.

1. Wählen Sie die vertikalen Auslassungspunkte (&vellip;) für den Workflow und dann **Ausführen** aus. Ihr Workflow läuft auch automatisch bei jeder [geplanten Aktualisierung](schedule-refresh.md).

## <a name="manage-an-existing-workflow"></a>Einen vorhandenen Workflow verwalten

Gehen Sie zu **Intelligenz** > **Benutzerdefinierte Modelle**, um die von Ihnen erstellten Workflows anzuzeigen.

Wählen Sie einen Workflow aus, um verfügbare Aktionen anzuzeigen.

- Einen Workflow **bearbeiten**
- Einen Workflow **ausführen**
- Einen Workflow [**löschen**](#delete-a-workflow)

### <a name="edit-a-workflow"></a>Einen Workflow bearbeiten

1. Gehen Sie zu **Intelligenz** > **Benutzerdefinierte Modelle**.

1. Wählen Sie neben dem Workflow, den Sie aktualisieren möchten, die vertikalen Auslassungspunkte (&vellip;) und dann **Bearbeiten**.

1. Ändern Sie bei Bedarf den **Anzeigename** und wählen Sie **Weiter** aus.

1. Aktualisieren Sie bei Bedarf für jede **Webdienst-Eingabe** die passende **Entität** aus Customer Insights. Wählen Sie anschließend **Weiter** aus.

1. Nehmen Sie für **Modellausgabeparameter** eine der folgenden Änderungen vor:
   - **Entitätsname** für die Pipeline-Ausgabeergebnisse
   - **Parameternamen des Ausgabedatenspeichers** Ihrer Batch-Pipeline
   - **Parameternamen des Ausgabepfads** Ihrer Batch-Pipeline

1. Ändern Sie das übereinstimmende Attribut aus den **Kunden-ID in Ergebnissen**, um den Kunden zu identifizieren. Wählen Sie ein Attribut aus der Inferenzausgabe aus, dessen Werte der Spalte Kunden-ID der Entität Kunde ähneln. Wenn Sie keine solche Spalte in Ihrem Datensatz haben, wählen Sie ein Attribut, das die Zeile eindeutig identifiziert.

1. Wählen Sie **Speichern**

### <a name="delete-a-workflow"></a>Löschen eines Workflows

1. Gehen Sie zu **Intelligenz** > **Benutzerdefinierte Modelle**.

1. Wählen Sie neben dem Workflow, den Sie löschen möchten, die vertikalen Auslassungspunkte (&vellip;) und dann **Löschen**.

1. Bestätigen Sie den Löschvorgang.

Ihr Workflow wird gelöscht. Die [Entität](entities.md), die beim Anlegen des Workflows angelegt wurde, bleibt bestehen und kann auf der Seite **Daten** > **Entitäten** eingesehen werden.

## <a name="view-the-results"></a>Ergebnisse anzeigen

Ergebnisse aus einem Workflow werden in dem für **Modellausgabeparameter** festgelegten Entitätsnamen gespeichert. Greifen Sie auf diese Daten über die [Seite **Daten** > **Entitäten**](entities.md) oder mit [API-Zugriff](apis.md) zu.

### <a name="api-access"></a>API-Zugriff

Verwenden Sie für die spezifische OData-Abfrage das folgende Format, um Daten von einer benutzerdefinierten Modellentität abzurufen:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Ersetzen Sie `<your instance id>` mit der ID Ihrer Customer Insights-Umgebung, die beim Zugriff auf Customer Insights in der Adressleiste Ihres Browsers angezeigt wird.

1. Ersetzen Sie `<custom model output entity>` mit dem Entitätsnamen, den Sie für die **Modellausgabeparameter** angegeben haben.

1. Ersetzen Sie `<guid value>` mit der Kunden-ID des Kunden, auf den Sie zugreifen möchten. Diese ID wird auf der [Kundenprofilseite](customer-profiles.md) im Feld „CustomerID“ angezeigt.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

- Warum kann ich meine Pipeline beim Einrichten eines benutzerdefinierten Modellworkflows nicht sehen?
  Dieses Problem wird häufig durch ein Konfigurationsproblem in der Pipeline verursacht. Stellen Sie sicher, dass der [Eingabeparameter konfiguriert ist](azure-machine-learning-experiments.md#dataset-configuration), und dass [Ausgabedatenspeicher und Pfadparameter](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) ebenfalls konfiguriert sind.

- Was bedeutet der Fehler „Intelligenz-Workflow konnte nicht gespeichert werden“? 
  Benutzer sehen diese Fehlermeldung normalerweise, wenn sie keine Berechtigungen für den Eigentümer- oder Benutzerzugriff Administrator im Arbeitsbereich haben. Der Benutzer benötigt eine höhere Berechtigungsstufe, damit Customer Insights den Workflow als Service verarbeiten kann, anstatt die Benutzeranmeldeinformationen für nachfolgende Ausführungen des Workflows zu verwenden.

- Wird ein privater Endpunkt/eine private Verbindung für meinen benutzerdefinierten Modellworkflow unterstützt?
  Customer Insights unterstützt derzeit keine privaten Endpunkt für benutzerdefinierte Modelle, aber eine manuelle Problemumgehung ist verfügbar. Wenden Sie sich an den Support, um detaillierte Informationen zu erhalten.

## <a name="responsible-ai"></a>Verantwortliche KI

Vorhersagen bieten Funktionalitäten, um bessere Kundenerlebnisse zu erstellen, Geschäftsfunktionen zu verbessern und Umsatzströme zu steigern. Wir empfehlen Ihnen dringend, den Wert Ihrer Vorhersage gegen die Auswirkungen und Verzerrungen abzuwägen, die auf ethische Art und Weise eingeführt werden können. Erfahren Sie mehr darüber, wie Microsoft [verantwortungsvolle KI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) berücksichtigt. Sie können sich auch über [Techniken und Prozesse für verantwortungsvolles maschinelles Lernen](/azure/machine-learning/concept-responsible-ml) speziell für Azure Machine Learning informieren.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
