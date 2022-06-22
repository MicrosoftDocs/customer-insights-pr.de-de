---
title: Customer Insights-Daten zu Azure Data Lake Storage Gen2 exportieren
description: Lernen Sie, wie Sie die Verbindung zu Azure Data Lake Storage Gen2 konfigurieren.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22eee11666752459a1750d728c4e254ab0c59e58
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947229"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Segmentliste und andere Daten exportieren nach Azure Data Lake Storage Gen2 (Vorschau)

Speichern Sie Ihre Customer Insights Daten in einem Data Lake Storage Gen2 Konto, oder verwenden Sie es, um Ihre Daten in andere Anwendungen zu übertragen.

## <a name="known-limitations"></a>Bekannte Einschränkungen

1. Für Azure Data Lake Storage Gen2 können Sie zwischen [Standardleistungs- und Premiumleistungsstufe](/azure/storage/blobs/create-data-lake-storage-account) wählen, wenn Sie ein Speicherkonto für Ihren Data Lake erstellen. Wenn Sie sich für die Premium-Leistungsstufe entscheiden, wählen Sie die Premium-Block-Blobs als Kontotyp aus.

## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Richten Sie die Verbindung mit Azure Data Lake Storage Gen2 ein

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und dann **Azure Data Lake Gen 2** aus, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie **Kontobezeichnung**, **Kontoschlüssel** und **Container** für den Azure Data Lake Storage Gen2 ein.
    - Erfahren Sie, wie Sie ein Speicherkonto erstellen, das Sie mit Azure Data Lake Storage Gen2 verwenden können, unter [Speicherkonto erstellen](/azure/storage/blobs/create-data-lake-storage-account). 
    - Weitere Informationen zum Azure Data Lake Gen 2-Kontonamen und Kontoschlüssel finden Sie unter [Verwalten Sie die Speicherkontoeinstellungen im Azure-Portal](/azure/storage/common/storage-account-manage).

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Um einen neuen Export zu erstellen, wählen Sie **Export hinzufügen** aus.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem **Azure Data Lake**-Abschnitt aus. Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. Aktivieren Sie das Kontrollkästchen neben jeder der Entitäten, die Sie an dieses Ziel exportieren möchten.

1. Wählen Sie **Speichern** aus.

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.
Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).

Exportierte Daten werden in dem von Ihnen konfigurierten Azure Data Lake Gen 2-Speichercontainer gespeichert.

> [!TIP]
> Der Export von Entitäten, die eine große Datenmenge enthalten, kann bei jedem Export zu mehreren CSV-Dateien im selben Ordner führen. Das Aufteilen von Exporten erfolgt aus Leistungsgründen, um die Zeit zu minimieren, die für den Abschluss eines Exports benötigt wird.

[!INCLUDE [footer-include](includes/footer-banner.md)]
