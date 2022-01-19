---
title: Semantische Analyse für Kundenfeedback
description: Erfahren Sie, wie Sie ein Stimmungsanalysemodell für Kundenfeedback in Dynamics 365 Customer Insights verwenden.
ms.date: 12/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 05e530a1bc96c5fd9c7a3bc0197563d8fe330387
ms.sourcegitcommit: cb71e39de9b891c24bd5cd9c014eb3eeb537ac24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/10/2022
ms.locfileid: "7951080"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Stimmung im Kundenfeedback analysieren (Vorschau)

Kunden erwarten heutzutage qualitativ hochwertige Produkte, Dienstleistungen und Erlebnisse. Vor allem Kunden, die ihr Feedback teilen. Für Organisationen ist es eine große Herausforderung, ein wachsendes Datenvolumen zu analysieren, ohne die Genauigkeit zu verringern und die Arbeitskosten zu erhöhen. Dynamics 365 Customer Insights bietet ein Stimmungsanalysemodell für Kundenfeedback, mit dem Unternehmen ihre Daten genauer und zu geringeren Kosten analysieren können.

Mit der Stimmungsanalyse können Sie die Kundenstimmung zusammenfassen und Geschäftsaspekte als Verbesserungsmöglichkeiten identifizieren. Diese Customer Insights-Funktion hilft Ihnen zu verstehen, was gut funktioniert und worauf Sie achten müssen. Konzentrieren Sie sich auf die relevantesten und wirkungsvollsten Geschäftsbereiche, um das Erlebnis für Ihre Kunden zu verbessern. Letztendlich kann Ihnen das helfen, Geschäftsmaßnahmen voranzutreiben, die Erfahrungen ermöglichen, die zu hoher Kundenzufriedenheit und -loyalität führen.

## <a name="overview"></a>Überblick

Die Stimmungsanalysefunktion generiert zwei abgeleitete Erkenntnisse pro Kunden-ID. Ein Stimmungs-Score (von -5 bis 5) und eine Liste anwendbarer Geschäftsaspekte (Geschäftsbereiche) zusammen, helfen Ihnen das Kundenfeedback besser zu verstehen. 

Diese Informationen können Ihnen dabei helfen, die folgenden Ergebnisse zu erzielen: 
- Verschaffen Sie sich einen Überblick über die Kundenstimmung bezüglich einer Marke oder Organisation
- Identifizieren Sie Kunden mit negativer Stimmung, um Ihre Kampagnen und Engagements zu fokussieren und für eine höhere Rendite zu optimieren  
- Identifizieren Sie geschäftliche Aspekte mit Problemen, auf die Kunden hinweisen  
- Segmentieren Sie Kunden basierend auf ihrer Stimmung, um personalisierte Kampagnen mit gezielten Vertriebs-, Marketing- und Supportmaßnahmen durchzuführen
- Optimieren Sie den Geschäftsbetrieb, indem Sie von Kunden erwähnte Problembereiche oder Chancen ansprechen
- Erkennen Sie Geschäftsaspekte, die gut laufen, und belohnen Sie zufriedene Kunden durch Treue- und Werbeprogramme

Damit Sie den Ergebnissen der Modelle vertrauen können, informieren wir Sie transparent darüber, wie die Modelle Entscheidungen treffen. Sie erhalten eine Liste mit Wörtern, die die Entscheidung des Models beeinflusst haben, Feedback-Kommentaren eine bestimmte Stimmung oder einen bestimmten Geschäftsaspekt zuzuweisen.  

Wir verwenden zwei **Natural Language Processing (NLP)-Modelle**: Der erste weist jedem Feedback-Kommentar einen Stimmungs-Score zu. Das zweite Modell verknüpft jedes Feedback mit allen anwendbaren Geschäftsaspekten. Die Modelle werden mit öffentlichen Daten aus Quellen aus den Bereichen soziale Medien, Einzelhandel, Gastronomie, Konsumgüter und Automobilindustrie trainiert.    
  
- Zu den vordefinierten Geschäftsaspekten für das Modell, die mit Feedbackdaten verknüpft werden sollen, gehören:
-   Kontoverwaltung
-   Checkout und Bezahlung
-   Kundenbetreuung
-   Abholung in der Filiale
-   Verpackungsversand und Abholung
-   Vorbestellung
-   Preis
-   Datenschutz und Sicherheit
-   Werbeaktionen und Prämien
-   Beleg und Garantie
-   Umtausch und Stornierung
-   Liefergenauigkeit
-   Website/App-Qualität

> [!NOTE]
> Derzeit unterstützen wir nur Stimmungsanalysen für englisches Kundenfeedback. Weitere Sprachen werden in Zukunft unterstützt. Wenn Feedback in anderen Sprachen hochgeladen wird, gibt das Modell dennoch Ergebnisse zurück. Diese Ergebnisse sind jedoch nicht genau. 

## <a name="prerequisites"></a>Anforderungen

Die Stimmungsanalyse basiert auf Text-Feedback-Daten, die den [Datenvereinheitlichungsprozess](data-unification.md) durchlaufen haben. Wir empfehlen Ihnen unbedingt, das Sie im Voraus [Ihre Feedback-Datenentitäten als Aktivitätsentitäten vom semantischen Typ konvertieren](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (Feedback-Typ). 

Um ein Stimmungsanalysemodell zu konfigurieren, benötigen Sie mindestens [Mitwirkendenberechtigungen](permissions.md).

Customer Insights kann bis zu 10 Millionen Feedback-Datensätze für einen einzelnen Modelllauf verarbeiten. Das Modell kann Feedback-Kommentare mit bis zu 128 Wörtern analysieren. Wenn ein Feedback-Kommentar länger ist, berücksichtigt die Analyse nur die ersten 128 Wörter.

### <a name="data-requirements"></a>Datenanforderungen
  
Die folgenden Datenattribute sind erforderlich:
- Unified Customer ID (UCID) für die Zuordnung von Text-Feedback-Datensätzen zu einem einzelnen Kunden. Diese ID ergibt sich aus dem [Datenvereinheitlichungsprozess](data-unification.md).
- Feedback-ID
- Feedback-Zeitstempel
- Feedbacktext   

> [!TIP]
> Die Stimmungsanalyse benötigt das Text-Feedback Ihrer Kunden. Derzeit kann nur eine Feedbackentität konfiguriert werden. Wenn es mehrere Feedbackentitäten gibt, können Sie sie in Power Query vereinen, bevor die Datenaufnahme beginnt.

## <a name="configure-a-sentiment-analysis"></a>Konfigurieren einer Stimmungsanalyse 

1. Gehen Sie in Customer Insights zu **Intelligenz** > **Vorhersagen**.

1. Wählen Sie auf der Kachel **Kundenstimmungsanalyse** die Option **Modell verwenden** aus.

1. Wählen Sie im Bereich **Kundenstimmungsanalyse (Vorschau)** **Erste Schritte** aus.

1. Geben Sie im Schritt **Modellname** einen **Namen** für Ihre Analyse ein. 

1. Stellen Sie den **Entitätsname der Ausgabe des Geschäftsaspekts** und den **Entitätsname der Ausgabe des Stimmungs-Score** bereit und wählen Sie **Weiter** aus.

1. Wählen Sie im Schritt **Benötigte Daten** **Daten hinzufügen** aus.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Datenfluss im Stimmungsanalysemodell hinzufügen.":::

1. Wählen Sie im Bereich **Daten hinzufügen** den semantischen Typ **Feedback** von der Liste aus.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Konfigurationsschritt zur Auswahl von Feedback-Aktivitäten für die Stimmungsanalyse.":::

1. Wählen Sie die Aktivitäten aus, die Sie für diese Stimmungsanalyse verwenden möchten, und wählen Sie dann **Weiter** aus.
 
1. Ordnen Sie die Attribute in Ihren Daten den Modellattributen zu. Wählen Sie **Speichern** aus, um Ihre Auswahl anzuwenden. 

1. Sie sehen den Status der Datenzuordnung. Wählen Sie **Weiter** aus, um den Vorgang fortzusetzen. 

1. Im Schritt **Ihre Modelldetails überprüfen** validieren Sie die Konfiguration Ihrer Stimmungsanalyse. Sie können zu jedem Teil der Vorhersagekonfiguration zurückkehren. Wählen Sie **Speichern und Ausführen** aus, um die Analyse zu starten. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Überprüfungsschritt für das Stimmungsmodell mit allen konfigurierten Elementen.":::

1. Wählen Sie **Fertig** aus, um das Konfigurationserlebnis zu verlassen. Der Vorgang kann je nach verwendeter Datenmenge mehrere Stunden dauern. 

## <a name="review-analysis-status"></a>Analysestatus bewerten

1.  Gehen Sie zu **Intelligenz** > **Vorhersagen** und wählen Sie die Registerkarte **Meine Vorhersagen**.
2.  Wählen Sie die Vorhersage aus, die Sie überprüfen möchten.
- **Vorhersagename**: Name der Vorhersage, der beim Erstellen der Vorhersage angegeben wird.
- **Vorhersagetyp**: Typ des für die Vorhersage verwendeten Modells.
- **Ausgabeentität**: Name der Entität zum Speichern der Ausgabe der Vorhersage. Gehen Sie zu **Daten** > **Entitäten**, um die Entität mit diesem Namen zu finden.
- **Vorhersagefeld:**: Dieses Feld wird nur für einige Arten von Vorhersagen ausgefüllt und wird nicht für die Vorhersage des langfristigen Kundenwerts verwendet.
- **Status:** Status des Vorhersagelaufs.
  - **In Warteschlange:** Die Vorhersage wartet auf den Abschluss anderer Prozesse.
  - **Wird aktualisiert:** Die Vorhersage läuft gerade, um Ergebnisse zu erstellen, die in die Ausgabe-Entität fließen.
  - **Fehlgeschlagen:** Der Vorhersagelauf ist fehlgeschlagen. Betrachten Sie die Protokolle für weitere Details.
  - **Erfolgreich:** Die Vorhersage ist erfolgreich. Wählen Sie Anzeigen unter den vertikalen Ellipsen, um die Ergebnisse der Vorhersage anzuzeigen.
- **Bearbeitet:** Das Datum, an dem die Konfiguration für die Vorhersage geändert wurde.
- **Letzte Aktualisierung**: Das Datum, an dem die Ausgabeentität mit den Ergebnissen der Vorhersage aktualisiert wurde.

## <a name="manage-sentiment-analysis"></a>Stimmungsanalyse verwalten

Sie können Vorhersagen optimieren, Fehler beheben, aktualisieren oder löschen. Sehen Sie sich einen Eingabedaten-Nutzungsberichts an, um herauszufinden, wie Sie Vorhersagen schneller und zuverlässiger machen. Weitere Informationen finden Sie unter [Verwalten von Vorhersagen](manage-predictions.md).

## <a name="review-analysis-results"></a>Analyseergebnisse bewerten
 
1. Gehen Sie zu **Intelligenz** > **Vorhersagen** und wählen Sie die Registerkarte **Meine Vorhersagen**. 
1. Wählen Sie den Namen der Vorhersage aus, für die Sie die Ergebnisse bewerten möchten. Wählen Sie in diesem Fall die Stimmungsanalyse aus, die Sie bewerten möchten. 

### <a name="summary-tab"></a>Registerkarte „Zusammenfassung“

Auf der Ergebnisseite gibt es vier primäre Datenabschnitte. 

- **Durchschnittlicher Stimmungs-Score** : Hilft Ihnen, die Gesamtstimmung aller Kunden zu verstehen. Stimmungs-Scores werden in drei Kategorien eingeteilt: 
  1.    Negativ (-5 > 2)
  2.    Neutral (-1 > 1)
  3.    Positiv (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Visuelle Darstellung der allgemeinen Kundenstimmung.":::

- **Verteilung der Kunden nach Stimmungs-Score** : Kunden werden basierend auf ihren Stimmungs-Scores in negative, neutrale und positive Gruppen eingeteilt. Bewegen Sie den Mauszeiger über die Balken im Histogramm, um die Anzahl der Kunden und den durchschnittlichen Stimmungswert in jeder Gruppe anzuzeigen. Diese Daten können Ihnen helfen [Kundensegmente zu erstellen](segments.md), die auf ihren Stimmungs-Scores basieren.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Balkendiagramm, das die Kundenstimmung in den drei Stimmungsgruppen zeigt.":::

- **Durchschnittlicher Stimmungs-Score im Laufe der Zeit** : Die Kundenstimmung kann sich im Laufe der Zeit ändern. Wir stellen Trends in der Stimmung Ihrer Kunden für den Zeitraum Ihrer Daten bereit. Diese Ansicht kann Ihnen dabei helfen, die Auswirkungen von saisonalen Werbeaktionen, Produkteinführungen oder anderen zeitgebundenen Eingriffen auf die Kundenstimmung abzuschätzen. Sehen Sie sich die Grafik an, indem Sie das gewünschte Jahr aus dem Dropdown-Menü auswählen. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Verlaufsdiagramm mit als Linie dargestelltem Stimmungs-Score im Zeitverlauf.":::
 
- **Stimmung über Geschäftsaspekte hinweg** : Diese Tabelle listet die durchschnittliche Stimmung nach Geschäftsaspekten auf. Es kann Ihnen helfen, einzuschätzen, welche Aspekte Ihres Unternehmens Kunden bereits zufriedenstellen oder welche Aspekte mehr Aufmerksamkeit erfordern. Feedback-Datensätze, die keinem der unterstützten Geschäftsaspekte entsprechen, werden unter **Sonstige** kategorisiert. Die Tabelle wird standardmäßig alphabetisch sortiert. Sie können die Sortierung ändern, indem Sie eine Tabellenüberschrift auswählen.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Liste der geschäftlichen Aspekte mit dem zugehörigen Stimmungs-Score und der Anzahl der Kunden, die den Aapekt erwähnen.":::
 
  Wählen Sie den Namen eines Geschäftsaspekts aus, um zusätzliche Informationen darüber anzuzeigen, wie ein Geschäftsaspekt vom Modell identifiziert wird. Es gibt zwei Teile in diesem Bereich: 

  - **Einflussreiche Wörter** : Zeigt die wichtigsten Wörter, die die Identifizierung eines Geschäftsaspekts im Kundenfeedback durch das KI-Modell beeinflusst haben. 
    **Anstößige Wörter anzeigen**: Ermöglicht es Ihnen, anstößige Wörter aus ursprünglichen Kundenfeedbackdaten in die Liste aufzunehmen. Dies ist standardmäßig deaktiviert.  Die anstößige Wortmaskierung wird von einem KI-Modell unterstützt und erkennt möglicherweise nicht alle anstößigen Wörter. Wir iterieren und trainieren die Klassifizierung für eine optimale Leistung weiter. Wenn Sie ein anstößiges Wort entdecken, das nicht wie erwartet herausgefiltert wurde, teilen Sie uns dies mit. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Liste einflussreicher Wörter mit dem Schalter zum Ein- oder Ausblenden anstößiger Wörter.":::
 
  - **Feedbackbeispiele** : Zeigt tatsächliche Feedbackdatensätze in Ihren Daten an. Wörter sind entsprechend ihres Einflusses auf die Identifizierung eines Geschäftsaspekts farbcodiert. 


### <a name="influential-words-analysis-tab"></a>Registerkarte „Analyse einflussreicher Wörter“

Es gibt drei Abschnitte mit zusätzlichen Informationen, die erklären, wie das Stimmungsmodell funktioniert.
  
1. **Top-Wörter, die zu einer positiven Stimmung beitragen**: Zeigt die wichtigsten Wörter, die die Identifizierung positiver Stimmungen im Kundenfeedback durch das KI-Modell beeinflusst haben.  
2. **Top-Wörter, die zu einer negativen Stimmung beitragen**: Zeigt die wichtigsten Wörter, die die Identifizierung negativer Stimmungen im Kundenfeedback durch das KI-Modell beeinflusst haben.  
3. **Feedbackbeispiele** : Zeigt tatsächliche Feedbackdatensätze an, einen mit negativer Stimmung und einen mit positiver Stimmung. Wörter in den Feedbackdatensätzen werden entsprechend ihrem Beitrag zum zugewiesenen Stimmungs-Score hervorgehoben. Wörter, die zu einem positiven Stimmungs-Score beitragen, sind grün hervorgehoben. Wörter, die zu einem negativen Score beitragen, sind rot hervorgehoben.
   Wählen Sie **Mehr anzeigen** aus, um weitere Feedbackbeispiele zu laden, die mehr Informationen und Kontext zur Funktionsweise des Stimmungsmodells bieten.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Beispiele für Stimmungsanalysen zu Kundenfeedback.":::
 
**Anstößige Wörter anzeigen**: Ermöglicht es Ihnen, anstößige Wörter aus ursprünglichen Kundenfeedbackdaten in die Liste aufzunehmen. Dies ist standardmäßig deaktiviert.  Die anstößige Wortmaskierung wird von einem KI-Modell unterstützt und erkennt möglicherweise nicht alle anstößigen Wörter. Wir iterieren und trainieren die Klassifizierung für eine optimale Leistung weiter. Wenn Sie ein anstößiges Wort entdecken, das nicht wie erwartet herausgefiltert wurde, teilen Sie uns dies mit. 

## <a name="act-on-analysis-results"></a>Aktionen zu Analyseergebnissen

Sie können auf der Ergebnisseite der Stimmungsanalyse ganz einfach mit der Erstellung neuer Kundensegmente beginnen, indem Sie oben auf der Modellergebnisseite **Segmente erstellen** auswählen.

:::image type="content" source="media/create-segment-model.png" alt-text="Befehlsleiste mit Optionen für Vorhersagemodelle.":::
 
## <a name="potential-bias"></a>Mögliche Voreingenommenheit

Wie bei jeder Funktion, die prädiktive künstliche Intelligenz verwendet, sollten Sie sich möglicher Verzerrungen in den Daten bewusst sein, die Sie zur Vorhersage der Kundenstimmung verwenden. Wenn Sie beispielsweise Feedback nur digital sammeln, könnten Sie Feedback von Kunden verpassen, die hauptsächlich persönlich mit Ihnen Geschäfte tätigen, was sich auf die Ausgabe der Funktion auswirken könnte.

Da diese Funktion automatisierte Mittel verwendet, um Daten auszuwerten und auf der Grundlage dieser Daten Vorhersagen zu treffen, kann sie daher als Methode zur Profilerstellung verwendet werden, wie dieser Begriff in der allgemeinen Datenschutzverordnung („DSGVO“) definiert ist. Ihre Verwendung dieser Funktion zur Verarbeitung von Daten unterliegt möglicherweise der DSGVO oder anderen Gesetzen oder Vorschriften. Sie sind dafür verantwortlich, sicherzustellen, dass Ihre Verwendung von Dynamics 365 Customer Insights, einschließlich Stimmungsanalyse, allen geltenden Gesetzen und Vorschriften, einschließlich Gesetzen in Bezug auf Datenschutz, personenbezogene Daten, biometrische Daten, Datenschutz und Vertraulichkeit der Kommunikation, entspricht.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

