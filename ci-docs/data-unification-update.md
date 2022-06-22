---
title: Aktualisieren der Vereinigungseinstellungen
description: Aktualisieren Sie Duplikatsregeln, Vergleichsregeln oder einheitliche Felder in den Vereinigungseinstellungen.
ms.date: 06/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 590a2996cf8b2b1c6def59b78583169ec1910b59
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844039"
---
# <a name="update-the-unification-settings"></a>Aktualisieren der Vereinigungseinstellungen

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Führen Sie die folgenden Schritte aus, um die Vereinigungseinstellungen zu überprüfen oder zu ändern, nachdem ein einheitliches Profil erstellt wurde.

1. Gehen Sie zu **Daten** > **Vereinheitlichen**.

   :::image type="content" source="media/m3_unified.png" alt-text="Screenshot der Seite zur Vereinheitlichung von Daten, nachdem die Daten vereinheitlicht wurden.":::

   > [!TIP]
   > Die Kachel **Abgleich-Bedingungen** wird nur angezeigt, wenn mehrere Entitäten ausgewählt wurden.

1. Wählen Sie aus, was Sie aktualisieren möchten:
   - [Quellfelder](#edit-source-fields), um Entitäten oder Attribute hinzuzufügen oder Attributtypen zu ändern.
   - [Doppelte Datensätze](#manage-deduplication-rules), um Deduplizierungsregeln zu verwalten oder Einstellungen zusammenzuführen.
   - [Abgleich-Bedingungen](#manage-match-rules) zum Aktualisieren von Abgleichsregeln für zwei oder mehr Entitäten.
   - [Einheitliche Kundenfelder](#manage-unified-fields), um Felder zu kombinieren oder auszuschließen. Sie können verwandte Profile auch in Clustern gruppieren.

1. Nachdem Sie Ihre Änderungen vorgenommen haben, wählen Sie Ihre nächste Option:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Screenshot der Seite zur Vereinheitlichung von Daten mit hervorgehobenen Optionen zur Vereinheitlichung.":::

   - Informationen zum schnellen Bewerten der Qualität Ihrer Abgleich-Bedingungen ohne Aktualisieren des einheitlichen Profils (Nichtduplizierungs- und Übereinstimmungsregel) finden Sie unter [Ausführen von Abgleich-Bedingungen](#run-matching-conditions). Die Option **Nur übereinstimmende Bedingungen ausführen** wird nicht für eine einzelne Entität angezeigt.
   - [Kundenprofile vereinheitlichen](#run-updates-to-the-unified-customer-profile), um übereinstimmende Bedingungen auszuführen und die Unified customer profile-Entität ohne Auswirkungen auf Abhängigkeiten (wie Anreicherungen, Segmente oder Kennzahlen) auszuführen. Abhängige Prozesse werden nicht ausgeführt, aber [gemäß Definition im Aktualisierungszeitplan](system.md#schedule-tab) aktualisiert.
   - [Kundenprofile und Abhängigkeiten vereinheitlichen](#run-updates-to-the-unified-customer-profile), um übereinstimmende Bedingungen auszuführen und die Unified customer profile-Entität und alle Abhängigkeiten (wie Anreicherungen, Segmente oder Kennzahlen) auszuführen. Alle Prozesse werden automatisch wiederholt.

## <a name="edit-source-fields"></a>Bearbeiten von Quellfeldern

Sie können ein Attribut oder eine Entität nicht entfernen, wenn sie bereits vereinheitlicht wurde.

1. Wählen Sie **Bearbeiten** auf der Kachel **Quellfelder** aus.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Screenshot der Seite „Quellfelder“ mit der Anzahl der Primärschlüssel, zugeordneten und nicht zugeordneten Felder":::

   Die Anzahl der zugeordneten und nicht zugeordneten Felder wird angezeigt.

1. Wählen Sie **Entitäten und Felder auswählen**, um weitere Attribute oder Entitäten hinzuzufügen. Verwenden Sie die Suche oder den Bildlauf, um Ihre Attribute und Objekte von Interesse zu finden und auszuwählen. Wählen Sie **Übernehmen** aus.

1. Optional können Sie den Primärschlüssel für eine Entität und die Attributtypen ändern und **Intelligente Zuordnung** an- oder ausschalten. Weitere Informationen finden Sie unter [Auswählen des Primärschlüssels und Semantiktyps für Attribute](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Wählen Sie **Weiter** aus, um Änderungen an den Deduplizierungsregeln vorzunehmen, oder wählen Sie **Speichern und schließen**, um zurückzukehren zu [Aktualisieren der Vereinigungseinstellungen](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Verwalten von Deduplizierungsregeln

1. Wählen Sie **Bearbeiten** auf der Kachel **Doppelte Datensätze** aus.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Screenshot der Seite „Doppelte Datensätze“ mit der Anzahl doppelter Datensätze" lightbox="media/m3_duplicates_edit.png":::

   Die Anzahl der gefundenen doppelten Datensätze wird unter **Duplikate** angezeigt. Die Spalte **Doppelte Datensätze wurden beseitigt** zeigt, welche Entitäten doppelte Datensätze hatten, und den Prozentsatz der doppelten Datensätze.

1. Wenn Sie eine angereicherte Entität hinzugefügt haben, wählen Sie **Angereicherte Entitäten verwenden**. Weitere Informationen finden Sie unter [Anreicherungen für Datenquellen](data-sources-enrichment.md).

1. Um Deduplizierungsregeln zu verwalten, wählen Sie eine der folgenden Optionen:
   - **Neue Regel erstellen**: Wählen Sie **Regel hinzufügen** unter der entsprechenden Entität. Weitere Informationen finden Sie unter [Definieren der Deduplizierungsregeln](remove-duplicates.md#define-deduplication-rules).
   - **Regelbedingungen ändern**: Wählen Sie die Regel und dann **Bearbeiten**. Ändern Sie Felder, fügen Sie Bedingungen hinzu oder entfernen Sie sie oder fügen Sie Ausnahmen hinzu oder entfernen Sie sie.
   - **Vorschau**: Wählen Sie die Regel und dann **Vorschau**, um die letzten Ausführungsergebnisse für diese Regel anzuzeigen.
   - **Regel deaktivieren**: Wählen Sie die Regel und dann **Deaktivieren**, um eine Deduplizierungsregel beizubehalten, während sie vom Abgleichsprozess ausgeschlossen wird.
   - **Regel duplizieren**: Wählen Sie die Regel und dann **Duplizieren**, um eine ähnliche Regel mit Modifikationen zu erstellen.
   - **Regel löschen**: Wählen Sie die Regel und dann **Löschen**.

1. Um Zusammenführungseinstellungen zu ändern, wählen Sie die Entität aus. Sie können die Einstellungen nur ändern, wenn eine Regel erstellt wird.
   1. Wählen Sie **Einstellungen für die Zusammenführung bearbeiten**, und ändern Sie die Option **Beizubehaltender Datensatz**.
   1. Um Zusammenführungseinstellungen für einzelne Attribute einer Entität zu ändern, wählen Sie **Erweitert** und nehmen Sie die notwendigen Änderungen vor.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Screenshot der erweiterten Zusammenführungseinstellungen mit der neuesten E-Mail und der vollständigsten Adresse":::

   1. Wählen Sie **Fertig** aus.

1. Wählen Sie **Weiter** aus, um Änderungen an den Abgleichbedingungen vorzunehmen, oder wählen Sie **Speichern und schließen**, um zurückzukehren zu [Aktualisieren der Vereinigungseinstellungen](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Abgleichregeln verwalten

Sie können die meisten Übereinstimmungsparameter neu konfigurieren und optimieren. Sie können Entitäten nicht hinzufügen oder löschen. Abgleichsregeln gelten nicht für eine einzelne Entität.

1. Wählen Sie **Bearbeiten** auf der Kachel **Abgleich-Bedingungen** aus.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Screenshot der Seite für Abgleichsregeln und -bedingungen mit Statistiken." lightbox="media/m3_match_edit.png":::

   Die Seite zeigt die Abgleichreihenfolge und definierte Regeln sowie die folgenden Statistiken an:
   - **Einzigartige Quelldatensätze** zeigt die Anzahl der einzelnen Quelldatensätze an, die im letzten Übereinstimmungslauf verarbeitet wurden.
   - **Übereinstimmende und nicht übereinstimmende Datensätze** hebt hervor, wie viele eindeutige Datensätze nach der Verarbeitung der Übereinstimmungsregeln verbleiben.
   - **Nur übereinstimmende Datensätze** zeigt die Anzahl der Übereinstimmungen über alle Ihre Übereinstimmungspaare hinweg an.

1. Um die Ergebnisse aller Regeln und ihre Punktzahlen anzuzeigen, wählen Sie **Letzte Ausführung anzeigen**. Die Ergebnisse werden angezeigt, einschließlich der alternativen Kontakt-IDs. Sie können die Ergebnisse herunterladen.

1. Um die Ergebnisse und Bewertungen einer bestimmten Regel anzuzeigen, wählen Sie die Regel und dann **Vorschau**. Die Ergebnisse werden angezeigt. Sie können die Ergebnisse herunterladen.

1. Um die Ergebnisse einer bestimmten Bedingung für eine Regel anzuzeigen, wählen Sie die Regel und dann **Bearbeiten**. Wählen Sie im Bearbeitungsbereich **Vorschau** unter der Bedingung aus. Sie können die Ergebnisse herunterladen.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Grafische Darstellung von nicht abgeglichenen und abgeglichenen Datensätzen, einschließlich einer Liste der Daten.":::

1. Wenn Sie eine angereicherte Entität hinzugefügt haben, wählen Sie **Angereicherte Entitäten verwenden**. Weitere Informationen finden Sie unter [Anreicherungen für Datenquellen](data-sources-enrichment.md).

1. Um Regeln zu verwalten, wählen Sie eine der folgenden Optionen:
   - **Neue Regel erstellen**: Wählen Sie **Regel hinzufügen** unter der entsprechenden Entität. Weitere Informationen finden Sie unter [Definieren von Regeln für abgeglichene Paare](match-entities.md#define-rules-for-match-pairs).
   - **Ändern Sie die Reihenfolge Ihrer Regeln**, wenn Sie mehrere Regeln definiert haben: Ziehen Sie die Regeln per Drag & Drop in die gewünschte Reihenfolge. Weitere Informationen finden Sie unter [Abgleichreihenfolge festlegen](match-entities.md#specify-the-match-order).
   - **Regelbedingungen ändern**: Wählen Sie die Regel und dann **Bearbeiten**. Ändern Sie Felder, fügen Sie Bedingungen hinzu oder entfernen Sie sie oder fügen Sie Ausnahmen hinzu oder entfernen Sie sie.
   - **Regel deaktivieren**: Wählen Sie die Regel und dann **Deaktivieren**, um eine Abgleichregel beizubehalten, während sie vom Abgleichsprozess ausgeschlossen wird.
   - **Regel duplizieren**: Wählen Sie die Regel und dann **Duplizieren**, um eine ähnliche Regel mit Modifikationen zu erstellen.
   - **Regel löschen**: Wählen Sie die Regel und dann **Löschen**.

1. Wählen Sie **Weiter** aus, um Änderungen an den vereinheitlichten Feldern vorzunehmen, oder wählen Sie **Speichern und schließen**, um zurückzukehren zu [Aktualisieren der Vereinigungseinstellungen](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Verwalten vereinheitlichter Felder

1. Wählen Sie **Bearbeiten** auf der Kachel **Vereinheitlichte Kundenfelder** aus.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Screenshot der vereinheitlichten Kundenfelder":::

1. Überprüfen Sie die kombinierten und ausgeschlossenen Felder und nehmen Sie bei Bedarf Änderungen vor. Fügen Sie den CustomerID-Schlüssel hinzu oder bearbeiten Sie ihn oder gruppieren Sie Profile in Clustern. Weitere Informationen finden Sie unter [Vereinheitlichen von Kundenfeldern](merge-entities.md).

1. Wählen Sie **Weiter**, um die Vereinheitlichungseinstellungen zu überprüfen und [das vereinheitlichte Profile und die Abhängigkeiten zu aktualisieren](#run-updates-to-the-unified-customer-profile), oder wählen Sie **Speichern und schließen** und kehren Sie zu [Aktualisieren der Vereinigungseinstellungen](#update-the-unification-settings) für weitere Änderungen zurück.

## <a name="run-matching-conditions"></a>Ausführen von Abgleich-Bedingungen

Matching-Bedingungen ausführen führt nur die Deduplizierung und Abgleichregeln aus und aktualisiert die Entitäten *Deduplication_* und *ConflationMatchPair*.

1. Wählen Sie auf der Seite **Daten** > **Vereinheitlichen** die Option **Nur übereinstimmende Bedingungen ausführen**.

   Für die Kacheln **Doppelte Datensätze** und **Abgleich-Bedingungen** wird der Status **In Warteschlange** oder **Wird aktualisiert** angezeigt.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Wenn der Abgleichvorgang abgeschlossen ist, wählen Sie **Bearbeiten** auf der Seite **Abgleich-Bedingungen**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Beschnittener Screenshot der wichtigsten Metriken auf der Match-Seite mit Zahlen und Details.":::

1. Informationen zum Vornehmen von Änderungen finden Sie unter [Verwalten von Deduplizierungsregeln](#manage-deduplication-rules) oder [Verwalten von Abgleichregeln](#manage-match-rules).

1. Führen Sie den Abgleichprozess erneut aus oder [führen Sie Aktualisierungen des Kundenprofils durch](#run-updates-to-the-unified-customer-profile).

## <a name="run-updates-to-the-unified-customer-profile"></a>Ausführen von Aktualisierungen des Unified Customer Profile

1. Auf der Seite **Daten** > **Vereinheitlichen** wählen Sie:

   - **Kundenprofile vereinheitlichen**: Führt übereinstimmende Bedingungen aus und aktualisiert die Unified customer profile-Entität ohne Auswirkungen auf Abhängigkeiten (wie Anreicherungen, Segmente oder Kennzahlen). Abhängige Prozesse werden nicht ausgeführt, aber [gemäß Definition im Aktualisierungszeitplan](system.md#schedule-tab) aktualisiert.

   - **Kundenprofile und Abhängigkeiten zusammenführen**: Führt übereinstimmende Bedingungen aus und aktualisiert das einheitliche Profil und alle Abhängigkeiten. Alle Prozesse werden automatisch wiederholt. Nachdem alle nachgelagerten Prozesse abgeschlossen sind, spiegelt das Kundenprofil die aktualisierten Daten wider.

   Für die Kacheln **Doppelte Datensätze**, **Abgleich-Bedingungen** und **Vereinheitlichte Kundenfelder** wird der Status **In Warteschlange** oder **Wird aktualisiert** angezeigt.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Die Ergebnisse eines erfolgreichen Laufs werden auf der Seite **Vereinheitlichen** mit der Anzahl der Unified Customer Profiles angezeigt.
