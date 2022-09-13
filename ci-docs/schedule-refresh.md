---
title: Systemaktualisierung planen
description: Planen Sie den Zeitpunkt ein, zu dem das System aktualisiert werden soll
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 949ea071ca41127b0c45488d5d7af3f6aa4e1c35
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2022
ms.locfileid: "9395955"
---
# <a name="schedule-system-refresh"></a>Systemaktualisierung planen

Planen Sie automatische Aktualisierungen aller Ihrer [eingespeicherten Datenquellen](data-sources.md) zu planen. Automatische Aktualisierungen sorgen dafür, dass Aktualisierungen aus Ihren Datenquellen in Ihren einheitlichen Kundenprofilen berücksichtigt werden.

> [!NOTE]
> Von Ihnen verwaltete Power Query-Datenquellen werden nach ihren eigenen Zeitplänen aktualisiert. Um die Aktualisierung der von Ihnen verwalteten Power Query-Datenquellen zu planen, konfigurieren Sie die Aktualisierungseinstellungen für dieses bestimmte Datenquelle über die Seite **Datenquellen**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Dataflow-Aktualisierungseinstellungen.":::

## <a name="set-system-refresh-schedule"></a>Systemaktualisierungsplan festlegen

1. Gehen Sie zu **Admin** > **System** und wählen Sie die Registerkarte **Planung**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Registerkarte „Aktualisierung planen“ auf der Seite „System“.":::

1. Der Standardstatus für die geplante Aktualisierung ist **Aus**. Um die zeitgesteuerte Aktualisierung zu aktivieren, ändern Sie den Schalter am oberen Bildschirmrand auf **Ein**.

1. Wählen Sie zwischen **Wöchentlich** (Standard) und **Täglich** Aktualisierung. Wenn Sie beabsichtigen, wöchentliche Aktualisierungen zu planen, wählen Sie einen oder mehrere Tage aus, an denen Sie die Aktualisierung ausführen möchten.

1. Stellen Sie Ihre **Zeitzone** ein und verwenden Sie dann die Dropdown-Liste **Zeit**, um Ihr Aktualisierungs-Timing einzustellen. Wenn Sie mehrere Aktualisierungen an einem einzigen Tag planen möchten, wählen Sie **Andere Zeit hinzufügen**. Sie können bis zu vier Aktualisierungen hinzufügen.

1. Wählen Sie **Speichern**, um Ihre Änderungen zu übernehmen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
