---
title: Entitäten für die Datenvereinheitlichung abgleichen
description: Gleichen Sie Entitäten ab, um vereinheitlichte Kundenprofile zu erstellen.
ms.date: 02/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: ab4ab0dba1bd91b1893cd4b16b8d51381d5b6ef8
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376921"
---
# <a name="match-entities"></a>Entitäten anpassen

Die Abgleichsphase gibt an, wie Ihre Datensätze zu einem einheitlichen Kundenprofil-Datensatz kombiniert werden können. Nach Abschluss des [Kartenschritts](map-entities.md) während des Datenvereinigungsprozesses sind Sie bereit, Ihre Entitäten abzugleichen. Die Abgleichsphase erfordert mindestens zwei zugeordnete Entitäten.

Die Match-Seite besteht aus drei Abschnitten: 
- Wichtige Metriken, die die Anzahl der übereinstimmenden Datensätze zusammenfassen
- Übereinstimmungsreihenfolge und Regeln für den entitätsübergreifenden Abgleich
- Regeln für die Deduplizierung von Übereinstimmungsentitäten

## <a name="specify-the-match-order"></a>Geben Sie die Reihenfolge der Übereinstimmung an

Jede Übereinstimmung vereint zwei oder mehr Entitäten zu einer einzigen konsolidierten Entität. Gleichzeitig werden die eindeutigen Kundendatensätze geführt. Die Übereinstimmungsreihenfolge gibt die Reihenfolge an, in der das System versucht, die Datensätze abzugleichen.

> [!IMPORTANT]
> Die Entität, die Sie als Ihre primäre Entität wählen, dient als Grundlage für Ihren einheitlichen Profildatensatz. Zusätzliche Entitäten, die während der Übereinstimmungsphase ausgewählt werden, werden zu dieser Entität hinzugefügt. Dass bedeutet nicht, dass der vereinheitlichte Entität *alle* Daten dieser Entität enthält
>
> Es gibt zwei Überlegungen, die Ihnen bei der Auswahl der Hierarchie Ihrer Entitäten helfen können:
>
> - Wählen Sie die Entität mit den vollständigsten und zuverlässigsten Profildaten Ihrer Kunden als primäre Entität aus.
> - Wählen Sie die Entität, die mehrere Attribute mit anderen Entitäten gemeinsam hat (z. B. Name, Telefonnummer oder E-Mail-Adresse) als primäre Entität.

1. Gehen Sie zu **Daten** > **Zusammenführen** > **Abgleichen** und wählen Sie **Reihenfolge einrichten**, um die Abgleichungsphase zu starten.
1. Wählen Sie **Entitätsreihenfolge** aus. Wählen Sie zum Beispiel **eCommerce:eCommerceContacts** als primäre Entität und **LoyaltyScheme:loyCustomers** als zweite Instanz. 
1. Um alle Datensätze in der Entität als eindeutigen Kunden zu führen und mit jeder folgenden Entität abzugleichen, wählen Sie **Include all**.
1. Wählen Sie **Fertig** aus. 

Nach Angabe der Zuordnungsreihenfolge werden die definierten Zuordnungspaare im Abschnitt **Details zu übereinstimmenden Datensätzen** unter **Daten** > **Vereinheitlichen** > **Zuordnen** angezeigt. Die Schlüsselmetriken sind leer, bis der Abgleichvorgang abgeschlossen ist.

:::image type="content" source="media/match-page.png" alt-text="Screenshot der Seite „Übereinstimmung” im Bereich „Vereinheitlichen” des Datenvereinigungsprozesses.":::
  
Die primäre Entität *eCommerce:eCommerceContacts* wird mit der nächsten Entität *LoyaltyScheme:loyCustomers* abgeglichen. Das DataSet, das sich aus dem ersten Vergleichsschritt ergibt, wird mit der folgenden Entität abgeglichen, wenn Sie mehr als zwei Entitäten haben.

## <a name="define-rules-for-match-pairs"></a>Regeln für das abgeglichene Paar definieren

Übereinstimmungsregeln legen die Logik fest, nach der ein bestimmtes Paar von Entitäten abgeglichen wird.

Die Warnung **Benötigt Regeln** neben einem Entitätsnamen weist darauf hin, dass für ein Übereinstimmungspaar keine Übereinstimmungsregel definiert ist. 

:::image type="content" source="media/match-rule-add.png" alt-text="Screenshot des Abschnitts „Details zu übereinstimmenden Datensätzen” mit Steuerelement zum Hinzufügen hervorgehobener Regeln.":::

1. Wählen Sie **Regel hinzufügen** unter einer Entität im Abschnitt **Details zu übereinstimmenden Datensätzen** zum Definieren von Übereinstimmungsregeln.

1. Konfigurieren Sie im Bereich **Regel erstellen** die Bedingungen für die Regel.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Screenshot einer geöffneten Match-Regel mit hinzugefügten Bedingungen.":::

   - **Entität/Feld (erste Zeile)**: Wählen Sie eine verwandte Entität und ein Attribut aus, um eine Datensatzeigenschaft anzugeben, die für einen Kunden wahrscheinlich eindeutig ist. Zum Beispiel eine Telefonnummer oder eine E-Mail-Adresse. Vermeiden Sie Übereinstimmungen nach Attributen des Aktivitätstyps. Beispielsweise findet eine Kauf-ID wahrscheinlich keine Übereinstimmung in anderen Datensatztypen.

   - **Entität/Feld (zweite Reihe)**: Wählen Sie ein Attribut aus, das sich auf das Attribut der in der ersten Zeile angegebenen Entität bezieht.

   - **Normalisieren**: Wählen Sie aus den folgenden Normalisierungsoptionen für die ausgewählten Attribute. 
     - Ziffern: Konvertiert andere Zahlensysteme, z. B. römische Ziffern, in arabische Ziffern. *VIII* wird *8*.
     - Symbole: Entfernt alle Symbole und Sonderzeichen. *Head&Shoulder* wird *HeadShoulder*.
     - Text in Kleinbuchstaben: Konvertiert alle Zeichen in Kleinbuchstaben. *ALL CAPS und Erster Buchstabe groß* wird *all caps und erster buchstabe groß*.
     - Typ (Telefon, Name, Adresse, Organisation): Standardisiert Namen, Titel, Telefonnummern, Adressen usw. 
     - Unicode in ASCII: Konvertiert die Unicode-Notation in ASCII-Zeichen. */u00B2* wird *2*.
     - Leerzeichen: Entfernt alle Leerzeichen. *Hallo   Welt* wird *Hallo Welt*.

   - **Präzision**: Legen Sie die Genauigkeit fest, die für diese Bedingung gelten soll. 
     - **Basic** : Wählen Sie *Niedrig*, *Mittel*, *Hoch*, und *Genau*. Wählen Sie **Genau**, um nur Datensätze abzugleichen, die zu 100 Prozent übereinstimmen. Wählen Sie eine der anderen Ebenen aus, um Datensätze abzugleichen, die nicht 100 Prozent identisch sind.
     - **Benutzerdefiniert**: Legen Sie einen Prozentsatz fest, mit dem Datensätze übereinstimmen müssen. Das System stimmt nur mit Datensätzen überein, die diesen Schwellenwert überschreiten.

1. Geben Sie einen **Namen** für die Regel an.

1. [Fügen Sie weitere Bedingungen hinzu](#add-conditions-to-a-rule) oder wählen Sie **Fertig**, um die Regel abzuschließen.

1. Optional [weitere Regeln hinzufügen](#add-rules-to-a-match-pair).

1. Wählen Sie **Speichern**, um Ihre Änderungen zu übernehmen.

### <a name="add-conditions-to-a-rule"></a>Bedingungen zu einer Regel hinzufügen

Fügen Sie einer Übereinstimmungsregel weitere Bedingungen hinzu, um Entitäten nur dann abzugleichen, wenn Attribute mehrere Bedingungen erfüllen. Bedingungen sind mit einem logischen UND-Operator verbunden und werden daher nur ausgeführt, wenn alle Bedingungen erfüllt sind.

1. Gehe zu **Daten** > **Vereinheitlichen** > **Abgleichen** und wählen Sie **Bearbeiten** zu der Regel, zu der Sie Bedingungen hinzufügen möchten.

1. Wählen Sie im Bereich **Regel bearbeiten** die Option **Bedingung hinzufügen**.

1. Wählen Sie **Abgeschlossen**, um die Regel zu speichern.

### <a name="add-rules-to-a-match-pair"></a>Fügen Sie einem abgeglichenen Paar Regeln hinzu

Übereinstimmungsregeln repräsentieren Sätze von Bedingungen. Um Entitäten nach Bedingungen abzugleichen, die auf verschiedenen Attributen basieren, fügen Sie weitere Regeln hinzu.

1.  Gehe zu **Daten** > **Vereinheitlichen** > **Abgleichen** und wählen Sie **Regel hinzufügen** zu der Entität, zu der Sie Regeln hinzufügen möchten.

2. Befolgen Sie die Schritte in [Definieren Sie Regeln für Übereinstimmungspaare](#define-rules-for-match-pairs).

> [!NOTE]
> Die Reihenfolge der Regeln ist wichtig. Der Abgleichalgorithmus versucht, basierend auf der ersten Regel eine Übereinstimmung zu finden, und fährt mit der zweiten Regel fort, wenn unter der ersten Regel keine Übereinstimmungen identifiziert wurden.

### <a name="change-the-entity-order-in-match-rules"></a>Ändern Sie die Entitätsreihenfolge in Übereinstimmungsregeln

Sie können Entitäten für Vergleichsregeln neu anordnen, um die Reihenfolge zu ändern, in der sie verarbeitet werden. Regeln, die aufgrund einer geänderten Reihenfolge in Konflikt stehen, werden entfernt. Sie müssen entfernte Regeln mit einer aktualisierten Konfiguration neu erstellen.

1. Gehen Sie zu **Daten** > **Zusammenführen** > **Abgleichen** und wählen Sie **Bearbeiten** aus.

1. In dem Bereich **Regel bearbeiten** wählen Sie das Steuerelement **Nach oben/unten verschieben** oder Ziehen und legen Sie Entitäten ab, um die Reihenfolge zu ändern.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Optionen, um zu ändern, in welcher Reihenfolge Entitäten in der Übereinstimmungsphase verarbeitet werden.":::

1. Wählen Sie **Abgeschlossen**, um die Regel zu speichern.

## <a name="define-deduplication-on-a-match-entity"></a>Definieren Sie die Deduplizierung auf einer Match-Entität

Zusätzlich zu [entitätsübergreifenden Übereinstimmungsregeln](#define-rules-for-match-pairs) können Sie auch Deduplizierungsregeln angeben. *Deduplizierung* ist ein weiterer Prozess beim Abgleichen von Datensätzen. Sie identifiziert doppelte Datensätze und führt sie zu einem Datensatz zusammen. Quelldatensätze werden mit alternativen IDs mit dem zusammengeführten Datensatz verknüpft.

Deduplizierte Datensätze werden im entitätsübergreifenden Abgleichprozess verwendet. Die Deduplizierung erfolgt auf einzelnen Entitäten und kann für jede Entität konfiguriert werden, die in Übereinstimmungspaaren verwendet wird.

Die Angabe von Deduplizierungsregeln ist nicht obligatorisch. Wenn keine solchen Regeln konfiguriert sind, werden die systemdefinierten Regeln angewendet. Sie kombinieren alle Datensätze zu einem einzigen Datensatz, bevor sie die Entitätsdaten an einen entitätsübergreifenden Abgleich übergeben, um die Leistung zu verbessern.

### <a name="add-deduplication-rules"></a>Deduplizierungsregeln hinzufügen

1. Gehen Sie zu **Daten** > **Vereinheitlichen** > **Abgleichen**.

1. Im **Details zu deduplizierten Datensätzen**-Abschnitt wählen Sie **Entitäten festlegen** aus. Falls bereits Deduplizierungsregeln erstellt wurden, wählen Sie **Bearbeiten**.

1. Wählen Sie im Bereich **Zusammenführungseinstellungen** die Entitäten aus, auf die Sie die Deduplizierung anwenden wollen.

   1. Geben Sie an, wie die doppelten Datensätze kombiniert werden sollen und wählen Sie eine von drei Optionen:
      - **Am häufigsten**: Identifiziert den Datensatz mit den meisten ausgefüllten Attributfeldern als Gewinner-Datensatz. Dies ist die standardmäßige Zusammenführungsoption.
      - **Aktuell**: Identifiziert den Gewinner-Datensatz auf der Basis der größten Aktualität. Erfordert ein Datum oder ein numerisches Feld, um die Aktualität zu definieren.
      - **Letzer**: Identifiziert den Gewinner-Datensatz basierend auf der besten Aktualität. Erfordert ein Datum oder ein numerisches Feld, um die Aktualität zu definieren.

   1. Wählen Sie optional **Erweitert** aus, um Deduplizierungsregeln für einzelne Attribute einer Entität zu definieren. Sie können beispielsweise wählen, ob Sie die neueste E-Mail UND die vollständigste Adresse aus verschiedenen Datensätzen behalten möchten. Erweitern Sie die Entität, um alle ihre Attribute anzuzeigen, und definieren Sie, welche Option für einzelne Attribute verwendet werden soll. Wenn Sie eine auf Aktualität basierende Option wählen, müssen Sie auch ein Datums-/Uhrzeitfeld angeben, das die Aktualität definiert. 
 
      > [!div class="mx-imgBorder"]
      > ![Deduplizierungsregeln Schritt 1.](media/match-selfconflation.png "Deduplizierungsregeln Schritt 1")

   1. Wählen Sie **Fertig** aus, um Ihre Zusammenführungseinstellungen für die Deduplizierung anzuwenden.
 
1. Sobald die Entitäten ausgewählt sind und ihre Zusammenführungspräferenz eingestellt ist, wählen Sie **Regel hinzufügen**, um die Deduplizierungsregeln auf Entitätsebene zu definieren.
   - **Feld auswählen** listet alle verfügbaren Felder dieser Entität auf. Wählen Sie das Feld aus, das Sie auf Duplikate prüfen möchten. Wählen Sie Felder aus, die wahrscheinlich für jeden einzelnen Kunden eindeutig sind. Zum Beispiel eine E-Mail-Adresse oder die Kombination aus Name, Stadt und Telefonnummer.
   - Geben Sie die Normalisierungs- und Genauigkeitseinstellungen an.
   - Definieren Sie zusätzliche Bedingungen, indem Sie **Bedingung hinzufügen** wählen.
 
   > [!div class="mx-imgBorder"]
   > ![Deduplizierungsregeln Schritt 2.](media/match-selfconflation-rules.png "Deduplizierungsregeln Schritt 2")

  Sie können mehrere Deduplizierungsregeln für eine Entität erstellen. 

1. Das Ausführen des Abgleichsprozesses gruppiert nun die Datensätze basierend auf den in den Deduplizierungsregeln definierten Bedingungen. Nach der Gruppierung der Datensätze wird die Richtlinie für die Zusammenführung angewendet, um den Gewinner-Datensatz zu identifizieren.

1. Dieser Gewinnerdatensatz wird dann zusammen mit den Nicht-Gewinnerdatensätzen (z. B. alternativen IDs) an den entitätsübergreifenden Abgleich weitergeleitet, um die Übereinstimmungsqualität zu verbessern.

1. Alle benutzerdefinierten Übereinstimmungsregeln, die definiert wurden, überschreiben Deduplizierungsregeln. Wenn eine Deduplizierungsregel übereinstimmende Datensätze identifiziert und eine benutzerdefinierte Abgleichsregel so eingestellt ist, dass diese Datensätze nie abgeglichen werden, dann werden diese beiden Datensätze nicht abgeglichen.

1. Nach dem [Ausführen des Vergleichsprozesses](#run-the-match-process) sehen Sie die Deduplizierungsstatistiken in den Schlüsselmetrikkacheln.

### <a name="deduplication-output-as-an-entity"></a>Deduplizierungsausgabe als Entität

Der Deduplizierungsprozess erstellt für jede Entität aus den Übereinstimmungspaaren eine neue Entität, um die deduplizierten Datensätze zu identifizieren. Diese Entitäten können zusammen mit **ConflationMatchPairs: CustomerInsights** gefunden werden im **System**-Abschnitt auf der **Entitäten**-Seite mit dem Namen **Deduplication_DataSource_Entity** gefunden werden.

Eine Deduplizierungsausgabeentität enthält die folgenden Informationen:
- IDs/Schlüssel
  - Primärschlüsselfeld und sein alternatives ID-Feld. Das Feld „Alternative IDs“ besteht aus allen alternativen IDs, die für einen Datensatz identifiziert wurden.
  - Das Feld „Deduplication_GroupId“ zeigt die Gruppe oder den Cluster an, die bzw. der innerhalb einer Entität identifiziert wurde, die alle ähnlichen Datensätze basierend auf den angegebenen Deduplizierungsfeldern gruppiert. Dies wird für Systemverarbeitungszwecke verwendet. Wenn keine manuellen Deduplizierungsregeln angegeben sind und systemdefinierte Deduplizierungsregeln gelten, finden Sie dieses Feld möglicherweise nicht in der Deduplizierungsausgabeentität.
  - Deduplication_WinnerId: Dieses Feld enthält die Gewinner-ID der identifizierten Gruppen oder Cluster. Wenn „Deduplication_WinnerId“ mit dem Primärschlüsselwert für einen Datensatz identisch ist, bedeutet dies, dass der Datensatz der Gewinnerdatensatz ist.
- Felder zum Definieren der Deduplizierungsregeln.
- Regel- und Bewertungsfelder geben an, welche der Deduplizierungsregeln angewendet und welche Bewertung vom Übereinstimmungsalgorithmus zurückgegeben wurde.
 
## <a name="include-enriched-entities-preview"></a>Angereicherte Entitäten einschließen (Vorschau)

Wenn Sie Entitäten auf der Ebene Datenquelle angereichert haben, wählen Sie sie aus, bevor Sie den Abgleichsprozess ausführen. Die angereicherten Entitäten können Ihre Vereinigungsergebnisse verbessern. Weitere Informationen finden Sie unter [Anreicherungen für Datenquellen](data-sources-enrichment.md). 

Die angereicherte Entität enthält die ursprünglichen Datenquelle-Felder und die angereicherten Felder. Wenn Sie sich also dafür entscheiden, mit der angereicherten Entität zu arbeiten, wird die vorhandene Konfiguration nicht beeinträchtigt. Möglicherweise müssen Sie jedoch die Übereinstimmungsregeln aktualisieren, um stattdessen die angereicherten Felder zu verwenden.

1. Gehen Sie zu **Daten** > **Vereinheitlichen** > **Anpassen** und wähle Sie **Verwenden Sie angereicherte Entitäten** oben auf der Seite.

1. Von dem Bereich **Verwenden Sie angereicherte Entitäten** wählen Sie im Bereich eine oder mehrere angereicherte Entitäten aus.

1. Wählen Sie **Fertig** aus. Überall dort, wo die Quellentität verwendet wird (z. B. Match-Reihenfolge oder Regeln), wird sie automatisch in die angereicherte Entität geändert.
  
## <a name="run-the-match-process"></a>Den Abgleichprozess ausführen

Nachdem Sie die Abgleichsregeln konfiguriert haben, einschließlich der Regeln für den entitätsübergreifenden Abgleich und die Deduplizierung, können Sie den Abgleichprozess ausführen. 

Gehen Sie zu **Daten** > **Vereinheitlichen** > **Abgleichen** und wählen Sie **Ausführen**, um den Prozess zu starten. Der Übereinstimmungsalgorithmus dauert einige Zeit und Sie können die Konfiguration erst ändern, wenn sie abgeschlossen ist. Um Änderungen vorzunehmen, können Sie die Ausführung abbrechen. Wählen Sie den Status des Jobs und wählen Sie **Auftrag abbrechen** im Bereich **Fortschrittsdetails**.

Das Ergebnis einer erfolgreichen Ausführung, die einheitliche Kundenprofilentität, finden Sie auf der Seite **Entitäten** Seite. Ihre einheitliche Kundenentität lautet **Kunden** im Abschnitt **Profile**. Die erste erfolgreiche Übereinstimmungsausführung erstellt die Entität einheitlicher *Kunde*. Alle nachfolgenden Übereinstimmungsausführungen erweitern diese Entität.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="review-and-validate-your-matches"></a>Überprüfen und validieren Sie Ihre Übereinstimmungen

Gehen Sie zu **Daten** > **Vereinheitlichen** > **Abgleichen**, um die Qualität Ihrer abgeglichenen Paare zu bewerten und gegebenenfalls zu verfeinern.

Die Kacheln oben auf der Seite zeigen wichtige Metriken, in denen die Anzahl der übereinstimmenden Datensätze und Duplikate zusammengefasst ist.

:::image type="content" source="media/match-KPIs.png" alt-text="Beschnittener Screenshot der wichtigsten Metriken auf der Match-Seite mit Zahlen und Details.":::

- **Einzigartige Quelldatensätze** zeigt die Anzahl der einzelnen Quelldatensätze an, die im letzten Übereinstimmungslauf verarbeitet wurden.
- **Übereinstimmende und nicht übereinstimmende Datensätze** hebt hervor, wie viele eindeutige Datensätze nach der Verarbeitung der Übereinstimmungsregeln verbleiben.
- **Nur übereinstimmende Datensätze** zeigt die Anzahl der Übereinstimmungen über alle Ihre Übereinstimmungspaare hinweg an.

Sie können die Ergebnisse jedes abgeglichenen Paares und seine Regeln in der Tabelle **Übereinstimmende Datensatzdetails** bewerten. Vergleichen Sie die Anzahl der Datensätze, die von einem Übereinstimmungspaar stammen, mit dem Prozentsatz der erfolgreich übereinstimmenden Datensätze.

Überprüfen Sie die Regeln eines Übereinstimmungspaars, um den Prozentsatz der erfolgreich übereinstimmenden Datensätze auf Regelebene zu ermitteln. Wählen Sie die Auslassungspunkte (...) und dann **Vorschau für Übereinstimmung** aus, um alle diese Datensätze auf Regelebene anzuzeigen. Wir empfehlen, dass Sie sich einige Datensätze ansehen, um zu überprüfen, ob sie korrekt übereinstimmen.

Probieren Sie verschiedene Präzisionsschwellenwerte für Bedingungen aus, um den optimalen Wert zu finden.

  1. Wählen Sie die Auslassungspunkte (...) für die Regel aus, mit der Sie experimentieren möchten, und wählen Sie **Bearbeiten** aus.

  2. Ändern Sie die Präzisionsbedingungen in den Bedingungen, die Sie überarbeiten möchten.

  3. Wählen Sie **Vorschau**, um sich die Anzahl der übereinstimmenden und nicht übereinstimmenden Datensätze für die ausgewählte Bedingung anzusehen.

## <a name="manage-match-rules"></a>Abgleichregeln verwalten

Sie können die meisten Übereinstimmungsparameter neu konfigurieren und optimieren.

:::image type="content" source="media/match-rules-management.png" alt-text="Screenshot des Dropdownmenüs mit passenden Regeloptionen.":::

- **Ändern Sie die Reihenfolge Ihrer Regeln**, wenn Sie mehrere Regeln definiert haben. Sie können die Spielregeln neu anordnen, indem Sie die Optionen **Nach oben** und **Nach unten** wählen oder per Drag & Drop.

- **Regelbedingungen ändern** durch die Auswahl von **Bearbeiten** und wählen Sie verschiedene Felder.

- **Regel deaktivieren**, um eine Übereinstimmungsregel beizubehalten und sie gleichzeitig vom Übereinstimmungsprozess auszuschließen.

- **Duplizieren Sie Ihre Regeln**, wenn Sie eine Vergleichsregel definiert haben und eine ähnliche Regel mit Änderungen erstellen möchten, wählen Sie **Duplizieren**.

- **Regel löschen** durch Auswahl des Symbols **Löschen**.

## <a name="advanced-options"></a>Erweiterte Optionen

### <a name="add-exceptions-to-a-rule"></a>Einer Regel Ausnahmen hinzufügen

In den meisten Fällen führt der Entitätsvergleich zu eindeutigen Benutzerprofilen mit konsolidierten Daten. Um seltene Fälle von falsch positiven und falsch negativen Ergebnissen dynamisch anzugehen, können Sie Ausnahmen für eine Vergleichsregel definieren. Ausnahmen werden nach Verarbeitung der Vergleichsregeln angewendet und vermeiden den Vergleich aller Datensätze, die die Ausnahmekriterien erfüllen.

Wenn Ihre Vergleichsregel beispielsweise Nachname, Stadt und Geburtsdatum kombiniert, würde das System Zwillinge mit demselben Nachnamen, die in derselben Stadt leben, als dasselbe Profil identifizieren. Sie können eine Ausnahme angeben, die die Profile nicht vergleicht, wenn der Vorname in den von Ihnen kombinierten Entitäten nicht identisch sind.

1. Gehe zu **Daten** > **Vereinheitlichen** > **Abgleichen** und wählen Sie **Bearbeiten** zu der Regel, zu der Sie Bedingungen hinzufügen möchten.

1. Im **Regel bearbeiten**-Bereich wählen Sie **Ausnahme hinzufügen**.

1. Geben Sie die Ausnahmekriterien an. 

1. Wählen Sie **Abgeschlossen** und speichern Sie die Regel.

### <a name="specify-custom-match-conditions"></a>Benutzerdefinierte Vergleichsbedingungen angeben

Sie können Bedingungen angeben, die die standardmäßige Vergleichslogik überschreiben. Die folgenden vier Optionen sind verfügbar: 

|Option  |Beschreibung des Dataflows |Beispiel  |
|---------|---------|---------|
|Immer übereinstimmen     | Definiert Werte, die immer übereinstimmen.         |  *Mike* und *MikeR* immer übereinstimmen.       |
|Nicht übereinstimmen     | Definiert Werte, die niemals übereinstimmen.        | *John* und *Jonathan* nie übereinstimmen.        |
|Benutzerdefinierte Umgehung     | Definiert Werte, die das System in der Übereinstimmungsphase immer ignorieren soll. |  Werte *11111* und *Unbekannt* während der Übereinstimmung ignorieren.        |
|Alias-Zuordnung    | Definieren von Werten, die das System als denselben Wert betrachten soll.         | *Joe* als gleich zu *Joseph* betrachten.        |

1. Gehen Sie zu **Daten** > **Vereinheitlichen** > **Abgleichen** und wählen Sie **Benutzerdefinierte Übereinstimmung** im Abschnitt **Übereinstimmende Datensatzdetails** aus.

   :::image type="content" source="media/custom-match-create.png" alt-text="Screenshot des Abschnitts „Abgleichregeln” mit hervorgehobenem Steuerelement zum Überwachen benutzerdefinierter Übereinstimmungen.":::

1. Gehen Sie im Bereich **Benutzerdefiniert** zur Registerkarte **Datensätze**.

1. Wählen Sie die benutzerdefinierte Vergleichsoption aus dem **Benutzerdefinierter Typ**-Dropdownmenü und dann **Vorlage herunterladen**. Sie benötigen für jede Vergleichsoption eine separate Vorlage.

1. Öffnen Sie die heruntergeladene Vorlagendatei und geben Sie die Details ein. Die Vorlage enthält Felder zur Angabe der Entität und der Primärschlüsselwerte der Entität, die beim benutzerdefinierten Vergleich verwendet werden sollen. Wenn Sie bespielsweise einen Primärschlüssel *12345* von der Entität *Vertrieb* möchten, die immer mit dem Primärschlüssel *34567* der Entität *Kontakt* übereinstimmt, füllen Sie die Vorlage aus:
    - Entität1: Verkauf
    - Entity1Key: 12345
    - Entität2: Kontakt
    - Entity2Key: 34567

   Dieselbe Vorlagendatei kann benutzerdefinierte Match-Datensätze von mehreren Entitäten angeben.
   
   Wenn Sie eine benutzerdefinierte Übereinstimmung für die Deduplizierung einer Entität angeben möchten, geben Sie dieselbe Entität wie Entität1 und Entität2 an und legen Sie die verschiedenen Primärschlüsselwerte fest.

1. Nachdem Sie alle Überschreibungen hinzugefügt haben, speichern Sie die Vorlagendatei.

1. Gehen Sie zu **Daten** > **Datenquellen** und nehmen Sie die Vorlagedateien als neue Entitäten auf.

1. Nachdem die Dateien und Entitäten hochgeladen wurden und verfügbar sind, wählen Sie erneut die Option **Abgleich nach Kennzahl**. Sie sehen Optionen zur Angabe der Entitäten, die Sie einbeziehen möchten. Wählen Sie die erforderlichen Entitäten aus dem Dropdownmenü und dann **Fertig** aus.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Screenshot des Dialogfelds zum Auswählen von Überschreibungen für ein benutzerdefiniertes Übereinstimmungsszenario.":::

1. Das Anwenden der benutzerdefinierten Übereinstimmung hängt von der Übereinstimmungsoption ab, die Sie verwenden möchten. 

   - Für **Immer übereinstimmen** oder **Nie übereinstimmen** fahren Sie mit dem nächsten Schritt fort.
   - Für **Benutzerdefinierte Umgehung** oder **Alias-Zuordnung** wählen Sie **Bearbeiten** in einer vorhandenen Übereinstimmungsregel aus oder erstellen eine neue Regel. Wählen Sie im Normalisierungen-Dropdownmenü die Option **Benutzerdefinierte Umgehung** oder **Alias-Zuordnung** und dann **Fertig** aus.

1. Wählen Sie **Speichern** auf der Seite **Abgleichen**, um die benutzerdefinierte Übereinstimmungskonfiguration anzuwenden.

1. Wählen Sie **Ausführen** auf der Seite **Abgleichen**, um den Abgleich zu starten. Andere angegebene Übereinstimmungsregeln werden von der benutzerdefinierten Übereinstimmungskonfiguration überschrieben.

#### <a name="known-issues"></a>Bekannte Probleme

- Bei der Selbstzusammenführung werden die normalisierten Daten in Deduplizierungsentitäten nicht angezeigt. Es wendet die Normalisierung jedoch intern während der Deduplizierung an. Dies gilt entwurfsbedingt für alle Normalisierungen. 
- Wenn die Einstellung für den Semantiktyp in der Phase **Zuordnung** entfernt wird, wenn eine Alias-Zuordnungs- oder benutzerdefinierte Umgehungs-Übereinstimmungsregel verwendet wird, wird die Normalisierung nicht angewendet. Dies geschieht nur, wenn Sie den Semantiktyp löschen, nachdem Sie die Normalisierung in der Übereinstimmungsregel konfiguriert haben, da der Semantiktyp unbekannt ist.


## <a name="next-step"></a>Nächster Schritt

Nachdem Sie den Übereinstimmungsprozess für mindestens ein Übereinstimmungspaar abgeschlossen haben, fahren Sie mit dem [**Zusammenführen**](merge-entities.md)-Schritt fort.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
