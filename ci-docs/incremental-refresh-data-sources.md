---
title: Inkrementelle Aktualisierung für Power Query und Azure Data Lake-Datenquellen
description: Aktualisieren Sie neue und aktualisierte Daten für große Datenquellen basierend auf Power Query oder Azure Data Lake-Datenquellen.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: de39743eb8728fac34e417724c5f73bf44309c89
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207136"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Inkrementelle Aktualisierung für Power Query und Azure Data Lake-Datenquellen

Die inkrementelle Aktualisierung von Datenquellen basierend auf Power Query oder Azure Data Lake bietet die folgenden Vorteile:

- **Schneller aktualisiert** – Nur geänderte Daten werden aktualisiert. Beispielsweise können Sie nur die letzten fünf Tage eines historischen DataSet aktualisieren.
- **Erhöhte Zuverlässigkeit** – Bei kleineren Aktualisierungen müssen Sie die Verbindungen zu flüchtigen Quellsystemen nicht so lange aufrechterhalten, um das Risiko von Verbindungsproblemen zu verringern.
- **Reduzierter Ressourcenverbrauch** – Das Aktualisieren nur einer Teilmenge Ihrer Gesamtdaten führt zu einer effizienteren Nutzung der Computerressourcen und verringert den ökologischen Fußabdruck.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Inkrementelle Aktualisierung für auf Power Query basierenden Datenquellen konfigurieren

Customer Insights lässt eine inkrementelle Aktualisierung für Datenquellen zu, die über Power Query importiert wurden und eine inkrementelle Einbindung unterstützen. Azure SQL-Datenbanken mit Datums- und Zeitfeldern geben beispielsweise an, wann Datensätze zuletzt aktualisiert wurden.

1. [Erstellen Sie eine neue Datenquelle basierend auf Power Query.](connect-power-query.md)

1. Wählen Sie eine Datenquelle aus, die inkrementelle Aktualisierungen unterstützt, z. B. [Azure SQL-Datenbank](/power-query/connectors/azuresqldatabase).

1. Wählen Sie die Entitäten oder Tabellen aus, die erfasst werden sollen.

1. Schließen Sie die Transformationsschritte ab und wählen Sie **Nächster**.

1. In dem **Richten Sie eine inkrementelle Aktualisierung ein** Dialogfeld wählen Sie **Konfiguration**, um die **Inkrementelle Aktualisierungseinstellungen** zu öffnen. Wenn Sie **Überspringen** auswählen, aktualisiert die Datenquelle das gesamte Dataset.
   > [!TIP]
   > Sie können die inkrementelle Aktualisierung auch später anwenden, indem Sie ein vorhandenes Datenquelle bearbeiten.

1. Auf **Inkrementelle Aktualisierungseinstellungen** konfigurieren Sie die inkrementelle Aktualisierung für alle Entitäten, die Sie beim Erstellen des Datenquelle ausgewählt haben.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Inkrementelle Aktualisierungseinstellungen konfigurieren.":::

1. Wählen Sie eine Entität aus und geben Sie die folgenden Details an:

   - **Definieren Sie den Primärschlüssel**: Wählen Sie einen Primärschlüssel für die Entität oder Tabelle aus.
   - **Definieren Sie das Feld Zuletzt aktualisiert** : In diesem Feld werden nur Attribute vom Typ Datum oder Uhrzeit angezeigt. Wählen Sie ein Attribut aus, das angibt, wann die Datensätze zuletzt aktualisiert wurden. Es wird verwendet, um die Datensätze zu identifizieren, die in den inkrementellen Aktualisierungszeitrahmen fallen.
   - **Nach Updates suche, alle** : Geben Sie an, wie lange der Zeitrahmen für die inkrementelle Aktualisierung dauern soll.

1. Wählen Sie **speichern**, um die Erstellung des Datenquelle abzuschließen. Die anfängliche Datenaktualisierung ist eine vollständige Aktualisierung. Anschließend erfolgt die inkrementelle Datenaktualisierung wie im vorherigen Schritt konfiguriert.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Inkrementelle Aktualisierung für Azure Data Lake-Datenquellen konfigurieren

Customer Insights ermöglicht eine inkrementelle Aktualisierung für verbundene Datenquellen mit Azure Data Lake Storage. Um die inkrementelle Aufnahme und Aktualisierung für eine Entität zu verwenden, konfigurieren Sie diese Entität beim Hinzufügen von Azure Data Lake Datenquelle oder später beim Bearbeiten von Datenquelle. Der Entitätsdatenordner muss die folgenden Ordner enthalten:

- Der Ordner **FullData** mit Datendateien mit Anfangsdatensätzen
- **IncrementalData**: Ordner mit Datum/Uhrzeit-Hierarchieordnern in **jjjj/mm/tt/hh** Format, das die inkrementellen Updates enthält. **hh** stellt die UTC-Stunde der Updates dar und enthält die **Upserts** und **Löschen** Ordner. **Upserts** enthält Datendateien mit Aktualisierungen bestehender Datensätze oder neuer Datensätze. **Löscht** enthält Datendateien mit Datensätzen, die entfernt werden sollen.

1. Navigieren Sie beim Hinzufügen oder Bearbeiten eines Datenquelle zum Bereich **Attribute** für die Entität.

1. Atribute bewerten. Stellen Sie sicher, dass ein erstelltes oder zuletzt aktualisiertes Datumsattribut mit einem *dateTime* **Dateiformat** und einem *Kalender.Date* **Semantischem Typ** eingerichtet ist. Bearbeiten Sie ggf. das Attribut und wählen Sie **Fertig**.

1. Von dem Bereich **Wählen Sie Entitäten aus** bearbeiten Sie die Entität. Das **Inkrementelle Erfassung** Kontrollkästchen ist aktiviert.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Konfigurieren Sie Entitäten in einem Datenquelle für die inkrementelle Aktualisierung.":::

   1. Navigieren Sie zum Stammordner, der die .csv- oder .parquet-Dateien für vollständige Daten, inkrementelle Daten-Upserts und inkrementelle Datenlöschungen enthält.
   1. Geben Sie die Erweiterung für die vollständigen Daten und beide inkrementellen Dateien ein (\.csv bzw \.Parquet).
   1. Wählen Sie für .csv-Dateien das Spaltentrennzeichen und wenn Sie die erste Zeile der Datei als Spaltenüberschrift haben möchten.
   1. Wählen Sie **Save** (Speichern).

1. Für **Zuletzt aktualisiert** wählen Sie das Attribut date timestamp aus.

1. Wenn der **Primärschlüssel** nicht ausgewählt ist, wählen Sie den Primärschlüssel aus. Der Primärschlüssel ist ein für die Entität eindeutiges Attribut. Damit ein Attribut ein gültiger Primärschlüssel ist, sollte es keine doppelten Werte, fehlenden Werte oder Nullwerte enthalten. Als Primärschlüssel werden String-, Integer- und GUID-Datentypattribute unterstützt.

1. Wählen Sie **Schließen**, um den Bereich zu speichern und zu schließen.

1. Fahren Sie mit dem Hinzufügen oder Bearbeiten der Datei Datenquelle fort.

[!INCLUDE [footer-include](includes/footer-banner.md)]
