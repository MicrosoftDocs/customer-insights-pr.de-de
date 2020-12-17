---
title: Segmente erstellen und verwalten
description: Erstellen Sie Kundensegmente, um sie auf der Grundlage verschiedener Attribute zu gruppieren.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405802"
---
# <a name="create-and-manage-segments"></a>Segmente erstellen und verwalten

Mit Segmenten können Sie Ihre Kunden anhand von demografischen, transaktionalen oder verhaltensbezogenen Attributen gruppieren. Sie können Segmente verwenden, um Werbekampagnen, Vertriebsaktivitäten und Kundensupportaktionen gezielt auf die Erreichung Ihrer Geschäftsziele auszurichten.

Sie können komplexe Filter um die Entität Kundenprofil und die damit verbundenen Entitäten definieren. Jedes Segment erstellt nach der Verarbeitung eine Reihe von Kundendatensätzen, die Sie exportieren und für die Sie Maßnahmen ergreifen können. Es gelten einige [Serviceeinschränkungen](service-limits.md).

Wenn nicht anders angegeben, handelt es sich bei allen Segmenten um **Dynamische Segmente**, die in einem wiederkehrenden Zeitplan aufgefrischt werden.

Das folgende Beispiel veranschaulicht die Funktionalität der Segmentierung. Wir haben ein Segment für Kunden definiert, die in den letzten 90 Tagen Waren im Wert von mindestens 500 US-Dollar bestellt haben *und* die an einem Kundenserviceanruf beteiligt waren, der eskaliert wurde.

> [!div class="mx-imgBorder"]
> ![Mehrere Gruppen](media/segmentation-group1-2.png "Mehrere Gruppen")

## <a name="create-a-new-segment"></a>Ein neues Segment erstellen

Segmente werden auf der Seite **Segmente** verwaltet.

1. Gehen Sie in den Zielgruppen-Insights auf die Seite **Segmente**.

2. Wählen Sie **Neu** > **Leeres Segment** aus.

3. Wählen Sie im Bereich **Neues Segment** einen Segmenttyp und geben Sie **Name** ein.

   Geben Sie optional einen Anzeigenamen und eine Beschreibung an, die die Identifizierung des Segments erleichtert.

4. Wählen Sie **Weiter**, um zu der Seite **Segment-Builder** zu gelangen, auf der Sie eine Gruppe definieren. Eine Gruppe ist eine Gruppe von Kunden.

5. Wählen Sie die Entität, die das Attribut enthält, nach dem Sie segmentieren möchten.

6. Wählen Sie das Attribut aus, nach dem segmentiert werden soll. Dieses Attribut kann einen von vier Werttypen haben: numerisch, Zeichenfolge, Datum oder boolesch.

7. Wählen Sie einen Operator und einen Wert für das ausgewählte Attribut.

   > [!div class="mx-imgBorder"]
   > ![Benutzerdefinierter Gruppenfilter](media/customer-group-numbers.png "Kundengruppen-Filter")

   |Anzahl |Definition  |
   |---------|---------|
   |1     |Entity          |
   |2     |Attribut          |
   |3    |Operator         |
   |4    |Wert         |

8. Wenn die Entität über [Beziehungen](relationships.md) mit der einheitlichen Kundenentität verbunden ist, müssen Sie den Beziehungspfad definieren, um ein gültiges Segment zu erstellen. Fügen Sie die Entitäten aus dem Beziehungspfad hinzu, bis Sie die Entität **Kunde: Customer Insights** aus der Dropdownliste auswählen können. Wählen Sie dann **Alle Datensätze** für jede Bedingung aus.

   > [!div class="mx-imgBorder"]
   > ![Beziehungspfad während der Segmenterstellung](media/segments-multiple-relationships.png "Beziehungspfad während der Segmenterstellung")

9. Wählen Sie **Speichern**, um Ihr Segment zu speichern. Ihr Segment wird gespeichert und verarbeitet, wenn alle Anforderungen validiert sind. Andernfalls wird es als Entwurf gespeichert.

10. Wählen Sie **Zurück zu Segmenten**, um zur Seite **Segmente** zurückzukehren.

## <a name="manage-existing-segments"></a>Vorhandene Segmente verwalten

Auf der Seite **Segmente** können Sie alle Ihre gespeicherten Segmente anzeigen und verwalten.

Jedes Segment wird durch eine Zeile dargestellt, die zusätzliche Informationen über das Segment enthält.

Sie können die Segmente in einer Spalte sortieren, indem Sie die Spaltenüberschrift auswählen.

Verwenden Sie das Feld **Suchen** in der oberen rechten Ecke, um die Segmente zu filtern.

> [!div class="mx-imgBorder"]
> ![Optionen zum Verwalten eines vorhandenen Segments](media/segments-selected-segment.png "Optionen zum Verwalten eines vorhandenen Segments")

Die folgende Aktion ist verfügbar, wenn Sie ein Segment auswählen:

- **Anzeigen** der Segmentdetails, einschließlich Trend der Anzahl der Mitglieder, Vorschau der Segmentmitglieder.
- **Bearbeiten** des Segments, um seine Eigenschaften zu ändern.
- **Aktualisieren** des Segments, um die neuesten Daten einzuschließen.
- **Aktivieren** oder **Deaktivieren** des Segments. Segmente haben zwei mögliche Status – aktiv oder inaktiv. Diese Status sind nützlich, wenn Sie ein Segment bearbeiten. Für inaktive Segmente ist die Segmentdefinition vorhanden, enthält jedoch noch keine Kunden. Wenn Sie ein Segment aktivieren, ändert sich sein Status von inaktiv in aktiv und es wird nach Kunden gesucht, die der Segmentdefinition entsprechen. Wenn eine [geplante Aktualisierung](system.md#schedule-tab) konfiguriert ist, haben inaktive Segmente den **Status** aufgelistet als **Übersprungen**. Dies zeigt an, dass nicht einmal eine Aktualisierung versucht wurde. Wenn ein inaktives Segment aktiviert wird, wird es aktualisiert und in geplante Aktualisierungen einbezogen.
  Alternativ können Sie die Funktionalität **Planen Sie später** im Auswahlmenü unter **Aktivieren/Deaktivieren** zur Angabe eines zukünftigen Datums und einer zukünftigen Uhrzeit für die Aktivierung und Deaktivierung eines bestimmten Segments verwenden.
- **Umbenennen** des Segments.
- **Download** die Liste der Mitglieder als .CSV-Datei herunterladen.
- **Hinzufügen zu**-Option sendet die Liste der Kunden-IDs im Segment zur Verarbeitung in einer anderen Anwendung.
- **Löschen** des Segments.

## <a name="refresh-segments"></a>Aktualisieren von Segmenten

Sie können alle Segmente auf einmal aktualisieren, indem Sie **Alles aktualisieren** auf der Seite **Segmente** wählen, oder Sie können ein oder mehrere Segmente aktualisieren, wenn Sie sie auswählen und **Aktualisieren** aus den Optionen wählen. Alternativ können Sie eine laufende Aktualisierung unter **Administrator** > **System** > **Zeitplan** konfigurieren.

> [!TIP]
> Es gibt [sechs Arten von Status](system.md#status-types) für Aufgaben/Prozesse. Darüber hinaus [hängen die meisten Prozesse von anderen nachfolgenden Prozessen ab](system.md#refresh-policies). Sie können den Status eines Prozesses auswählen, um Details zum Fortschritt des gesamten Auftrags anzuzeigen. Nach der Auswahl von **Siehe Details** für eine der Aufgaben des Auftrags finden Sie zusätzliche Informationen: Verarbeitungszeit, das letzte Verarbeitungsdatum sowie alle mit der Aufgabe verbundenen Fehler und Warnungen.

## <a name="download-and-export-segments"></a>Herunterladen und Exportieren von Segmenten

Sie können Ihre Segmente in eine CSV-Datei herunterladen oder nach Dynamics 365 Sales exportieren.

### <a name="download-segments-to-a-csv-file"></a>Herunterladen von Segmenten in eine CSV-Datei

1. Gehen Sie in den Zielgruppen-Insights auf die Seite **Segmente**.

2. Wählen Sie die Auslassungspunkte in der Kachel eines bestimmten Segments aus.

3. Wählen Sie **Download als CSV** aus der Dropdown-Liste Aktionen.

### <a name="export-segments-to-dynamics-365-sales"></a>Exportieren von Segmenten nach Dynamics 365 Sales

Vor dem Exportieren von Segmenten nach Dynamics 365 Sales muss ein Administrator [die Erstellung des Exportziels](export-destinations.md) für Dynamics 365 Sales vornehmen.

1. Gehen Sie in den Zielgruppen-Insights auf die Seite **Segmente**.

2. Wählen Sie die Auslassungspunkte in der Kachel eines bestimmten Segments aus.

3. Wählen Sie aus der Aktionen-Dropdownliste die Option **Hinzufügen** und dann das Exportziel aus, an das Sie die Daten senden möchten.

## <a name="draft-mode-for-segments"></a>Entwurfsmodus für Segmente

Wenn nicht alle Voraussetzungen für die Verarbeitung eines Segments erfüllt sind, können Sie das Segment als Entwurf speichern und von der Seite **Segmente** aufrufen.

Es wird als inaktives Segment gespeichert und kann erst aktiviert werden, wenn es gültig ist.

## <a name="add-more-conditions-to-a-group"></a>Weitere Bedingungen zu einer Gruppe hinzufügen

Um weitere Bedingungen zu einer Gruppe hinzuzufügen, können Sie zwei logische Operatoren verwenden:

- **AND** Operator: Beide Bedingungen müssen als Teil des Segmentierungsprozesses erfüllt sein. Diese Option ist am nützlichsten, wenn Sie Bedingungen für verschiedene Entitäten definieren.

- **OR**-Operator: Jede der beiden Bedingungen muss als Teil des Segmentierungsprozesses erfüllt sein. Diese Option ist am nützlichsten, wenn Sie mehrere Bedingungen für dieselbe Entität definieren.

   > [!div class="mx-imgBorder"]
   > ![OR-Operator, wobei jede der beiden Bedingungen erfüllt sein muss](media/segmentation-either-condition.png "OR-Operator, wobei jede der beiden Bedingungen erfüllt sein muss")

Es ist derzeit möglich, einen **OR** Operator unter einem **AND** Operator zu verschachteln, aber nicht umgekehrt.

## <a name="combine-multiple-groups"></a>Kombinieren mehrerer Gruppen

Jede Gruppe produziert eine bestimmte Gruppe von Kunden. Sie können diese Gruppen kombinieren, um die Kunden einzuschließen, die für Ihren Geschäftsfall erforderlich sind.

1. Gehen Sie in Zielgruppen-Insights auf die Seite **Segmente** und wählen Sie ein Segment aus.

2. Wählen Sie **Gruppe hinzufügen**.

   > [!div class="mx-imgBorder"]
   > ![Kundengruppe Gruppe hinzufügen](media/customer-group-add-group.png "Kundengruppe Gruppe hinzufügen")

3. Wählen Sie einen der folgenden Set-Operatoren aus: **Vereinigen**, **Überschneiden** oder **Außer**.

   > [!div class="mx-imgBorder"]
   > ![Kundengruppe Vereinigung hinzufügen](media/customer-group-union.png "Kundengruppe Vereinigung hinzufügen")

   Wählen Sie einen Set-Operator aus, um eine neue Gruppe zu definieren. Speichern Sie verschiedene Gruppen, um zu bestimmen, welche Daten erhalten bleiben sollen:

   - **Vereinigen** vereinigt die beiden Gruppen.

   - **Überschneiden** überschneidet die beiden Gruppen. Nur Daten, die *beiden Gruppen gemeinsam* sind, werden in der vereinigten Gruppe beibehalten.

   - **Außer** kombiniert die beiden Gruppen. Nur Daten in Gruppe A, die *nicht gemeinsam* mit Daten in Gruppe B sind, bleiben erhalten.

## <a name="view-processing-history-and-segment-members"></a>Anzeigen der Verarbeitungsgeschichte und der Segmentmitglieder

Sie können konsolidierte Daten zu einem Segment anzeigen, indem Sie die Details des Segments überprüfen.

Wählen Sie auf der Seite **Segmente** das Segment aus, das Sie überprüfen möchten.

Der obere Teil der Seite enthält ein Trenddiagramm, das Änderungen in der Mitgliederzahl visualisiert. Bewegen Sie die Maus über Datenpunkte, um die Mitgliederzahl an einem bestimmten Datum zu sehen.

Sie können den Zeitrahmen der Visualisierung aktualisieren.

> [!div class="mx-imgBorder"]
> ![Segmentzeitbereich](media/segment-time-range.png "Segmentzeitbereich")

Der untere Teil enthält eine Liste der Segmentmitglieder.

> [!NOTE]
> Felder, die in dieser Liste erscheinen, basieren auf den Attributen der Entitäten Ihres Segments.
>
>Die Liste ist eine Vorschau der passenden Segmentmitglieder und zeigt die ersten 100 Datensätze Ihres Segments an, so dass Sie es schnell auswerten und seine Definitionen bei Bedarf überprüfen können. Um alle übereinstimmenden Datensätze zu sehen, müssen Sie [Segment](export-destinations.md) exportieren.

## <a name="quick-segments"></a>Schnelle Segmente

Zusätzlich zum Segment-Builder gibt es einen weiteren Weg, um Segmente zu erstellen. Mit schnellen Segmenten können Sie einfache Segmente mit einem einzigen Operator schnell und mit sofortigen Erkenntnissen erstellen.

1. Wählen Sie auf der Seite **Segmente** die Option **Neu** > **Schnell erstellen aus**.

   - Wählen Sie die Option **Profile**, um ein Segment zu erstellen, das auf der einheitlichen Kundenentität basiert.
   - Wählen Sie die Option **Kennzahlen**, um ein Segment um jeden Kennzahlentyp vom Typ Kundenattribut herum aufzubauen, den Sie zuvor auf der Seite **Kennzahlen** erstellt haben.
   - Wählen Sie die Option **Intelligenz** zum Erstellen eines Segments für eine der Ausgabeentitäten aus, die Sie mit einer der beiden Funktionen **Vorhersagen** oder **Benutzerdefinierte Modelle** generiert haben.

2. Wählen Sie im Dialogfeld **Neues schnelles Segment** ein Attribut aus der Dropdownliste **Feld** aus.

3. Das System liefert einige zusätzliche Erkenntnisse, die Ihnen helfen, bessere Segmente Ihrer Kunden zu erstellen.
   - Für kategoriale Felder werden 10 Top-Kundenzahlen angezeigt. Wählen Sie einen **Wert** und wählen Sie **Überprüfung**.

   - Bei einem numerischen Attribut zeigt das System an, welcher Attributwert unter das Perzentil des jeweiligen Kunden fällt. Wählen Sie einen **Bediener** und einen **Wert**, dann wählen Sie **Review**.

4. Das System liefert Ihnen eine **geschätzte Segmentgröße**. Sie können wählen, ob Sie das von Ihnen definierte Segment generieren oder es zunächst erneut aufrufen, um eine andere Segmentgröße zu erhalten.

    > [!div class="mx-imgBorder"]
    > ![Name und Schätzung für ein Quick-Segment](media/quick-segment-name.png "Name und Schätzung für ein schnelles Segment")

5. Geben Sie einen **Name** für Ihr Segment an. Geben Sie optional einen **Anzeigename** ein.

6. Wählen Sie **Speichern**, um Ihr Segment zu erstellen.

7. Nachdem das Segment fertig bearbeitet wurde, können Sie es wie jedes andere von Ihnen erstellte Segment anzeigen.

Für die folgenden Szenarien empfehlen wir, den Segment-Builder statt der empfohlenen Segment-Fähigkeit zu verwenden:

- Erstellen von Segmenten mit Filtern auf kategoriale Felder, bei denen sich der Operator von dem Operator **Ist** unterscheidet
- Erstellen von Segmenten mit Filtern für numerische Felder, bei denen der Operator sich von den Operatoren **Zwischen**, **Größer als** und **Kleiner als** unterscheidet
- Erstellen von Segmenten mit Filtern für Datumsfelder

## <a name="next-steps"></a>Nächste Schritte

[Exportieren Sie ein Segment](export-destinations.md) und erkunden Sie die [Kundenkarte](customer-card-add-in.md) und [Connectors](export-power-bi.md), um Einblicke auf Kundenebene zu erhalten.
