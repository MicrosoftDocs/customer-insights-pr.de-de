---
title: Kennzahlen erstellen und verwalten
description: Kennzahlen definieren, um Leistung und Zustand Ihres Unternehmens zu analysieren und widerzuspiegeln.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654731"
---
# <a name="define-and-manage-measures"></a>Definieren und Verwalten von Kennzahlen

Mithilfe von Kennzahlen können Sie das Kundenverhalten und die Geschäftsleistung besser verstehen, indem Sie relevante Werte von [einheitlichen Profilen](data-unification.md) abrufen. Zum Beispiel möchte ein Unternehmen die *Gesamtausgaben pro Kunde* ermitteln, um die Kaufhistorie des einzelnen Kunden zu verstehen. Oder messen Sie den *Gesamtumsatz des Unternehmens*, um den aggregierten Gesamtumsatz im gesamten Unternehmen zu verstehen.  

Kennzahlen werden mit dem Kennzahlungsgenerator erstellt, einer Datenabfrageplattform mit verschiedenen Operatoren und einfachen Zuordnungsoptionen. Sie können die Daten filtern, Ergebnisse gruppieren und [Entitätsbeziehungspfade](relationships.md) erkennen und zeigen eine Vorschau der Ausgabe anzeigen.

Verwenden Sie die Kennzahlenerstellung, um Geschäftsaktivitäten zu planen, indem Sie Kundendaten abfragen und Erkenntnisse extrahieren. Erstellen Sie beispielsweise eine Kennzahl für *Gesamtausgaben pro Kunde* und *Gesamtrendite pro Kunde* hilft bei der Identifizierung einer Gruppe von Kunden mit hohen Ausgaben und hoher Rendite. Sie können [ein Segment erstellen](segments.md), um die nächstbesten Aktionen zu fahren. 

## <a name="create-a-measure"></a>Eine Kennzahl erstellen

In diesem Abschnitt erfahren Sie, wie Sie eine neue Kennzahl von Grund auf neu erstellen. Sie können eine Kennzahl mit Datenattributen aus Datenentitäten erstellen, für die eine Beziehung zur Verbindung mit der Kundenentität eingerichtet wurde. 

1. Gehen Sie in den Zielgruppen-Insights auf **Kennzahlen**.

1. Wählen Sie **Neu**.

1. Wählen **Namen bearbeiten** und stellen einen **Namen** für die Kennzahl bereit. 
   > [!NOTE]
   > Wenn Ihre neue Kennzahlkonfiguration nur zwei Felder enthält, z. B. CustomerID und eine Berechnung, wird die Ausgabe als neue Spalte zu der vom System generierten Entität Customer_Measure hinzugefügt. Und Sie können den Wert der Kennzahl im einheitlichen Kundenprofil sehen. Andere Kennzahlen werden ihre eigenen Einheiten erzeugen.

1. Wählen Sie im Konfigurationsbereich die Aggregationsfunktion aus dem **Funktion auswählen** Dropdownmenü aus. Zu den Aggregationsfunktionen gehören: 
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
  
   1. Im **Attribut hinzufügen**-Abschnitt des **Filter** -Bereichs wählen Sie das Attribut aus, mit dem Sie Filter erstellen möchten.
   1. Legen Sie die Filteroperatoren fest, um den Filter für jedes ausgewählte Attribut zu definieren.
   1. Wählen Sie **Anwenden**, um den Filter zur Kennzahl hinzuzufügen.

1. Um Dimensionen hinzuzufügen, wählen Sie **Dimension** im Konfigurationsbereich. Dimensionen werden als Spalten in der Kennzahlausgabeeinheit angezeigt.
   1. Wählen Sie **Dimensionen bearbeiten** aus, um Datenattribute hinzuzufügen, nach denen Sie die Kennzahlen gruppieren möchten. Zum Beispiel Stadt oder Geschlecht. Standardmäßig wird die *Kundennummer*-Dimension zum Erstellen von *Kennzahlen auf Kundenebene* ausgewählt. Sie können die Standarddimension entfernen, wenn Sie *Kennzahlen auf Unternehmensebene* erstellen möchten.
   1. Wählen Sie **Fertig**, um die Dimensionen zur Kennzahl hinzuzufügen.

1. Wenn zwischen der von Ihnen zugeordneten Datenentität und der *Kunden* Entität mehrere Pfade vorhanden sind, müssen Sie einen der identifizierten [Entitätsbeziehungspfade auswählen](relationships.md). Die Kennzahlenergebnisse können je nach ausgewähltem Pfad variieren. 
   1. Wählen Sie **Dateneinstellungen**, und wählen Sie den Entitätspfad aus, der zur Identifizierung Ihrer Kennzahl verwendet werden soll. Wenn es nur einen einzigen Weg zur Entität *Kunde* gibt, wird dieses Steuerelement nicht angezeigt.
   1. Wählen **Fertig**, um Ihre Auswahl anzuwenden. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Wählen Sie den Entitätspfad für die Kennzahl aus.":::

1. Wählen Sie aus **Neue Berechnung**, um weitere Berechnungen für die Kennzahl hinzuzufügen. Sie können nur Entitäten im selben Entitätspfad für neue Berechnungen verwenden. Weitere Berechnungen werden als neue Spalten in der Kennzahlausgabeeinheit angezeigt.

1. Wählen Sie **...** für die Berechnung aus, um **Duplikat**, **Umbenennen** oder **Entfernen** zur Berechnung einer Kennzahl auszuwählen.

1. Im Bereich **Vorschau** sehen Sie das Datenschema der Kennzahlausgabeentität, einschließlich Filter und Dimensionen. Die Vorschau reagiert dynamisch auf Änderungen in der Konfiguration.

1. Wählen **Ausführen**, um die Ergebnisse für die konfigurierte Messung zu berechnen. Wählen Sie **Speichern und schließen** aus, wenn Sie die aktuelle Konfiguration beibehalten und die Kennzahlmessung später ausführen möchten.

1. Gehen Sie zu **Kennzahlen**, um die neu erstellte Kennzahl in der Liste anzuzeigen.

## <a name="manage-your-measures"></a>Verwalten von Kennzahlen

Nachdem Sie mindestens eine [Kennzahl erstellt](#create-a-measure) haben, sehen Sie eine Liste der Kennzahlen auf der Seite **Kennzahlen**.

Sie finden Informationen zu Kennzahlentyp, Ersteller, Erstellungsdatum, Status und Zustand. Wenn Sie eine Kennzahl aus der Liste auswählen, können Sie eine Vorschau der Ausgabe anzeigen und eine CSV-Datei herunterladen.

Um alle Ihre Kennzahlen gleichzeitig zu aktualisieren, wählen Sie **Alle aktualisieren** aus, ohne eine bestimmte Kennzahl auszuwählen.

> [!div class="mx-imgBorder"]
> ![Maßnahmen zur Verwaltung einzelner Kennzahlen](media/measure-actions.png "Maßnahmen zur Verwaltung einzelner Kennzahlen")

Wählen Sie eine Kennzahl aus den folgenden Optionen in der Liste aus:

- Wählen Sie den Kennzahlnamen aus, um dessen Details anzuzeigen.
- **Bearbeiten** der Konfiguration der Kennzahl.
- **Aktualisieren** Sie die Maßnahme basierend auf den neuesten Daten.
- **Umbenennen** der Kennzahl.
- **Löschen** der Kennzahl.
- **Aktivieren** oder **Deaktivieren**. Inaktive Maßnahmen werden während einer [geplanten Aktualisierung](system.md#schedule-tab) nicht aktualisiert.

> [!TIP]
> Es gibt [sechs Arten von Status](system.md#status-types) für Aufgaben/Prozesse. Darüber hinaus [hängen die meisten Prozesse von anderen nachfolgenden Prozessen ab](system.md#refresh-policies). Sie können den Status eines Prozesses auswählen, um Details zum Fortschritt des gesamten Auftrags anzuzeigen. Nach der Auswahl von **Siehe Details** für eine der Aufgaben des Auftrags finden Sie zusätzliche Informationen: Verarbeitungszeit, das letzte Verarbeitungsdatum sowie alle mit der Aufgabe verbundenen Fehler und Warnungen.

## <a name="next-step"></a>Nächster Schritt

Sie können vorhandene Kennzahlen zum Erstellen [eines Kundensegments](segments.md) verwenden.


[!INCLUDE[footer-include](../includes/footer-banner.md)]