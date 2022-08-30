---
title: Ein vereinheitlichtes Kontaktprofil erstellen (Vorschauversion)
description: Führen Sie den Datenvereinigungsprozess mit Ihren Daten durch, um einen einzigen Master DataSet von Kontakten zu erstellen.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305030"
---
# <a name="create-a-unified-contact-profile-preview"></a>Ein vereinheitlichtes Kontaktprofil erstellen (Vorschauversion)

Nach [Geschäftskonten vereinheitlichen](map-entities.md), können Sie optional Kontakte für diese Konten vereinheitlichen und die vereinheitlichten Kontakte mit den vereinheitlichten Konten verknüpfen. Der Kontaktvereinheitlichungsprozess ordnet Kontaktdaten aus mehreren Datenquellen zu, entfernt Duplikate, gleicht die Daten über Entitäten hinweg ab, richtet semantische Zuordnung ein, erstellt Beziehungen zwischen Kontakten und Konten und erstellt dann ein einheitliches Kontaktprofil.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

Die ersten Schritte sind identisch mit den Schritten zur Kontenvereinheitlichung.

## <a name="prerequisites"></a>Anforderungen

Konto- und Kontaktdatensätze müssen über einen eindeutigen Schlüssel (als Fremdschlüssel bezeichnet) verfügen, der sie verbindet. Beispielsweise eine Konto-ID, die im Konto-Datensatz und im Kontaktdatensatz vorhanden ist, der den Account und den Kontakt miteinander verbindet.

## <a name="preview-limitations"></a>Vorschaueinschränkungen

- Kontakte ohne Verknüpfung zu einem Konto werden gelöscht.
- Wenn ein Konto dedupliziert wird, wird basierend auf den Zusammenführungseinstellungen ein Gewinnerdatensatz identifiziert. Verlierer-Datensätze werden nicht ausgewählt und fallen daher weg. Kontakte, die den verlorenen Datensätzen zugeordnet sind, werden gelöscht.
- Ein Konto kann mehrere Kontakte haben, aber ein Kontakt ist mit einem einzigen Konto verknüpft.
- Die im Schritt der semantischen Zuordnung zugeordneten Kontaktattribute sind die einzigen Attribute, die auf der Kundenkarte angezeigt werden können. Es stehen jedoch 17 Attribute zur Verfügung.

## <a name="select-source-fields"></a>Auswählen von Quellfeldern

1. Unter **Kontakte vereinheitlichen (Vorschauversion)** wählen Sie **Erste Schritte**.

1. [Wählen Sie die Entitäten und Felder aus](map-entities.md) für Ihre Kontaktdatenquellen, einschließlich der Primärschlüssel und Attributtypen.

1. Wählen Sie **Weiter** aus.

## <a name="remove-duplicate-records"></a>Entfernen doppelter Datensätze

1. Optional [Deduplizierungsregeln definieren](remove-duplicates.md) für Ihre ausgewählten Entitäten.

1. Wählen Sie **Weiter** aus.

## <a name="match-conditions"></a>Abgleich-Bedingungen

1. [Übereinstimmungsreihenfolge und Regeln](match-entities.md) für den entitätsübergreifenden Abgleich.

1. Wählen Sie **Weiter** aus.

## <a name="unify-contact-fields"></a>Kontaktfelder vereinheitlichen

1. [Kontaktfelder kombinieren und ausschließen](merge-entities.md).

1. Wählen Sie **Weiter** aus.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Semantische Felder für vereinheitlichte Kontakte definieren

Dieser Schritt im Vereinheitlichungsprozess ordnet Ihre vereinheitlichten Kontaktfelder semantischen Typen zu. Im B-to-B zeigen die Kundenkarten Konten. Wenn die Karte ausgewählt wird, werden alle dem Konto zugeordneten Kontakte angezeigt. Die Felder, die Sie in diesem Schritt zuordnen, sind die Felder, die auf den Karten angezeigt werden.

1. Wählen Sie die semantischen Type  aus, die zu den vereinheitlichten Felder passen. Wählen Sie **Keiner** wenn ein semantischer Typ nicht verfügbar ist.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Screenshot der Seite „Semantische Felder“ zum Definieren der semantischen Typen." lightbox="media/semantic_mapping.png":::

1. Nachdem Sie alle einheitlichen Felder zugeordnet haben, wählen Sie **Weiter** aus.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Beziehung zwischen Kontakten und Konten festlegen

Dieser Schritt im Vereinheitlichungsprozess verbindet Ihre Kontaktdaten mit den entsprechenden Kontodaten.

1. Geben Sie für jede Entität die folgenden Informationen ein:

   - **Fremdschlüssel aus Kontaktentität**: Wählen Sie das Attribut aus Ihrer Quellentität aus, das Ihre Kontaktentität mit einer anderen Entität verbindet.
   - **Zur Kontoeinheit**: Wählen Sie die dem Kontakt zugeordnete Kontoentität aus.

   :::image type="content" source="media/contact_relationship.png" alt-text="Screenshot der Beziehungsseite zum Verbinden der Kontakt- und Kontoentitäten.":::

1. Wählen Sie **Weiter** aus.

## <a name="review-contact-unification"></a>Überprüfen der Kontaktvereinheitlichung

Überprüfen Sie die Zusammenfassung der Änderungen, erstellen Sie das einheitliche Profil und überprüfen Sie die Ergebnisse.

### <a name="review-and-create-contact-profiles"></a>Kontaktprofile überprüfen und erstellen

Dieser letzte Schritt im Vereinheitlichungsprozess zeigt eine Zusammenfassung der Schritte im Prozess und bietet die Möglichkeit, Änderungen vorzunehmen, bevor Sie das vereinheitlichte Kontaktprofil erstellen.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Screenshot von Profil überprüfen und erstellen.":::

1. Wählen Sie **Bearbeiten** bei allen Kontaktvereinheitlichungsschritten, um sie zu überprüfen und Änderungen vorzunehmen.

1. Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **Kontaktprofile erstellen**. Die Seite **Vereinheitlichen** wird angezeigt, während das vereinheitlichte Kontaktprofil erstellt wird.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Screenshot der Seite Unify Kontaktseite mit Kacheln, die In Warteschlange oder Aktualisieren angezeigt werden.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Es dauert einige Zeit, bis der Vereinigungsalgorithmus abgeschlossen ist, und Sie können die Konfiguration nicht ändern, bis er abgeschlossen ist.

### <a name="view-the-results-of-contact-unification"></a>Anzeigen der Ergebnisse der Kontaktvereinheitlichung

Nach der Vereinigung zeigt die Seite **Daten** > **Vereinheitlichen** die Anzahl der einheitlichen Kontaktprofile. Die Ergebnisse jedes Schritts im Vereinigungsprozess werden auf jeder Kachel angezeigt. Zum Beispiel enthält **Quellfelder** die Anzahl der zugeordneten Attribute (Felder) und **Doppelte Datensätze** zeigt die Anzahl der gefundenen doppelten Datensätze.

:::image type="content" source="media/unified_contacts.png" alt-text="Screenshot der Seite zur Vereinheitlichung von Daten, nachdem die Kontakte vereinheitlicht wurden.":::

> [!TIP]
> Die Kachel **Abgleich-Bedingungen** wird nur angezeigt, wenn mehrere Entitäten ausgewählt wurden.

Wir empfehlen Ihnen, die Ergebnisse zu überprüfen, insbesondere die Qualität Ihrer [Abgleich-Bedingungen](data-unification-update.md#manage-match-rules), und sie ggf. zu verfeinern.

Wenn erforderlich, [nehmen Sie Änderungen an den Kontakt-Vereinigungseinstellungen vor](data-unification-update.md) und führen Sie das einheitliche Profil erneut aus.

### <a name="verify-output-entities-from-data-unification"></a>Überprüfen Sie Ausgabeentitäten aus der Datenvereinheitlichung

Gehen Sie zu **Daten** > **Entitäten**, um die Ausgabeentitäten zu überprüfen.

Die einheitliche Kontaktprofilentität, genannt *ContactProfile* wird im Abschnitt **Semantische Entitäten** angezeigt. Die erste erfolgreiche Ausführung der Vereinheitlichung erstellt die Entität *ContactProfile*. Alle nachfolgenden Läufe erweitern diese Entität.

Die Entität *ContactsCustomer* (Vorschauversion) wird erstellt und im Abschnitt **Profile** angezeigt. Diese Entität enthält die Kontaktdaten ohne die Verknüpfungen zu den Konten. Diese Entität wird als Eingabe für die semantische Abbildung und die Beziehungsschritte der Kontaktvereinheitlichung verwendet.

Deduplizierungs- und Zusammenführungsentitäten werden erstellt und im Abschnitt **System** angezeigt. Eine Deduplizierungsentität wir für jede Quellentität mit dem Namen **Deduplication_DataSource_Entity** erstellt. Die **ContactsConflationMatchPairs** Entität enthält Informationen zu entitätsübergreifenden Übereinstimmungen.

Eine Deduplizierungsausgabeentität enthält die folgenden Informationen:
- IDs/Schlüssel
  - Felder „Primärschlüssel“ und „Alternative ID“. Das Feld „Alternative ID“ besteht aus allen alternativen IDs, die für einen Datensatz identifiziert wurden.
  - Das Feld „Deduplication_GroupId“ zeigt die Gruppe oder den Cluster an, die bzw. der innerhalb einer Entität identifiziert wurde, die alle ähnlichen Datensätze basierend auf den angegebenen Deduplizierungsfeldern gruppiert. Dies wird für Systemverarbeitungszwecke verwendet. Wenn keine manuellen Deduplizierungsregeln angegeben sind und systemdefinierte Deduplizierungsregeln gelten, finden Sie dieses Feld möglicherweise nicht in der Deduplizierungsausgabeentität.
  - Deduplication_WinnerId: Dieses Feld enthält die Gewinner-ID der identifizierten Gruppen oder Cluster. Wenn „Deduplication_WinnerId“ mit dem Primärschlüsselwert für einen Datensatz identisch ist, bedeutet dies, dass der Datensatz der Gewinnerdatensatz ist.
- Felder zum Definieren der Deduplizierungsregeln.
- Regel- und Bewertungsfelder geben an, welche der Deduplizierungsregeln angewendet und welche Bewertung vom Übereinstimmungsalgorithmus zurückgegeben wurde.

## <a name="next-step"></a>Nächster Schritt

Konfigurieren von [Aktivitäten](activities.md), [Anreicherung](enrichment-hub.md) oder [Beziehungen](relationships.md), um mehr Einblicke über Ihre Kontakte zu gewinnen.
