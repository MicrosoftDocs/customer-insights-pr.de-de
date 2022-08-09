---
title: Daten in Azure Data Lake Storage Gen2 exportieren (Vorschauversion)
description: Lernen Sie, wie Sie die Verbindung zu Azure Data Lake Storage Gen2 konfigurieren.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196439"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Daten in Azure Data Lake Storage Gen2 exportieren (Vorschauversion)

Speichern Sie Ihre Customer Insights Daten in einem Data Lake Storage Gen2 Konto, oder verwenden Sie es, um Ihre Daten in andere Anwendungen zu übertragen.

## <a name="prerequisites"></a>Anforderungen

- Ein [Speicherkonto zur Verwendung mit Azure Data Lake Gen 2](/azure/storage/blobs/create-data-lake-storage-account). Zum Ermitteln des Blob Storage Kontonamens und des Kontoschlüssels finden Sie unter [Verwalten Sie die Speicherkontoeinstellungen im Azure-Portal](/azure/storage/common/storage-account-manage).
- Ein [Azure Blob Storage Container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)

## <a name="known-limitations"></a>Bekannte Einschränkungen

- For Azure Data Lake Storage Gen2 können Sie zwischen wählen [Standardleistungs- und Premiumleistungsstufe](/azure/storage/blobs/create-data-lake-storage-account). Wenn Sie sich für die Premium-Leistungsstufe entscheiden, wählen Sie die [Premium-Block-Blobs als Kontotyp](/azure/storage/common/storage-account-overview#types-of-storage-accounts) aus.

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Richten Sie die Verbindung mit Azure Data Lake Storage Gen2 ein

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Azure Data Lake Gen 2**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie **Kontobezeichnung**, **Kontoschlüssel** und **Container** für den Azure Data Lake Storage Gen2 ein.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Abschnitt Azure Data Lake aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. Geben Sie den Ordnernamen für den Azure Data Lake Storage Gen2 Speicher ein.

1. Aktivieren Sie das Kontrollkästchen neben jeder der Entitäten, die Sie an dieses Ziel exportieren möchten.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Exportierte Daten werden in dem von Ihnen konfigurierten Azure Data Lake Gen 2-Speichercontainer gespeichert.

> [!TIP]
> Der Export von Entitäten, die eine große Datenmenge enthalten, kann bei jedem Export zu mehreren CSV-Dateien im selben Ordner führen. Das Aufteilen von Exporten erfolgt aus Leistungsgründen, um die Zeit zu minimieren, die für den Abschluss eines Exports benötigt wird.

[!INCLUDE [footer-include](includes/footer-banner.md)]
