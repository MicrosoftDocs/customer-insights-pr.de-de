---
title: Exportieren von Daten in einen Azure Blob Storage (Vorschauversion)
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zum Azure Blob Storage exportieren.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195703"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Exportieren von Daten in einen Azure Blob Storage (Vorschauversion)

Speichern Sie Ihre Customer Insights-Daten in einem Azure Blob Storage, oder verwenden Sie es, um Ihre Daten in andere Anwendungen zu übertragen.

## <a name="prerequisites"></a>Anforderungen

- Ein [Azure Blob Storage-Konto](/azure/storage/blobs/create-data-lake-storage-account) Name und Kontoschlüssel. Zum Ermitteln des Namens und des Schlüssels finden Sie unter [Verwalten Sie die Speicherkontoeinstellungen im Azure-Portal](/azure/storage/common/storage-account-manage).
- Ein [Azure Blob Storage Container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Für Azure Blob Storage können Sie zwischen [Standardleistungs- und Premiumleistungsstufe](/azure/storage/blobs/storage-blob-performance-tiers) wählen. Wenn Sie sich für die Premium-Leistungsstufe entscheiden, wählen Sie die [Premium-Block-Blobs als Kontotyp](/azure/storage/common/storage-account-overview#types-of-storage-accounts) aus.

## <a name="set-up-connection-to-blob-storage"></a>Richten Sie die Verbindung mit Blob Storage ein

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Azure Blob Storage**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie **Kontobezeichnung**, **Kontoschlüssel** und **Container** für Ihr Blob Storage-Konto ein.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Um diesen Export zu konfigurieren, müssen Sie eine [Genehmigung](export-destinations.md#set-up-a-new-export) für diese Verbindungsart haben.

> [!IMPORTANT]
> Wenn Sie die Einstellung für [vorläufiges Löschen](/azure/storage/blobs/soft-delete-blob-enable) für das Azure Blob Storage-Konto aktiviert haben, schlagen Exporte fehl. Deaktivieren Sie das vorläufige Löschen, um Daten in Blobs zu exportieren.

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Azure Blob Storage-Abschnitt aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. Geben Sie den Ordnernamen für den Blobspeicher ein.

1. Aktivieren Sie das Kontrollkästchen neben jeder der Entitäten, die Sie an dieses Ziel exportieren möchten.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Exportierte Daten werden in dem von Ihnen konfigurierten Blob Storage-Container gespeichert. Die folgenden Ordnerpfade werden automatisch in Ihrem Container erstellt:

- Für Quell-Entitäten und vom System generierte Entitäten:  
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Beispiel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Der Export von Entitäten, die eine große Datenmenge enthalten, kann bei jedem Export zu mehreren CSV-Dateien im selben Ordner führen. Das Aufteilen von Exporten erfolgt aus Leistungsgründen, um die Zeit zu minimieren, die für den Abschluss eines Exports benötigt wird.

- Das model.json für die exportierten Entitäten befindet sich auf der *%ExportDestinationName%*-Ebene.  
  
  Beispiel Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
