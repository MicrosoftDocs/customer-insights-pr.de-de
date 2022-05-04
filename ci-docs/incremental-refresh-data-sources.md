---
title: Inkrementelle Aktualisierung für Power Query-basierte Datenquellen
description: Aktualisieren Sie neue und aktualisierte Daten für große Datenquellen basierend auf Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 3d21baf9804f300802b066df0183fc8f01abba9a
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647183"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Inkrementelle Aktualisierung für auf Power Query basierenden Datenquellen

In diesem Artikel wird erläutert, wie die inkrementelle Aktualisierung für Datenquellen basierend auf Power Query konfiguriert wird.

Die inkrementelle Aktualisierung für Datenquellen bietet die folgenden Vorteile:

- **Schneller aktualisiert** – Nur geänderte Daten werden aktualisiert. Beispielsweise können Sie nur die letzten fünf Tage eines historischen DataSet aktualisieren.
- **Erhöhte Zuverlässigkeit** – Bei kleineren Aktualisierungen müssen Sie die Verbindungen zu flüchtigen Quellsystemen nicht so lange aufrechterhalten, um das Risiko von Verbindungsproblemen zu verringern.
- **Reduzierter Ressourcenverbrauch** – Das Aktualisieren nur einer Teilmenge Ihrer Gesamtdaten führt zu einer effizienteren Nutzung der Computerressourcen und verringert den ökologischen Fußabdruck.

## <a name="configure-incremental-refresh"></a>Inkrementelle Aktualisierung konfigurieren

Customer Insights lässt eine inkrementelle Aktualisierung für Datenquellen zu, die über Power Query importiert wurden und eine inkrementelle Einbindung unterstützen. Azure SQL-Datenbanken mit Datums- und Zeitfeldern geben beispielsweise an, wann Datensätze zuletzt aktualisiert wurden.

1. [Erstellen Sie eine neue Datenquelle basierend auf Power Query.](connect-power-query.md)

1. Geben Sie dann einen **Namen** für die Datenquelle ein.

1. Wählen Sie eine Datenquelle aus, die inkrementelle Aktualisierungen unterstützt, z. B. [Azure SQL-Datenbank](/power-query/connectors/azuresqldatabase).

1. Wählen Sie die Entitäten oder Tabellen aus, die erfasst werden sollen.

1. Schließen Sie die Transformationsschritte ab und wählen Sie **Nächster**.

1. In dem **Richten Sie eine inkrementelle Aktualisierung ein** Dialogfeld wählen Sie **Konfiguration**, um die **Inkrementelle Aktualisierungseinstellungen** zu öffnen. Wenn Sie **Überspringen** auswählen, aktualisiert die Datenquelle das gesamte Dataset.
   > [!TIP]
   > Sie können die inkrementelle Aktualisierung auch später anwenden, indem Sie ein vorhandenes Datenquelle bearbeiten.

1. Auf **Inkrementelle Aktualisierungseinstellungen** konfigurieren Sie die inkrementelle Aktualisierung für alle Entitäten, die Sie beim Erstellen des Datenquelle ausgewählt haben.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigurieren Sie Entitäten in einem Datenquelle für die inkrementelle Aktualisierung.":::

1. Wählen Sie eine Entität aus und geben Sie die folgenden Details an:

   - **Definieren Sie den Primärschlüssel**: Wählen Sie einen Primärschlüssel für die Entität oder Tabelle aus.
   - **Definieren Sie das Feld Zuletzt aktualisiert** : In diesem Feld werden nur Attribute vom Typ Datum oder Uhrzeit angezeigt. Wählen Sie ein Attribut aus, das angibt, wann die Datensätze zuletzt aktualisiert wurden. Es wird verwendet, um die Datensätze zu identifizieren, die in den inkrementellen Aktualisierungszeitrahmen fallen.
   - **Nach Updates suche, alle** : Geben Sie an, wie lange der Zeitrahmen für die inkrementelle Aktualisierung dauern soll.

1. Wählen Sie **speichern**, um die Erstellung des Datenquelle abzuschließen. Die anfängliche Datenaktualisierung ist eine vollständige Aktualisierung. Anschließend erfolgt die inkrementelle Datenaktualisierung wie im vorherigen Schritt konfiguriert.


[!INCLUDE [footer-include](includes/footer-banner.md)]
