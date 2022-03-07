---
title: Entitäten für die Datenvereinheitlichung abgleichen
description: Gleichen Sie Entitäten ab, um vereinheitlichte Kundenprofile zu erstellen.
ms.date: 02/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2eb84c44aa530346a73ba720106734d705a45f23
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595563"
---
# <a name="match-entities"></a>Entitäten anpassen

Die Abgleichsphase gibt an, wie Ihre Datensätze zu einem einheitlichen Kundenprofil-Datensatz kombiniert werden können. Nach Abschluss des [Kartenschritts](map-entities.md) während des Datenvereinigungsprozesses sind Sie bereit, Ihre Entitäten abzugleichen. Die Abgleichsphase erfordert mindestens zwei zugeordnete Entitäten.

Die Match-Seite besteht aus drei Abschnitten: 
- Wichtige Metriken, die die Anzahl der übereinstimmenden Datensätze zusammenfassen
- Übereinstimmungsreihenfolge und Regeln für den entitätsübergreifenden Abgleich
- Regeln für die Deduplizierung von Übereinstimmungsentitäten

## <a name="specify-the-match-order"></a>Geben Sie die Reihenfolge der Übereinstimmung an

Gehen Sie zu **Daten** > **Zusammenführen** > **Abgleichen** und wählen Sie **Reihenfolge einrichten**, um die Abgleichungsphase zu starten.

Jede Übereinstimmung vereint zwei oder mehr Entitäten zu einer einzigen konsolidierten Entität. Gleichzeitig werden die eindeutigen Kundendatensätze geführt. Zum Beispiel haben wir zwei Entitäten ausgewählt: **eCommerce:eCommerceContacts** als primäre Einheit und **LoyaltyScheme:loyCustomers** als zweite Einheit. Die Reihenfolge der Entitäten gibt an, in welcher Reihenfolge das System versucht, die Datensätze abzugleichen.

:::image type="content" source="media/match-page.png" alt-text="Screenshot der Seite „Übereinstimmung” im Bereich „Vereinheitlichen” des Datenvereinigungsprozesses.":::
  
Die primäre Entität *eCommerce:eCommerceContacts* wird mit der nächsten Entität *LoyaltyScheme:loyCustomers* abgeglichen. Das DataSet, das sich aus dem ersten Übereinstimmungsschritt ergibt, wird mit der folgenden Entität abgeglichen, wenn Sie mehr als zwei Entitäten haben.

> [!IMPORTANT]
> Die Entität, die Sie als Ihre primäre Entität wählen, dient als Grundlage für Ihren einheitlichen Profildatensatz. Zusätzliche Entitäten, die während der Übereinstimmungsphase ausgewählt werden, werden zu dieser Entität hinzugefügt. Dass bedeutet nicht, dass der vereinheitlichte Entität *alle* Daten dieser Entität enthält
>
> Es gibt zwei Überlegungen, die Ihnen bei der Auswahl der Hierarchie Ihrer Entitäten helfen können:
>
> - Wählen Sie die Entität mit den vollständigsten und zuverlässigsten Profildaten Ihrer Kunden als primäre Entität aus.
> - Wählen Sie als primäre Entität die Entität aus, die mehrere Attribute mit anderen Entitäten gemeinsam hat (z. B. Name, Telefonnummer oder E-Mail-Adresse).

Nachdem Sie die Übereinstimmungsreihenfolge angegeben haben, sehen Sie die definierten Übereinstimmungspaare im Abschnitt **Übereinstimmende Datensatzdetails** über **Daten** > **Vereinheitlichen** > **Spiel**. Die Schlüsselmetriken bleiben leer, bis der Übereinstimmungsprozess abgeschlossen ist.

## <a name="define-rules-for-match-pairs"></a>Regeln für das abgeglichene Paar definieren

Übereinstimmungsregeln legen die Logik fest, nach der ein bestimmtes Paar von Entitäten abgeglichen wird.

Die Warnung **Benötigt Regeln** neben einem Entitätsnamen weist darauf hin, dass für ein Übereinstimmungspaar keine Übereinstimmungsregel definiert ist. 

:::image type="content" source="media/match-rule-add.png" alt-text="Screenshot des Abschnitts „Details zu übereinstimmenden Datensätzen” mit Steuerelement zum Hinzufügen hervorgehobener Regeln.":::

1. Wählen Sie **Regeln hinzufügen** unter einer Entität im Abschnitt **Übereinstimmende Datensatzdetails** zum Definieren von Übereinstimmungsregeln.

1. Konfigurieren Sie im Bereich **Regel erstellen** die Bedingungen für die Regel.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Screenshot einer geöffneten Match-Regel mit hinzugefügten Bedingungen.":::

   - **Entität/Feld (erste Zeile)**: Wählen Sie eine verwandte Entität und ein Attribut aus, um eine Datensatzeigenschaft anzugeben, die für einen Kunden wahrscheinlich eindeutig ist. Zum Beispiel eine Telefonnummer oder eine E-Mail-Adresse. Vermeiden Sie Übereinstimmungen nach Attributen des Aktivitätstyps. Beispielsweise findet eine Kauf-ID wahrscheinlich keine Übereinstimmung in anderen Datensatztypen.

   - **Entität/Feld (zweite Reihe)**: Wählen Sie ein Attribut aus, das sich auf das Attribut der in der ersten Zeile angegebenen Entität bezieht.

   - **Normalisieren**: Wählen Sie aus den folgenden Normalisierungsoptionen für die ausgewählten Attribute. 
     - Leerzeichen: Entfernt alle Leerzeichen. *Hallo   Welt* wird *Hallo Welt*.
     - Symbole: Entfernt alle Symbole und Sonderzeichen. *Head&Shoulder* wird *HeadShoulder*.
     - Text in Kleinbuchstaben: Konvertiert alle Zeichen in Kleinbuchstaben. *ALL CAPS und Erster Buchstabe groß* wird *all caps und erster buchstabe groß*.
     - Unicode in ASCII: Konvertiert die Unicode-Notation in ASCII-Zeichen. */u00B2* wird *2*.
     - Ziffern: Konvertiert andere Zahlensysteme, z. B. römische Ziffern, in arabische Ziffern. *VIII* wird *8*.
     - Semantische Typen: Standardisiert Namen, Titel, Telefonnummern, Adressen usw. 

   - **Präzision**: Legen Sie die Genauigkeit fest, die für diese Bedingung gelten soll. 
     - **Basic** : Wählen Sie *Niedrig*, *Mittel*, *Hoch*, und *Genau*. Wählen Sie **Exakt**, um nur Datensätze abzugleichen, die zu 100 Prozent übereinstimmen. Wählen Sie eine der anderen Ebenen aus, um Datensätze abzugleichen, die nicht 100 Prozent identisch sind.
     - **Benutzerdefiniert**: Legen Sie einen Prozentsatz fest, mit dem Datensätze übereinstimmen müssen. Das System stimmt nur mit Datensätzen überein, die diesen Schwellenwert überschreiten.

1. Geben Sie einen **Namen** für die Regel an.

1. [Fügen Sie weitere Bedingungen hinzu](#add-conditions-to-a-rule) oder wählen Sie **Fertig**, um die Regel abzuschließen.

1. Optional [weitere Regeln hinzufügen](#add-rules-to-a-match-pair).

1. Wählen Sie **Speichern**, um Ihre Änderungen zu übernehmen.

### <a name="add-conditions-to-a-rule"></a>Bedingungen zu einer Regel hinzufügen

Fügen Sie einer Übereinstimmungsregel weitere Bedingungen hinzu, um Entitäten nur dann abzugleichen, wenn Attribute mehrere Bedingungen erfüllen. Bedingungen sind mit einem logischen UND-Operator verbunden und werden daher nur ausgeführt, wenn alle Bedingungen erfüllt sind.

1. Gehe zu **Daten** > **Vereinheitlichen** > **Abgleichen** und wählen Sie **Bearbeiten** zu der Regel, zu der Sie Bedingungen hinzufügen möchten.

1. Wählen Sie im Bereich **Regel bearbeiten** die Option **Bedingung hinzufügen**.

1. Wählen Sie **Abgeschlossen** und speichern Sie die Regel.

### <a name="add-rules-to-a-match-pair"></a>Fügen Sie einem abgeglichenen Paar Regeln hinzu

Übereinstimmungsregeln repräsentieren Sätze von Bedingungen. Um Entitäten nach Bedingungen abzugleichen, die auf verschiedenen Attributen basieren, fügen Sie weitere Regeln hinzu.

1.  Gehe zu **Daten** > **Vereinheitlichen** > **Abgleichen** und wählen Sie **Regel hinzufügen** zu der Entität, zu der Sie Regeln hinzufügen möchten.

2. Befolgen Sie die Schritte in [Definieren Sie Regeln für Übereinstimmungspaare](#define-rules-for-match-pairs).

> [!NOTE]
> Die Reihenfolge der Regeln ist wichtig. Der Abgleichalgorithmus versucht, basierend auf der ersten Regel eine Übereinstimmung zu finden, und fährt mit der zweiten Regel fort, wenn unter der ersten Regel keine Übereinstimmungen identifiziert wurden.

## <a name="define-deduplication-on-a-match-entity"></a>Definieren Sie die Deduplizierung auf einer Match-Entität

Zusätzlich zu [entitätsübergreifenden Übereinstimmungsregeln](#define-rules-for-match-pairs) können Sie auch Deduplizierungsregeln angeben. *Deduplizierung* ist ein weiterer Prozess beim Abgleichen von Datensätzen. Es identifiziert doppelte Datensätze und führt sie zu einem Datensatz zusammen. Quelldatensätze werden mit alternativen IDs mit dem zusammengeführten Datensatz verknüpft.

Deduplizierte Datensätze werden dann im entitätsübergreifenden Abgleichprozess verwendet. Die Deduplizierung erfolgt für einzelne Entitäten und kann für jede Entität konfiguriert werden, die in Übereinstimmungspaaren verwendet wird.

Die Angabe von Deduplizierungsregeln ist nicht zwingend erforderlich. Wenn keine solchen Regeln konfiguriert sind, werden die systemdefinierten Regeln angewendet. Sie kombinieren alle Datensätze zu einem einzigen Datensatz, bevor sie die Entitätsdaten an einen entitätsübergreifenden Abgleich übergeben, um die Leistung zu verbessern.

### <a name="add-deduplication-rules"></a>Deduplizierungsregeln hinzufügen

1. Gehen Sie zu **Daten** > **Vereinheitlichen** > **Abgleichen**.

1. Wählen Sie im Abschnitt **Zusammengeführte Duplikate** die Option **Entitäten einrichten**. Falls bereits Deduplizierungsregeln erstellt wurden, wählen Sie **Bearbeiten**.

1. Wählen Sie im Bereich **Zusammenführungseinstellungen** die Entitäten aus, auf die Sie die Deduplizierung anwenden wollen.

1. Geben Sie an, wie die doppelten Datensätze kombiniert werden sollen und wählen Sie eine von drei Optionen:
   - **Am häufigsten**: Identifiziert den Datensatz mit den meisten ausgefüllten Attributfeldern als Gewinner-Datensatz. Dies ist die Standard-Zusammenführungsoption.
   - **Aktuell**: Identifiziert den Gewinner-Datensatz auf der Basis der größten Aktualität. Benötigt ein Datum oder ein numerisches Feld, um die Aktualität zu definieren.
   - **Letzer**: Identifiziert den Gewinner-Datensatz basierend auf der besten Aktualität. Benötigt ein Datum oder ein numerisches Feld, um die Aktualität zu definieren.
 
   > [!div class="mx-imgBorder"]
   > ![Deduplizierungsregeln Schritt 1](media/match-selfconflation.png "Deduplizierungsregeln Schritt 1")
 
1. Sobald die Entitäten ausgewählt sind und ihre Zusammenführungspräferenz eingestellt ist, wählen Sie **Regel hinzufügen**, um die Deduplizierungsregeln auf Entitätsebene zu definieren.
   - **Feld auswählen** listet alle verfügbaren Felder dieser Entität auf. Wählen Sie das Feld aus, das Sie auf Duplikate prüfen möchten. Wählen Sie Felder aus, die wahrscheinlich für jeden einzelnen Kunden eindeutig sind. Zum Beispiel eine E-Mail-Adresse oder die Kombination aus Name, Stadt und Telefonnummer.
   - Geben Sie die Normalisierungs- und Genauigkeitseinstellungen an.
   - Definieren Sie zusätzliche Bedingungen, indem Sie **Bedingung hinzufügen** wählen.
 
   > [!div class="mx-imgBorder"]
   > ![Deduplizierungsregeln Schritt 2](media/match-selfconflation-rules.png "Deduplizierungsregeln Schritt 2")

  Sie können mehrere Deduplizierungsregeln für eine Entität erstellen. 

1. Das Ausführen des Abgleichsprozesses gruppiert nun die Datensätze basierend auf den in den Deduplizierungsregeln definierten Bedingungen. Nach der Gruppierung der Datensätze wird die Richtlinie für die Zusammenführung angewendet, um den Gewinner-Datensatz zu identifizieren.

1. Dieser Gewinnerdatensatz wird dann zusammen mit den Nicht-Gewinnerdatensätzen (z. B. alternativen IDs) an den entitätsübergreifenden Abgleich weitergeleitet, um die Übereinstimmungsqualität zu verbessern.

1. Alle benutzerdefinierten Übereinstimmungsregeln, die definiert wurden, überschreiben Deduplizierungsregeln. Wenn eine Deduplizierungsregel übereinstimmende Datensätze identifiziert und eine benutzerdefinierte Abgleichsregel so eingestellt ist, dass diese Datensätze nie abgeglichen werden, dann werden diese beiden Datensätze nicht abgeglichen.

1. Nach dem [Ausführen des Abgleichs](#run-the-match-process) sehen Sie die Deduplizierungsstatistiken auf den Kacheln für wichtige Metriken.

### <a name="deduplication-output-as-an-entity"></a>Deduplizierungsausgabe als Entität

Der Deduplizierungsprozess erstellt für jede Entität aus den Übereinstimmungspaaren eine neue Entität, um die deduplizierten Datensätze zu identifizieren. Diese Entitäten können zusammen mit **ConflationMatchPairs: CustomerInsights** gefunden werden im **System**-Abschnitt auf der **Entitäten**-Seite mit dem Namen **Deduplication_DataSource_Entity** gefunden werden.

Eine Deduplizierungsausgabeentität enthält die folgenden Informationen:
- IDs/Schlüssel
  - Primärschlüsselfeld und sein alternatives ID-Feld. Das Feld „Alternative IDs“ besteht aus allen alternativen IDs, die für einen Datensatz identifiziert wurden.
  - Das Feld „Deduplication_GroupId“ zeigt die Gruppe oder den Cluster an, die bzw. der innerhalb einer Entität identifiziert wurde, die alle ähnlichen Datensätze basierend auf den angegebenen Deduplizierungsfeldern gruppiert. Dies wird für Systemverarbeitungszwecke verwendet. Wenn keine manuellen Deduplizierungsregeln angegeben sind und systemdefinierte Deduplizierungsregeln gelten, finden Sie dieses Feld möglicherweise nicht in der Deduplizierungsausgabeentität.
  - Deduplication_WinnerId: Dieses Feld enthält die Gewinner-ID der identifizierten Gruppen oder Cluster. Wenn „Deduplication_WinnerId“ mit dem Primärschlüsselwert für einen Datensatz identisch ist, bedeutet dies, dass der Datensatz der Gewinnerdatensatz ist.
- Felder zum Definieren der Deduplizierungsregeln.
- Regel- und Bewertungsfelder geben an, welche der Deduplizierungsregeln angewendet und welche Bewertung vom Übereinstimmungsalgorithmus zurückgegeben wurde.
   
## <a name="run-the-match-process"></a>Den Abgleichprozess ausführen

Nachdem Sie die Abgleichsregeln konfiguriert haben, einschließlich der Regeln für den entitätsübergreifenden Abgleich und die Deduplizierung, können Sie den Abgleichprozess ausführen. 

Gehen Sie zu **Daten** > **Vereinheitlichen** > **Abgleichen** und wählen Sie **Ausführen**, um den Prozess zu starten. Der Übereinstimmungsalgorithmus dauert einige Zeit und Sie können die Konfiguration erst ändern, wenn sie abgeschlossen ist. Um Änderungen vorzunehmen, können Sie die Ausführung abbrechen. Wählen Sie den Status des Jobs und wählen Sie **Auftrag abbrechen** im Bereich **Fortschrittsdetails**.

Das Ergebnis einer erfolgreichen Ausführung, die einheitliche Kundenprofilentität, finden Sie auf der Seite **Entitäten** Seite. Ihre einheitliche Kundenentität lautet **Kunden** im Abschnitt **Profile**. Die erste erfolgreiche Übereinstimmungsausführung erstellt die Entität einheitlicher *Kunde*. Alle nachfolgenden Übereinstimmungsausführungen erweitern diese Entität.

> [!TIP]
> Es gibt [sechs Arten von Status](system.md#status-types) für Aufgaben/Prozesse. Darüber hinaus [hängen die meisten Prozesse von anderen nachfolgenden Prozessen ab](system.md#refresh-policies). Sie können den Status eines Prozesses auswählen, um Details zum Fortschritt des gesamten Auftrags anzuzeigen. Nach der Auswahl von **Siehe Details** für eine der Aufgaben des Auftrags finden Sie zusätzliche Informationen: Verarbeitungszeit, das letzte Verarbeitungsdatum sowie alle mit der Aufgabe verbundenen Fehler und Warnungen.

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

:::image type="content" source="media/match-rules-management.png" alt-text="Screenshot des Dropdownmenüs mit Optionen für Übereinstimmungsregeln.":::

- **Ändern Sie die Reihenfolge Ihrer Regeln**, wenn Sie mehrere Regeln definiert haben. Sie können die Spielregeln neu anordnen, indem Sie die Optionen **Nach oben** und **Nach unten** wählen oder per Drag & Drop.

- **Regelbedingungen ändern** durch die Auswahl von **Bearbeiten** und wählen Sie verschiedene Felder.

- **Regel deaktivieren**, um eine Übereinstimmungsregel beizubehalten und sie gleichzeitig vom Übereinstimmungsprozess auszuschließen.

- **Duplizieren Sie Ihre Regeln**, wenn Sie eine Übereinstimmungsregel definiert haben und eine ähnliche Regel mit Änderungen erstellen möchten, wählen Sie **Duplizieren**.

- **Regel löschen** durch Auswahl des Symbols **Löschen**.

## <a name="specify-custom-match-conditions"></a>Benutzerdefinierte Übereinstimmungsbedingungen angeben

Sie können Bedingungen festlegen, dass bestimmte Datensätze immer oder nie übereinstimmen sollen. Diese Regeln können hochgeladen werden, um den Standard-Übereinstimmungsprozess zu überschreiben. Wenn beispielsweise John Doe I und John Doe II in unseren Aufzeichnungen enthalten sind, kann das System diese als eine Person abgleichen. Mit benutzerdefinierten Übereinstimmungsregeln können Sie festlegen, dass sich ihre Profile auf verschiedene Personen beziehen. 

1. Gehen Sie zu **Daten** > **Vereinheitlichen** > **Abgleichen** und wählen Sie **Benutzerdefinierte Übereinstimmung** im Abschnitt **Übereinstimmende Datensatzdetails** aus.

  :::image type="content" source="media/custom-match-create.png" alt-text="Screenshot des Abschnitts „Abgleichregeln” mit hervorgehobenem Steuerelement zum Überwachen benutzerdefinierter Übereinstimmungen.":::

1. Wenn Sie keine benutzerdefinierten Übereinstimmungsregeln festgelegt haben, wird ein neuer Bereich **Benutzerdefinierte Übereinstimmung** mit weiteren Details angezeigt.

1. Wählen Sie **Ausfüllen der Vorlage**, um eine Vorlagendatei zu erhalten, die angeben kann, welche Datensätze von welchen Entitäten immer oder nie übereinstimmen sollen. Sie müssen die "immer übereinstimmenden" und "nie übereinstimmenden" Datensätze in zwei verschiedenen Dateien getrennt ausfüllen.

1. Die Vorlage enthält Felder zur Angabe der Entität und der Primärschlüsselwerte der Entität, die bei der benutzerdefinierten Übereinstimmung verwendet werden sollen. Wenn Sie bespielsweise einen Primärschlüssel *12345* von der Entität *Vertrieb* möchten, die immer mit dem Primärschlüssel *34567* der Entität *Kontakt* übereinstimmt, füllen Sie die Vorlage aus:
    - Entität1: Verkauf
    - Entity1Key: 12345
    - Entität2: Kontakt
    - Entity2Key: 34567

   Dieselbe Vorlagendatei kann benutzerdefinierte Match-Datensätze von mehreren Entitäten angeben.
   
   Wenn Sie eine benutzerdefinierte Übereinstimmung für die Deduplizierung einer Entität angeben möchten, geben Sie dieselbe Entität wie Entität1 und Entität2 an und legen Sie die verschiedenen Primärschlüsselwerte fest.

1. Nachdem Sie alle Überschreibungen hinzugefügt haben, die Sie anwenden möchten, speichern Sie die Vorlagendatei.

1. Gehen Sie zu **Daten** > **Datenquellen** und nehmen Sie die Vorlagedateien als neue Entitäten auf. Nach der Aufnahme können Sie diese zur Festlegung der Match-Konfiguration verwenden.

1. Nachdem die Dateien und Entitäten hochgeladen wurden und verfügbar sind, wählen Sie erneut die Option **Abgleich nach Kennzahl**. Sie sehen Optionen zur Angabe der Entitäten, die Sie einbeziehen möchten. Wählen Sie die gewünschten Entitäten aus dem Dropdown-Menü.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Screenshot des Dialogfelds zum Auswählen von Überschreibungen für ein benutzerdefiniertes Übereinstimmungsszenario.":::

1. Markieren Sie die Entitäten, die Sie für **Immer gleich** und **Niemals gleich** verwenden möchten, wählen Sie **Erledigt**.

1. Wählen Sie **Speichern** auf der Seite **Abgleichen**, um die benutzerdefinierte Übereinstimmungskonfiguration anzuwenden.

1. Wählen Sie **Ausführen** auf der Seite **Abgleichen**, um den Abgleich zu starten. Andere angegebene Übereinstimmungsregeln werden von der benutzerdefinierten Übereinstimmungskonfiguration überschrieben.

> [!TIP]
> Gehen Sie zu **Daten** > **Entitäten** und überprüfen Sie die Entität **ConflationMatchPair**, um zu bestätigen, dass die Überschreibungen angewendet werden.

## <a name="next-step"></a>Nächster Schritt

Nachdem Sie den Abgleichsprozess für mindestens ein Abgleichspaar abgeschlossen haben, können Sie mögliche Widersprüche in Ihren Daten auflösen, indem Sie das Thema [**Zusammenführen**](merge-entities.md) durchlaufen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
