---
title: Customer Insights-Daten nach InMobi exportieren
description: Weitere Informationen zum Konfigurieren der Verbindung und zum Exportieren nach InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9056541"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Segmentliste und andere Daten exportieren nach InMobi (Vorschauversion)

Exportieren Sie Segmentlisten oder andere Daten aus Ihrer Customer Insights-Instanz nach [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Anforderungen

1. Sie haben ein [InMobi-Konto](https://www.inmobi.com/) und Admin-Anmeldeinformationen.
1. Sie haben einen Azure Blob Storage-Kontonamen und den entsprechenden Kontoschlüssel. Weitere Informationen finden Sie unter [Verwalten von Speicherkontoeinstellungen im Azure-Portal](/azure/storage/common/storage-account-manage). Es gibt einen Container im Speicherkonto, in den inMobi-Daten exportiert werden können. Weitere Informationen finden Sie unter [Erstellen von Containern](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi stellt eine direkte Verbindung zu Ihrem Blob-Speicher her und konfiguriert einen automatischen Import Ihrer Daten in InMobi. Wenden Sie sich an Ihren InMobi-Vertreter, um den Vorgang einzuleiten.

## <a name="known-limitations"></a>Bekannte Einschränkungen

1. Für Azure Blob Storage können Sie zwischen [Standardleistungs- und Premiumleistungsstufe](/azure/storage/blobs/storage-blob-performance-tiers) wählen. Wenn Sie sich für die Premium-Leistungsstufe entscheiden, wählen Sie die [Premium-Block-Blobs als Kontotyp](/azure/storage/common/storage-account-overview#types-of-storage-accounts) aus.

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Richten Sie die Verbindung zu Azure Blob Storage ein und konfigurieren Sie einen Export

1. Befolgen Sie die Anweisungen zum [Einrichten einer Verbindung zu Ihrem Azure Blob Storage](export-azure-blob-storage.md).
2. Befolgen Sie die Anweisungen zum [Konfigurieren eines Exports](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
