---
title: Customer Insights-Daten in einen Azure Blob storage exportieren
description: Erfahren Sie, wie Sie die Verbindung zum Azure-Blobspeicher konfigurieren.
ms.date: 09/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0986ee5caf5fa079994ca584fb2c4d9294ddb80b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596176"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Connector für Azure-Blobspeicher (Vorschau)

Speichern Sie Ihre Customer Insights-Daten in einem Azure Blob storage oder nutzen Sie ihn, um Ihre Daten an andere Anwendungen zu übertragen.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Connector für Azure-Blobspeicher konfigurieren

1. Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Ziele exportieren**.

1. Unter **Azure-Blobspeicher** wählen Sie **Installieren**.

1. Geben Sie **Kontobezeichnung**, **Kontoschlüssel** und **Container** für Ihr Azure-Blobspeicherkonto ein.
    - Weitere Informationen zum Suchen des Azure-Blobspeicherkontonamens und des Kontoschlüssels finden Sie unter [Verwalten von Speicherkontoeinstellungen im Azure-Portal](/azure/storage/common/storage-account-manage).
    - Informationen zum Erstellen eines Containers finden Sie unter [Erstellen eines Containers](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Geben Sie Ihrem Ziel einen erkennbaren Namen im Feld **Anzeigename**.

1. Wählen Sie **Weiter**.

1. Aktivieren Sie das Kontrollkästchen neben jeder der Entitäten, die Sie an dieses Ziel exportieren möchten.

1. Wählen Sie **Speichern** aus.

Exportierte Daten werden in dem von Ihnen konfigurierten Azure-Blobspeichercontainer gespeichert. Die folgenden Ordnerpfade werden automatisch in Ihrem Container erstellt:

- Für Quell-Entitäten und vom System generierte Entitäten: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Beispiel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Das model.json für die exportierten Entitäten befindet sich auf der %ExportDestinationName%-Ebene.
  - Beispiel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Exportieren der Daten

Sie könenn [Daten nach Bedarf exportieren](export-destinations.md#export-data-on-demand). Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.


[!INCLUDE[footer-include](../includes/footer-banner.md)]