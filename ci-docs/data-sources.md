---
title: Übersicht über Datenquellen
description: Erfahren Sie, wie Sie Daten aus verschiedenen Quellen importieren oder aufnehmen.
ms.date: 05/18/2022
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
ms.openlocfilehash: fbe44f655bdbc20ef7f0956022395e2dcb570adf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051452"
---
# <a name="data-sources-overview"></a>Übersicht über Datenquellen

Dynamics 365 Customer Insights stellt eine Verbindung zu Daten aus einer breiten Palette von Quellen her. Das Herstellen einer Verbindung zu einem Datenquelle wird häufig als Prozess von *Datenerfassung* bezeichnet. Nachdem Sie die Daten aufgenommen haben, können Sie die Daten [vereinheitlichen](data-unification.md), Erkenntnisse generieren und die Daten für den Aufbau personalisierter Erlebnisse aktivieren.

## <a name="add-data-sources"></a>Datenquellen hinzufügen

Sie können Datenquellen in Customer Insights anhängen oder importieren. Die folgenden Links enthalten Anweisungen zum Hinzufügen von Datenquellen.

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

Gehen Sie zu **Daten** > **Datenquellen**, um den Namen für jede aufgenommene Datenquelle, den Status und das letzte Mal, dass die Daten für diese Datenquelle aktualisiert wurden, anzuzeigen. Sie können die Liste der Datenquellen nach jeder Spalte sortieren.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Datenquelle hinzugefügt":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Das Laden von Daten kann einige Zeit in Anspruch nehmen. Nach einer erfolgreichen Aktualisierung können die aufgenommenen Daten von der Seite **Entitäten** überprüft werden. Weitere Informationen finden Sie unter [Entitäten](entities.md).

## <a name="refresh-data-sources"></a>Datenquellen aktualisieren

Datenquellen können nach einem automatischen Zeitplan oder manuell bei Bedarf aufgefrischt werden. [Lokale Datenquellen](connect-power-query.md#add-data-from-on-premises-data-sources) Aktualisierung nach ihren eigenen Zeitplänen, die während der Datenaufnahme eingerichtet werden. Für angehängte Datenquellen verbraucht die Datenaufnahme die neuesten Daten, die von diesem Datenquelle verfügbar sind.

Gehen Sie zu **Administrator** > **System** > [**Zeitplan**](system.md#schedule-tab), um vom System geplante Aktualisierungen Ihrer aufgenommenen Datenquellen zu konfigurieren.

Um eine Datenquelle bei Bedarf zu aktualisieren, folgen Sie diesen Schritten:

1. Wechseln Sie zu **Daten** > **Datenquellen**.

1. Wählen Sie die vertikalen Auslassungspunkte (&vellip;) neben dem Datenquelle, die Sie ändern möchten, und wählen Sie **Aktualisieren** aus dem Dropdown-Menü. Die Datenquelle wird jetzt für eine manuelle Aktualisierung ausgelöst. Durch das Aktualisieren eines Datenquelle werden sowohl das Entitätsschema als auch die Daten für alle im Datenquelle angegebenen Entitäten aktualisiert.

1. Wählen Sie **Auffrischung stoppen**, wenn Sie eine bestehende Auffrischung abbrechen wollen und die Datenquelle in ihren letzten Auffrischungsstatus zurückkehren soll.

## <a name="delete-a-data-source"></a>Löschen einer Datenquelle

Ein Datenquelle kann nur gelöscht werden, wenn die Daten in keiner Verarbeitung wie Vereinheitlichung, Einblicke, Aktivierungen oder Exporte verwendet werden.

1. Wechseln Sie zu **Daten** > **Datenquellen**.

2. Wählen Sie die vertikalen Auslassungspunkte (&vellip;) neben dem Datenquelle, die Sie entfernen möchten, und wählen Sie **Löschen** aus dem Dropdown-Menü.

3. Bestätigen Sie den Löschvorgang.


[!INCLUDE [footer-include](includes/footer-banner.md)]
