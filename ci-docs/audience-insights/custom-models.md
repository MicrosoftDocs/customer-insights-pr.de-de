---
title: Benutzerdefinierte Maschinelles Lernen Modelle | Microsoft Docs
description: Arbeiten Sie mit benutzerdefinierten Modellen aus Azure Machine Learning in Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267233"
---
# <a name="custom-machine-learning-models"></a>Benutzerdefinierte Maschinelles Lernen Modelle

**Intelligenz** > **Benutzerdefinierte Modelle** ermöglicht die Verwaltung von Workflows auf Basis von Azure Machine Learning-Modellen. Workflows helfen Ihnen bei der Auswahl der Daten, aus denen Sie Insights generieren möchten, und bei der Zuordnung der Ergebnisse zu Ihren vereinheitlichten Kundendaten. Weitere Informationen zum Erstellen von benutzerdefinierten ML-Modellen finden Sie unter [Verwenden von Azure Machine Learning-basierten Modellen](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Verantwortliche KI

Vorhersagen bieten Funktionalitäten, um bessere Kundenerlebnisse zu erstellen, Geschäftsfunktionen zu verbessern und Umsatzströme zu steigern. Wir empfehlen Ihnen dringend, den Wert Ihrer Vorhersage gegen die Auswirkungen und Verzerrungen abzuwägen, die auf ethische Art und Weise eingeführt werden können. Erfahren Sie mehr darüber, wie Microsoft [verantwortungsvolle KI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) berücksichtigt. Sie können sich auch über [Techniken und Prozesse für verantwortungsvolles maschinelles Lernen](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) speziell für Azure Machine Learning informieren.

## <a name="prerequisites"></a>Anforderungen

- Derzeit unterstützt diese Funktion Webdienste, die über [Machine Learning Studio (Classic)](https://studio.azureml.net) und [Azure Machine Learning Batch Pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines) veröffentlicht werden.

- Sie benötigen ein Azure Data Lake Gen2-Speicherkonto, das mit Ihrer Azure Studio-Instanz verbunden ist, um diese Funktion zu verwenden. Weitere Informationen finden Sie unter [Erstellen eines Azure Data Lake Storage Gen2-Speicherkontos](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>Einen neuen Workflow hinzufügen

1. Gehen Sie zu **Intelligenz** > **Benutzerdefinierte Modelle** und wählen Sie **Neuer Workflow**.

1. Ihr benutzerdefiniertes Modell wird im Feld **Name** mit einem erkennbaren Namen benannt.

   > [!div class="mx-imgBorder"]
   > ![Screenshot des Fensters Neuer Workflow](media/new-workflowv2.png "Screenshot des Fensters Neuer Workflow")

1. Wählen Sie die Organisation, die den Webdienst enthält, unter **Mandant, der Ihren Webdienst enthält**.

1. Wenn Ihr Azure Machine Learning-Abonnement einen anderen Mandant als Customer Insights hat, wählen Sie **Anmelden** mit Ihren Anmeldedaten für die ausgewählte Organisation.

1. Wählen Sie die **Arbeitsbereiche**, die mit Ihrem Webdienst verbunden sind. Es sind zwei Bereiche aufgeführt, einer für Azure Machine Learning v1 (Machine Learning Studio (Classic)) und Azure Machine Learning v2 (Azure Machine Learning). Wenn Sie sich nicht sicher sind, welcher Arbeitsbereich der richtige für Ihren Machine Learning Studio (Classic) Webservice ist, wählen Sie **Beliebig**.

1. Wählen Sie den Machine Learning Studio (Classic)-Webdienst oder die Azure Machine Learning-Pipeline in der Dropdown-Liste **Webdienst, der Ihr Modell enthält**. Wählen Sie anschließend **Weiter** aus.
   - Erfahren Sie mehr über [das Veröffentlichen eines Webdienstes in Machine Learning Studio (Classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Erfahren Sie mehr über [Veröffentlichen einer Pipeline in Azure Machine Learning mithilfe des Designers](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) oder [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Ihre Pipeline muss unter einem [Pipeline-Endpunkt](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) veröffentlicht werden.

1. Wählen Sie für jede **Webdienst-Eingabe** die passende **Entität** aus Zielgruppen-Insights und wählen Sie **Weiter**.
   > [!NOTE]
   > Der benutzerdefinierte Modellworkflow wendet Heuristiken an, um die Webdienst-Eingabefelder den Entitätsattributen basierend auf dem Namen und dem Datentyp des Felds zuzuordnen. Es wird ein Fehler angezeigt, wenn ein Webdienstfeld keiner Entität zugeordnet werden kann.

   > [!div class="mx-imgBorder"]
   > ![Workflow konfigurieren](media/intelligence-screen2-updated.png "Workflow konfigurieren")
   
1. Legen Sie im Schritt **Modellausgabeparameter** die folgenden Eigenschaften fest:
   - Machine Learning Studio (Classic)
      1. Geben Sie den Ausgang **Entitätsname** ein, in den die Ergebnisse der Web-Service-Ausgabe fließen sollen.
   - Azure Machine Learning
      1. Geben Sie den Ausgabe-**Entitätsnamen** ein, in den die Ergebnisse der Pipeline-Ausgabe fließen sollen.
      1. Wählen Sie den **Output-Datenspeicher-Parameternamen** Ihrer Batch-Pipeline aus dem Dropdown-Menü.
      1. Wählen Sie den **Output Path-Parameternamen** Ihrer Batch-Pipeline aus der Auswahlliste.
      
      > [!div class="mx-imgBorder"]
      > ![Modellausgabe-Parameterbereich](media/intelligence-screen3-outputparameters.png "Modellausgabe-Parameterbereich")

1. Wählen Sie das passende Attribut aus der Dropdown-Liste **Kunden-ID in Ergebnissen**, das den Kunden identifiziert, und wählen Sie **Speichern**.
   
   > [!div class="mx-imgBorder"]
   > ![Ergebnisse in den Kundendatenbereich überführen](media/intelligence-screen4-relatetocustomer.png "Ergebnisse mit dem Bereich Kundendaten in Beziehung setzen")

1. Sie sehen dann das Bild **Workflow Gespeichert** mit Einzelheiten zum Workflow.    
   Wenn Sie einen Workflow für eine Azure Machine Learning-Pipeline konfiguriert haben, wird Zielgruppen-Insights an den Arbeitsbereich angehängt, der die Pipeline enthält. Zielgruppen-Insights erhalten eine **Beitragender**-Rolle auf dem Azure-Arbeitsbereich.

1. Wählen Sie **Fertig** aus.

1. Sie können jetzt den Workflow von der Seite **Benutzerdefinierte Modelle** aus starten.

## <a name="edit-a-workflow"></a>Einen Workflow bearbeiten

1. Auf der Seite **Benutzerdefinierte Modelle** wählen Sie die vertikalen Auslassungspunkte in der Spalte **Aktionen** neben einem Workflow, den Sie zuvor erstellt und ausgewählt haben und wählen **Bearbeiten**.

1. Sie können den erkennbaren Namen Ihres Workflows im Feld **Anzeigename** aktualisieren, aber Sie können den konfigurierten Webdienst oder die Pipeline nicht ändern. Klicken Sie auf **Weiter**.

1. Für jede **Web-Service-Eingabe** können Sie die passende **Entität** aus den Zielgruppen-Insights aktualisieren. Wählen Sie anschließend **Weiter** aus.

1. Legen Sie im Schritt **Modellausgabeparameter** die folgenden Eigenschaften fest:
   - Machine Learning Studio (Classic)
      1. Geben Sie den Ausgang **Entitätsname** ein, in den die Ergebnisse der Web-Service-Ausgabe fließen sollen.
   - Azure Machine Learning
      1. Geben Sie den Ausgabe-**Entitätsnamen** ein, in den die Ergebnisse der Pipeline-Ausgabe fließen sollen.
      1. Wählen Sie den **Parameternamen des Ausgabedatenspeichers** für Ihre Test-Pipeline.
      1. Wählen Sie den **Output Path-Parameternamen** für Ihre Test-Pipeline.

1. Wählen Sie das passende Attribut aus der Dropdown-Liste **Kunden-ID in Ergebnissen**, das den Kunden identifiziert, und wählen Sie **Speichern**.
   Sie müssen ein Attribut aus der Inferenzausgabe auswählen, dessen Werte der Spalte Kunden-ID der Entität Kunde ähneln. Wenn Sie eine solche Spalte nicht in Ihrem Datensatz haben, wählen Sie ein Attribut, das die Zeile eindeutig identifiziert.

## <a name="run-a-workflow"></a>Ausführen eines Workflows

1. Auf der Seite **Benutzerdefinierte Modelle** wählen Sie die vertikalen Auslassungspunkte in der Spalte **Aktionen** neben einem Workflow, den Sie zuvor erstellt und ausgewählt haben.

1. **Ausführen** auswählen.

Ihr Workflow läuft auch automatisch bei jeder geplanten Aktualisierung. Mehr erfahren zum [Einrichten geplanter Aktualisierungen](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Löschen eines Workflows

1. Auf der Seite **Benutzerdefinierte Modelle** wählen Sie die vertikalen Auslassungspunkte in der Spalte **Aktionen** neben einem Workflow, den Sie zuvor erstellt und ausgewählt haben.

1. Wählen Sie **Löschen** und bestätigen Sie Ihre Löschung.

Ihr Workflow wird gelöscht. Die [Entität](entities.md), die beim Anlegen des Workflows angelegt wurde, bleibt bestehen und kann auf der Seite **Entitäten** eingesehen werden.


[!INCLUDE[footer-include](../includes/footer-banner.md)]