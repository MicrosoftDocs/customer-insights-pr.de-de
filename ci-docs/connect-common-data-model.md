---
title: Verbinden Sie Common Data Model-Daten mit einem Azure Data Lake-Konto
description: Arbeiten Sie mit Common Data Model-Daten unter Verwendung von Azure Data Lake Storage.
ms.date: 05/24/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: 2e8564950a3269180a85f80fb736d2dcbd1b03b6
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833356"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Verbinden Sie den Ordner Common Data Model mithilfe einem Azure Data Lake-Konto

In diesem Artikel erfahren Sie, wie Sie mit Ihrem Azure Data Lake Storage-Gen2-Konto Daten aus einem Common Data Model-Ordner in Dynamics 365 Customer Insights einbinden können.

## <a name="important-considerations"></a>Wichtige Überlegungen

- Daten in Azure Data Lake müssen dem Common Data Model-Standard entsprechen. Andere Formate werden derzeit nicht unterstützt.

- Die Datenerfassung unterstützt ausschließlich Azure Data Lake *Gen2* Speicherkonten. Sie können keine Azure Data Lake Gen1-Speicherkonten für die Datenerfassung verwenden.

- Bei dem Azure Data Lake-Speicherkonto muss [hierarchischer Namespace aktiviert](/azure/storage/blobs/data-lake-storage-namespace) sein.

- Um sich mit einem Azure Service Prinzipal zu authentifizieren, stellen Sie sicher, dass es in Ihrem Mandanten konfiguriert ist. Weitere Informationen finden Sie unter [Verbinden Sie sich mit einem Azure Dienstprinzipal mit einem Azure Data Lake Storage Gen2 Konto](connect-service-principal.md).

- Der Azure Data Lake, mit dem Sie sich verbinden und von dem Sie Daten aufnehmen möchten, muss sich in derselben Azure-Region befinden wie die Dynamics 365 Customer Insights-Umgebung. Verbindungen zu einem Common Data Model-Ordner aus einem Data Lake in einer anderen Azure-Region werden nicht unterstützt. Um die Azure-Region der Umgebung zu erfahren, gehen Sie zu **Admin** > **System** > **Über** in Customer Insights.

- Daten, die in Online-Diensten gespeichert sind, können an einem anderen Ort gespeichert werden als dort, wo die Daten verarbeitet oder in Dynamics 365 Customer Insights gespeichert werden. Durch das Importieren von oder Verbinden mit Daten, die in Online-Diensten gespeichert sind, erklären Sie sich damit einverstanden, dass Daten an das Microsoft Trust Center übertragen und dort mit Dynamics 365 Customer Insights gespeichert werden können. [Erfahren Sie mehr im Microsoft Trust Center.](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-common-data-model-folder"></a>Mit einem „Common Data Model“-Ordner verbinden

1. Wechseln Sie zu **Daten** > **Datenquellen**.

1. Wählen Sie **Datenquelle hinzufügen**.

1. Wählen Sie **Azure Data Lake Storage** aus, geben Sie einen **Namen** für Datenquelle ein, und wählen Sie dann **Weiter** aus.

   - Wählen Sie bei entsprechender Aufforderung einen der zu Ihrer Branche gehörenden Beispieldatensätze und anschließend **Weiter** aus.

1. Sie können zwischen einer ressourcenbasierten Option und einer abonnementbasierten Option für die Authentifizierung wählen. Weitere Informationen finden Sie unter [Verbinden Sie sich mit einem Azure Dienstprinzipal mit einem Azure Data Lake Storage Gen2 Konto](connect-service-principal.md). Geben Sie die **Serveradresse** ein, und wählen Sie **Anmelden** und dann **Weiter** aus.
   > [!div class="mx-imgBorder"]
   > ![Dialogfeld zum Eingeben neuer Verbindungsdetails für Azure Data Lake.](media/enter-new-storage-details.png)
   > [!NOTE]
   > Sie benötigen entweder eine der folgenden Rollen, um den Container auf dem Speicherkonto zu erstellen und Datenquelle zu erstellen:
   >
   >  - Datenleser des Speicher-Blobs reicht aus, um von einem Speicherkonto zu lesen und die Daten in Customer Insights zu übernehmen. 
   >  - Storage Blob-Datenmitwirkender oder Besitzer ist erforderlich, wenn Sie die Manifestdateien direkt in Customer Insights bearbeiten möchten.

1. Wählen Sie im Dialog **Wählen Sie einen gemeinsamen Datenmodell-Ordner** die Datei manifest.json aus, aus der Daten importiert werden sollen, und wählen Sie **Weiter**.
   > [!NOTE]
   > Jede model.json- oder manifest.json-Datei, die mit einer anderen Datenquelle in der Umgebung verbunden ist, wird nicht in der Liste angezeigt.

1. In der ausgewählten model.json- oder manifest.json-Datei wird eine Liste der verfügbaren Entitäten angezeigt. Überprüfen Sie die Liste der verfügbaren Entitäten, treffen Sie eine Auswahl, und wählen Sie anschließend **Speichern** aus. Alle ausgewählten Entitäten werden von der neuen Datenquelle aufgenommen.
   > [!div class="mx-imgBorder"]
   > ![Dialogfeld mit einer Liste von Entitäten aus einer model.json-Datei.](media/review-entities.png)

1. Geben Sie an, für welche Datenentitäten die Datenprofilerstellung aktiviert werden soll, und wählen Sie dann **Speichern** aus. Die Datenprofilerstellung ermöglicht Analysen und andere Funktionen. Sie können die gesamte Entität auswählen, wodurch alle Attribute der Entität ausgewählt werden, oder Sie können bestimmte Attribute Ihrer Wahl auswählen. Standardmäßig ist keine Entität für die Datenprofilierung aktiviert.
   > [!div class="mx-imgBorder"]
   > ![Dialogfeld, das eine Datenprofilierung zeigt.](media/dataprofiling-entities.png)

1. Nachdem Sie Ihre Auswahl gespeichert haben, wird die Seite **Datenquellen** geöffnet. Sie sollten nun die Ordnerverbindung Common Data Model als Datenquelle sehen.

> [!NOTE]
> Eine model.json- oder manifest.json-Datei kann nur mit einer Datenquelle in derselben Umgebung verknüpft werden. Allerdings kann dieselbe model.json- oder manifest.json-Datei für Datenquellen in mehreren Umgebungen verwendet werden.

## <a name="edit-a-common-data-model-folder-data-source"></a>Bearbeiten eines allgemeinen Datenmodellordners Datenquelle

Sie können den Zugriffsschlüssel für das Speicherkonto aktualisieren, das den Ordner Common Data Model enthält. Sie können auch die model.json- oder manifest.json-Datei ändern. Um eine Verbindung zu einem anderen Container als Ihrem Speicherkonto herzustellen oder den Kontonamen zu ändern, [erstellen Sie eine neue Datenquellenverbindung](#connect-to-a-common-data-model-folder).

1. Wechseln Sie zu **Daten** > **Datenquellen**.

2. Wählen Sie neben dem Datenquelle, das Sie aktualisieren möchten, die vertikalen Auslassungspunkte (&vellip;).

3. Wählen Sie eine Option **Bearbeiten** in der Liste aus.

4. Aktualisieren Sie optional den **Zugriffsschlüssel** und wählen Sie **Weiter** aus.

   ![Dialog, um einen Zugriffsschlüssel für eine vorhandene Datenquelle zu bearbeiten und zu aktualisieren.](media/edit-access-key.png)

5. Optional können Sie von einer Kontoschlüssel-Verbindung zu einer ressourcenbasierten oder abonnementbasierten Verbindung aktualisieren. Weitere Informationen finden Sie unter [Verbinden Sie sich mit einem Azure Dienstprinzipal mit einem Azure Data Lake Storage Gen2 Konto](connect-service-principal.md). Sie können die **Container**-Informationen beim Aktualisieren der Verbindung nicht ändern.
   > [!div class="mx-imgBorder"]

   > ![Dialogfeld zum Eingeben von Verbindungsdetails für Azure Data Lake zu einem vorhandenen Speicherkonto.](media/enter-existing-storage-details.png)

6. Wählen Sie optional eine andere model.json- oder manifest.json-Datei mit einer anderen Gruppe von Entitäten aus dem Container.

7. Optional können Sie zusätzliche Entitäten zum Einlesen auswählen. Sie können auch bereits ausgewählte Entitäten entfernen, wenn es keine Abhängigkeiten gibt.

   > [!IMPORTANT]
   > Wenn Abhängigkeiten von der vorhandenen model.json- oder manifest.json-Datei und der Gruppe von Entitäten bestehen, wird eine Fehlermeldung angezeigt und Sie können keine andere model.json- oder manifest.json-Datei auswählen. Entfernen Sie diese Abhängigkeiten, bevor Sie die model.json- oder manifest.json-Datei ändern, oder erstellen Sie eine neue Datenquelle mit der model.json- oder manifest.json-Datei, die Sie verwenden möchten, um das Entfernen der Abhängigkeiten zu vermeiden.

8. Optional können Sie zusätzliche Attribute oder Entitäten auswählen, um die Datenprofilierung zu aktivieren oder bereits ausgewählte zu deaktivieren.

[!INCLUDE [footer-include](includes/footer-banner.md)]
