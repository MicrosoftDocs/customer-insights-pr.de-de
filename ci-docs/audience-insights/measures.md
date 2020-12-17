---
title: Erstellen und Bearbeiten von Kennzahlen
description: Definieren Sie kundenbezogene Kennzahlen, um die Leistung bestimmter Geschäftsbereiche zu analysieren und widerzuspiegeln.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405793"
---
# <a name="define-and-manage-measures"></a>Definieren und Verwalten von Kennzahlen

**Kennzahlen** stellen Key Performance Indicators (KPIs) dar, die die Leistung und den Gesundheitszustand bestimmter Geschäftsbereiche widerspiegeln. Zielgruppen-Insights bietet ein intuitives Erlebnis für die Erstellung verschiedener Arten von Kennzahlen mithilfe eines Query Builders, der es nicht erforderlich macht, dass Sie Ihre Kennzahlen manuell codieren oder validieren müssen. Sie können Ihre Geschäftskennzahlen auf der Seite **Home** verfolgen, Kennzahlen für bestimmte Kunden auf der Seite **Kundenkarte** sehen und Kennzahlen zur Definition von Kundensegmenten auf der Seite **Segmente** verwenden.

## <a name="create-a-measure"></a>Eine Kennzahl erstellen

Dieser Abschnitt führt Sie durch die Erstellung einer Kennzahl von Grund auf. Sie können Kennzahlen mit Daten aus mehreren Datenquellen erstellen, die über die Entität Kunde verbunden sind. Es gelten einige [Serviceeinschränkungen](service-limits.md).

1. Gehen Sie in den Zielgruppen-Insights auf **Kennzahlen**.

2. Wählen Sie **Neue Kennzahl**.

3. Wählen Sie die Kennzahl **Typ**:

   - **Kundenattribut**: Ein einzelnes Feld pro Kunde, das einen Score, Wert oder Zustand für den Kunden widerspiegelt. Kundenattribute werden als Attribute in einer neuen, vom System generierten Entität mit dem Namen **Customer_Measure** angelegt.

   - **Kundenkennzahlen**: Einblicke in das Kundenverhalten mit Aufschlüsselung nach ausgewählten Dimensionen. Für jede Kennzahl wird eine neue Einheit generiert, möglicherweise mit mehreren Datensätzen pro Kunde.

   - **Business-Kennzahlen**: Verfolgt Ihre geschäftliche Leistung und den Zustand des Unternehmens. Geschäftskennzahlen können zwei verschiedene Ausgaben haben: eine numerische Ausgabe, die auf der Seite **Start** angezeigt wird, oder eine neue Einheit, die Sie auf der Seite **Entitäten** finden.

4. Geben Sie einen **Name** und einen optionalen **Anzeigename** ein und wählen Sie dann **Nächster**.

5. Wählen Sie im Bereich **Entitäten** die erste Entität aus der Dropdown-Liste aus. An diesem Punkt sollten Sie entscheiden, ob zusätzliche Entitäten als Teil Ihrer Kennzahlendefinition benötigt werden.

   > [!div class="mx-imgBorder"]
   > ![Kennzahldefinition](media/measure-definition.png "Definition der Kennzahl")

   Um weitere Entitäten hinzuzufügen, wählen Sie **Entität hinzufügen** und wählen Sie die Entitäten aus, die Sie für die Kennzahl verwenden möchten.

   > [!NOTE]
   > Sie können nur Entitäten auswählen, die Beziehungen zu Ihrer Ausgangsentität haben. Weitere Informationen zur Definition von Beziehungen finden Sie unter [Beziehungen](relationships.md).

6. Optional können Sie Variablen konfigurieren. Wählen Sie im Abschnitt **Variablen** **Neue Variable**.

   Variablen sind Berechnungen, die für jeden Ihrer ausgewählten Datensätze durchgeführt werden. Zum Beispiel die Summierung von Point-of-Sale (POS) und Online-Verkäufen für jeden Datensatz Ihrer Kunden.

7. Geben Sie einen **Name** für die Variable an.

8. Wählen Sie im Bereich **Ausdruck** ein Feld aus, mit dem Ihre Berechnung beginnen soll.

9. Geben Sie einen Ausdruck in den Bereich **Ausdruck** ein und wählen Sie gleichzeitig weitere Felder aus, die in Ihre Berechnung einbezogen werden sollen.

   > [!NOTE]
   > Zurzeit werden nur arithmetische Ausdrücke unterstützt. Darüber hinaus wird die Berechnung von Variablen für Entitäten von verschiedenen [Entitätspfaden](relationships.md) nicht unterstützt.

10. **Fertig** auswählen

11. Im Abschnitt **Kennzahldefinition** definieren Sie, wie die von Ihnen gewählten Entitäten und berechneten Variablen in einer neuen Kennzahlentität oder einem neuen Attribut aggregiert werden.

12. Wählen Sie **Neue Dimension**. Sie können sich eine Dimension als eine Funktion *Gruppieren nach* vorstellen. Die Datenausgabe Ihrer Kennzahl-Entität oder Ihres Kennzahl-Attributs wird nach allen von Ihnen definierten Dimensionen gruppiert.

    > [!div class="mx-imgBorder"]
    > ![Aggregatzyklus auswählen](media/measures-businessreport-measure-definition2.png "Wählen Sie den Aggregatzyklus")

    Wählen Sie die folgenden Informationen aus oder geben Sie sie als Teil der Definition Ihrer Dimension ein:

    - **Entität**: Wenn Sie eine Entitätskennzahl definieren, sollte diese mindestens ein Attribut enthalten. Wenn Sie ein Kennzahl-Attribut definieren, wird es standardmäßig nur ein Attribut enthalten. Bei dieser Auswahl geht es um die Auswahl der Entität, die dieses Attribut enthält.
    - **Feld**: Wählen Sie das spezifische Attribut, das entweder in Ihre Kennzahlentität oder in das Attribut aufgenommen werden soll.
    - **Bucket**: Wählen Sie, ob Sie Daten auf Tages-, Monats- oder Jahresbasis aggregieren möchten. Diese Auswahl ist nur erforderlich, wenn Sie ein Datumstypattribut ausgewählt haben.
    - **Als**: Definiert den Namen Ihres neuen Feldes.
    - **Anzeigename**: Definiert den Anzeigenamen Ihres Feldes.

    > [!NOTE]
    > Ihre Geschäftskennzahl wird als Einzahl-Einheit gespeichert und erscheint auf der Seite **Home**, es sei denn, Sie fügen weitere Dimensionen zu Ihrer Kennzahl hinzu. Nachdem Sie weitere Dimensionen hinzugefügt haben, wird die Kennzahl *nicht* auf der Seite **Start** angezeigt.

13. Optional können Sie Aggregationsfunktionen hinzufügen. Jede Aggregation, die Sie erstellen, führt zu einem neuen Wert innerhalb Ihrer Kennzahlen-Entität oder Ihres Attributs. Unterstützte Aggregationsfunktionen sind: **Min**, **Max**, **Durchschnitt**, **Median**, **Summe**, **Zahl eindeutig**, **Erster** (nimmt den ersten Satz eines Dimensionswertes) und **Letzter** (nimmt den letzten zu einem Dimensionswert addierten Satz).

14. Wählen Sie **Speichern**, um Ihre Änderungen auf die Kennzahl anzuwenden.

## <a name="manage-your-measures"></a>Verwalten von Kennzahlen

Nachdem Sie mindestens eine Kennzahl erstellt haben, sehen Sie eine Liste der Kennzahlen auf der Seite **Kennzahlen**.

Dort finden Sie Informationen über den Kennzahlentyp, den Ersteller, Erstellungsdatum und -uhrzeit, Datum und Uhrzeit der letzten Bearbeitung, den Status (ob die Kennzahl aktiv, inaktiv oder fehlgeschlagen ist) sowie Datum und Uhrzeit der letzten Aktualisierung. Wenn Sie eine Kennzahl aus der Liste auswählen, wird eine Vorschau der Ausgabe angezeigt.

Um alle Ihre Kennzahlen gleichzeitig zu aktualisieren, wählen Sie **Alle aktualisieren** aus, ohne eine bestimmte Kennzahl auszuwählen.

> [!div class="mx-imgBorder"]
> ![Maßnahmen zur Verwaltung einzelner Kennzahlen](media/measure-actions.png "Maßnahmen zur Verwaltung einzelner Kennzahlen")

Alternativ können Sie eine Kennzahl aus der Liste auswählen und eine der folgenden Aktionen ausführen:

- Wählen Sie den Kennzahlnamen aus, um dessen Details anzuzeigen.
- **Bearbeiten** der Konfiguration der Kennzahl.
- **Umbenennen** der Kennzahl.
- **Löschen** der Kennzahl.
- Wählen Sie die Auslassungspunkte (...) und dann **Aktualisieren** aus, um den Aktualisierungsprozess für die Kennzahl zu starten.
- Wählen Sie die Auslassungspunkte (...) und dann **Herunterladen** aus, um eine CSV-Datei der Kennzahl zu erhalten.

> [!TIP]
> Es gibt [sechs Arten von Status](system.md#status-types) für Aufgaben/Prozesse. Darüber hinaus [hängen die meisten Prozesse von anderen nachfolgenden Prozessen ab](system.md#refresh-policies). Sie können den Status eines Prozesses auswählen, um Details zum Fortschritt des gesamten Auftrags anzuzeigen. Nach der Auswahl von **Siehe Details** für eine der Aufgaben des Auftrags finden Sie zusätzliche Informationen: Verarbeitungszeit, das letzte Verarbeitungsdatum sowie alle mit der Aufgabe verbundenen Fehler und Warnungen.

## <a name="next-step"></a>Nächster Schritt

Sie nutzen bestehende Kennzahlen, um Ihr erstes Kundensegment auf der Seite **Segmente** zu erstellen. Weitere Informationen finden Sie unter [Segmente](segments.md).
