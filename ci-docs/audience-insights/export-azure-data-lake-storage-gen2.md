---
title: Customer Insights-Daten zu Azure Data Lake Storage Gen2 exportieren
description: Lernen Sie, wie Sie die Verbindung zu Azure Data Lake Storage Gen2 konfigurieren.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596636"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Konnektor für Azure Data Lake Storage Gen2 (Vorschau)

Speichern Sie Ihre Customer Insights-Daten in Azure Data Lake Storage Gen2, oder verwenden Sie es, um Ihre Daten in andere Anwendungen zu übertragen.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Konfigurieren Sie den Konnektor für Azure Data Lake Storage Gen2

1. Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Ziele exportieren**.

1. Unter **Azure Data Lake Storage Gen2** wählen Sie **Einrichten**.

1. Geben Sie Ihrem Ziel einen erkennbaren Namen im Feld **Anzeigename**.

1. Geben Sie **Kontobezeichnung**, **Kontoschlüssel** und **Container** für den Azure Data Lake Storage Gen2 ein.
    - Erfahren Sie, wie Sie ein Speicherkonto erstellen, das Sie mit Azure Data Lake Storage Gen2 verwenden können, unter [Speicherkonto erstellen](/azure/storage/blobs/create-data-lake-storage-account). 
    - Weitere Informationen zum Ermitteln des Azure Data Lake Gen2-Speicherkontonamens und des Kontoschlüssels finden Sie unter [Verwalten Sie die Speicherkontoeinstellungen im Azure-Portal](/azure/storage/common/storage-account-manage).

1. Klicken Sie auf **Weiter**.

1. Aktivieren Sie das Kontrollkästchen neben jeder der Entitäten, die Sie an dieses Ziel exportieren möchten.

1. Wählen Sie **Speichern** aus.

## <a name="export-the-data"></a>Exportieren der Daten

Sie könenn [Daten nach Bedarf exportieren](export-destinations.md#export-data-on-demand). Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.