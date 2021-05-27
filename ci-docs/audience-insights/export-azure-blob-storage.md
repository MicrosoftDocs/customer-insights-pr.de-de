---
title: Customer Insights-Daten in einen Azure Blob Storage exportieren
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zum Azure Blob Storage exportieren.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976133"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Exportieren Sie die Segmentliste und andere Daten in den Azure Blob Storage (Vorschau)

Speichern Sie Ihre Customer Insights-Daten in einem Azure Blob Storage, oder verwenden Sie es, um Ihre Daten in andere Anwendungen zu übertragen.

## <a name="set-up-the-connection-to-blob-storage"></a>Richten Sie die Verbindung mit Azure Blob Storage ein

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und dann **Azure Blob Storage** aus, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie **Kontobezeichnung**, **Kontoschlüssel** und **Container** für Ihr Blob Storage-Konto ein.
    - Weitere Informationen zum Ermitteln des Blob Storage-Kontonamens und des Kontoschlüssels finden Sie unter [Verwalten Sie die Speicherkontoeinstellungen im Azure-Portal](/azure/storage/common/storage-account-manage).
    - Informationen zum Erstellen eines Containers finden Sie unter [Erstellen eines Containers](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus. 

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Azure Blob Storage-Abschnitt aus. Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. Aktivieren Sie das Kontrollkästchen neben jeder der Entitäten, die Sie an dieses Ziel exportieren möchten.

1. Wählen Sie **Speichern** aus.

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.     
Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand). 

Exportierte Daten werden in dem von Ihnen konfigurierten Blob Storage-Container gespeichert. Die folgenden Ordnerpfade werden automatisch in Ihrem Container erstellt:

- Für Quell-Entitäten und vom System generierte Entitäten: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Beispiel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Die model.json-Datei für die exportierten Entitäten befindet sich auf der %ExportDestinationName%-Ebene
  - Beispiel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
