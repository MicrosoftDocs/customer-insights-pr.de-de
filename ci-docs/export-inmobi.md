---
title: Customer Insights-Daten nach InMobi exportieren
description: Weitere Informationen zum Konfigurieren der Verbindung und zum Exportieren nach InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195887"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Customer Insights-Daten nach InMobi exportieren (Vorschau)

Exportieren Sie Segmentlisten oder andere Daten aus Ihrer Customer Insights-Instanz nach [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Anforderungen

- Ein [InMobi-Konto](https://www.inmobi.com/) und Admin-Anmeldeinformationen.
- Ein [Azure Blob Storage-Konto](/azure/storage/blobs/create-data-lake-storage-account) Name und Kontoschlüssel. Zum Ermitteln des Namens und des Schlüssels finden Sie unter [Verwalten Sie die Speicherkontoeinstellungen im Azure-Portal](/azure/storage/common/storage-account-manage).
- Ein [Azure Blob Storage Container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) zum Exportieren von InMobi-Daten.
- InMobi stellt eine direkte Verbindung zu Ihrem Blob-Speicher her und konfiguriert einen automatischen Import Ihrer Daten in InMobi. Wenden Sie sich an Ihren InMobi-Vertreter, um den Vorgang einzuleiten.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Für Azure Blob Storage können Sie zwischen [Standardleistungs- und Premiumleistungsstufe](/azure/storage/blobs/storage-blob-performance-tiers) wählen. Wenn Sie sich für die Premium-Leistungsstufe entscheiden, wählen Sie die [Premium-Block-Blobs als Kontotyp](/azure/storage/common/storage-account-overview#types-of-storage-accounts) aus.

## <a name="set-up-connection-to-azure-blob-storage"></a>Richten Sie die Verbindung mit Azure Blob Storage ein

[Richten Sie die Verbindung mit Azure Blob Storage ein](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[Konfigurieren Sie einen Export](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
