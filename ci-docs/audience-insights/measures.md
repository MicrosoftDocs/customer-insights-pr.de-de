---
title: Kennzahlen erstellen und verwalten
description: Kennzahlen definieren, um Leistung und Zustand Ihres Unternehmens zu analysieren und widerzuspiegeln.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a83caf2428f3dbd9791b9f746d00d370362a508c
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304792"
---
# <a name="define-and-manage-measures"></a>Definieren und Verwalten von Kennzahlen

Mithilfe von Kennzahlen können Sie das Kundenverhalten und die Geschäftsleistung besser verstehen. Sie betrachten relevante Werte aus [einheitlichen Profilen](data-unification.md). Ein Unternehmen möchte beispielsweise die *Gesamtausgaben pro Kunde* ermitteln, um den Kaufverlauf oder -messung eines einzelnen Kunden oder den *Gesamtumsatz des Unternehmens* zu verstehen, um den aggregierten Gesamtumsatz des gesamten Unternehmens zu verstehen.  

Kennzahlen werden mit dem Kennzahlungsgenerator erstellt, einer Datenabfrageplattform mit verschiedenen Operatoren und einfachen Zuordnungsoptionen. Sie können die Daten filtern, Ergebnisse gruppieren und [Entitätsbeziehungspfade](relationships.md) erkennen und zeigen eine Vorschau der Ausgabe anzeigen.

Verwenden Sie die Kennzahlenerstellung, um Geschäftsaktivitäten zu planen, indem Sie Kundendaten abfragen und Erkenntnisse extrahieren. Erstellen Sie beispielsweise eine Kennzahl für *Gesamtausgaben pro Kunde* und *Gesamtrendite pro Kunde* hilft bei der Identifizierung einer Gruppe von Kunden mit hohen Ausgaben und hoher Rendite. Sie können [ein Segment erstellen](segments.md), um die nächstbesten Aktionen zu fahren. 

## <a name="build-your-own-measure-from-scratch"></a>Eigene Kennzahlen von Grund auf neu erstellen

In diesem Abschnitt erfahren Sie, wie Sie eine neue Kennzahl von Grund auf neu erstellen. Sie können eine Kennzahl mit Datenattributen aus Datenentitäten erstellen, für die eine Beziehung zur Verbindung mit der Kundenentität eingerichtet wurde. 

1. Gehen Sie in den Zielgruppen-Insights auf **Kennzahlen**.

1. Wählen Sie **Neu** und dann **Eigene erstellen** aus.

1. Wählen **Namen bearbeiten** und stellen einen **Namen** für die Kennzahl bereit. 
   > [!NOTE]
   > Wenn Ihre neue Kennzahlkonfiguration nur zwei Felder enthält, z. B. CustomerID und eine Berechnung, wird die Ausgabe als neue Spalte zu der vom System generierten Entität Customer_Measure hinzugefügt. Und Sie können den Wert der Kennzahl im einheitlichen Kundenprofil sehen. Andere Kennzahlen werden ihre eigenen Einheiten erzeugen.

1. Wählen Sie im Konfigurationsbereich die Aggregationsfunktion aus dem Dropdown-Menü **Funktion auswählen** aus. Zu den Aggregationsfunktionen gehören: 
   - **Sum**
   - **Durchschnitt**
   - **Anzahl**
   - **Anzahl einzigartiger Elemente**
   - **Max.**
   - **Min**
   - **Erste**: Nimmt den ersten Wert des Datensatzes
   - **Letzte**: Nimmt den letzten Wert, der dem Datensatz hinzugefügt wurde

   :::image type="content" source="media/measure-operators.png" alt-text="Operatoren für Kennzahlberechnungen.":::

1. WählenSie **Attribute hinzufügen**, um die Daten auszuwählen, die Sie zum Erstellen dieser Kennzahl benötigen.
   
   1. Die **Attribute**-Registerkarte auswählen. 
   1. Datenentität: Wählen Sie die Entität aus, die das Attribut enthält, das Sie messen möchten. 
   1. Datenattribut: Wählen Sie das Attribut aus, das Sie in der Aggregationsfunktion zur Berechnung der Kennzahl verwenden möchten. Sie können jeweils nur ein Attribut auswählen.
   1. Sie können auch ein Datenattribut aus einer vorhandenen Kennzahl auswählen, indem Sie die Registerkarte **Kennzahlen** auswählen. Sie können auch nach einem Entitäts- oder Kennzahlnamen suchen. 
   1. WählenSie **Hinzufügen**, um das ausgewählte Attribut zur Kennzahl hinzuzufügen.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Wählen Sie ein Attribut aus, das in Berechnungen verwendet werden soll.":::

1. Um komplexere Kennzahlen zu erstellen, können Sie weitere Attribute hinzufügen oder mathematische Operatoren für Ihre Kennzahlfunktion verwenden.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Erstellen Sie eine komplexe Kennzahl mit mathematischen Operatoren.":::

1. Um Filter hinzuzufügen, wählen Sie **Filter** im Konfigurationsbereich. 
  
   1. In dem Abschnitt **Attribute hinzufügen** des Bereichs **Filter** wählen Sie im Bereich das Attribut aus, das Sie zum Erstellen von Filtern verwenden möchten.
   1. Legen Sie die Filteroperatoren fest, um den Filter für jedes ausgewählte Attribut zu definieren.
   1. Wählen Sie **Anwenden**, um den Filter zur Kennzahl hinzuzufügen.

1. Um Dimensionen hinzuzufügen, wählen Sie **Dimension** im Konfigurationsbereich. Dimensionen werden als Spalten in der Kennzahlausgabeeinheit angezeigt.
 
   1. Wählen Sie **Dimensionen bearbeiten** aus, um Datenattribute hinzuzufügen, nach denen Sie die Kennzahlen gruppieren möchten. Zum Beispiel Stadt oder Geschlecht. Standardmäßig wird die *Kundennummer*-Dimension zum Erstellen von *Kennzahlen auf Kundenebene* ausgewählt. Sie können die Standarddimension entfernen, wenn Sie *Kennzahlen auf Unternehmensebene* erstellen möchten.
   1. Wählen Sie **Fertig**, um die Dimensionen zur Kennzahl hinzuzufügen.

1. Wenn Ihre Daten Werte enthalten, die Sie beispielsweise durch eine Ganzzahl ersetzen müssen, ersetzen Sie *null* mit *0* und wählen **Regeln** aus. Konfigurieren Sie die Regel und stellen Sie sicher, dass Sie nur ganze Zahlen als Ersatz auswählen.

1. Wenn zwischen der von Ihnen zugeordneten Datenentität und der *Kunden* Entität mehrere Pfade vorhanden sind, müssen Sie einen der identifizierten [Entitätsbeziehungspfade auswählen](relationships.md). Die Kennzahlenergebnisse können je nach ausgewähltem Pfad variieren. 
   
   1. Wählen Sie **Dateneinstellungen**, und wählen Sie den Entitätspfad aus, der zur Identifizierung Ihrer Kennzahl verwendet werden soll. Wenn es nur einen einzigen Weg zur Entität *Kunde* gibt, wird dieses Steuerelement nicht angezeigt.
   1. Wählen **Fertig**, um Ihre Auswahl anzuwenden. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Wählen Sie den Entitätspfad für die Kennzahl aus.":::

1. Wählen Sie aus **Neue Berechnung**, um weitere Berechnungen für die Kennzahl hinzuzufügen. Sie können nur Entitäten im selben Entitätspfad für neue Berechnungen verwenden. Weitere Berechnungen werden als neue Spalten in der Kennzahlausgabeeinheit angezeigt.

1. Wählen Sie **...** für die Berechnung aus, um **Duplikat**, **Umbenennen** oder **Entfernen** zur Berechnung einer Kennzahl auszuwählen.

1. Im Bereich **Vorschau** sehen Sie das Datenschema der Kennzahlausgabeentität, einschließlich Filter und Dimensionen. Die Vorschau reagiert dynamisch auf Änderungen in der Konfiguration.

1. Wählen **Ausführen**, um die Ergebnisse für die konfigurierte Messung zu berechnen. Wählen Sie **Speichern und schließen** aus, wenn Sie die aktuelle Konfiguration beibehalten und die Kennzahlmessung später ausführen möchten.

1. Gehen Sie zu **Kennzahlen**, um die neu erstellte Kennzahl in der Liste anzuzeigen.

## <a name="use-a-template-to-build-a-measure"></a>Verwenden Sie eine Vorlage, um eine Kennzahl zu erstellen

Sie können vordefinierte Vorlagen häufig verwendeter Kennzahlen verwenden, um sie zu erstellen. Detaillierte Beschreibungen der Vorlagen und eine geführte Erfahrung helfen Ihnen bei der effizienten Erstellung von Kennzahlen. Vorlagen bauen auf zugeordneten Daten aus der *Einheitliche Aktivität*-Entität auf. Stellen Sie also sicher, dass Sie [Kundenaktivitäten](activities.md) konfiguriert haben, bevor Sie eine Kennzahl aus einer Vorlage erstellen.

Verfügbare Kennzahlenvorlagen: 
- Durchschnittlicher Transaktionswert (ATV)
- Transaktionswert insgesamt
- Durchschnittlicher täglicher Umsatz
- Durchschnittlicher Jahresumsatz
- Transaktionsanzahl
- Erhaltene Treuepunkte
- Eingelöste Treuepunkte
- Treuepunktebilanz
- Aktive Kundenlebensdauer
- Dauer der Treuemitgliedschaft
- Zeit seit dem letzten Kauf

Das folgende Verfahren beschreibt die Schritte zum Erstellen einer neuen Kennzahl mithilfe einer Vorlage.

1. Gehen Sie in den Zielgruppen-Insights auf **Kennzahlen**.

1. Wählen Sie **Neu** und dann **Vorlage auswählen** aus.

   :::image type="content" source="media/measure-use-template.png" alt-text="Screenshot des Dropdown-Menüs beim Erstellen einer neuen Kennzahl mit Hervorhebung auf der Vorlage.":::

1. Suchen Sie die Vorlage, die Ihren Anforderungen entspricht, und wählen Sie **Vorlage auswählen** aus.

1. Überprüfen Sie die erforderlichen Daten und wählen Sie **Los geht's** aus, wenn Sie alle Daten an Ort und Stelle haben.

1. Im Bereich **Name bearbeiten** legen Sie den Namen für Ihre Kennzahl und die Ausgabeentität fest. 

1. Wählen Sie **Fertig** aus.

1. Im Abschnitt **Zeitraum festlegen** definieren Sie den Zeitrahmen der zu verwendenden Daten. Wählen Sie aus, ob die neue Kennzahl das gesamte DataSet abdecken soll, indem Sie **Immer** oder **Spezifischen Zeitraum** auswählen, wenn Sie möchten, dass sich die Kennzahl nur auf einen bestimmten Zeitraum bezieht.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Screenshot mit dem Abschnitt zum Zeitraum beim Konfigurieren einer Kennzahl aus einer Vorlage.":::

1. Wählen Sie im nächsten Abschnitt **Daten hinzufügen** aus, um die Aktivitäten auszuwählen und die entsprechenden Daten von Ihrer *Einheitliche Aktivität*-Entität zuzuordnen.

    1. Schritt 1 von 2: Unter **Aktivitätstyp** wählen Sie den Typ der Entität, die Sie verwenden möchten. Für **Aktivitäten** wählen Sie die Objekte aus, die Sie zuordnen möchten.
    1. Schritt 2 von 2: Wählen Sie das Attribut aus der *Einheitliche Aktivität*-Entität für die von der Formel geforderte Komponente aus. Für den durchschnittlichen Transaktionswert ist dies beispielsweise das Attribut, das den Transaktionswert darstellt. Für **Aktivitätszeitstempel** wählen Sie das Attribut aus der Entität „Einheitliche Aktivität“ aus, das Datum und Uhrzeit der Aktivität darstellt.
   
1. Sobald die Datenzuordnung erfolgt ist, können Sie den Status als **Abgeschlossen** und den Namen der zugeordneten Aktivitäten und Attribute anzeigen.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Screenshot einer abgeschlossenen Kennzahlvorlagenkonfiguration.":::

1. Sie können jetzt **Ausführen** auswählen, um die Ergebnisse der Messung zu berechnen. Um dies später zu verfeinern, wählen Sie **Entwurf speichern**.

## <a name="manage-your-measures"></a>Verwalten von Kennzahlen

Die Liste der Kennzahlen finden Sie auf der Seite **Kennzahlen**.

Sie finden Informationen zu Kennzahlentyp, Ersteller, Erstellungsdatum, Status und Zustand. Wenn Sie eine Kennzahl aus der Liste auswählen, können Sie eine Vorschau der Ausgabe anzeigen und eine CSV-Datei herunterladen.

Um alle Ihre Kennzahlen gleichzeitig zu aktualisieren, wählen Sie **Alle aktualisieren** aus, ohne eine bestimmte Kennzahl auszuwählen.

> [!div class="mx-imgBorder"]
> ![Maßnahmen zur Verwaltung einzelner Kennzahlen.](media/measure-actions.png "Maßnahmen zur Verwaltung einzelner Kennzahlen.")

Wählen Sie eine Kennzahl aus den folgenden Optionen in der Liste aus:

- Wählen Sie den Kennzahlnamen aus, um dessen Details anzuzeigen.
- **Bearbeiten** der Konfiguration der Kennzahl.
- **Aktualisieren** Sie die Maßnahme basierend auf den neuesten Daten.
- **Umbenennen** der Kennzahl.
- **Löschen** der Kennzahl.
- **Aktivieren** oder **Deaktivieren**. Inaktive Maßnahmen werden während einer [geplanten Aktualisierung](system.md#schedule-tab) nicht aktualisiert.

> [!TIP]
> Es gibt [sechs Arten von Status](system.md#status-types) für Aufgaben/Prozesse. Darüber hinaus [hängen die meisten Prozesse von anderen nachfolgenden Prozessen ab](system.md#refresh-policies). Sie können den Status eines Prozesses auswählen, um Details zum Fortschritt des gesamten Auftrags anzuzeigen. Nach der Auswahl von **Siehe Einzelheiten** für eine der Aufgaben des Auftrags finden Sie zusätzliche Informationen: Bearbeitungszeit, das letzte Verarbeitungsdatum und alle mit der Aufgabe verbundenen Fehler und Warnungen.

## <a name="next-step"></a>Nächster Schritt

Sie können vorhandene Maßnahmen verwenden, um [ein Kundensegment](segments.md) zu erstellen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
