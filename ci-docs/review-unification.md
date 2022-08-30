---
title: Überprüfen der Datenvereinheitlichung
description: Überprüfen Sie die Schritte zur Datenvereinheitlichung, erstellen Sie einheitliche Kundenprofile und überprüfen Sie die Ergebnisse
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303966"
---
# <a name="review-data-unification"></a>Überprüfen der Datenvereinheitlichung

Überprüfen Sie die Zusammenfassung der Änderungen, erstellen Sie das einheitliche Profil und überprüfen Sie die Ergebnisse.

## <a name="review-and-create-customer-profiles"></a>Kundenprofile überprüfen und erstellen

Dieser letzte Schritt im Vereinheitlichungsprozess zeigt eine Zusammenfassung der Schritte im Prozess und bietet die Möglichkeit, Änderungen vorzunehmen, bevor Sie das vereinheitlichte Profil erstellen.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Screenshot von „Kundenprofile überprüfen und erstellen“.":::

1. Wählen Sie **Bearbeiten** bei allen Datenvereinheitlichungsschritten, um sie zu überprüfen und Änderungen vorzunehmen.

1. Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **Kundenprofile erstellen** (oder **Kontoprofile erstellen** für B-to-B). Die Seite **Vereinheitlichen** wird angezeigt, während das Unified customer profile erstellt wird.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Screenshot der Seite Unify mit Kacheln, die In Warteschlange gestellt oder Aktualisieren anzeigen.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Es dauert einige Zeit, bis der Vereinigungsalgorithmus abgeschlossen ist, und Sie können die Konfiguration nicht ändern, bis er abgeschlossen ist.

## <a name="view-the-results-of-data-unification"></a>Ergebnisse der Datenvereinheitlichung anzeigen

Nach der Vereinigung zeigt die Seite **Daten** > **Vereinheitlichen** die Anzahl der einheitlichen Kundenprofile (oder Kontoprofilen für B-to-B) an. Die Ergebnisse jedes Schritts im Vereinigungsprozess werden auf jeder Kachel angezeigt. Zum Beispiel enthält **Quellfelder** die Anzahl der zugeordneten Attribute (Felder) und **Doppelte Datensätze** zeigt die Anzahl der gefundenen doppelten Datensätze.

:::image type="content" source="media/m3_unified.png" alt-text="Screenshot der Seite zur Vereinheitlichung von Daten, nachdem die Daten vereinheitlicht wurden.":::

> [!TIP]
> Die Kachel **Abgleich-Bedingungen** wird nur angezeigt, wenn mehrere Entitäten ausgewählt wurden.

Wir empfehlen Ihnen, die Ergebnisse zu überprüfen, insbesondere die Qualität Ihrer [Abgleich-Bedingungen](data-unification-update.md#manage-match-rules), und sie ggf. zu verfeinern.

Wenn erforderlich, [nehmen Sie Änderungen an den Vereinigungseinstellungen vor](data-unification-update.md) und führen Sie das einheitliche Profil erneut aus.

### <a name="verify-output-entities-from-data-unification"></a>Überprüfen Sie Ausgabeentitäten aus der Datenvereinheitlichung

Gehen Sie zu **Daten** > **Entitäten**, um die Ausgabeentitäten zu überprüfen.

Die einheitliche Kundenprofilentität lautet *Kunden* im Abschnitt **Profile**. Die erste erfolgreiche Ausführung der Vereinheitlichung erstellt die Entität *Kunde*. Alle nachfolgenden Läufe erweitern diese Entität.

Deduplizierungs- und Zusammenführungsentitäten werden erstellt und im Abschnitt **System** angezeigt. Eine Deduplizierungsentität wir für jede Quellentität mit dem Namen **Deduplication_DataSource_Entity** erstellt. Die **ConflationMatchPairs** Entität enthält Informationen zu entitätsübergreifenden Übereinstimmungen.

Eine Deduplizierungsausgabeentität enthält die folgenden Informationen:
- IDs/Schlüssel
  - Felder „Primärschlüssel“ und „Alternative ID“. Das Feld „Alternative ID“ besteht aus allen alternativen IDs, die für einen Datensatz identifiziert wurden.
  - Das Feld „Deduplication_GroupId“ zeigt die Gruppe oder den Cluster an, die bzw. der innerhalb einer Entität identifiziert wurde, die alle ähnlichen Datensätze basierend auf den angegebenen Deduplizierungsfeldern gruppiert. Dies wird für Systemverarbeitungszwecke verwendet. Wenn keine manuellen Deduplizierungsregeln angegeben sind und systemdefinierte Deduplizierungsregeln gelten, finden Sie dieses Feld möglicherweise nicht in der Deduplizierungsausgabeentität.
  - Deduplication_WinnerId: Dieses Feld enthält die Gewinner-ID der identifizierten Gruppen oder Cluster. Wenn „Deduplication_WinnerId“ mit dem Primärschlüsselwert für einen Datensatz identisch ist, bedeutet dies, dass der Datensatz der Gewinnerdatensatz ist.
- Felder zum Definieren der Deduplizierungsregeln.
- Regel- und Bewertungsfelder geben an, welche der Deduplizierungsregeln angewendet und welche Bewertung vom Übereinstimmungsalgorithmus zurückgegeben wurde.

## <a name="next-step"></a>Nächster Schritt

- Für B-to-B optional [Vereinheitlichung kontaktieren](data-unification-contacts.md) durchführen.

- Konfigurieren Sie [Aktivitäten](activities.md), [Anreicherung](enrichment-hub.md), [Beziehungen](relationships.md) oder [Kennzahlen](measures.md) für B-to-C, um mehr Erkenntnisse zu Ihren Kunden zu gewinnen.

[!INCLUDE[footer-include](includes/footer-banner.md)]
