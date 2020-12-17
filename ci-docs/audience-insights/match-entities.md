---
title: Entitäten für die Datenvereinheitlichung abgleichen
description: Gleichen Sie Entitäten ab, um vereinheitlichte Kundenprofile zu erstellen.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 78549037f9c9e59329f5423c36eeb058128802c0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405791"
---
# <a name="match-entities"></a>Entitäten anpassen

Nach Abschluss der Zurordnungsphase sind Sie bereit, Ihre Entitäten abzugleichen. Die Abgleichsphase gibt an, wie Ihre Datensätze zu einem einheitlichen Kundenprofil-Datensatz kombiniert werden können. Die Abgleichsphase erfordert mindestens [zwei zugeordnete Entitäten](map-entities.md).

## <a name="specify-the-match-order"></a>Geben Sie die Reihenfolge der Übereinstimmung an

Gehen Sie zu **Vereinigen** > **Abgleichen** und wählen Sie **Reihenfolge festlegen**, um die Matchphase zu beginnen.

Jede Übereinstimmung vereinigt zwei oder mehr Entitäten zu einer einzigen Entität, wobei jeder eindeutige Kundendatensatz erhalten bleibt. Im folgenden Beispiel haben wir drei Entitäten ausgewählt: **KontaktCSV: TestData** als **Primary** Entität, **WebAccountCSV: TestData** als **Entität 2** und **CallRecordSmall: TestData** als **Entität 3**. Das Diagramm über den Auswahlen veranschaulicht, wie der Übereinstimmungsauftrag ausgeführt wird.

> [!div class="mx-imgBorder"]
> ![Reihenfolge der Datenabgleiche bearbeiten](media/configure-data-match-order-edit-page.png "Bearbeiten der Datenabgleichsreihenfolge")
  
Die Seite **Primär** wird mit **Entität 2** abgeglichen. Der Datensatz, der sich aus dem ersten Abgleich ergibt, wird mit **Entität3** abgeglichen.
In diesem Beispiel haben wir nur zwei Übereinstimmungen ausgewählt, aber das System kann mehr unterstützen.

> [!IMPORTANT]
> Die Entität, die Sie als Ihre **Primäre** Entität wählen, dient als Grundlage für Ihren einheitlichen Stammdatensatz. Zusätzliche Entitäten, die während der Übereinstimmungsphase ausgewählt werden, werden zu dieser Entität hinzugefügt. Gleichzeitig bedeutet dies nicht, dass die vereinheitlichte Entität *alle* der in dieser Entität enthaltenen Daten enthält.
>
> Es gibt zwei Überlegungen, die Ihnen bei der Auswahl der Hierarchie Ihrer Entitäten helfen können:
>
> - Welche Einheit verfügt Ihrer Meinung nach über die vollständigsten und zuverlässigsten Daten über Ihre Kunden?
> - Verfügt die gerade identifizierte Entität über Attribute, die auch von anderen Entitäten genutzt werden (z. B. Name, Telefonnummer oder E-Mail-Adresse)? Wenn nicht, wählen Sie Ihre zweitverlässigste Entität.

Wählen Sie **Abgeschlossen**, um die Übereinstimmungsreihenfolge zu speichern.

## <a name="define-rules-for-your-first-match-pair"></a>Definieren Sie Regeln für Ihr erstes Übereinstimmungspaar

Nachdem Sie die Reihenfolge der Übereinstimmungen festgelegt haben, sehen Sie die definierten Übereinstimmungen auf der Seite **Übereinstimmung**. Die Kacheln am oberen Bildschirmrand sind leer, bis Sie Ihren Abgleichsauftrag ausführen.

> [!div class="mx-imgBorder"]
> ![Regeln definieren](media/configure-data-match-need-rules.png "Definieren Sie Regeln")

Die Warnung **Benötigt Regeln** deutet darauf hin, dass für ein Match-Paar keine Match-Regel definiert ist. Übereinstimmungsregeln legen die Logik fest, nach der ein bestimmtes Paar von Entitäten abgeglichen wird.

1. Um Ihre erste Regel zu definieren, öffnen Sie den Bereich **Regeldefinition**, indem Sie die entsprechende Übereinstimmungsreihe in der Übereinstimmungstabelle (1) auswählen und dann **Neue Regel erstellen** (2) wählen.

   > [!div class="mx-imgBorder"]
   > ![Neue Regel erstellen](media/configure-data-match-new-rule2.png "Neue Regel erstellen")

2. Im Bereich **Regel bearbeiten** konfigurieren Sie die Bedingungen für diese Regel. Jede Bedingung wird durch zwei Zeilen dargestellt, die obligatorische Auswahlen enthalten.

   > [!div class="mx-imgBorder"]
   > ![Neuer Regelbereich](media/configure-data-match-new-rule-condition.png "Neues Regelfenster")

   Entität/Feld (erste) - Ein Attribut, das für den Abgleich von der ersten Übereinstimmung aus der ersten übereinstimmenden Paar-Entität verwendet wird. Beispiele könnten eine Telefonnummer oder E-Mail-Adresse sein. Wählen Sie ein Attribut, das wahrscheinlich für den Kunden eindeutig ist.

   > [!TIP]
   > Vermeiden Sie eine Zuordnung auf der Grundlage von Aktivitätsattributen. Mit anderen Worten, wenn ein Attribut eine Aktivität zu sein scheint, dann könnte es ein schlechtes Kriterium sein, dem man entsprechen muss.  

   Entität/Feld (zweite) - Ein Attribut, das für den Abgleich von der zweiten übereinstimmenden Paar-Entität verwendet wird.

   Normalisieren - **Normalisierungsmethode**: Für die ausgewählten Attribute stehen verschiedene Normierungsoptionen zur Verfügung. Zum Beispiel: Entfernen von Satzzeichen oder Leerzeichen

   Für die Normalisierung des Organisationsnamens (Vorschau) können Sie auch **Typ (Telefon, Name, Organisation)** wählen

   > [!div class="mx-imgBorder"]
   > ![Normalisierung-B2B](media/match-normalization-b2b.png "Normalisierung-B2B")

   Präzisionsniveau - Das Präzisionsniveau, das für diese Bedingung verwendet wird. Das Einstellen einer Präzisionsstufe für eine Übereinstimmungsbedingung kann zwei Arten haben: **Grundlegend** und **Anpassende Bedingung**.  
   - Basis: Bietet Ihnen vier Optionen zur Auswahl: Niedrig, Mittel, Hoch und Exakt. Wählen Sie **Exakt**, um nur Datensätze abzugleichen, die zu 100 Prozent übereinstimmen. Wählen Sie eine der anderen Ebenen aus, um Datensätze abzugleichen, die nicht 100 Prozent identisch sind.
   - Benutzerdefiniert: Verwenden Sie den Schieberegler, um den benutzerdefinierten Prozentsatz zu definieren, mit dem die Datensätze übereinstimmen müssen, oder geben Sie einen Wert in das Feld **Benutzerdefiniert** ein. Das System gleicht nur Datensätze, die diesen Schwellenwert überschreiten, als zusammengeführte Übereinstimmungspaare ab. Die Werte auf dem Schieberegler liegen zwischen 0 und 1. 0,64 entspricht also 64 Prozent.

3. Wählen Sie **Abgeschlossen**, um die Regel zu speichern.

### <a name="add-multiple-conditions"></a>Mehrere Bedingungen hinzufügen

Um Ihre Entitäten nur dann anzupassen, wenn mehrere Bedingungen erfüllt sind, fügen Sie weitere Bedingungen hinzu, die durch einen UND-Operator verknüpft sind.

1. Wählen Sie im Bereich **Regel bearbeiten** die Option **Bedingung hinzufügen**. Sie können auch Bedingungen löschen, indem Sie die Schaltfläche Entfernen neben einer vorhandenen Bedingung wählen.

2. Wählen Sie **Abgeschlossen** und speichern Sie die Regel.

## <a name="add-multiple-rules"></a>Mehrere Regeln hinzufügen

Jede Bedingung gilt für ein einzelnes Paar von Attributen, während Regeln Sätze von Bedingungen darstellen. Um Ihre Entitäten durch verschiedene Sätze von Attributen abzugleichen, können Sie weitere Regeln hinzufügen.

1. Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Vereinheitlichen** > **Zuordnen**.

2. Wählen Sie die Entität, die Sie aktualisieren möchten, und wählen Sie **Regeln hinzufügen**.

3. Befolgen Sie das Verfahren wie unter [Regeln für Ihr erstes Match-Paar definieren](#define-rules-for-your-first-match-pair) beschrieben.

> [!NOTE]
> Die Reihenfolge der Regeln ist wichtig. Der Matching-Algorithmus versucht, auf der Grundlage Ihrer ersten Regel einen Abgleich durchzuführen und fährt nur dann mit der zweiten Regel fort, wenn unter der ersten Regel keine Übereinstimmungen identifiziert wurden.

## <a name="define-deduplication-on-a-match-entity"></a>Definieren Sie die Deduplizierung auf einer Match-Entität

Neben der Angabe von Regeln für den Abgleich von Entitäten wie in den obigen Abschnitten beschrieben, können Sie auch Regeln für die Deduplizierung angeben. *Deduplizierung* ist ein Prozess. Es identifiziert doppelte Datensätze, fasst sie zu einem Datensatz zusammen und verknüpft alle Quelldatensätze mit diesem zusammengeführten Datensatz mit alternativen IDs zum zusammengeführten Datensatz.

Nachdem ein deduplizierter Datensatz identifiziert wurde, wird dieser Datensatz im Cross-Entity-Matching-Prozess verwendet. Die Deduplizierung wird auf der Ebene der Entitäten implementiert und kann auf jede Entität angewendet werden, die im Match-Prozess verwendet wird.

### <a name="add-deduplication-rules"></a>Deduplizierungsregeln hinzufügen

1. Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Vereinheitlichen** > **Zuordnen**.

1. Wählen Sie im Abschnitt **Zusammengeführte Duplikate** die Option **Entitäten einrichten**.

1. Wählen Sie im Bereich **Zusammenführungseinstellungen** die Entitäten aus, auf die Sie die Deduplizierung anwenden wollen.

1. Geben Sie an, wie die doppelten Datensätze zusammengeführt werden sollen und wählen Sie eine von drei Zusammenführungsoptionen:
   - *Am häufigsten*: Identifiziert den Datensatz mit den meisten ausgefüllten Attributen als Gewinner-Datensatz. Dies ist die Standard-Zusammenführungsoption.
   - *Aktuell*: Identifiziert den Gewinner-Datensatz auf der Basis der größten Aktualität. Benötigt ein Datum oder ein numerisches Feld, um die Aktualität zu definieren.
   - *Letzer*: Identifiziert den Gewinner-Datensatz basierend auf der besten Aktualität. Benötigt ein Datum oder ein numerisches Feld, um die Aktualität zu definieren.
 
   > [!div class="mx-imgBorder"]
   > ![Deduplizierungsregeln Schritt 1](media/match-selfconflation.png "Deduplizierungsregeln Schritt 1")
 
1. Sobald die Entitäten ausgewählt sind und ihre Zusammenführungspräferenz eingestellt ist, wählen Sie **Neue Regel erstellen**, um die Deduplizierungsregeln auf Entitätsebene zu definieren.
   - **Feld auswählen** listet alle verfügbaren Felder der Entität auf, für die Sie Quelldaten deduplizieren möchten.
   - Geben Sie die Normalisierungs- und Genauigkeitseinstellungen in ähnlicher Weise wie beim Cross-Entity-Abgleich an.
   - Sie können zusätzliche Bedingungen definieren, indem Sie **Bedingung hinzufügen** wählen.
 
   > [!div class="mx-imgBorder"]
   > ![Deduplizierungsregeln Schritt 2](media/match-selfconflation-rules.png "Deduplizierungsregeln Schritt 2")

  Sie können mehrere Deduplizierungsregeln für eine Entität erstellen. 

1. Das Ausführen des Abgleichsprozesses gruppiert nun die Datensätze basierend auf den in den Deduplizierungsregeln definierten Bedingungen. Nach der Gruppierung der Datensätze wird die Richtlinie für die Zusammenführung angewendet, um den Gewinner-Datensatz zu identifizieren.

1. Dieser Gewinner-Datensatz wird dann an den entitätsübergreifenden Abgleich weitergegeben.

1. Alle benutzerdefinierten Übereinstimmungsregeln, die für „Immer übereinstimmen“ und „Nie übereinstimmen“ definiert sind, setzen die Deduplizierungsregeln außer Kraft. Wenn eine Deduplizierungsregel übereinstimmende Datensätze identifiziert und eine benutzerdefinierte Abgleichsregel so eingestellt ist, dass diese Datensätze nie abgeglichen werden, dann werden diese beiden Datensätze nicht abgeglichen.

1. Nach dem Ausführen des Abgleichs sehen Sie die Deduplizierungsstatistiken.
   
> [!NOTE]
> Die Angabe von Deduplizierungsregeln ist nicht zwingend erforderlich. Wenn keine solchen Regeln konfiguriert sind, werden die systemdefinierten Regeln angewendet. Sie fassen alle Datensätze, die dieselbe Wertekombination (exakte Übereinstimmung) aus dem Primärschlüssel und den Feldern in den Abgleichsregeln haben, in einem einzigen Datensatz zusammen, bevor sie die Daten der Entitäten an den entitätsübergreifenden Abgleich weitergeben, um die Leistung und die Systemsauberkeit zu verbessern.

## <a name="run-your-match-order"></a>Führen Sie Ihre Übereinstimmungsreihenfolge aus

Nachdem Sie die Abgleichsregeln definiert haben, einschließlich der Regeln für den entitätsübergreifenden Abgleich und die Deduplizierung, können Sie die Abgleichsreihenfolge ausführen. Wählen Sie auf der Seite **Übereinstimmung** die Option **Ausführen**, um den Prozess zu starten. Der Matching-Algorithmus kann einige Zeit in Anspruch nehmen. Sie können die Eigenschaften auf der Seite **Abgleich** nicht ändern, bis der Abgleich-Prozess abgeschlossen ist. Sie finden die einheitliche Kundenprofil-Entität, die auf der Seite **Entitäten** erstellt wurde. Ihre vereinheitlichte Kundeneinheit heißt **ConflationMatchPairs : CustomerInsights**.

Um weitere Änderungen vorzunehmen und den Schritt erneut auszuführen, können Sie einen laufenden Abgleich abbrechen. Wählen Sie den Text **Wird aktualisiert ...** und **Auftrag abbrechen** am unteren Rand des angezeigten Seitenbereichs aus.

Wenn der Abgleichvorgang abgeschlossen ist, wird der Text **Wird aktualisiert ...** zu **Erfolgreich** geändert und Sie können alle Funktionen der Seite wieder verwenden.

Der erste Abgleichvorgang führt zur Erstellung einer einheitlichen Master-Entität. Alle nachfolgenden Abgleichsläufe führen zu einer Erweiterung dieser Entität.

> [!TIP]
> Es gibt [sechs Arten von Status](system.md#status-types) für Aufgaben/Prozesse. Darüber hinaus [hängen die meisten Prozesse von anderen nachfolgenden Prozessen ab](system.md#refresh-policies). Sie können den Status eines Prozesses auswählen, um Details zum Fortschritt des gesamten Auftrags anzuzeigen. Nach der Auswahl von **Siehe Details** für eine der Aufgaben des Auftrags finden Sie zusätzliche Informationen: Verarbeitungszeit, das letzte Verarbeitungsdatum sowie alle mit der Aufgabe verbundenen Fehler und Warnungen.

## <a name="review-and-validate-your-matches"></a>Überprüfen und validieren Sie Ihre Übereinstimmungen

Bewerten Sie die Qualität Ihrer Übereinstimmungspaarungen und verfeinern Sie sie:

- Auf der Seite **Übereinstimmung** finden Sie zwei Kacheln, die erste Erkenntnisse über Ihre Daten zeigen.

  - **Vereinigen**: zeigt die Anzahl der eindeutigen Profile, die das System identifiziert hat.
  - **Abgleichsätze**: zeigt die Anzahl der Übereinstimmungen über alle Ihre Übereinstimmungspaare an.

- In der Tabelle **Abgleichsreihenfolge** können Sie die Ergebnisse jedes Abgleichspaares bewerten, indem Sie die Anzahl der Datensätze, die von dieser Abgleichspaar-Einheit stammen, mit dem Prozentsatz der erfolgreich abgeglichenen Datensätze vergleichen.

- Im Bereich **Regeln** einer Entität in der Tabelle **Abgleichsreihenfolge** finden Sie den Prozentsatz der erfolgreich abgeglichenen Datensätze auf Regelebene. Wenn Sie das Tabellensymbol neben einer Regel auswählen, können Sie alle diese Datensätze auf Regelebene anzeigen. Wir empfehlen, dass Sie eine Teilmenge der Datensätze überprüfen, um zu überprüfen, ob sie korrekt zugeordnet wurden.

- Experimentieren Sie mit verschiedenen Präzisionsschwellenwerten um Ihre Bedingungen herum, um den optimalen Wert zu ermitteln.

  1. Wählen Sie die Auslassungspunkte (...) für die Match-Pair-Regel, mit der Sie experimentieren möchten, und wählen Sie **Bearbeiten**.

  2. Wählen Sie die Bedingung, mit der Sie experimentieren möchten. Jedes Kriterium wird durch eine Zeile im Bereich **Übereinstimmungsregel** repräsentiert.

  3. Was Sie auf der Seite **Kriterienvorschau** sehen, hängt von der Genauigkeitsstufe ab, die Sie für eine Bedingung gewählt haben. Suchen Sie die Anzahl der übereinstimmenden und nicht übereinstimmenden Datensätze für die ausgewählte Bedingung.

     Erhalten Sie ein umfassendes Verständnis der Auswirkungen verschiedener Schwellenwerte. Sie können vergleichen, wie viele Datensätze unter jeder der Schwellenwertebenen abgeglichen werden, und die Datensätze unter jeder Option anzeigen. Wählen Sie jede der Kacheln aus und überprüfen Sie die Daten im Tabellenbereich.

## <a name="optimize-your-matches"></a>Optimieren Sie Ihre Übereinstimmungen

Erhöhen Sie die Qualität, indem Sie einige Ihrer Abgleichsparameter neu konfigurieren:

- **Ändern Sie die Übereinstimmungsreihenfolge** durch Auswahl von **Bearbeiten** und ändern Sie die Felder der Übereinstimmungsreihenfolge.

  > [!div class="mx-imgBorder"]
  > ![Datenabgleichsreihenfolge bearbeiten](media/configure-data-match-order-edit.png "Reihenfolge des Datenabgleichs bearbeiten")

- **Ändern Sie die Reihenfolge Ihrer Regeln**, wenn Sie mehrere Regeln definiert haben. Sie können die Ablgeichsregeln neu anordnen, indem Sie die Optionen **Nach oben** und **Nach unten** im Abgleichsregelraster auswählen.

  > [!div class="mx-imgBorder"]
  > ![Regelreihenfolge ändern](media/configure-data-change-rule-order.png "Reihenfolge der Regeln ändern")

- **Duplizieren Sie Ihre Regeln** wenn Sie eine Übereinstimmungsregel definiert haben und eine ähnliche Regel mit Änderungen erstellen möchten. Wählen Sie dazu **Duplizieren**.

  > [!div class="mx-imgBorder"]
  > ![Regel duplizieren](media/configure-data-duplicate-rule.png "Eine Regel duplizieren")

- **Bearbeiten Sie Ihre Regeln** durch Auswahl des Symbols **Bearbeiten**. Sie können die folgenden Änderungen vornehmen:

  - Attribute für eine Bedingung ändern: Wählen Sie neue Attribute innerhalb der spezifischen Bedingungszeile aus.
  - Ändern Sie den Schwellenwert für eine Bedingung: Passen Sie den Präzisionsschieberegler an.
  - Ändern Sie die Normalisierungsmethode für eine Bedingung: Aktualisieren Sie die Normalisierungsmethode.

## <a name="specify-your-custom-match-records"></a>Geben Sie Ihre benutzerdefinierten Match-Datensätze an

Sie können Bedingungen festlegen, dass bestimmte Datensätze immer oder nie übereinstimmen sollen. Diese Regeln können in großen Mengen in den Abgleichprozess hochgeladen werden.

1. Wählen Sie die Option **Benutzerdefinierter Abgleich** auf dem Bildschirm **Abgleichauftrag**.

   > [!div class="mx-imgBorder"]
   > ![Erstellen einer benutzerdefinierten Übereinstimmung](media/custom-match-create.png "Erstellen Sie eine benutzerdefinierte Übereinstimmung")

2. Wenn Sie keine hochgeladenen Instanzen haben, wird ein neues Dialogfeld **Anpassung** angezeigt, in dem Sie einige Details ausfüllen müssen. Wenn Sie diese Details bereits früher angegeben haben, fahren Sie mit Schritt 8 fort.

   > [!div class="mx-imgBorder"]
   > ![Neues Dialogfeld für benutzerdefinierten Abgleich](media/custom-match-new-dialog-box.png "Neue benutzerdefinierte Dialogbox für die Übereinstimmung")

3. Wählen Sie **Ausfüllen der Vorlage**, um eine Vorlagendatei zu erhalten, die angeben kann, welche Datensätze von welchen Entitäten immer oder nie übereinstimmen sollen. Sie müssen die "immer übereinstimmenden" und "nie übereinstimmenden" Datensätze in zwei verschiedenen Dateien getrennt ausfüllen.

4. Die Vorlage enthält Felder zur Angabe der Entität und der Primärschlüsselwerte der Entität, die bei der benutzerdefinierten Übereinstimmung verwendet werden sollen. Wenn Sie beispielsweise möchten, dass der Primärschlüssel 12345 der Entität "Vertrieb" immer mit dem Primärschlüssel 34567 der Entität "Kontakt" übereinstimmt, müssen Sie Folgendes angeben:
    - Entität1: Verkauf
    - Entity1Key: 12345
    - Entität2: Kontakt
    - Entity2Key: 34567

   Dieselbe Vorlagendatei kann benutzerdefinierte Match-Datensätze von mehreren Entitäten angeben.

5. Nachdem Sie alle Überschreibungen hinzugefügt haben, die Sie anwenden möchten, speichern Sie die Vorlagendatei.

6. Gehen Sie zu **Daten** > **Datenquellen** und nehmen Sie die Vorlagedateien als neue Entitäten auf. Nach der Aufnahme können Sie diese zur Festlegung der Match-Konfiguration verwenden.

7. Nachdem die Dateien und Entitäten hochgeladen wurden und verfügbar sind, wählen Sie erneut die Option **Abgleich nach Kennzahl**. Sie sehen Optionen zur Angabe der Entitäten, die Sie einbeziehen möchten. Wählen Sie die gewünschten Entitäten aus dem Dropdown-Menü.

   > [!div class="mx-imgBorder"]
   > ![Überschiebung der Übereinstimmung durch den Kunden ](media/custom-match-overrides.png "Benutzerdefinierte Übereinstimmungen überschreiben")

8. Markieren Sie die Entitäten, die Sie für **Immer gleich** und **Niemals gleich** verwenden möchten, wählen Sie **Erledigt**.

9. Wählen Sie **Speichern** auf der Seite **Match** für die benutzerdefinierte Match-Konfiguration, die Sie gerade eingerichtet haben.

10. Wählen Sie **Ausführen** auf der Seite **Match**, um den Matching-Prozess zu starten, und die benutzerdefinierte Match-Konfiguration wird in Kraft gesetzt. Alle systemabgestimmten Regeln werden durch den Konfigurationssatz außer Kraft gesetzt.

11. Sobald der Abgleich abgeschlossen ist, können Sie die Entität **ConflationMatchPair** verifizieren, um zu bestätigen, dass die Überschreibungen in den Zusammenführungsübereinstimmungen angewendet werden.

## <a name="next-step"></a>Nächster Schritt

Nachdem Sie den Abgleichsprozess für mindestens ein Abgleichspaar abgeschlossen haben, können Sie mögliche Widersprüche in Ihren Daten auflösen, indem Sie das Thema [**Zusammenführen**](merge-entities.md) durchlaufen.
