---
title: Stimmung für Kundenfeedback analysieren (Vorschauversion)
description: Erfahren Sie, wie Sie ein Stimmungsanalysemodell für Kundenfeedback in Dynamics 365 Customer Insights verwenden.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610465"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Stimmung im Kundenfeedback analysieren (Vorschauversion)

Mit der Stimmungsanalyse können Sie die Kundenstimmung zusammenfassen und Geschäftsaspekte als Verbesserungsmöglichkeiten identifizieren. Diese Customer Insights-Funktion hilft Ihnen zu verstehen, was gut funktioniert und worauf Sie achten müssen. Dies kann Ihnen helfen, Geschäftsmaßnahmen voranzutreiben, die Erfahrungen ermöglichen, die zu hoher Kundenzufriedenheit und -loyalität führen.

## <a name="overview"></a>Überblick

Die Stimmungsanalysefunktion generiert zwei abgeleitete Erkenntnisse pro Kunden-ID. Ein Stimmungspunktzahl (von -5 bis 5) und eine Liste anwendbarer Geschäftsaspekte (Geschäftsbereiche), die Ihnen gemeinsam helfen, das Kundenfeedback besser zu verstehen.

Diese Analyse hilft Ihnen bei Folgendem:
- Verschaffen Sie sich einen Überblick über die Kundenstimmung bezüglich einer Marke oder Organisation
- Identifizieren Sie Kunden mit negativer Stimmung, um Ihre Kampagnen und Engagements zu fokussieren und für eine höhere Rendite zu optimieren  
- Identifizieren Sie geschäftliche Aspekte mit Problemen, auf die Kunden hinweisen  
- Segmentieren Sie Kunden basierend auf ihrer Stimmung, um personalisierte Kampagnen mit gezielten Vertriebs-, Marketing- und Supportmaßnahmen durchzuführen
- Optimieren Sie den Geschäftsbetrieb, indem Sie von Kunden erwähnte Problembereiche oder Chancen ansprechen
- Erkennen Sie Geschäftsaspekte, die gut laufen, und belohnen Sie zufriedene Kunden durch Treue- und Werbeprogramme

Das Modell stellt eine Liste mit Wörtern, bereit die die Entscheidung des Models beeinflusst haben, Feedback-Kommentaren eine bestimmte Stimmungspunktzahl oder einen bestimmten Geschäftsaspekt zuzuweisen.  

Wir verwenden zwei **Natural Language Processing (NLP)-Modelle**: Der erste weist jedem Feedback-Kommentar einen Stimmungs-Score zu. Das zweite Modell verknüpft jedes Feedback mit allen anwendbaren Geschäftsaspekten. Die Modelle werden mit öffentlichen Daten aus Quellen aus den Bereichen soziale Medien, Einzelhandel, Gastronomie, Konsumgüter und Automobilindustrie trainiert.
  
Zu den vordefinierten Geschäftsaspekten für das Modell, die mit Feedbackdaten verknüpft werden sollen, gehören:
- Kontoverwaltung
- Checkout und Bezahlung
- Kundenbetreuung
- Abholung in der Filiale
- Verpackungsversand und Abholung
- Vorbestellung
- Preis
- Datenschutz und Sicherheit
- Werbeaktionen und Prämien
- Beleg und Garantie
- Umtausch und Stornierung
- Liefergenauigkeit
- Website/App-Qualität

> [!NOTE]
> Derzeit unterstützen wir nur Stimmungsanalysen für englisches Kundenfeedback. Weitere Sprachen werden in Zukunft unterstützt. Wenn Feedback in anderen Sprachen hochgeladen wird, gibt das Modell dennoch Ergebnisse zurück. Diese Ergebnisse sind jedoch nicht genau.

## <a name="prerequisites"></a>Anforderungen

- Mindestens [Berechtigungen als Mitwirkender](permissions.md)
- [Einheitliche](data-unification.md) Text-Feedback-Daten. Wir empfehlen Ihnen unbedingt, das Sie [Ihre Feedback-Datenentitäten als Aktivitätsentitäten vom semantischen Typ konvertieren](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (Feedback-Typ).
- Unified Customer ID (UCID) aus der Datenvereinheitlichung für die Zuordnung von Text-Feedback-Datensätzen zu einem einzelnen Kunden.
- Feedback-ID
- Feedback-Zeitstempel
- Feedbacktext

Customer Insights kann bis zu 10 Millionen Feedback-Datensätze für einen einzelnen Modelllauf verarbeiten. Das Modell kann Feedback-Kommentare mit bis zu 128 Wörtern analysieren. Wenn ein Feedback-Kommentar länger ist, berücksichtigt die Analyse nur die ersten 128 Wörter.

> [!NOTE]
> Nur eine Feedbackentität kann konfiguriert werden. Wenn es mehrere Feedbackentitäten gibt, kombinieren Sie sie vor der Datenaufnahme in Power Query.

## <a name="configure-a-sentiment-analysis"></a>Konfigurieren einer Stimmungsanalyse

1. Gehen Sie zu **Intelligenz** > **Vorhersagen**.

1. Wählen Sie in der Registerkarte **Erstellen** **Modell verwenden** auf der Kachel **Kundenstimmungsanalyse (Vorschauversion)** aus.

1. Wählen Sie **Erste Schritte** aus.

1. Geben Sie den **Namen** der Analyse und den **Entitätsname der Ausgabe des Geschäftsaspekts** und den **Entitätsname der Ausgabe des Stimmungspunktzahl** an.

1. Wählen Sie **Weiter** aus.

1. Wählen Sie **Daten hinzufügen** für **Kundenfeedback** aus.

1. Wählen Sie den semantischen Aktivitätstyp **Feedback** aus, der die Feedbackdaten enthält. Wenn die Aktivität nicht eingerichtet wurde, wählen Sie sie **hier** aus und erstellen Sie sie.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Konfigurationsschritt zur Auswahl von Feedback-Aktivitäten für die Stimmungsanalyse.":::

1. Wählen Sie die Aktivitäten aus, die Sie für diese Stimmungsanalyse verwenden möchten, und wählen Sie dann **Weiter** aus.

1. Ordnen Sie die Attribute in Ihren Daten den Modellattributen zu. 

1. Wählen Sie **Save** (Speichern).

1. Wählen Sie **Weiter** aus. Der Schritt **Überprüfen und ausführen** zeigt eine Zusammenfassung der Konfiguration und bietet die Möglichkeit, Änderungen vorzunehmen, bevor Sie die Analyse erstellen.

1. Wählen Sie **Bearbeiten** bei einem der Schritte, um sie zu überprüfen und Änderungen vorzunehmen.

1. Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **Speichern und ausführen** aus, um das Modell ausführen zu lassen. Wählen Sie **Fertig** aus. Die Registerkarte **Meine Vorhersagen** wird angezeigt, während Vorhersage erstellt wird. Der Prozess kann je nach der Menge der in der Vorhersage verwendeten Daten mehrere Stunden dauern.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Analyseergebnisse anzeigen

1. Gehen Sie zu **Intelligenz** > **Vorhersagen**.

1. Wählen Sie in der Registerkarte **Meine Vorhersagen** die Vorhersage aus, die Sie ansehen möchten.

Es gibt zwei Registerkarten mit Ergebnissen.

### <a name="sumary-tab"></a>Registerkarte „Zusammenfassung“

Auf der Ergebnisseite gibt es vier primäre Datenabschnitte.

- **Durchschnittliche Stimmungspunktzahl** : Stimmungspunktzahlen helfen Ihnen, die Gesamtstimmung aller Kunden zu verstehen.
  - **Negativ** (-5 > 2)
  - **Neutral** (-1 > 1)
  - **Positiv** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Visuelle Darstellung der allgemeinen Kundenstimmung.":::

- **Verteilung der Kunden nach Stimmungs-Score** : Kunden werden basierend auf ihren Stimmungs-Scores in negative, neutrale und positive Gruppen eingeteilt. Bewegen Sie den Mauszeiger über die Balken im Histogramm, um die Anzahl der Kunden und den durchschnittlichen Stimmungswert in jeder Gruppe anzuzeigen. Diese Daten können Ihnen helfen [Kundensegmente zu erstellen](prediction-based-segment.md), die auf ihren Stimmungs-Scores basieren.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Balkendiagramm, das die Kundenstimmung in den drei Stimmungsgruppen zeigt.":::

- **Durchschnittlicher Stimmungs-Score im Laufe der Zeit** : Die Kundenstimmung kann sich im Laufe der Zeit ändern. Wir stellen Trends in der Stimmung Ihrer Kunden für den Zeitraum Ihrer Daten bereit. Diese Ansicht hilft Ihnen dabei, die Auswirkungen von saisonalen Werbeaktionen, Produkteinführungen oder anderen zeitgebundenen Eingriffen auf die Kundenstimmung abzuschätzen. Sehen Sie sich die Grafik an, indem Sie das gewünschte Jahr aus dem Dropdown-Menü auswählen.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Verlaufsdiagramm mit als Linie dargestelltem Stimmungs-Score im Zeitverlauf.":::

- **Stimmung über Geschäftsaspekte hinweg**: Die durchschnittliche Stimmung in Bezug auf Geschäftsaspekte hilft Ihnen, einzuschätzen, welche Aspekte Ihres Unternehmens Kunden bereits zufriedenstellen und welche mehr Aufmerksamkeit benötigen. Feedback-Datensätze, die keinem der unterstützten Geschäftsaspekte entsprechen, werden unter **Sonstige** kategorisiert. Sortieren Sie die Daten, indem Sie eine beliebige Spalte auswählen.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Liste der geschäftlichen Aspekte mit dem zugehörigen Stimmungs-Score und der Anzahl der Kunden, die den Aapekt erwähnen.":::

  Wählen Sie den Namen eines Geschäftsaspekts aus, um zu sehen, wie ein Geschäftsaspekt vom Modell identifiziert wird:

  - **Einflussreiche Wörter** : Wichtigste Wörter, die die Identifizierung eines Geschäftsaspekts im Kundenfeedback durch das KI-Modell beeinflusst haben.
    **Anstößige Wörter anzeigen**: Ermöglicht es Ihnen, anstößige Wörter aus ursprünglichen Kundenfeedbackdaten in die Liste aufzunehmen. Dies ist standardmäßig deaktiviert.  Die anstößige Wortmaskierung wird von einem KI-Modell unterstützt und erkennt möglicherweise nicht alle anstößigen Wörter. Wenn Sie ein anstößiges Wort entdecken, das nicht wie erwartet herausgefiltert wurde, teilen Sie uns dies mit.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Liste einflussreicher Wörter mit dem Schalter zum Ein- oder Ausblenden anstößiger Wörter.":::

  - **Feedbackbeispiele** : Tatsächliche Feedbackdatensätze in Ihren Daten. Wörter sind entsprechend ihres Einflusses auf die Identifizierung eines Geschäftsaspekts farbcodiert.

### <a name="influential-words-analysis-tab"></a>Registerkarte „Analyse einflussreicher Wörter“

Es gibt drei Abschnitte mit zusätzlichen Informationen, die erklären, wie das Stimmungsmodell funktioniert.
  
- **Wichtigste Wörter, die zu einer positiven Stimmung beitragen**: Wichtigste Wörter, die die Identifizierung positiver Stimmungen im Kundenfeedback durch das KI-Modell beeinflusst haben.  

- **Wichtigste Wörter, die zu einer negativen Stimmung beitragen**: Wichtigste Wörter, die die Identifizierung negativer Stimmungen im Kundenfeedback durch das KI-Modell beeinflusst haben.

- **Feedbackbeispiele** : Tatsächliche Feedbackdatensätze, einen mit negativer Stimmung und einen mit positiver Stimmung. Wörter in den Feedbackdatensätzen werden entsprechend ihrem Beitrag zum zugewiesenen Stimmungs-Score hervorgehoben. Wörter, die zu einem positiven Stimmungs-Score beitragen, sind grün hervorgehoben. Wörter, die zu einem negativen Score beitragen, sind rot hervorgehoben.
   Wählen Sie **Weitere anzeigen** aus, um mehr Feedbackbeispiele zu laden.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Beispiele für Stimmungsanalysen zu Kundenfeedback.":::

**Anstößige Wörter anzeigen**: Ermöglicht es Ihnen, anstößige Wörter aus ursprünglichen Kundenfeedbackdaten in die Liste aufzunehmen. Dies ist standardmäßig deaktiviert.  Die anstößige Wortmaskierung wird von einem KI-Modell unterstützt und erkennt möglicherweise nicht alle anstößigen Wörter. Wenn Sie ein anstößiges Wort entdecken, das nicht wie erwartet herausgefiltert wurde, teilen Sie uns dies mit.

## <a name="act-on-analysis-results"></a>Aktionen zu Analyseergebnissen

Um aus den Ergebnissen der Stimmungsanalyse neue Segmente zu erstellen, wählen Sie oben auf der Modellergebnisseite **Segmente erstellen** aus.

## <a name="potential-bias"></a>Mögliche Voreingenommenheit

Wie bei jeder Funktion, die prädiktive künstliche Intelligenz verwendet, könnten eventuell Verzerrungen in den Daten vorliegen, die Sie zur Vorhersage der Kundenstimmung verwenden. Wenn Sie beispielsweise Feedback nur digital sammeln, könnten Sie Feedback von Kunden verpassen, die hauptsächlich persönlich mit Ihnen zu tun haben, was sich auf das Ergebnis der Funktion auswirken könnte.

Da diese Funktion automatisierte Mittel verwendet, um Daten auszuwerten und auf der Grundlage dieser Daten Vorhersagen zu treffen, kann sie daher als Methode zur Profilerstellung verwendet werden, wie dieser Begriff in der allgemeinen Datenschutzverordnung („DSGVO“) definiert ist. Ihre Verwendung dieser Funktion zur Verarbeitung von Daten unterliegt möglicherweise der DSGVO oder anderen Gesetzen oder Vorschriften. Sie sind dafür verantwortlich, sicherzustellen, dass Ihre Verwendung von Dynamics 365 Customer Insights, einschließlich Stimmungsanalyse, allen geltenden Gesetzen und Vorschriften, einschließlich Gesetzen in Bezug auf Datenschutz, personenbezogene Daten, biometrische Daten, Datenschutz und Vertraulichkeit der Kommunikation, entspricht.

[!INCLUDE [footer-include](includes/footer-banner.md)]

