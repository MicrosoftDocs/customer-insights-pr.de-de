---
title: Segmente erstellen und verwalten
description: Erstellen Sie Kundensegmente, um sie auf der Grundlage verschiedener Attribute zu gruppieren.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064936"
---
# <a name="create-and-manage-segments"></a>Segmente erstellen und verwalten

Sie können komplexe Filter mit Bezug zur einheitlichen Kundenentität und den verwandten Entitäten festlegen. Jedes Segment erstellt nach der Verarbeitung eine Reihe von Kundendatensätzen, die Sie exportieren und für die Sie Maßnahmen ergreifen können. Segmente werden auf der Seite **Segmente** verwaltet. 

Das folgende Beispiel veranschaulicht die Funktionalität der Segmentierung. Wir haben ein Segment für Kunden definiert, die in den letzten 90 Tagen Waren im Wert von mindestens 500 US-Dollar bestellt haben *und* die an einem Kundenserviceanruf beteiligt waren, der eskaliert wurde.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Screenshot der Segment Builder-Benutzeroberfläche mit zwei Gruppen, die ein Kundensegment angeben.":::

## <a name="create-a-new-segment"></a>Ein neues Segment erstellen

Es gibt mehrere Wege, ein neues Segment zu erstellen. In diesem Abschnitt wird beschrieben, wie Sie ein *leeres Segment* von Grund auf neu erstellen. Sie können auch ein *schnelles Segment* basierend auf vorhandenen Entitäten erstellen oder Maschinelles Lernen-Modelle verwenden, um *vorgeschlagene Segmente* zu erhalten. Weitere Informationen: [Segmentübersicht](segments.md).

Während Sie ein Segment erstellen, können Sie einen Entwurf speichern. Es wird als inaktives Segment gespeichert und kann nicht aktiviert werden, wenn eine gültige Konfiguration vorliegt.

1. Gehen Sie zur Seite **Segmente**.

1. Wählen Sie **Neu** > **Leeres Segment** aus.

1. In dem Bereich **Neues Segment** wählen Sie einen Segmenttyp aus.

   - **Dynamische Segmente** nach einem wiederkehrenden Zeitplan [aktualisieren](segments.md#refresh-segments).
   - **Statische Segmente** einmal ausführen, wenn Sie sie erstellen.

1. Stellen Sie einen **Name der Ausgabeentität** für das Segment bereit. Geben Sie optional einen Anzeigenamen und eine Beschreibung an, die die Identifizierung des Segments erleichtert.

1. Wählen Sie **Weiter**, um zu der Seite **Segment-Builder** zu gelangen, auf der Sie eine Gruppe definieren. Eine Gruppe ist eine Gruppe von Kunden.

1. Wählen Sie die Entität, die das Attribut enthält, nach dem Sie segmentieren möchten.

1. Wählen Sie das Attribut aus, nach dem segmentiert werden soll. Dieses Attribut kann einen von vier Werttypen haben: numerisch, Zeichenfolge, Datum oder boolesch.

1. Wählen Sie einen Operator und einen Wert für das ausgewählte Attribut.

   > [!div class="mx-imgBorder"]
   > ![Benutzerdefinierter Gruppenfilter](media/customer-group-numbers.png "Kundengruppen-Filter")

   |Anzahl |Definition  |
   |---------|---------|
   |1     |Entity          |
   |2     |Attribut          |
   |3    |Operator         |
   |4    |Wert         |

   1. Um weitere Bedingungen zu einer Gruppe hinzuzufügen, können Sie zwei logische Operatoren verwenden:

      - **AND** Operator: Beide Bedingungen müssen als Teil des Segmentierungsprozesses erfüllt sein. Diese Option ist am nützlichsten, wenn Sie Bedingungen für verschiedene Entitäten definieren.

      - **OR**-Operator: Jede der beiden Bedingungen muss als Teil des Segmentierungsprozesses erfüllt sein. Diese Option ist am nützlichsten, wenn Sie mehrere Bedingungen für dieselbe Entität definieren.

      > [!div class="mx-imgBorder"]
      > ![OR-Operator, wobei jede der beiden Bedingungen erfüllt sein muss](media/segmentation-either-condition.png "OR-Operator, wobei jede der beiden Bedingungen erfüllt sein muss")

      Es ist derzeit möglich, einen **OR** Operator unter einem **AND** Operator zu verschachteln, aber nicht umgekehrt.

   1. Jede Gruppe entspricht einer Gruppe von Kunden. Sie können Gruppen kombinieren, um die Kunden einzuschließen, die für Ihren Geschäftsfall erforderlich sind.    
   Wählen Sie **Gruppe hinzufügen**.

      > [!div class="mx-imgBorder"]
      > ![Kundengruppe Gruppe hinzufügen](media/customer-group-add-group.png "Kundengruppe Gruppe hinzufügen")

   1. Wählen Sie einen der eingestellten Operatoren aus: **Gesamtmenge**, **Überschneiden**, oder **Außer**.

   > [!div class="mx-imgBorder"]
   > ![Kundengruppe Vereinigung hinzufügen](media/customer-group-union.png "Kundengruppe Vereinigung hinzufügen")

   - **Vereinigen** vereinigt die beiden Gruppen.

   - **Überschneiden** überschneidet die beiden Gruppen. Nur Daten, die *beiden Gruppen gemeinsam* sind, werden in der vereinigten Gruppe beibehalten.

   - **Außer** kombiniert die beiden Gruppen. Nur Daten in Gruppe A, die *nicht gemeinsam* mit Daten in Gruppe B sind, bleiben erhalten.

1. Wenn die Entität über [Beziehungen](relationships.md) mit der einheitlichen Kundenentität verbunden ist, müssen Sie den Beziehungspfad definieren, um ein gültiges Segment zu erstellen. Fügen Sie die Entitäten aus dem Beziehungspfad hinzu, bis Sie die Entität **Kunde: Customer Insights** aus der Dropdownliste auswählen können. Dann wählen Sie **Alle Datensätze** für jeden Schritt aus.

   > [!div class="mx-imgBorder"]
   > ![Beziehungspfad während der Segmenterstellung](media/segments-multiple-relationships.png "Beziehungspfad während der Segmenterstellung")

1. Standardmäßig generieren Segmente eine Ausgabeentität, die alle Attribute von Kundenprofilen enthält, die den definierten Filtern entsprechen. Wenn ein Segment auf anderen Entitäten als der Entität *Kunde* basiert, können Sie der Ausgabeentität weitere Attribute dieser Entitäten hinzufügen. Wählen Sie, **Projektattribute**, um die Attribute auszuwählen, die an die Ausgabeentität angehängt werden.  
  
   Beispiel: Ein Segment basiert auf einer Entität, die Kundenaktivitätsdaten enthält, die sich auf die Entität *Kunde* beziehen. Das Segment sucht nach allen Kunden, die in den letzten 60 Tagen den Helpdesk angerufen haben. Sie können die Anrufdauer und die Anzahl der Anrufe an alle übereinstimmenden Kundendatensätze in der Ausgabeentität anhängen. Diese Informationen können hilfreich sein, um eine E-Mail mit hilfreichen Links zu Online-Hilfeartikeln und häufig gestellten Fragen an Kunden zu senden, die häufig angerufen haben.

   > [!NOTE]
   > - Projizierte Attribute funktionieren nur für Entitäten, die eine Eins-zu-Viele-Beziehung zur Kundenentität haben. Beispielsweise kann ein Kunde mehrere Abonnements haben.
   > - Sie können nur Attribute einer Entität projizieren, die in jeder Gruppe von Segmentabfragen verwendet wird, die Sie erstellen.
   > - Projizierte Attribute werden bei Verwendung von festgelegten Operatoren berücksichtigt.

1. Wählen Sie **Speichern**, um Ihr Segment zu speichern. Ihr Segment wird gespeichert und verarbeitet, wenn alle Anforderungen validiert sind. Andernfalls wird es als Entwurf gespeichert.

1. Wählen Sie **Zurück zu Segmenten**, um zur Seite **Segmente** zurückzukehren.



## <a name="quick-segments"></a>Schnelle Segmente

Mit schnellen Segmenten können Sie schnell einfache Segmente mit einem einzigen Operator erstellen, um schnellere Einblicke zu erhalten.

1. Wählen Sie auf der Seite **Segment** aus und wählen Sie **Neu** > **Erstellen aus**.

   - Wählen Sie die Option **Profile**, um ein Segment zu erstellen, das auf der *einheitlichen Kundenentität* basiert.
   - Wählen Sie die Option **Maßnahmen** zum Erstellen eines Segments um zuvor erstellte Kennzahlen.
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

## <a name="next-steps"></a>Nächste Schritte

[Exportieren Sie ein Segment](export-destinations.md) und erkunden Sie die [Kundenkarte](customer-card-add-in.md) und [Connectors](export-power-bi.md), um Einblicke auf Kundenebene zu erhalten.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
