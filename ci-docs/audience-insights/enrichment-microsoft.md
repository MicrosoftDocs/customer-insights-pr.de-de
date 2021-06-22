---
title: Kundenprofile mit Daten von Microsoft anreichern
description: Verwenden Sie proprietäre Daten von Microsoft, um Ihre Kundendaten mit Marken- und Interessenbeziehungen zu bereichern.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e92360bb886739cfe477ce1d2eb62219228a0292
ms.sourcegitcommit: d4b4053f6ee8f60f1a214982c4726c9de84615ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "6245706"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Anreichern von Kundenprofilen mit Marken- und Interessenbeziehungen (Vorschau)

Verwenden Sie proprietäre Daten von Microsoft, um Ihre Kundendaten mit Marken- und Interessenbeziehungen zu bereichern. Diese Affinitäten werden basierend auf Daten von Personen mit ähnlichen demografischen Merkmalen wie Ihre Kunden ermittelt. Diese Informationen helfen Ihnen dabei, Ihre Kunden anhand ihrer Affinität zu bestimmten Marken und Interessen besser zu verstehen und zu segmentieren.

Gehen Sie in Zielgruppenerkenntnisse auf **Daten** > **Anreicherung**, um [Anreicherungen zu konfigurieren und anzuzeigen](enrichment-hub.md).

Um die Anreicherung von Markenaffinitäten zu konfigurieren, gehen Sie zur Registerkarte **Entdecken** und wählen Sie **Anreicherung meiner Daten** auf der Kachel **Marken**.

Um die Anreicherung von Interessenaffinitäten zu konfigurieren, gehen Sie zum Register **Entdecken** und wählen Sie **Anreicherung meiner Daten** auf der Kachel **Interessen**.

   > [!div class="mx-imgBorder"]
   > ![Marken und Interessenkacheln](media/BrandsInterest-tile-Hub.png "Marken und Interessenkacheln")

## <a name="how-we-determine-affinities"></a>Wie wir Affinitäten bestimmen

Wir verwenden die Online-Suchdaten von Microsoft, um Affinitäten für Marken und Interessen in verschiedenen demografischen Segmenten (definiert nach Alter, Geschlecht oder Standort) zu finden. Das Onlinesuchvolumen für eine Marke oder ein Interesse bestimmt, wie viel Affinität ein demografisches Segment im Vergleich zu anderen Segmenten zu dieser Marke oder diesem Interesse hat.

## <a name="affinity-level-and-score"></a>Affinitätsstufe und Punktzahl

Für jedes erweiterte Kundenprofil geben wir zwei verwandte Werte an – Affinitätsstufe und Affinitätsbewertung. Mithilfe dieser Werte können Sie bestimmen, wie stark die Affinität für das demografische Segment dieses Profils, für eine Marke oder ein Interesse im Vergleich zu anderen demografischen Segmenten ist.

*Affinitätsstufe* besteht aus vier Ebenen und *Affinitätsbewertung* wird auf einer 100-Punkte-Skala berechnet, die den Affinitätsstufen zugeordnet ist.


|Affinitätsstufe |Affinitätsbewertung  |
|---------|---------|
|Sehr hoch     | 85-100       |
|Hoch     | 70-84        |
|Mittel     | 35-69        |
|Niedrig     | 1-34        |

Abhängig von der Granularität, die Sie zum Messen der Affinität wünschen, können Sie entweder die Affinitätsstufe oder die Punktzahl verwenden. Der Affinitätswert gibt Ihnen eine genauere Kontrolle.

## <a name="supported-countriesregions"></a>Unterstützte Länder/Regionen

Wir unterstützen derzeit die folgenden Länder-/Regionenoptionen: Australien, Kanada (Englisch), Frankreich, Deutschland, Großbritannien oder USA (Englisch).

Um ein Land auszuwählen, öffnen Sie die **Markenanreicherung** oder **Zinsanreicherung** und wählen Sie **Veränderung** neben dem **Land/Region**. In dem Bereich **Länder-/Regionseinstellungen** wählen Sie eine Option und wählen Sie **Anwenden**.

### <a name="implications-related-to-country-selection"></a>Auswirkungen auf die Länderauswahl

- Wenn Sie [Ihre eigenen Marken auswählen](#define-your-brands-or-interests), liefert das System Vorschläge basierend auf dem ausgewählten Land oder der ausgewählten Region.

- Wenn Sie [eine Branche auswählen](#define-your-brands-or-interests), erhalten Sie die relevantesten Marken oder Interessen basierend auf dem ausgewählten Land oder der ausgewählten Region.

- Wenn Sie [Profile anreichern](#refresh-enrichment), reichern wir alle Kundenprofile, für die wir Daten für die ausgewählten Marken und Interessen erhalten, an. Dies bezieht Profile ein, die sich nicht im ausgewählten Land oder in der ausgewählten Region befinden. Wenn Sie beispielsweise Deutschland ausgewählt haben, bereichern wir Profile in den USA, wenn Daten für die ausgewählten Marken und Interessen in den USA verfügbar sind.

## <a name="configure-enrichment"></a>Anreicherung konfigurieren

Eine geführte Erfahrung hilft Ihnen bei der Konfiguration der Anreicherungen. 

### <a name="define-your-brands-or-interests"></a>Definieren Sie Ihre Marken oder Interessen

Wählen Sie bis zu fünf Marken oder Interessen mit einer oder beiden dieser Optionen aus:

- **Industrie**: Wählen Sie aus der Dropdownliste Ihre Branche aus und treffen Sie dann eine Wahl aus den Top-Marken oder den führenden Interessen für diese Branche.
- **Eigene auswählen**: Geben Sie eine Marke oder ein Interesse ein, die bzw. das für Ihr Unternehmen relevant ist, und wählen Sie dann aus den passenden Vorschlägen aus. Wenn wir keine Marke oder kein Interesse auflisten, nach dem Sie suchen, senden Sie uns Feedback über den Link **Vorschlagen**.

### <a name="review-enrichment-preferences"></a>Anreicherungseinstellungen überprüfen

Überprüfen Sie Ihre Standardeinstellungen für die Anreicherung und aktualisieren Sie sie nach Bedarf.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Screenshot des Fensters „Anreicherungseinstellungen“.":::

### <a name="select-entity-to-enrich"></a>Anzureichernde Entität auswählen

Wählen Sie **Entität anreichern** und wählen Sie den Kundendatensatz, den Sie mit Unternehmensdaten von Microsoft anreichern möchten. Sie können die Kundenentität auswählen, um alle Ihre Kundenprofile anzureichern, oder eine Segmententität auswählen, um nur Kundenprofile anzureichern, die in diesem Segment enthalten sind.

### <a name="map-your-fields"></a>Ihre Felder zuordnen

Ordnen Sie Felder Ihrer einheitlichen Kundenentität zu, um das demografische Segment zu definieren, das das System zur Anreicherung Ihrer Kundendaten verwenden soll. Ordnen Sie Land/Region und mindestens Geburtsdatum oder Geschlechtsattribute zu. Sie müssen außerdem mindestens einen Ort (und ein Bundesland/Kanton) bzw. eine Postleitzahl zuordnen. Wählen Sie **Bearbeiten**, um die Zuordnung der Felder zu definieren und wählen Sie dann **Anwenden**, wenn Sie fertig sind. Wählen Sie **Speichern** aus, um die Feldzuordnung abzuschließen.

Die folgenden Formate und Werte werden unterstützt. Bei Werten wird nicht zwischen Groß- und Kleinschreibung unterschieden:

- **Geburtsdatum**: Wir empfehlen, das Geburtsdatum während der Datenaufnahme in den DateTime-Typ zu konvertieren. Alternativ kann es sich um eine Zeichenfolge handeln im [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) Format JJJJ-MM-TT oder JJJJ-MM-TTTHH: MM: SSZ.
- **Geschlecht**: Männlich, Weiblich, Unbekannt
- **Postleitzahl**: Fünfstellige Postleitzahlen für die USA, Standard-Postleitzahl überall sonst
- **Stadt** : Name der Stadt in Englisch
- **Bundesland/Kanton** : Zwei-Buchstaben-Abkürzung für die USA und Kanada. Zwei oder drei Buchstaben Abkürzung für Australien. Gilt nicht für Frankreich, Deutschland oder Großbritannien.
- **Land/Region**:

  - USA: Vereinigte Staaten von Amerika, USA, USA, USA, Amerika
  - CA: Kanada, CA
  - GB: Vereinigtes Königreich, Großbritannien, Großbritannien, GB, Vereinigtes Königreich Großbritannien und Nordirland, Vereinigtes Königreich Großbritannien
  - AU: Australien, AU, Common Wealth of Australia
  - FR: – Frankreich, FR, Republik Frankreich
  - DE: Deutschland, Deutsch, Deutschland, Allemagne, DE, Bundesrepublik Deutschland, Republik Deutschland

## <a name="review-and-name-the-enrichment"></a>Überprüfen und benennen Sie die Anreicherung

Schließlich können Sie die Informationen überprüfen und einen Namen für die Anreicherung angeben.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Seite zur Überprüfung und Benennung von Interessen.":::

## <a name="refresh-enrichment"></a>Anreicherung aktualisieren

Führen Sie die Anreicherung aus, nachdem Sie Marken, Interessen und die Feldzuordnung für die Demografie konfiguriert haben. Um den Prozess zu starten, wählen Sie **Ausführen** auf der Seite der Marken- oder Interessenkonfiguration. Darüber hinaus können Sie das System die Anreicherung im Rahmen einer geplanten Aktualisierung automatisch ausführen lassen.
Abhängig von der Menge Ihrer Kundendaten kann es einige Minuten dauern, bis ein Anreicherungslauf abgeschlossen ist.

> [!TIP]
> Es gibt [sechs Arten von Status](system.md#status-types) für Aufgaben/Prozesse. Darüber hinaus [hängen die meisten Prozesse von anderen nachfolgenden Prozessen ab](system.md#refresh-policies). Sie können den Status eines Prozesses auswählen, um Details zum Fortschritt des gesamten Auftrags anzuzeigen. Nach der Auswahl von **Siehe Details** für eine der Aufgaben des Auftrags finden Sie zusätzliche Informationen: Verarbeitungszeit, das letzte Verarbeitungsdatum sowie alle mit der Aufgabe verbundenen Fehler und Warnungen.

## <a name="enrichment-results"></a>Anreicherungsergebnisse

Nachdem Sie den Anreicherungsprozess ausgeführt haben, gehen Sie zu **Meine Anreicherungen**, um die Gesamtzahl der angereicherten Kunden und eine Aufschlüsselung der Marken oder Interessen in den angereicherten Kundenprofilen zu überprüfen.

:::image type="content" source="media/my-enrichments.png" alt-text="Vorschau der Ergebnisse nach Ausführung des Anreicherungsprozesses":::

Überprüfen Sie die angereicherten Daten durch Auswahl **Angereicherte Daten anzeigen** in der Grafik. Angereicherte Daten für Marken gehen an die Entität **BrandAffinityFromMicrosoft**. Daten für Interessen sind in der Entität **InterestAffinityFromMicrosoft**. Sie finden diese Entitäten auch in der Gruppe **Anreicherung** unter **Daten** > **Entitäten**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Siehe Anreicherungsdaten auf der Kundenkarte

Marken- und Interessenbeziehungen können auch auf einzelnen Kundenkarten eingesehen werden. Gehen Sie zu **Kunden** und wählen Sie ein Kundenprofil. In der Kundenkarte finden Sie Diagramme für die Marken oder Interessen, für die Personen im demografischen Profil dieses Kunden eine Affinität haben.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kundenkarte mit angereicherten Daten":::

## <a name="next-steps"></a>Nächste Schritte

Bauen Sie auf Ihren angereicherten Kundendaten auf. Erstellen Sie [Segmente](segments.md), [Maße](measures.md), und selbst [Exportdaten](export-destinations.md), um Ihren Kunden personalisierte Erlebnisse zu bieten.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
