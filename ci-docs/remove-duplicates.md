---
title: Entfernen von Duplikaten, bevor Sie Daten vereinheitlichen
description: Der zweite Schritt im Vereinheitlichungsprozess ist die Auswahl, welcher Datensatz aufbewahrt werden soll, wenn Duplikate gefunden werden.
recommendations: false
ms.date: 08/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 3f84c1c149f0befcbe489ccdd8a666ce6d5d798a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304472"
---
# <a name="remove-duplicates-before-unifying-data"></a>Entfernen von Duplikaten, bevor Sie Daten vereinheitlichen

Diese optionale Schritt der Vereinheitlichung ermöglicht es Ihnen optional, Regeln für das Löschen doppelter Datensätze **innerhalb** einer Entität einzurichten. Die Deduplizierung identifiziert mehrere Datensätze für einen Kunden und wählt den besten aufzubewahrenden Datensatz aus (basierend auf grundlegenden Zusammenführungspräferenzen) oder führt die Datensätze zu einem zusammen (basierend auf erweiterten Zusammenführungspräferenzen). Quelldatensätze werden mit alternativen IDs mit dem zusammengeführten Datensatz verknüpft. Wenn keine Regeln konfiguriert sind, werden die systemdefinierten Regeln angewendet.

## <a name="default-deduplication"></a>Standarddeduplizierung

Wenn keine Deduplizierungsregeln konfiguriert sind, werden die systemdefinierten Regeln angewendet.

- Der Primärschlüssel ist dedupliziert.
  Für alle Datensätze mit demselben Primärschlüssel ist der Datensatz **Am häufigsten** (derjenige mit den wenigsten Nullwerten) der Gewinner.
- Alle entitätsübergreifenden Abgleichsregeln werden auf die Entität angewendet.
  Zum Beispiel: Im Abgleichsschritt, wenn Entität A mit Entität B *Vollständiger Name* und *Geburtsdatum* abgeglichen wird, dann wird Entität A auch nach *Vollständiger Name* und *Geburtsdatum* dedupliziert. Da *Vollständiger Name* und *Geburtsdatum* gültige Schlüssel zum Identifizieren eines Kunden in Entität A sind, sind diese Schlüssel auch gültig zum Identifizieren doppelter Kunden in Entität A.

## <a name="include-enriched-entities-preview"></a>Angereicherte Entitäten einschließen (Vorschauversion)

Wenn Sie Entitäten auf der Ebene der Datenquelle angereichert haben, um Ihre Vereinigungsergebnisse zu verbessern, wählen Sie sie aus. Weitere Informationen finden Sie unter [Anreicherungen für Datenquellen](data-sources-enrichment.md).

1. Wählen Sie auf der Seite **Doppelte Datensätze** oben auf der Seite **Angereicherte Entitäten verwenden**.

1. Von dem Bereich **Verwenden Sie angereicherte Entitäten** wählen Sie im Bereich eine oder mehrere angereicherte Entitäten aus.

1. Wählen Sie **Fertig** aus.

## <a name="define-deduplication-rules"></a>Definieren von Deduplizierungsregeln

1. Wählen Sie auf der Seite **Doppelte Datensätze** eine Entität aus und wählen Sie **Regel hinzufügen**, um die Deduplizierungsregeln zu definieren.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Screenshot der Seite Doppelte Datensätze mit hervorgehobener Entität und angezeigter Regel hinzufügen"  lightbox="media/m3_duplicates_showmore.png":::

   1. Geben Sie im Bereich **Regel hinzufügen** die folgenden Informationen ein:
      - **Feld auswählen**: Wählen Sie aus der Liste der verfügbaren Felder der Entität aus, die Sie auf Duplikate prüfen möchten. Wählen Sie Felder aus, die wahrscheinlich für jeden einzelnen Kunden eindeutig sind. Zum Beispiel eine E-Mail-Adresse oder die Kombination aus Name, Stadt und Telefonnummer.
      - **Normalisieren**: Wählen Sie aus den folgenden Normalisierungsoptionen für die ausgewählten Attribute.
        - **Ziffern**: Konvertiert andere Zahlensysteme, z. B. römische Ziffern, in arabische Ziffern. *VIII* wird *8*.
        - **Symbole**: Entfernt alle Symbole und Sonderzeichen. *Head&Shoulder* wird *HeadShoulder*.
        - **Text in Kleinbuchstaben: Konvertiert alle Zeichen in Kleinbuchstaben**. *ALL CAPS und Erster Buchstabe groß* wird *all caps und erster buchstabe groß*.
        - **Typ (Telefon, Name, Adresse, Organisation)**: Standardisiert Namen, Titel, Telefonnummern, Adressen usw.
        - **Unicode in ASCII**: Konvertiert die Unicode-Notation in ASCII-Zeichen. */u00B2* wird *2*.
        - **Leerzeichen**: Entfernt alle Leerzeichen. *Hallo   Welt* wird *Hallo Welt*.
      - **Präzision**: Legen Sie die Genauigkeit fest, die für diese Bedingung gelten soll.
        - **Basic**: Wählen Sie *Niedrig (30 %)*, *Mittel (60 %)*, *Hoch (80 %)* und *Genau (100 %)*. Wählen Sie **Genau**, um nur Datensätze abzugleichen, die zu 100 Prozent übereinstimmen.
        - **Benutzerdefiniert**: Legen Sie einen Prozentsatz fest, mit dem Datensätze übereinstimmen müssen. Das System stimmt nur mit Datensätzen überein, die diesen Schwellenwert überschreiten.
      - **Name**: Der Name für die Regel.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Screenshot des Bereichs „Regel hinzufügen“ zum Entfernen von Duplikaten.":::

   1. Wählen Sie optional **Hinzufügen** > **Bedingung hinzufügen** aus, um der Regel weitere Bedingungen hinzuzufügen. Bedingungen sind mit einem logischen UND-Operator verbunden und werden daher nur ausgeführt, wenn alle Bedingungen erfüllt sind.

   1. Wählen Sie optional **Hinzufügen** > **Ausnahme hinzufügen**, um [Ausnahmen zur Regel hinzuzufügen](match-entities.md#add-exceptions-to-a-rule). Ausnahmen werden verwendet, um seltene Fälle von falsch positiven und falsch negativen Ergebnissen zu behandeln.

   1. Wählen Sie **Fertig**, um die Regel zu erstellen.

1. Optional [weitere Regeln hinzufügen](#define-deduplication-rules).

1. Wählen Sie eine Entität und dann **Einstellungen für die Zusammenführung bearbeiten**.

1. Im Bereich **Einstellungen für die Zusammenführunng**:
   1. Wählen Sie eine von drei Optionen aus, um zu bestimmen, welcher Datensatz aufbewahrt werden soll, wenn ein Duplikat gefunden wird:
      - **Am häufigsten**: Identifiziert den Datensatz mit den meisten ausgefüllten Attributfeldern als Gewinner-Datensatz. Dies ist die standardmäßige Zusammenführungsoption.
      - **Aktuell**: Identifiziert den Gewinner-Datensatz auf der Basis der größten Aktualität. Erfordert ein Datum oder ein numerisches Feld, um die Aktualität zu definieren.
      - **Letzer**: Identifiziert den Gewinner-Datensatz basierend auf der besten Aktualität. Erfordert ein Datum oder ein numerisches Feld, um die Aktualität zu definieren.

      Im Falle eines Unentschiedens ist der Gewinnerdatensatz derjenige mit dem MAX(PK)-Wert oder dem größeren Primärschlüsselwert.

   1. Um optional Zusammenführungspräferenzen für einzelne Attribute einer Entität zu definieren, wählen Sie **Erweitert** am unteren Rand des Bereichs. Sie können beispielsweise wählen, ob Sie die neueste E-Mail UND die vollständigste Adresse aus verschiedenen Datensätzen behalten möchten. Erweitern Sie die Entität, um alle ihre Attribute anzuzeigen, und definieren Sie, welche Option für einzelne Attribute verwendet werden soll. Wenn Sie eine auf Aktualität basierende Option wählen, müssen Sie auch ein Datums-/Uhrzeitfeld angeben, das die Aktualität definiert.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Bereich „Voreinstellungen für die erweiterte Zusammenführung“ mit der neuesten E-Mail und der vollständigen Adresse":::

   1. Wählen Sie **Fertig** aus, um Ihre Einstellungen zusammenzuführen.

1. Nachdem Sie die Deduplizierungsregeln und Zusammenführungseinstellungen definiert haben, wählen Sie **Weiter**.
  
> [!div class="nextstepaction"]
> [Nächster Schritt für eine einzelne Entität: Felder vereinheitlichen](merge-entities.md)

> [!div class="nextstepaction"]
> [Nächster Schritt für mehrere Entitäten: Abgleich-Bedingungen](match-entities.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
