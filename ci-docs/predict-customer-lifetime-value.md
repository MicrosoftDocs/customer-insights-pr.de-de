---
title: Langfristigen Kundenwert (CLV) vorhersagen
description: Prognostizieren Sie das Umsatzpotenzial für aktive Kunden in der Zukunft.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610373"
---
# <a name="predict-customer-lifetime-value-clv"></a>Langfristigen Kundenwert (CLV) vorhersagen

Prognostizieren Sie den potenziellen Wert (Umsatz), den einzelne aktive Kunden über einen definierten zukünftigen Zeitraum in Ihr Unternehmen einbringen werden. Diese Vorhersage hilft Ihnen bei Folgendem:

- Hochwertige Kunden identifizieren und diese Erkenntnisse verarbeiten.
- Strategische Kundensegmente basierend auf ihrem potenziellen Wert zu erstellen, um personalisierte Kampagnen mit gezielten Verkaufs-, Marketing- und Supportbemühungen durchzuführen.
- Die Produktentwicklung auszurichten, indem Sie sich auf Funktionen konzentrieren, die den Kundennutzen steigern.
- Die Vertriebs- oder Marketingstrategie zu optimieren und das Budget für die Kontaktaufnahme mit Kunden genauer zuzuweisen.
- Hochwertige Kunden zu erkennen und durch Treue- oder Prämienprogramme zu belohnen.

Bestimmen Sie was CLV für Ihr Unternehmen bedeutet. Wir unterstützen transaktionsbasierte CLV-Vorhersagen. Der prognostizierte Wert eines Kunden basiert auf dem Verlauf der Geschäftstransaktionen. Überlegen Sie, mehrere Modelle mit unterschiedlichen Eingabeeinstellungen zu erstellen und die Modellergebnisse zu vergleichen, um festzustellen, welches Modellszenario Ihren Geschäftsanforderungen am besten entspricht.

> [!TIP]
> Probieren Sie die CLV-Vorhersage mit Beispieldaten aus: [Beispielleitfaden zur Vorhersage des langfristigen Kundenwerts (CLV)](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Anforderungen

- Mindestens Berechtigungen als [Mitwirkender](permissions.md)
- Mindestens 100 einzigartige Kunden, vorzugsweise mehr als 10.000 Kunden
- Kundenkennung, eine eindeutige Kennung, um Transaktionen einem einzelnen Kunden zuzuordnen
- Mindestens ein Jahr Transaktionsverlauf, vorzugsweise zwei bis drei Jahre. Idealerweise mindestens zwei bis drei Transaktionen pro Kunden-ID, vorzugsweise über mehrere Daten hinweg. Der Transaktionsverlauf muss Folgendes enthalten:
  - **Transaktions-ID**: Eindeutiger Bezeichner der einzelnen Transaktionen
  - **Transaktionsdatum**: Datum oder Zeitstempel jeder Transaktion
  - **Transaktionsbetrag**: Geldwert (z. B. Umsatz oder Gewinnspanne) jeder Transaktion
  - **Retouren zugewiesene Bezeichnung**: Boolescher Wahr-/Falsch-Wert, der angibt, ob es sich bei der Transaktion um eine Retoure handelt
  - **Produkt-ID**: Produkt-ID des an der Transaktion beteiligten Produkts
- Daten über Kundenaktivitäten:
  - **Primärschlüssel**: Eindeutiger Bezeichner für eine Aktivität
  - **Zeitstempel**: Datum und die Uhrzeit des Ereignisses, identifiziert durch den Primärschlüssel
  - **Ereignis (Aktivitätsname)**: Name des Ereignisses, das Sie verwenden möchten
  - **Details (Betrag oder Wert)**: Details zur Kundenaktivität
- Weitere Daten wie:
  - Webaktivitäten: Website-Besuchsverlauf oder E-Mail-Verlauf
  - Loyalitätsaktivitäten: Sammeln von Treueprämienpunkten und Einlösungsverlauf
  - Kundenserviceprotokoll: Serviceanruf, Beschwerde oder Retourenverlauf
  - Kundenprofilinformationen
- Weniger als 20 % fehlende Werte in Pflichtfeldern

> [!NOTE]
> Nur eine Transaktionsverlaufsentität kann konfiguriert werden. Wenn es mehrere Kauf- oder Transaktionsentitäten gibt, kombinieren Sie sie vor der Datenaufnahme in Power Query.

## <a name="create-a-customer-lifetime-value-prediction"></a>Langfristige Kundenwertvorhersage erstellen

Wählen Sie **Entwurf speichern** aus, um die Vorhersage als Entwurf zu speichern. Die Entwurfsvorhersage wird in der Registerkarte **Meine Vorhersagen** angezeigt.

1. Gehen Sie zu **Intelligenz** > **Vorhersagen**.

1. Wählen Sie auf der Registerkarte **Erstellen** auf der Kachel **Langfristiger Kundenwert** **Modell verwenden** aus.

1. Wählen Sie **Erste Schritte** aus.

1. **Dieses Modell benennen** und **Ausgabeentitätsname**, um sie von anderen Modellen oder Entitäten zu unterscheiden.

1. Klicken Sie auf **Weiter**.

### <a name="define-model-preferences"></a>Modelleinstellungen definieren

1. Legen Sie einen **Vorhersagezeitraum** fest, um zu definieren, wie weit in die Zukunft Sie den CLV vorhersagen möchten. Standardmäßig ist die Einheit auf Monate eingestellt.

   > [!TIP]
   > Um den CLV für den von Ihnen festgelegten Zeitraum genau vorherzusagen, wird ein vergleichbarer Zeitraum historischer Daten benötigt. Wenn Sie beispielsweise CLV-Vorhersagen für die nächsten 12 Monate treffen möchten, brauchen Sie 18 bis 24 Monate historischer Daten

1. Legen Sie den Zeitrahmen fest, in dem ein Kunde mindestens eine Transaktion gehabt haben muss, um als aktiv zu gelten. Das Modell sagt nur CLV für **Aktive Kunden** voraus.
   - **Kaufintervall durch das Modell berechnen lassen (empfohlen)**: Modell analysiert Ihre Daten und ermittelt einen Zeitraum basierend auf historischen Einkäufen.
   - **Intervall manuell einstellen**: Zeitraum für Ihre Definition eines aktiven Kunden.

1. Definieren Sie das Perzentil für **Kunde mit hohem Wert**.
    - **Modellberechnung (empfohlen)**: Modell verwendet die 80/20-Regel. Der Prozentsatz der Kunden, die im historischen Zeitraum zu 80 % des kumulierten Umsatzes Ihres Unternehmens beigetragen haben, gelten als hochwertige Kunden. In der Regel tragen weniger als 30-40 % der Kunden zu 80 % des kumulierten Umsatzes bei. Diese Anzahl kann jedoch je nach Unternehmen und Branche variieren.
    - **Prozent der aktivsten Kunden**: Spezifisches Perzentil für einen Kunden mit hohem Wert. Geben Sie zum Beispiel **25** ein, um Kunden mit hohem Wert zum Beispiel als die oberen 25 % der zukünftigen zahlenden Kunden zu definieren.

    Wenn Ihr Unternehmen hochwertige Kunden anders definiert, [teilen Sie uns dies mit, da dies für uns interessant ist](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Wählen Sie **Weiter** aus.

### <a name="add-required-data"></a>Erforderliche Daten hinzufügen

1. Wählen Sie **Daten hinzufügen** für **Kundentransaktionsverlauf** aus.

1. Wählen Sie den semantischen Aktivitätstyp, **SalesOrder** oder **SalesOrderLine** aus, der den Transaktionsverlauf enthält. Wenn die Aktivität nicht eingerichtet wurde, wählen Sie sie **hier** aus und erstellen Sie sie.

1. Wählen Sie unter **Aktivitäten**, wenn die Aktivitätsattribute der Aktivität semantisch zugeordnet wurden, die spezifischen Attribute oder Entitäten aus, auf die sich die Berechnung konzentrieren soll. Wenn keine semantische Zuordnung erfolgt ist, wählen Sie **Bearbeiten** aus und ordnen Sie Ihre Daten aus.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Erforderliche Daten für das CLV-Modell hinzufügen":::

1. Wählen Sie **Nächste** und überprüfen Sie die für dieses Modell erforderlichen Attribute.

1. Wählen Sie **Save** (Speichern).

1. Fügen Sie weitere Aktivitäten hinzu oder wählen Sie **Weiter** aus.

### <a name="add-optional-activity-data"></a>Aktivitätsdaten (optional) hinzufügen

Daten, die wichtige Kundeninteraktionen widerspiegeln (wie Web, Kundenservice und Ereignisprotokolle), fügen den Transaktionsdatensätzen Kontext hinzu. Weitere Muster in Ihren Kundenaktivitätsdaten können die Genauigkeit der Vorhersagen verbessern.

1. Wählen Sie **Daten hinzufügen** unter **Modellerkenntnisse mit zusätzlichen Aktivitätsdaten verfeinern**.

1. Wählen Sie einen Aktivitätstyp aus, der dem Typ der Kundenaktivität entspricht, die Sie hinzufügen. Wenn die Aktivität nicht eingerichtet wurde, wählen Sie sie **hier** aus und erstellen Sie sie.

1. Wählen Sie unter **Aktivitäten**, wenn die Aktivitätsattribute beim Erstellen der Aktivität zugeordnet wurden, die spezifischen Attribute oder Entitäten aus, auf die sich die Berechnung konzentrieren soll. Wenn keine Zuordnung erfolgt ist, wählen Sie **Bearbeiten** aus und ordnen Sie Ihre Daten aus.

1. Wählen Sie **Nächste** und überprüfen Sie die für dieses Modell erforderlichen Attribute.

1. Wählen Sie **Save** (Speichern).

1. Wählen Sie **Weiter** aus.

1. [Fügen Sie optionale Kundendaten hinzu](#add-optional-customer-data) oder wählen Sie **Weiter** und gehen Sie zu [Aktualisierungszeitplan festlegen](#set-update-schedule).

### <a name="add-optional-customer-data"></a>Optionale Kundendaten hinzufügen

Wählen Sie aus 18 häufig verwendeten Kundenprofilattributen aus, die Sie als Eingabe in das Modell aufnehmen möchten. Diese Attribute können zu personalisierteren, relevanteren und umsetzbareren Modellergebnissen für Ihre geschäftlichen Anwendungsfälle führen.

Beispiel: Contoso Coffee möchte den Customer Lifetime Value vorhersagen, um hochwertige Kunden mit einem personalisierten Angebot im Zusammenhang mit der Einführung ihrer neuen Espressomaschine anzusprechen. Contoso verwendet das CLV-Modell und fügt alle 18 Kundenprofilattribute hinzu, um zu sehen, welche Faktoren ihre wertvollsten Kunden beeinflussen. Sie stellen fest, dass der Standort des Kunden der einflussreichste Faktor für diese Kunden ist.
Mit diesen Informationen organisieren sie eine lokale Veranstaltung zur Einführung der Espressomaschine und arbeiten mit lokalen Anbietern zusammen, um personalisierte Angebote und ein besonderes Erlebnis bei der Veranstaltung zu erhalten. Ohne diese Informationen hätte Contoso möglicherweise nur generische Marketing-E-Mails gesendet und die Gelegenheit verpasst, für dieses lokale Segment seiner hochwertigen Kunden zu personalisieren.

1. Wählen Sie **Daten hinzufügen** unter **Modellerkenntnisse mit zusätzlichen Kundendaten weiter verfeinern**.

1. Wählen Sie für **Entität** **Kunde: CustomerInsights** aus, um das vereinheitliche Kundenprofil auszuwählen, das den Kundenattributdaten zugeordnet ist. Für **Kunden-ID** wählen Sie **System.Customer.CustomerId**.

1. Ordnen Sie weitere Felder zu, wenn die Daten in Ihren einheitlichen Kundenprofilen verfügbar sind.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Beispiel für zugeordnete Felder für Kundenprofildaten.":::

1. Wählen Sie **Save** (Speichern).

1. Wählen Sie **Weiter** aus.

### <a name="set-update-schedule"></a>Zeitplanaktualisierung festlegen

1. Wählen Sie die Häufigkeit aus, mit der Sie Ihr Modell basierend auf den neuesten Daten erneut trainieren möchten. Diese Einstellung ist wichtig, um die Genauigkeit der Vorhersagen zu aktualisieren, wenn neue Daten in Customer Insights aufgenommen werden. Die meisten Unternehmen können einmal pro Monat eine Umschulung durchführen und erhalten eine gute Genauigkeit für ihre Vorhersagen.

1. Wählen Sie **Weiter** aus.

### <a name="review-and-run-the-model-configuration"></a>Überprüfen Sie die Modellkonfiguration und führen Sie sie aus

Der Schritt **Überprüfen und ausführen** zeigt eine Zusammenfassung der Konfiguration und bietet die Möglichkeit, Änderungen vorzunehmen, bevor Sie die Datei Vorhersage erstellen.

1. Wählen Sie **Bearbeiten** bei einem der Schritte, um sie zu überprüfen und Änderungen vorzunehmen.

1. Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **Speichern und ausführen** aus, um das Modell ausführen zu lassen. Wählen Sie **Fertig** aus. Die Registerkarte **Meine Vorhersagen** wird angezeigt, während Vorhersage erstellt wird. Der Prozess kann je nach der Menge der in der Vorhersage verwendeten Daten mehrere Stunden dauern.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Vorhersageergebnisse anzeigen

1. Gehen Sie zu **Intelligenz** > **Vorhersagen**.

1. Wählen Sie in der Registerkarte **Meine Vorhersagen** die Vorhersage aus, die Sie ansehen möchten.

Es gibt drei primäre Datenabschnitte innerhalb der Ergebnisseite.

- **Leistung des Trainingsmodells**: Die Stufen A, B oder C geben die Leistung der Vorhersage an und können Ihnen bei der Entscheidung helfen, die in der Ausgabeentität gespeicherten Ergebnisse zu verwenden.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Bild des Informationsfelds für die Modellbewertung mit der Stufe A.":::

  Customer Insights bewertet, wie das KI-Modell bei der Vorhersage von Kunden mit einem hohen Wert im Vergleich zu einem Baselinemodell abschneidet.

  Die Stufen werden nach den folgenden Regeln ermittelt:
  - **A**, wenn das Modell im Vergleich zum Basismodell mindestens 5 % mehr hochwertige Kunden genau vorhergesagt hat.
  - **B**, wenn das Modell im Vergleich zum Basismodell zwischen 0-5 % mehr hochwertige Kunden genau vorhergesagt hat.
  - **C**, wenn das Modell im Vergleich zum Basismodell weniger hochwertige Kunden genau vorhergesagt hat.
  
  Wählen Sie [**Informationen zu dieser Bewertung**](#learn-about-the-score) aus, um den Bereich **Modellbewertung** zu öffnen, der weitere Details zur Leistung des KI-Modells und zum Baselinemodell angezeigt. Dadurch erfahren Sie mehr über die zugrunde liegenden Modellleistungsmetriken und die Ableitung des endgültigen Modellleistungsgrads. Das Basismodell verwendet einen nicht auf KI basierenden Ansatz, um den langfristigen Kundenwert zu berechnen, der hauptsächlich auf historischen Einkäufen von Kunden basiert.

- **Wert der Kunden nach Perzentil**: Kunden mit geringem Wert und mit hohem Wert werden in einem Diagramm angezeigt. Bewegen Sie den Mauszeiger über das Histogramm, können Sie die Anzahl der Kunden in jeder Gruppe und den durchschnittlichen CLV dieser Gruppe anzeigen. Erstellen Sie optional [Kundensegmente](prediction-based-segment.md), die auf ihren CLV-Vorhersagen basieren.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Wert der Kunden nach Perzentil für CLV-Modell":::

- **Einflussreichste Faktoren**: Beim Erstellen Ihrer CLV-Vorhersage werden verschiedene Faktoren berücksichtigt, die auf den für das KI-Modell bereitgestellten Eingabedaten basieren. Für jeden dieser Faktoren wird ihre Bedeutung für die aggregierten Vorhersagen, die ein Modell erstellt, berechnet. Verwenden Sie diese Faktoren, um Ihre Vorhersageergebnisse zu validieren. Diese Faktoren bieten auch mehr Einblick in die einflussreichsten Faktoren, die zur Vorhersage des CLV bei all Ihren Kunden beigetragen haben.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Die einflussreichsten Faktoren für CLV-Modell":::

### <a name="learn-about-the-score"></a>Informationen zu der Bewertung

Die Standardformel zur Berechnung des CLV anhand des Basismodells:

 _**CLV für jeden Kunden** = durchschnittlicher monatlicher Einkauf des Kunden im aktiven Kundenfenster * Anzahl der Monate im CLV-Vorhersagezeitraum * Gesamtbindungsrate aller Kunden_

Das KI-Modell wird anhand von zwei Modellleistungsmetriken mit dem Basismodell verglichen.
  
- **Erfolgsrate bei der Vorhersage von Kunden mit hohem Wert**

  Sehen Sie den Unterschied bei der Vorhersage hochwertiger Kunden mithilfe des KI-Modells im Vergleich zum Basismodell. Zum Beispiel bedeutet eine Erfolgsquote von 84 %, dass das KI-Modell von allen hochwertigen Kunden in den Trainingsdaten 84 % genau erfassen konnte. Wir vergleichen diese Erfolgsrate dann mit der Erfolgsrate des Basismodells, um die relative Änderung zu melden. Dieser Wert wird verwendet, um dem Modell eine Stufe zuzuweisen.

- **Fehlermetriken**

  Sehen Sie sich die Gesamtleistung des Modells in Bezug auf Fehler bei der Vorhersage zukünftiger Werte an. Wir verwenden die RMSE-Metrik (Root Mean Squared Error), um diesen Fehler zu bewerten. RMSE ist eine Standardmethode zur Messung des Fehlers eines Modells bei der Vorhersage quantitativer Daten. Der RMSE des KI-Modells wird mit dem RMSE des Basismodells verglichen und der relative Unterschied angegeben.

Das KI-Modell priorisiert das genaue Ranking der Kunden nach dem Wert, den sie für Ihr Unternehmen bringen. Daher wird nur die Erfolgsrate der Vorhersage hochwertiger Kunden verwendet, um die endgültige Modellstufe abzuleiten. Die RMSE-Metrik reagiert empfindlich auf Ausreißer. In Szenarien, in denen Sie einen kleinen Prozentsatz von Kunden mit außerordentlich hohen Kaufwerten haben, liefert die RMSE-Gesamtmetrik möglicherweise nicht das vollständige Bild der Modellleistung.

[!INCLUDE [footer-include](includes/footer-banner.md)]
