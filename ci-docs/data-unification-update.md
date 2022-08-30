---
title: Aktualisieren Sie die Einstellungen für die Zusammenführung von Kunden, Konten oder Kontakten
description: Aktualisieren Sie Duplikatsregeln, Vergleichsregeln oder einheitliche Felder in den Vereinigungseinstellungen vom Kunden oder Konto.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: f2c14c169f5973b5f400989b9eeea593eba09182
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304334"
---
# <a name="update-unification-settings"></a>Aktualisieren der Vereinigungseinstellungen

Führen Sie die folgenden Schritte aus, um die Vereinigungseinstellungen zu überprüfen oder zu ändern, nachdem ein einheitliches Profil erstellt wurde.

1. Gehen Sie zu **Daten** > **Vereinheitlichen**.

   Für Privatkunden (B-to-C) zeigt die **Vereinheitlichen** Seite die Anzahl der vereinheitlichten Kundenprofile und Kacheln für jeden der Vereinheitlichungsschritte an.

   :::image type="content" source="media/m3_unified.png" alt-text="Screenshot der Seite zur Vereinheitlichung von Daten, nachdem die Daten vereinheitlicht wurden." lightbox="media/m3_unified.png":::

   Für Geschäftskunden (B-to-B) zeigt die **Vereinheitlichen** Seite die Anzahl der vereinheitlichten Kontoprofile und Kacheln für jeden der Konto-Vereinheitlichungsschritte an. Wenn Kontakte vereinheitlicht wurden, wird die Anzahl der vereinheitlichten Kontaktprofile und Kacheln für jeden Schritt der Kontaktvereinheitlichung angezeigt. Wählen Sie unten die entsprechende Kachel aus **Konten vereinheitlichen** oder **Kontakte vereinheitlichen (Vorschauversion)** je nachdem, was Sie aktualisieren möchten.

   :::image type="content" source="media/b2b_unified.png" alt-text="Screenshot der Seite zur Vereinheitlichung von Konto- und Kontaktdaten die vereinheitlicht wurden." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > Die Kachel **Abgleich-Bedingungen** wird nur angezeigt, wenn mehrere Entitäten ausgewählt wurden.

1. Wählen Sie aus, was Sie aktualisieren möchten:
   - [Quellfelder](#edit-source-fields), um Entitäten oder Attribute hinzuzufügen oder Attributtypen zu ändern.
   - [Doppelte Datensätze](#manage-deduplication-rules), um Deduplizierungsregeln zu verwalten oder Einstellungen zusammenzuführen.
   - [Abgleich-Bedingungen](#manage-match-rules) zum Aktualisieren von Abgleichsregeln für zwei oder mehr Entitäten.
   - [Einheitliche Kundenfelder](#manage-unified-fields), um Felder zu kombinieren oder auszuschließen. Sie können verwandte Profile auch in Clustern gruppieren.
   - [Semantische Felder](#manage-semantic-fields-for-unified-contacts), um semantische Typen für einheitliche Kontaktfelder zu verwalten.
   - [Beziehungen](#manage-contact-and-account-relationships), um die Kontakt-zu-Konto-Beziehung zu verwalten.

1. Nachdem Sie Ihre Änderungen vorgenommen haben, wählen Sie Ihre nächste Option:

   - Informationen zum schnellen Bewerten der Qualität Ihrer Abgleich-Bedingungen ohne Aktualisieren des einheitlichen Profils (Nichtduplizierungs- und Übereinstimmungsregel) finden Sie unter [Ausführen von Abgleich-Bedingungen](#run-matching-conditions). Die Option **Nur übereinstimmende Bedingungen ausführen** wird nicht für eine einzelne Entität angezeigt.
   - [Kundenprofile vereinheitlichen](#run-updates-to-the-unified-profile), um übereinstimmende Bedingungen auszuführen und die Unified customer profile-Entität ohne Auswirkungen auf Abhängigkeiten (wie Anreicherungen, Segmente oder Kennzahlen) auszuführen. Abhängige Prozesse werden nicht ausgeführt, aber [gemäß Definition im Aktualisierungszeitplan](schedule-refresh.md) aktualisiert.
   - [Kundenprofile und Abhängigkeiten vereinheitlichen](#run-updates-to-the-unified-profile), um übereinstimmende Bedingungen auszuführen und die Unified customer profile-Entität und alle Abhängigkeiten (wie Anreicherungen, Segmente oder Kennzahlen) auszuführen. Alle Prozesse werden automatisch wiederholt. Bei B-to-B wird die Vereinheitlichung sowohl für die Konto- als auch für die Kontaktentitäten ausgeführt, die die vereinheitlichten Profile aktualisieren.

## <a name="edit-source-fields"></a>Bearbeiten von Quellfeldern

Sie können ein Attribut oder eine Entität nicht entfernen, wenn sie bereits vereinheitlicht wurde.

1. Wählen Sie **Bearbeiten** auf der Kachel **Quellfelder** aus.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Screenshot der Seite „Quellfelder“ mit der Anzahl der Primärschlüssel, zugeordneten und nicht zugeordneten Felder":::

   Die Anzahl der zugeordneten und nicht zugeordneten Felder wird angezeigt.

1. Wählen Sie **Entitäten und Felder auswählen**, um weitere Attribute oder Entitäten hinzuzufügen.

1. Optional können Sie den Primärschlüssel für eine Entität und die Attributtypen ändern und **Intelligente Zuordnung** an- oder ausschalten. Weitere Informationen finden Sie unter [Quellfelder auswählen](map-entities.md).

1. Wählen Sie **Weiter** aus, um Änderungen an den Deduplizierungsregeln vorzunehmen, oder wählen Sie **Speichern und schließen**, um zu [Aktualisieren der Vereinigungseinstellungen](#update-unification-settings) zurückzukehren.

## <a name="manage-deduplication-rules"></a>Verwalten von Deduplizierungsregeln

1. Wählen Sie **Bearbeiten** auf der Kachel **Doppelte Datensätze** aus.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Screenshot der Seite „Doppelte Datensätze“ mit der Anzahl doppelter Datensätze" lightbox="media/m3_duplicates_edit.png":::

   Die Anzahl der gefundenen doppelten Datensätze wird unter **Duplikate** angezeigt. Die Spalte **Doppelte Datensätze wurden beseitigt** zeigt, welche Entitäten doppelte Datensätze hatten, und den Prozentsatz der doppelten Datensätze.

1. Um eine angereicherte Entität zu verwenden, wählen Sie **Angereicherte Entitäten verwenden**. Weitere Informationen finden Sie unter [Anreicherungen für Datenquellen](data-sources-enrichment.md).

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

   1. Wählen Sie **Fertig** aus.

1. Wählen Sie **Weiter** aus, um Änderungen an den Abgleichbedingungen vorzunehmen, oder wählen Sie **Speichern und schließen**, um zu [Aktualisieren der Vereinigungseinstellungen](#update-unification-settings) zurückzukehren.

## <a name="manage-match-rules"></a>Abgleichregeln verwalten

Sie können die meisten Übereinstimmungsparameter neu konfigurieren und optimieren. Sie können Entitäten nicht hinzufügen oder löschen. Abgleichsregeln gelten nicht für eine einzelne Entität.

1. Wählen Sie **Bearbeiten** auf der Kachel **Abgleich-Bedingungen** aus.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Screenshot der Seite für Abgleichsregeln und -bedingungen mit Statistiken." lightbox="media/m3_match_edit.png":::

   Die Seite zeigt die Abgleichreihenfolge und definierte Regeln sowie die folgenden Statistiken an:
   - **Einzigartige Quelldatensätze** zeigt die Anzahl der einzelnen Quelldatensätze an, die im letzten Übereinstimmungslauf verarbeitet wurden.
   - **Übereinstimmende und nicht übereinstimmende Datensätze** heben hervor, wie viele eindeutige Datensätze nach der Verarbeitung der Übereinstimmungsregeln verbleiben.
   - **Nur übereinstimmende Datensätze** zeigt die Anzahl der Übereinstimmungen über alle Ihre Übereinstimmungspaare hinweg an.

1. Um die Ergebnisse aller Regeln und ihre Punktzahlen anzuzeigen, wählen Sie **Letzte Ausführung anzeigen**. Die Ergebnisse werden angezeigt, einschließlich der alternativen Kontakt-IDs. Sie können die Ergebnisse herunterladen.

1. Um die Ergebnisse und Bewertungen einer bestimmten Regel anzuzeigen, wählen Sie die Regel und dann **Vorschau**. Die Ergebnisse anzeigen. Sie können die Ergebnisse herunterladen.

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

1. Wählen Sie **Weiter** aus, um Änderungen an den vereinheitlichten Feldern vorzunehmen, oder wählen Sie **Speichern und schließen**, um zu [Aktualisieren der Vereinigungseinstellungen](#update-unification-settings) zurückzukehren.

## <a name="manage-unified-fields"></a>Verwalten vereinheitlichter Felder

1. Wählen Sie **Bearbeiten** auf der Kachel **Vereinheitlichte Kundenfelder** aus.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Screenshot der vereinheitlichten Kundenfelder":::

1. Überprüfen Sie die kombinierten und ausgeschlossenen Felder und nehmen Sie bei Bedarf Änderungen vor. Fügen Sie den CustomerID-Schlüssel hinzu oder bearbeiten Sie ihn oder gruppieren Sie Profile in Clustern. Weitere Informationen finden Sie unter [Vereinheitlichen von Kundenfeldern](merge-entities.md).

1. Wählen Sie für Kunden oder Konten **Weiter** aus und überprüfen und [Aktualisieren Sie das einheitliche Profil und die Abhängigkeiten](#run-updates-to-the-unified-profile). Oder wählen Sie **Speichern und Schliessen** und wählen Weiter aus, um Änderungen an den vereinheitlichten Feldern vorzunehmen, oder wählen Sie [Speichern und schließen](#update-unification-settings), um zurückzukehren zu Aktualisieren der Vereinigungseinstellungen.

   Wählen Sie für Kontakte **Weiter** aus, um semantische Felder zu verwalten. Oder wählen Sie **Speichern und Schliessen** und wählen Weiter aus, um Änderungen an den vereinheitlichten Feldern vorzunehmen, oder wählen Sie [Speichern und schließen](#update-unification-settings), um zurückzukehren zu Aktualisieren der Vereinigungseinstellungen.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Semantische Felder für vereinheitlichte Kontakte verwalten

1. Wählen Sie **Bearbeiten** auf der Kachel **semantische Felder** aus.

1. Um den Semantiktyp für ein einheitliches Feld zu ändern, wählen Sie einen neuen Typ aus. Weitere Informationen unter [Semantische Felder für vereinheitlichte Kontakte definieren](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts).

1. Wählen Sie **Weiter** aus, um Kointen und Kontaktbeziehugen zu verwalten oder wählen Sie **Speichern und schließen**, um zurückzukehren zu [Aktualisieren der Vereinigungseinstellungen](#update-unification-settings).

## <a name="manage-contact-and-account-relationships"></a>Kontakte und Kontobeziehungen verwalten

1. Wählen Sie **Bearbeiten** auf der Kachel **Beziehungen** aus.

1. Um die Kontakt- und Kontobeziehung zu ändern, ändern Sie eine der folgenden Informationen:

   - **Fremdschlüssel aus Kontaktentität**: Wählen Sie das Attribut aus Ihrer Quellentität aus, das Ihre Kontaktentität mit einer anderen Entität verbindet.
   - **Zur Kontoeinheit**: Wählen Sie die dem Kontakt zugeordnete Kontoentität aus.

1. Wählen Sie **Weiter**, um die Vereinheitlichungseinstellungen zu überprüfen und [das vereinheitlichte Profile und die Abhängigkeiten zu aktualisieren](#run-updates-to-the-unified-profile) oder wählen Sie **Speichern und schließen** und kehren Sie zu [Aktualisieren der Vereinigungseinstellungen](#update-unification-settings) für weitere Änderungen zurück.

## <a name="run-matching-conditions"></a>Ausführen von Abgleich-Bedingungen

Matching-Bedingungen ausführen führt nur die Deduplizierung und Abgleichregeln aus und aktualisiert die Entitäten *Deduplication_* und *ConflationMatchPair*.

1. Wählen Sie auf der Seite **Daten** > **Vereinheitlichen** die Option **Nur übereinstimmende Bedingungen ausführen**.

   Für die Kacheln **Doppelte Datensätze** und **Abgleich-Bedingungen** wird der Status **In Warteschlange** oder **Wird aktualisiert** angezeigt.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Wenn der Abgleichvorgang abgeschlossen ist, wählen Sie **Bearbeiten** auf der Seite **Abgleich-Bedingungen**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Beschnittener Screenshot der wichtigsten Metriken auf der Match-Seite mit Zahlen und Details.":::

1. Informationen zum Vornehmen von Änderungen finden Sie unter [Verwalten von Deduplizierungsregeln](#manage-deduplication-rules) oder [Verwalten von Abgleichregeln](#manage-match-rules).

1. Führen Sie den Abgleichprozess erneut aus oder [führen Sie Aktualisierungen des Kundenprofils durch](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Ausführen von Aktualisierungen des Unified Customer Profile

- Kundenprofile vereinheitlichen, um übereinstimmende Bedingungen auszuführen und die vereinheitlichte Profilentität *ohne* auswirkende Abhängigkeiten (wie Anreicherungen, Segmente oder Kennzahlen) auszuführen. Wählen Sie dazu **Kundenprofile vereinheitlichen**. Wählen Sie für Konten **Konten vereinheitlichen** > **Profile vereinheitlichen** aus. Wählen Sie für Kontakte **Kontakte vereinheitlichen (Vorschauversion)** > **Profile vereinheitlichen** aus. Abhängige Prozesse werden nicht ausgeführt, aber [gemäß Definition im Aktualisierungszeitplan](schedule-refresh.md) aktualisiert.
- Um passende Bedingungen auszuführen, aktualisieren Sie das einheitliche Profil und führen Abhängigkeiten aus. Wählen Sie **Kundenprofile und Abhängigkeiten vereinheitlichen**. Alle Prozesse werden automatisch wiederholt. Wählen Sie für Konten und Kontakte **Konten vereinheitlichen** > **Profile und Abhängigkeiten vereinheitlichen**. Abgleichsbedingungen werden für beide Konten und Kontakte ausgeführt, die beide vereinheitlichten Profile aktualisieren, und alle anderen Abhängigkeiten werden ausgeführt.

Alle Kacheln außer **Quellfelder** zeigen **In Warteschlange** oder **wird aktualisiert** an.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Die Ergebnisse einer erfolgreichen Ausführing werden auf der Seite **Vereinheitlichen** mit der Anzahl der vereinheitlichten Profile angezeigt.
