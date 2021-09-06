---
title: Segmente erstellen und verwalten
description: Erstellen Sie Kundensegmente, um sie auf der Grundlage verschiedener Attribute zu gruppieren.
ms.date: 07/18/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e759872643cc7387cf732d73c7a320ae8901e5a9
ms.sourcegitcommit: 42692a815695b9fdc93b9358eae09f2c3e97293c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2021
ms.locfileid: "7377787"
---
# <a name="create-and-manage-segments"></a>Segmente erstellen und verwalten

> [!IMPORTANT]
> Im September 2021 werden mehrere Änderungen an der Segmenterstellung eingeführt: 
> - Der Segmentgenerator wird mit neu gestalteten Elementen und einem verbesserten Benutzerflow etwas anders aussehen.
> - Im Segmentgenerator sind neue Datetime-Operatoren und eine verbesserte Datumsauswahl aktiviert.
> - Sie können Bedingungen und Regeln zu Segmenten hinzufügen oder daraus entfernen. 
> - Geschachtelte Regeln, die mit einer ODER-Bedingung beginnen, sind verfügbar. Sie benötigen keine UND-Bedingung mehr auf der äußersten Ebene.
> - Ein Seitenbereich zum Auswählen von Attributen ist ständig verfügbar.
> - Eine Option zum Auswählen von Entitätsbeziehungspfaden.
> Um den neuen Segmentgenerator auszuprobieren, senden Sie eine E-Mail mit dem Betreff „Request to enable the new segment builder“ an cihelp [at] microsoft.com. Geben Sie den Namen Ihrer Organisation und die ID Ihrer Sandbox-Umgebung an.
> :::image type="content" source="media/segment-builder-overview.png" alt-text="Elemente des Segment-Builders." lightbox="media/segment-builder-overview.png":::
>
> 1 - Organisieren Sie Ihr Segment mit Regeln und Unterregeln. Jede Regel oder Unterregel besteht aus Bedingungen. Kombinieren Sie die Bedingungen mit logischen Operatoren
>
> 2 - Wählen Sie den [Beziehungspfad](relationships.md) zwischen Entitäten, die für eine Regel gelten. Der Beziehungspfad bestimmt, welche Attribute in einer Bedingung verwendet werden können.
>
> 3 - Regeln und untergeordnete Regeln verwalten. Ändern Sie die Position einer Regel oder löschen Sie sie.
>
> 4 - Fügen Sie Bedingungen hinzu und erstellen Sie mithilfe von Unterregeln die richtige Verschachtelungsebene.
>
> 5 - Wenden Sie Set-Operationen auf verbundene Regeln an.
>
> 6 - Verwenden Sie den Attributbereich, um verfügbare Entitätsattribute hinzuzufügen oder Bedingungen basierend auf Attributen zu erstellen. Der Bereich zeigt die Liste der Entitäten und Attribute basierend auf dem ausgewählten Beziehungspfad, die für die ausgewählte Regel verfügbar sind.
>
> 7 - Fügen Sie Bedingungen basierend auf Attributen zu bestehenden Regeln und untergeordneten Regeln hinzu oder fügen Sie sie zu einer neuen Regel hinzu.
>
> 8 - Machen Sie Änderungen beim Erstellen des Segments rückgängig und wiederholen Sie sie.

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
   > ![Benutzerdefinierter Gruppenfilter.](media/customer-group-numbers.png "Kundengruppen-Filter")

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
      > ![ODER-Operator, wobei jede der beiden Bedingungen erfüllt sein muss.](media/segmentation-either-condition.png "OR-Operator, wobei jede der beiden Bedingungen erfüllt sein muss")

      Es ist derzeit möglich, einen **OR** Operator unter einem **AND** Operator zu verschachteln, aber nicht umgekehrt.

   1. Jede Gruppe entspricht einer Gruppe von Kunden. Sie können Gruppen kombinieren, um die Kunden einzuschließen, die für Ihren Geschäftsfall erforderlich sind.    
   Wählen Sie **Gruppe hinzufügen**.

      > [!div class="mx-imgBorder"]
      > ![Kundengruppe „Gruppe hinzufügen“.](media/customer-group-add-group.png "Kundengruppe Gruppe hinzufügen")

   1. Wählen Sie einen der eingestellten Operatoren aus: **Gesamtmenge**, **Überschneiden**, oder **Außer**.

   > [!div class="mx-imgBorder"]
   > ![Kundengruppe „Vereinigung hinzufügen“.](media/customer-group-union.png "Kundengruppe Vereinigung hinzufügen")

   - **Vereinigen** vereinigt die beiden Gruppen.

   - **Überschneiden** überschneidet die beiden Gruppen. Nur Daten, die *beiden Gruppen gemeinsam* sind, werden in der vereinigten Gruppe beibehalten.

   - **Außer** kombiniert die beiden Gruppen. Nur Daten in Gruppe A, die *nicht gemeinsam* mit Daten in Gruppe B sind, bleiben erhalten.

1. Wenn die Entität über [Beziehungen](relationships.md) mit der einheitlichen Kundenentität verbunden ist, müssen Sie den Beziehungspfad definieren, um ein gültiges Segment zu erstellen. Fügen Sie die Entitäten aus dem Beziehungspfad hinzu, bis Sie die Entität **Kunde: Customer Insights** aus der Dropdownliste auswählen können. Dann wählen Sie **Alle Datensätze** für jeden Schritt aus.

   > [!div class="mx-imgBorder"]
   > ![Beziehungspfad während der Segmenterstellung.](media/segments-multiple-relationships.png "Beziehungspfad während der Segmenterstellung")

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
    > ![Name und Schätzung für ein schnelles Segment.](media/quick-segment-name.png "Name und Schätzung für ein schnelles Segment")

5. Geben Sie einen **Name** für Ihr Segment an. Geben Sie optional einen **Anzeigename** ein.

6. Wählen Sie **Speichern**, um Ihr Segment zu erstellen.

7. Nachdem das Segment fertig bearbeitet wurde, können Sie es wie jedes andere von Ihnen erstellte Segment anzeigen.

## <a name="next-steps"></a>Nächste Schritte,

[Exportieren eines Segments](export-destinations.md) und erkunden der [Kundenkartenintegration](customer-card-add-in.md), um Segmente in anderen Anwendungen zu verwenden.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
