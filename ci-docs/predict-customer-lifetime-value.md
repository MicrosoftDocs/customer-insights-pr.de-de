---
title: Benutzerdefinierte Lebensdauer-Wert(CLV)-Vorhersage
description: Prognostizieren Sie das Umsatzpotenzial für aktive Kunden in der Zukunft.
ms.date: 02/05/2021
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
ms.openlocfilehash: 3e1b1ce00eeda1cead9ba05beae65b6903d0b9cf
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647343"
---
# <a name="customer-lifetime-value-clv-prediction"></a>Benutzerdefinierte Lebensdauer-Wert(CLV)-Vorhersage

Prognostizieren Sie den potenziellen Wert (Umsatz), den einzelne aktive Kunden über einen definierten zukünftigen Zeitraum in Ihr Unternehmen einbringen werden. Mit dieser Funktion können Sie verschiedene Ziele erreichen: 
- Identifizieren Sie hochwertige Kunden und verarbeiten Sie diese Erkenntnisse
- Erstellen Sie strategische Kundensegmente basierend auf ihrem potenziellen Wert, um personalisierte Kampagnen mit gezielten Verkaufs-, Marketing- und Supportbemühungen durchzuführen
- Leiten Sie die Produktentwicklung an, indem Sie sich auf Funktionen konzentrieren, die den Kundennutzen steigern
- Optimieren Sie die Vertriebs- oder Marketingstrategie und weisen Sie das Budget für die Kundenansprache genauer zu
- Erkennen und belohnen Sie hochwertige Kunden durch Treue- oder Prämienprogramme 

## <a name="prerequisites"></a>Anforderungen

Überlegen Sie sich vor dem Start, was CLV für Ihr Unternehmen bedeutet. Derzeit unterstützen wir transaktionsbasierte CLV-Vorhersage. Der prognostizierte Wert eines Kunden basiert auf der Historie der Geschäftsvorfälle. Um die Vorhersage zu erstellen, benötigen Sie mindestens [Teilnehmer](permissions.md)-Berechtigungen.

Da das Konfigurieren und Ausführen eines CLV-Modells nicht viel Zeit in Anspruch nimmt, sollten Sie mehrere Modelle mit unterschiedlichen Eingabeeinstellungen erstellen und die Modellergebnisse vergleichen, um festzustellen, welches Modellszenario Ihren Geschäftsanforderungen am besten entspricht.

###  <a name="data-requirements"></a>Datenanforderungen

Die folgenden Daten sind erforderlich und werden, sofern als optional gekennzeichnet, für eine höhere Modellleistung empfohlen. Je mehr Daten das Modell verarbeiten kann, desto genauer ist die Vorhersage. Wir empfehlen Ihnen daher, weitere Daten zur Kundenaktivität zu erfassen, sofern verfügbar.

- Kundenkennung: Eindeutige Kennung, um Transaktionen einem einzelnen Kunden zuzuordnen

- Transaktionsverlauf: Protokoll historischer Transaktionen mit dem folgenden semantischen Datenschema
    - **Transaktions-ID**: Eindeutiger Bezeichner der einzelnen Transaktionen
    - **Transaktionsdatum**: Datum, vorzugsweise ein Zeitstempel jeder Transaktion
    - **Transaktionsbetrag**: Geldwert (z. B. Umsatz oder Gewinnspanne) jeder Transaktion
    - **Bezeichnung, die Retouren zugewiesen ist** (optional): Boolescher Wert, der angibt, ob es sich bei der Transaktion um eine Retoure handelt 
    - **Produkt-ID** (optional): Produkt-ID des an der Transaktion beteiligten Produkts

- Zusätzliche Daten (optional), zum Beispiel
    - Webaktivitäten: Website-Besuchsverlauf, E-Mail-Verlauf
    - Loyalitätsaktivitäten: Sammeln von Treueprämienpunkten und Einlösungsverlauf
    - Kundenservice-Protokoll, Serviceanruf, Beschwerde oder Rückgabeverlauf
- Daten über Kundenaktivitäten (optional):
    - Aktivitätskennungen zur Unterscheidung von Aktivitäten desselben Typs
    - Kundenidentifikatoren zur Zuordnung von Aktivitäten zu Ihren Kunden
    - Aktivitätsinformationen, die den Namen und das Datum der Aktivität enthalten
    - Das semantische Datenschema für Aktivitäten umfasst: 
        - **Primärschlüssel**: Ein eindeutiger Identifikator für eine Aktivität
        - **Zeitstempel**: Das Datum und die Uhrzeit des Ereignisses, identifiziert durch den Primärschlüssel
        - **Ereignis (Aktivitätsname)**: Der Name des Ereignisses, das Sie verwenden möchten
        - **Details (Betrag oder Wert)**: Details zur Kundenaktivität

- Vorgeschlagene Datencharakteristik:
    - Ausreichende historische Daten: Mindestens ein Jahr Transaktionsdaten. Vorzugsweise zwei bis drei Jahre Transaktionsdaten, um CLV für ein Jahr vorherzusagen.
    - Mehrere Einkäufe pro Kunde: Idealerweise mindestens zwei bis drei Transaktionen pro Kunden-ID, vorzugsweise über mehrere Daten hinweg.
    - Anzahl der Kunden: Mindestens 100 einzigartige Kunden, vorzugsweise mehr als 10.000 Kunden. Das Modell schlägt mit weniger als 100 Kunden und unzureichenden historischen Daten fehl
    - Vollständigkeit der Daten: Weniger als 20 % fehlende Werte in den erforderlichen Feldern in den Eingabedaten   

> [!NOTE]
> - Das Modell erfordert die Transaktionshistorie Ihrer Kunden. Derzeit kann nur eine Transaktionsverlaufsentität konfiguriert werden. Wenn es mehrere Kauf/Transaktionsentitäten gibt, können Sie sie vor der Datenaufnahme in Power Query vereinen.
> - Für zusätzliche Kundenaktivitätsdaten (optional) können Sie jedoch so viele Kundenaktivitätsentitäten hinzufügen, wie Sie für das Modell berücksichtigen möchten.

## <a name="create-a-customer-lifetime-value-prediction"></a>Langfristige Kundenwertvorhersage erstellen

1. Gehen Sie zu **Intelligenz** > **Vorhersagen**.

1. Wählen Sie die **Langfristiger Kundenwert**-Kachel und dann **Modell verwenden**. 

1. Wählen Sie im Bereich **Langfristiger Kundenwert** **Erste Schritte** aus.

1. **Dieses Modell benennen** und **Ausgabeentitätsname**, um sie von anderen Modellen oder Entitäten zu unterscheiden.

1. Klicken Sie auf **Weiter**.

### <a name="define-model-preferences"></a>Modelleinstellungen definieren

1. Legen Sie einen **Vorhersagezeitraum** fest, um zu definieren, wie weit in die Zukunft Sie den CLV vorhersagen möchten.    
   Standardmäßig ist die Einheit auf Monate eingestellt. Sie können sie in Jahre ändern, um weiter in die Zukunft zu schauen.

   > [!TIP]
   > Um den CLV für den von Ihnen festgelegten Zeitraum genau vorherzusagen, benötigen Sie einen vergleichbaren Zeitraum historischer Daten. Wenn Sie beispielsweise CLV-Vorhersagen für die nächsten 12 Monate treffen möchten, wird empfohlen, dass Sie über historische Daten für mindestens 18 bis 24 Monate verfügen.

1. Geben Sie an, was **Aktive Kunden** für Ihr Geschäft bedeuten. Legen Sie den Zeitrahmen fest, in dem ein Kunde mindestens eine Transaktion gehabt haben muss, um als aktiv zu gelten. Das Modell sagt CLV nur für aktive Kunden voraus. 
   - **Kaufintervall durch das Modell berechnen lassen (empfohlen)** : Das Modell analysiert Ihre Daten und ermittelt einen Zeitraum basierend auf historischen Einkäufen.
   - **Intervall manuell festlegen**: Wenn Sie eine bestimmte Geschäftsdefinition eines aktiven Kunden haben, wählen Sie diese Option und legen Sie den Zeitraum entsprechend fest.

1. Definieren Sie ein Perzentil von **Kunde mit hohem Wert**, damit das Modell Ergebnisse liefert, die Ihrer Geschäftsdefinition entsprechen.
    - **Modellberechnung (empfohlen)**: Das Modell analysiert Ihre Daten und ermittelt anhand der Transaktionshistorie Ihrer Kunden, was ein hochwertiger Kunde für Ihr Unternehmen sein könnte. Das Modell verwendet eine heuristische Regel (inspiriert von der 80/20-Regel oder dem Pareto-Prinzip), um den Anteil hochwertiger Kunden zu ermitteln. Der Prozentsatz der Kunden, die im historischen Zeitraum zu 80 % des kumulierten Umsatzes Ihres Unternehmens beigetragen haben, gelten als hochwertige Kunden. In der Regel tragen weniger als 30-40 % der Kunden zu 80 % des kumulierten Umsatzes bei. Diese Anzahl kann jedoch je nach Unternehmen und Branche variieren.    
    - **Prozent der aktivsten Kunden**: Definieren Sie hochwertige Kunden für Ihr Unternehmen als Perzentil der aktivsten zahlenden Kunden. Mit dieser Option können Sie beispielsweise hochwertige Kunden als Top 20 % der zukünftigen zahlenden Kunden definieren.

    Wenn Ihr Unternehmen hochwertige Kunden anders definiert, [teilen Sie uns dies mit, da dies für uns interessant ist](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Klicken Sie auf **Weiter**, um den Vorgang mit dem nächsten Schritt fortzusetzen.

### <a name="add-required-data"></a>Erforderliche Daten hinzufügen

1. Im Schritt **Erforderliche Daten** wählen Sie **Daten hinzufügen** für **Kundentransaktionsverlauf** und wählen Sie die Entität, die die Informationen zur Transaktionshistorie bereitstellt, wie in den [Voraussetzungen](#prerequisites) beschrieben.

1. Ordnen Sie die semantischen Felder den Attributen innerhalb Ihrer Entität „Kaufhistorie“ zu und wählen Sie **Nächste**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Bild des Konfigurationsschritts zum Zuordnen von Datenattributen für die erforderlichen Daten.":::
 
1. Wenn die Felder unten nicht ausgefüllt sind, konfigurieren Sie die Beziehung von Ihrer Entität „Kaufhistorie“ zur Entität *Kunde* und wählen **Speichern** aus.
    1. Wählen Sie die Entität „Transaktionshistorie“.
    1. Wählen Sie das Feld, das den Kunden in der Entität Kaufhistorie identifiziert. Es muss sich auf die primäre Kunden-ID Ihrer Entität Kunde beziehen.
    1. Wählen Sie die Entität aus, die der primären Kundenentität entspricht.
    1. Geben Sie einen Namen ein, der die Beziehung beschreibt.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Bild des Konfigurationsschritts zum Definieren der Beziehung zur Kundenentität.":::

1. Klicken Sie auf **Weiter**.

### <a name="add-optional-data"></a>Optionale Daten hinzufügen

Daten, die wichtige Kundeninteraktionen widerspiegeln (wie Web, Kundenservice und Ereignisprotokolle), fügen den Transaktionsdatensätzen Kontext hinzu. Weitere Muster in Ihren Kundenaktivitätsdaten können die Genauigkeit der Vorhersagen verbessern. 

1. Im Schritt **Zusätzliche Daten (optional)** wählen Sie **Daten hinzufügen**. Wählen Sie die Kundenaktivitätsentität, die die Kundenaktivitätsinformationen liefert, wie in den [Voraussetzungen](#prerequisites) beschrieben.

1. Ordnen Sie die semantischen Felder den Attributen innerhalb Ihrer Entität „Kundenaktivität“ zu und wählen Sie **Nächste**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Bild des Konfigurationsschritts zum Zuordnen von Feldern für zusätzliche Daten":::

1. Wählen Sie einen Aktivitätstyp aus, der dem Typ der Kundenaktivität entspricht, die Sie hinzufügen. Wählen Sie aus vorhandenen Aktivitätstypen oder fügen Sie einen neuen Aktivitätstyp hinzu.

1. Konfigurieren Sie die Beziehung von Ihrer Kundenaktivitätsentität zur *Kunde*-Entität.
    
    1. Wählen Sie das Feld, das den Kunden in der Kundenaktivitätstabelle identifiziert. Es kann sich direkt auf die primäre Kunden-ID Ihrer Entität *Kunde* beziehen.
    1. Wählen Sie das Feld *Kunde*-Entität, das sich auf Ihre primäre *Kundenentität* bezieht.
    1. Geben Sie einen Namen ein, der die Beziehung beschreibt.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Abbildung des Schritts im Konfigurationsablauf zum Hinzufügen zusätzlicher Daten und zum Konfigurieren der Aktivität mit ausgefüllten Beispielen":::

1. Wählen Sie **Speichern** aus.    
    Fügen Sie weitere Daten hinzu, wenn Sie andere Kundenaktivitäten einbeziehen möchten.

1. Klicken Sie auf **Weiter**.

### <a name="set-update-schedule"></a>Zeitplanaktualisierung festlegen

1. Im Schritt **Zeitplan für Datenupdates** wählen Sie die Häufigkeit aus, mit der Sie Ihr Modell basierend auf den neuesten Daten neu trainieren möchten. Diese Einstellung ist wichtig, um die Genauigkeit der Vorhersagen zu aktualisieren, wenn neue Daten in Customer Insights eingebunden werden. Die meisten Unternehmen können einmal pro Monat eine Umschulung durchführen und erhalten eine gute Genauigkeit für ihre Vorhersagen.

1. Klicken Sie auf **Weiter**.

### <a name="review-and-run-the-model-configuration"></a>Überprüfen Sie die Modellkonfiguration und führen Sie sie aus

1. Im Schritt **Überprüfen Sie die Modelldetails** überprüfen Sie die Konfiguration der Vorhersage. Sie können zu jedem Teil der Vorhersagekonfiguration zurückkehren, indem Sie unter dem angezeigten Wert **Bearbeiten** wählen. Sie können auch einen Konfigurationsschritt aus der Fortschrittsanzeige auswählen.

1. Wenn alle Werte korrekt konfiguriert sind, wählen Sie **Speichern und ausführen**, um das Modell zu starten. Auf der **Meine Vorhersagen**-Registerkarte können Sie den Status des Vorhersageprozesses anzeigen. Der Prozess kann je nach der Menge der in der Vorhersage verwendeten Daten mehrere Stunden dauern.

## <a name="review-prediction-status-and-results"></a>Status und Ergebnisse der Vorhersage überprüfen

### <a name="review-prediction-status"></a>Überprüfen Sie den Status der Vorhersage

1.  Gehen Sie zu **Intelligenz** > **Vorhersagen** und wählen Sie die Registerkarte **Meine Vorhersagen**.
2.  Wählen Sie die Vorhersage aus, die Sie überprüfen möchten.

- **Vorhersagename**: Name der Vorhersage, der beim Erstellen der Vorhersage angegeben wird.
- **Vorhersagetyp**: Typ des für die Vorhersage verwendeten Modells
- **Ausgabeentität**: Name der Entität zum Speichern der Ausgabe der Vorhersage. Gehen Sie zu **Daten** > **Entitäten**, um die Entität mit diesem Namen zu finden.
- **Vorhersagefeld:**: Dieses Feld wird nur für einige Arten von Vorhersagen ausgefüllt und wird nicht für die Vorhersage des langfristigen Kundenwerts verwendet.
- **Status:** Status des Vorhersagelaufs.
    - **In Warteschlange:** Die Vorhersage wartet auf den Abschluss anderer Prozesse.
    - **Wird aktualisiert:** Die Vorhersage läuft gerade, um Ergebnisse zu erstellen, die in die Ausgabe-Entität fließen.
    - **Fehlgeschlagen:** Der Vorhersagelauf ist fehlgeschlagen. [Betrachten Sie die Protokolle](manage-predictions.md#troubleshoot-a-failed-prediction) für weitere Details.
    - **Erfolgreich:** Die Vorhersage ist erfolgreich. Wählen Sie **Anzeigen** unter den vertikalen Ellipsen, um die Ergebnisse der Vorhersage anzuzeigen.
- **Bearbeitet:** Das Datum, an dem die Konfiguration für die Vorhersage geändert wurde.
- **Zuletzt aktualisiert:** Das Datum, an dem die Vorhersage in der Ausgabe-Entität aktualisiert wurde.

### <a name="review-prediction-results"></a>Überprüfen Sie die Ergebnisse der Vorhersage

1. Gehen Sie zu **Intelligenz** > **Vorhersagen** und wählen Sie die Registerkarte **Meine Vorhersagen**.

1. Wählen Sie das Vorhersage aus, für die Sie die Ergebnisse überprüfen möchten.

Es gibt drei primäre Datenabschnitte innerhalb der Ergebnisseite.

- **Leistung des Trainingsmodells**: A, B oder C sind mögliche Stufen. Diese Stufe gibt die Leistung der Vorhersage an und kann Ihnen bei der Entscheidung helfen, die in der Ausgabeentität gespeicherten Ergebnisse zu verwenden. Wählen Sie **Informationen zu dieser Bewertung** aus, um die zugrunde liegenden Modellleistungsmetriken und die Ableitung des endgültigen Modellleistungsgrads besser zu verstehen.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Bild des Informationsfelds für die Modellbewertung mit der Stufe A.":::

  Anhand der Definition von Kunden mit hohem Wert, die bei der Konfiguration von Vorhersage angegeben wurden, bewertet das System, wie sich das KI-Modell bei der Vorhersage von Kunden mit hohem Wert im Vergleich zu einem Basismodell verhält.    

  Die Stufen werden nach den folgenden Regeln ermittelt:
  - **A**, wenn das Modell im Vergleich zum Basismodell mindestens 5 % mehr hochwertige Kunden genau vorhergesagt hat.
  - **B**, wenn das Modell im Vergleich zum Basismodell zwischen 0-5 % mehr hochwertige Kunden genau vorhergesagt hat.
  - **C**, wenn das Modell im Vergleich zum Basismodell weniger hochwertige Kunden genau vorhergesagt hat.

  Im Bereich **Modellbewertung** werden weitere Details zur Leistung des KI-Modells und zum Basismodell angezeigt. Das Basismodell verwendet einen nicht auf KI basierenden Ansatz, um den langfristigen Kundenwert zu berechnen, der hauptsächlich auf historischen Einkäufen von Kunden basiert.     
  Die Standardformel zur Berechnung des CLV anhand des Basismodells:    

  _**CLV für jeden Kunden** = durchschnittlicher monatlicher Einkauf des Kunden im aktiven Kundenfenster * Anzahl der Monate im CLV-Vorhersagezeitraum * Gesamtbindungsrate aller Kunden_

  Das KI-Modell wird anhand von zwei Modellleistungsmetriken mit dem Basismodell verglichen.
  
  - **Erfolgsrate bei der Vorhersage von Kunden mit hohem Wert**

    Sehen Sie den Unterschied bei der Vorhersage hochwertiger Kunden mithilfe des KI-Modells im Vergleich zum Basismodell. Zum Beispiel bedeutet eine Erfolgsquote von 84 %, dass das KI-Modell von allen hochwertigen Kunden in den Trainingsdaten 84 % genau erfassen konnte. Wir vergleichen diese Erfolgsrate dann mit der Erfolgsrate des Basismodells, um die relative Änderung zu melden. Dieser Wert wird verwendet, um dem Modell eine Stufe zuzuweisen.

  - **Fehlermetriken**
    
    Mit einer anderen Metrik können Sie die Gesamtleistung des Modells in Bezug auf Fehler bei der Vorhersage zukünftiger Werte überprüfen. Wir verwenden die RMSE-Metrik (Root Mean Squared Error), um diesen Fehler zu bewerten. RMSE ist eine Standardmethode zur Messung des Fehlers eines Modells bei der Vorhersage quantitativer Daten. Der RMSE des KI-Modells wird mit dem RMSE des Basismodells verglichen und der relative Unterschied angegeben.

  Das KI-Modell priorisiert das genaue Ranking der Kunden nach dem Wert, den sie für Ihr Unternehmen bringen. Daher wird nur die Erfolgsrate der Vorhersage hochwertiger Kunden verwendet, um die endgültige Modellstufe abzuleiten. Die RMSE-Metrik reagiert empfindlich auf Ausreißer. In Szenarien, in denen Sie einen kleinen Prozentsatz von Kunden mit außerordentlich hohen Kaufwerten haben, liefert die RMSE-Gesamtmetrik möglicherweise nicht das vollständige Bild der Modellleistung.   

- **Wert der Kunden nach Perzentil**: Unter Verwendung Ihrer Definition von hochwertigen Kunden werden Kunden basierend auf ihren CLV-Vorhersagen in geringerwertige und hochwertige Kunden gruppiert und in einem Diagramm angezeigt. Wenn Sie mit der Maus über die Balken im Histogramm fahren, können Sie die Anzahl der Kunden in jeder Gruppe und den durchschnittlichen CLV dieser Gruppe anzeigen. Diese Daten können helfen, wenn Sie [Kundensegmente erstellen](segments.md), die auf ihren CLV-Vorhersagen basieren.

- **Einflussreichste Faktoren**: Beim Erstellen Ihrer CLV-Vorhersage werden verschiedene Faktoren berücksichtigt, die auf den für das KI-Modell bereitgestellten Eingabedaten basieren. Für jeden dieser Faktoren wird ihre Bedeutung für die aggregierten Vorhersagen, die ein Modell erstellt, berechnet. Sie können diese Faktoren verwenden, um Ihre Vorhersageergebnisse zu validieren. Diese Faktoren bieten auch mehr Einblick in die einflussreichsten Faktoren, die zur Vorhersage des CLV bei all Ihren Kunden beigetragen haben.

## <a name="manage-predictions"></a>Verwalten von Vorhersagen

Es ist möglich, Vorhersagen zu optimieren, zu korrigieren, zu aktualisieren oder zu löschen. Sehen Sie sich einen Eingabedaten-Nutzungsberichts an, um herauszufinden, wie Sie Vorhersagen schneller und zuverlässiger machen. Weitere Informationen finden Sie unter [Verwalten von Vorhersagen](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
