---
title: Übersicht über Datenquellen
description: Erfahren Sie, wie Sie Daten aus verschiedenen Quellen importieren oder aufnehmen.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 6ab97c535454e84c1bb18aca00bca2568eb65a2a
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207090"
---
# <a name="data-sources-overview"></a>Übersicht über Datenquellen

Dynamics 365 Customer Insights stellt eine Verbindung zu Daten aus einer breiten Palette von Quellen her. Das Herstellen einer Verbindung zu einem Datenquelle wird häufig als Prozess von *Datenerfassung* bezeichnet. Nachdem Sie die Daten aufgenommen haben, können Sie die Daten [vereinheitlichen](data-unification.md), Erkenntnisse generieren und die Daten für den Aufbau personalisierter Erlebnisse aktivieren.

## <a name="add-or-edit-data-sources"></a>Datenquellen hinzufügen oder bearbeiten

Sie können Datenquellen in Customer Insights anhängen oder importieren. Die folgenden Links enthalten Anweisungen zum Hinzufügen und Bearbeiten von Datenquellen.

**Eine Datenquelle einblenden**

Wenn Sie Daten in einem der Azure-Datendienste von Microsoft vorbereitet haben, kann Customer Insights problemlos eine Verbindung zu Datenquelle herstellen, ohne die Daten erneut erfassen zu müssen. Wählen Sie eine der folgenden Optionen aus:
- [Azure Data Lake Storage (CSV- oder Parquet-Dateien in einem Common Data Model-Ordner)](connect-common-data-model.md)
- [Azure Synapse Analytics (Lake Datenbanken)](connect-synapse.md)
- [Microsoft Dataverse Data Lake](connect-dataverse-managed-lake.md)

**Importieren und transformieren**

Wenn Sie lokale Datenquellen, Microsoft- oder Drittanbieterdaten verwenden, importieren und transformieren Sie die Daten mithilfe von Power Query Konnektoren.
- [Power Query-Connectors](connect-power-query.md)

## <a name="review-data-sources"></a>Datenquellen bewerten

Wenn Ihre Umgebung für die Verwendung von Customer Insights-Speicher konfiguriert wurde und Sie lokale Datenquellen verwenden, verwenden Sie Power Platform Dataflows. Mit Power Platform Dataflows können Sie freigegebene Datenquellen und von anderen verwaltete Datenquellen anzeigen. Die Seite **Datenquellen** listet die Datenquellen in drei Abschnitten auf:
- **Geteilt**: Datenquellen, die von allen Customer Insights-Administratoren verwaltet werden können. Power Platform Dataflows, Ihr eigenes Speicherkonto und das Anhängen an einen Dataverse verwaltete Data Lake sind Beispiele für gemeinsam genutzte Datenquellen.
- **Von mir verwaltet**: Power Platform Dataflows erstellt und können nur von Ihnen verwaltet werden. Andere Customer Insights-Administratoren können diese Datenflows nur anzeigen, aber nicht bearbeiten, aktualisieren oder löschen.
- **Von anderen verwaltet**: Power Platform Dataflows, die von anderen Administratoren erstellt wurden. Sie können sie nur anzeigen. Fürt den Besitzer des Dataflows auf, an den Sie sich für Unterstützung wenden können.
> [!NOTE]
> Alle Entitäten können von anderen Benutzern angezeigt und verwendet werden. Während Datenquellen dem Benutzer gehören, der sie erstellt hat, können die aus der Datenaufnahme resultierenden Entitäten von jedem Benutzer von Customer Insights verwendet werden.

Wenn Ihre Umgebung keine Power Platform Dataflows verwendet, enthält die Seite **Datenquellen** nur eine Liste aller Datenquellen. Keine Abschnitte angezeigt.

## <a name="manage-existing-data-sources"></a>Vorhandene Datenquellen verwalten

Gehen Sie zu **Daten** > **Datenquellen**, um den Namen für jede aufgenommene Datenquelle, den Status und das letzte Mal, dass die Daten für diese Datenquelle aktualisiert wurden, anzuzeigen. Sie können die Liste der Datenquellen nach einer beliebigen Spalte sortieren oder das Suchfeld verwenden, um die Datenquellen zu finden, die Sie verwalten möchten.

Wählen Sie die Datenquellen aus, um verfügbare Aktionen anzuzeigen.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Datenquelle hinzugefügt":::

- [**Bearbeiten**](#add-or-edit-data-sources) der Datenquelle, um seine Eigenschaften zu ändern.
- [**Aktualisieren**](#refresh-data-sources) der Datenquelle, um die neuesten Daten einzuschließen.
- [**Reichern**](data-sources-enrichment.md) Sie Datenquellen vor der Vereinheitlichung an.
- **Löschen** der Datenquelle. Ein Datenquelle kann nur gelöscht werden, wenn die Daten in keiner Verarbeitung wie Vereinheitlichung, Einblicke, Aktivierungen oder Exporte verwendet werden.

## <a name="refresh-data-sources"></a>Datenquellen aktualisieren

Datenquellen können nach einem automatischen Zeitplan oder manuell bei Bedarf aufgefrischt werden. [Lokale Datenquellen](connect-power-query.md#add-data-from-on-premises-data-sources) Aktualisierung nach ihren eigenen Zeitplänen, die während der Datenaufnahme eingerichtet werden. Für angehängte Datenquellen verbraucht die Datenaufnahme die neuesten Daten, die von diesem Datenquelle verfügbar sind.

Gehen Sie zu **Administrator** > **System** > [**Zeitplan**](system.md#schedule-tab), um vom System geplante Aktualisierungen Ihrer aufgenommenen Datenquellen zu konfigurieren.

Aktualisieren einer Datenquelle bei Bedarf:

1. Wechseln Sie zu **Daten** > **Datenquellen**.

1. Wählen Sie die Datenquelle aus, die Sie aktualisieren möchten, und wählen Sie sie aus **Aktualisierung**. Die Datenquelle wird jetzt für eine manuelle Aktualisierung ausgelöst. Durch das Aktualisieren eines Datenquelle werden sowohl das Entitätsschema als auch die Daten für alle im Datenquelle angegebenen Entitäten aktualisiert.

1. Wählen Sie den Status aus, um den Bereich **Fortschrittsdetails** zu öffnen und den Fortschritt des Prozesses anzuzeigen. Um den Auftrag abzubrechen, wählen Sie **Auftrag abbrechen** am unteren Rand des Bereichs.

[!INCLUDE [footer-include](includes/footer-banner.md)]
