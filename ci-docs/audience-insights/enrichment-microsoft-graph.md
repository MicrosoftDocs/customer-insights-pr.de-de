---
title: Anreichern von Kundenprofilen mit Microsoft Graph
description: Verwenden Sie proprietäre Daten aus Microsoft Graph, um Ihre Kundendaten mit Marken- und Interessenbeziehungen anzureichern.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405762"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Anreichern von Kundenprofilen mit Marken- und Interessenbeziehungen (Vorschau)

Verwenden Sie proprietäre Daten aus Microsoft Graph, um Ihre Kundendaten mit Marken- und Interessenbeziehungen anzureichern. Diese Affinitäten werden basierend auf Daten von Personen mit ähnlichen demografischen Merkmalen wie Ihre Kunden ermittelt. Diese Informationen helfen Ihnen dabei, Ihre Kunden anhand ihrer Affinität zu bestimmten Marken und Interessen besser zu verstehen und zu segmentieren.

Gehen Sie in Zielgruppen-Insights auf **Daten** > **Anreicherung**, um [Anreicherungen zu konfigurieren und anzuzeigen](enrichment-hub.md).

Um die Anreicherung von Markenaffinitäten zu konfigurieren, gehen Sie zur Registerkarte **Entdecken** und wählen Sie **Anreicherung meiner Daten** auf der Kachel **Marken**.

Um die Anreicherung von Interessenaffinitäten zu konfigurieren, gehen Sie zum Register **Entdecken** und wählen Sie **Anreicherung meiner Daten** auf der Kachel **Interessen**.

   > [!div class="mx-imgBorder"]
   > ![Marken und Interessenkacheln](media/BrandsInterest-tile-Hub.png "Marken und Interessenkacheln")

## <a name="about-microsoft-graph"></a>Über Microsoft Graph

Wir verwenden Onlinesuchdaten aus Microsoft Graph, um Affinitäten für Marken und Interessen in verschiedenen demografischen Segmenten (definiert nach Alter, Geschlecht oder Standort) zu finden. Das Onlinesuchvolumen für eine Marke oder ein Interesse bestimmt, wie viel Affinität ein demografisches Segment im Vergleich zu anderen Segmenten zu dieser Marke oder diesem Interesse hat.

[Weitere Informationen zu Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-score-and-confidence"></a>Affinitätswert und Selbstvertrauen

Die **Affinitätsbewertung** wird auf einer 100-Punkte-Skala berechnet, wobei 100 das Segment darstellt, das die höchste Affinität für eine Marke oder ein Interesse aufweist.

Das **Affinitätsvertrauen** wird auch auf einer 100-Punkte-Skala berechnet. Es zeigt das Vertrauensniveau des Systems an, dass ein Segment eine Affinität zur Marke oder zum Interesse hat. Das Konfidenzniveau basiert auf der Segmentgröße und der Segmentgranularität. Die Segmentgröße wird durch die Datenmenge bestimmt, die wir für ein bestimmtes Segment haben. Die Segmentgranularität wird dadurch bestimmt, wie viele Attribute (Alter, Geschlecht, Standort) in einem Profil verfügbar sind.

Wir normalisieren die Ergebnisse für Ihr DataSet nicht. Infolgedessen werden möglicherweise nicht alle möglichen Affinitätswertwerte für Ihr DataSet angezeigt. Beispielsweise enthalten Ihre Daten möglicherweise kein angereichertes Kundenprofil mit einem Affinitätswert von 100. Dies ist möglich, wenn im demografischen Segment keine Kunden existieren, die für eine bestimmte Marke oder ein bestimmtes Interesse 100 Punkte erzielt haben.

> [!TIP]
> Wenn [Segmente erstellen](segments.md) Affinitätswerte verwendet, überprüfen Sie die Verteilung der Affinitätswerte für Ihr DataSet, bevor Sie sich für die entsprechenden Bewertungsschwellen entscheiden. Beispielsweise kann ein Affinitätswert von 10 in einem DataSet als signifikant angesehen werden, der einen höchsten Affinitätswert von nur 25 für eine bestimmte Marke oder ein bestimmtes Interesse aufweist.

## <a name="supported-countriesregions"></a>Unterstützte Länder/Regionen

Wir unterstützen derzeit die folgenden Länder-/Regionenoptionen: Australien, Kanada (Englisch), Frankreich, Deutschland, Großbritannien oder USA (Englisch).

Um ein Land auszuwählen, öffnen Sie die **Markenanreicherung** oder **Zinsanreicherung** und wählen Sie **Veränderung** neben dem **Land/Region**. In dem Bereich **Länder-/Regionseinstellungen** wählen Sie eine Option und wählen Sie **Anwenden**.

### <a name="implications-related-to-country-selection"></a>Auswirkungen auf die Länderauswahl

- Wenn Sie [Ihre eigenen Marken auswählen](#define-your-brands-or-interests) werden wir Vorschläge basierend auf dem ausgewählten Land/der ausgewählten Region machen.

- Wenn Sie [eine Branche auswählen](#define-your-brands-or-interests), identifizieren wir die relevantesten Marken oder Interessen basierend auf dem ausgewählten Land/der ausgewählten Region.

- Wenn [Ihre Felder zugeordnet werden](#map-your-fields), wenn das Feld Land/Region nicht zugeordnet ist, verwenden wir Microsoft Graph-Daten aus dem ausgewählten Land/der ausgewählten Region, um Ihre Kundenprofile zu erweitern. Wir werden diese Auswahl auch verwenden, um Ihre Kundenprofile zu bereichern, für die keine Länder-/Regionsdaten verfügbar sind.

- Wann [Profile angereichert werden](#refresh-enrichment), reichern wir alle Kundenprofile an, für die Microsoft Graph-Daten für die ausgewählten Marken und Interessen verfügbar sind, einschließlich Profile, die sich nicht in dem ausgewählten Land/der ausgewählten Region befinden. Wenn Sie beispielsweise Deutschland ausgewählt haben, bereichern wir Profile in den USA, wenn Microsoft Graph-Daten für die ausgewählten Marken und Interessen in den USA verfügbar sind.

## <a name="configure-enrichment"></a>Anreicherung konfigurieren

Die Konfiguration der Anreicherung von Marken oder Interessen besteht aus zwei Schritten:

### <a name="define-your-brands-or-interests"></a>Definieren Sie Ihre Marken oder Interessen

Wählen Sie eine der folgenden Optionen aus:

- **Industrie**: Das System identifiziert die für Ihre Branche relevanten Top-Marken oder Interessen und reichert Ihre Kundendaten damit an.
- **Eigene wählen**: Wählen Sie bis zu fünf Elemente aus der Liste der Marken oder Interessen aus, die für Ihr Unternehmen am relevantesten sind.

Um eine Marke oder ein Interesse hinzuzufügen, geben Sie es in den Eingabebereich ein, um Vorschläge basierend auf übereinstimmenden Begriffen zu erhalten. Wenn wir keine Marke oder kein Interesse auflisten, nach dem Sie suchen, senden Sie uns Feedback über den Link **Vorschlagen**.

### <a name="map-your-fields"></a>Ihre Felder zuordnen

Ordnen Sie Felder Ihrer einheitlichen Kundenentität zu mindestens zwei Attributen, um das demografische Segment zu definieren, das wir zur Anreicherung Ihrer Kundendaten verwenden sollen. Wählen Sie **Bearbeiten**, um die Zuordnung der Felder zu definieren und wählen Sie dann **Anwenden**, wenn Sie fertig sind. Wählen Sie **Speichern** aus, um die Feldzuordnung abzuschließen.

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
