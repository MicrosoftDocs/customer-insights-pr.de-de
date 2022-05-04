---
title: Kundenprofile mit Daten von Microsoft anreichern
description: Verwenden Sie proprietäre Daten von Microsoft, um Ihre Kundendaten mit Affinitäten und Share of Voice anzureichern.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 5c016a394fdf485057a190d03bfed9ce5481f435
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646141"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Anreichern von Kundenprofilen mit Affinitäten und Share of Voice (Vorschau)

Verwenden Sie proprietäre Daten von Microsoft, um Ihre Kundendaten mit Markenaffinitäten, Interessenaffinitäten und Share of Voice (SoV) anzureichern. Diese Affinitäten und SoV basieren auf Daten von Personen in ähnlichen Bevölkerungsgruppen wie Ihre Kunden. Diese Informationen helfen Ihnen, Ihre Kunden basierend auf ihren Affinitäten oder SoV zu bestimmten Marken und Interessen besser zu verstehen und zu segmentieren.

Gehen Sie zu **Daten** > **Anreicherung**, um [Anreicherungen zu konfigurieren und anzuzeigen](enrichment-hub.md).

Um Markenaffinitäten und SoV-Anreicherung zu konfigurieren, gehen Sie zur **Erkunden**-Registerkarte und wählen **Meine Daten anreichern** auf der **Marken**-Kachel.

Um Interessenaffinitäten und SoV-Anreicherung zu konfigurieren, gehen Sie zur **Erkunden**-Registerkarte und wählen **Meine Daten anreichern** auf der **Interessen**-Kachel.

   > [!div class="mx-imgBorder"]
   > ![Marken- und Interessenkacheln.](media/BrandsInterest-tile-Hub.png "Marken und Interessenkacheln")

## <a name="how-we-determine-affinities-and-sov"></a>Wie wir Affinitäten und SoV bestimmen

Wir verwenden die Online-Suchdaten von Microsoft, um Affinitäten und SoV für Marken und Interessen in verschiedenen demografischen Segmenten (definiert nach Alter, Geschlecht oder Standort) zu finden. Das Online-Suchvolumen für eine Marke oder ein Interesse bildet die Grundlage für die Bestimmung der Affinität oder SoV. Die beiden bieten jedoch unterschiedliche Perspektiven, um die Kunden zu verstehen.

- Affinität ist ein Vergleich demografischer Segmente. Anhand dieser Informationen können Sie demografische Segmente identifizieren, die im Vergleich zu anderen Segmenten die höchste Affinität zu einer bestimmten Marke oder einem bestimmten Interesse aufweisen.

- Share of Voice ist ein Vergleich zwischen Ihren ausgewählten Marken oder Interessen. Anhand dieser Informationen können Sie ermitteln, welche Marke oder welches Interesse im Vergleich zu anderen von Ihnen ausgewählten Marken oder Interessen den höchsten Share-of-Voice für ein bestimmtes demografisches Segment hat.

## <a name="affinity-level-and-score"></a>Affinitätsstufe und Punktzahl

Für jedes erweiterte Kundenprofil geben wir zwei verwandte Werte an: Affinitätsstufe und Affinitätsbewertung. Mithilfe dieser Werte können Sie bestimmen, wie stark die Affinität für das demografische Segment dieses Profils, für eine Marke oder ein Interesse im Vergleich zu anderen demografischen Segmenten ist.

*Affinitätsstufe* besteht aus vier Ebenen und *Affinitätsbewertung* wird auf einer 100-Punkte-Skala berechnet, die den Affinitätsstufen zugeordnet ist.


|Affinitätsstufe |Affinitätsbewertung  |
|---------|---------|
|Sehr hoch     | 85-100       |
|Hoch     | 70-84        |
|Mittel     | 35-69        |
|Niedrig     | 1-34        |

Abhängig von der Granularität, die Sie zum Messen der Affinität wünschen, können Sie entweder die Affinitätsstufe oder die Punktzahl verwenden. Der Affinitätswert gibt Ihnen eine genauere Kontrolle.

## <a name="share-of-voice-sov"></a>Share of voice (SoV)

Wir berechnen SoV auf einer 100-Punkte-Skala. Der Gesamt-SoV über alle Marken oder Interessen für jedes angereicherte Kundenprofil summiert sich auf 100. Im Gegensatz zu Affinitäten ist SoV relativ zu den von Ihnen ausgewählten Marken und Interessen. Beispielsweise können die SoV-Werte für „Microsoft“ unterschiedlich sein, wenn die ausgewählten Marken („Microsoft“, „GitHub“) gegenüber („Microsoft“, „LinkedIn“) sind.

## <a name="supported-countriesregions"></a>Unterstützte Länder/Regionen

Wir unterstützen derzeit die folgenden Länder-/Regionenoptionen: Australien, Kanada (Englisch), Frankreich, Deutschland, Großbritannien oder USA (Englisch).

Um ein Land oder eine Region auszuwählen, öffnen Sie **Markenanreicherung** oder **Interessenanreicherung** und wählen Sie **Veränderung** neben **Land/Region** aus. In dem Bereich **Länder-/Regionseinstellungen** wählen Sie eine Option und wählen Sie **Anwenden**.

### <a name="implications-related-to-country-selection"></a>Auswirkungen auf die Länderauswahl

- Wenn Sie [Ihre eigenen Marken auswählen](#define-your-brands-or-interests), liefert das System Vorschläge basierend auf dem ausgewählten Land oder der ausgewählten Region.

- Wenn Sie [eine Branche auswählen](#define-your-brands-or-interests), erhalten Sie die relevantesten Marken oder Interessen basierend auf dem ausgewählten Land oder der ausgewählten Region.

- Wenn Sie [Profile anreichern](#refresh-enrichment), reichern wir alle Kundenprofile an, für die wir Daten für die ausgewählten Marken und Interessen erhalten, einschließlich Profile, die sich nicht in dem ausgewählten Land oder der ausgewählten Region befinden. Wenn Sie beispielsweise Deutschland ausgewählt haben, bereichern wir Profile in den USA, wenn Daten für die ausgewählten Marken und Interessen in den USA verfügbar sind.

## <a name="configure-enrichment"></a>Anreicherung konfigurieren

Eine geführte Erfahrung hilft Ihnen bei der Konfiguration der Anreicherungen. 

### <a name="define-your-brands-or-interests"></a>Definieren Sie Ihre Marken oder Interessen

Wählen Sie bis zu fünf Marken oder Interessen mit einer oder beiden dieser Optionen aus:

- **Branche**: Wählen Sie Ihre Branche aus der Dropdown-Liste aus und wählen Sie dann aus den Top-Marken oder -Interessen für diese Branche aus.
- **Eigene auswählen**: Geben Sie eine Marke oder ein Interesse ein, die bzw. das für Ihr Unternehmen relevant ist, und wählen Sie dann aus den passenden Vorschlägen aus. Wenn wir keine Marke oder kein Interesse auflisten, nach dem Sie suchen, senden Sie uns Feedback über den Link **Vorschlagen**.

### <a name="review-enrichment-preferences"></a>Anreicherungseinstellungen überprüfen

Überprüfen Sie Ihre Standardeinstellungen für die Anreicherung und aktualisieren Sie sie nach Bedarf.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Screenshot des Fensters „Anreicherungseinstellungen“.":::

### <a name="select-entity-to-enrich"></a>Anzureichernde Entität auswählen

Wählen Sie **Entität anreichern** und dann das Dataset aus, das Sie mit Daten von Microsoft anreichern möchten. Sie können die Kundenentität auswählen, um alle Ihre Kundenprofile anzureichern, oder eine Segmententität auswählen, um nur Kundenprofile anzureichern, die in diesem Segment enthalten sind.

### <a name="map-your-fields"></a>Ihre Felder zuordnen

Ordnen Sie Felder Ihrer einheitlichen Kundenentität zu, um das demografische Segment zu definieren, das das System zur Anreicherung Ihrer Kundendaten verwenden soll. Ordnen Sie Land / Region und mindestens Geburtsdatum oder Geschlechtsattribute zu. Sie müssen außerdem mindestens einen Ort (und ein Bundesland/Kanton) bzw. eine Postleitzahl zuordnen. Wählen Sie **Bearbeiten**, um die Zuordnung der Felder zu definieren und wählen Sie dann **Anwenden**, wenn Sie fertig sind. Wählen Sie **Speichern** aus, um die Feldzuordnung abzuschließen.

Die folgenden Formate und Werte werden unterstützt (Bei Werten wird nicht zwischen Groß- und Kleinschreibung unterschieden):

- **Geburtsdatum**: Wir empfehlen, das Geburtsdatum während der Datenaufnahme in den DateTime-Typ zu konvertieren. Alternativ kann es eine Zeichenfolge im [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) Format yyyy-MM-dd oder yyyy-MM-ddTHH:mm:ss sein.
- **Geschlecht**: Männlich, weiblich, unbekannt.
- **Postleitzahl**: Fünfstellige Postleitzahl für die USA, Standardpostleitzahl überall sonst.
- **Stadt**: Name der Stadt in Englisch.
- **Bundesland/Kanton** : Zwei-Buchstaben-Abkürzung für die USA und Kanada. Zwei oder drei Buchstaben Abkürzung für Australien. Gilt nicht für Frankreich, Deutschland oder Großbritannien.
- **Land / Region**:

  - USA: Vereinigte Staaten von Amerika, USA, USA, USA, Amerika
  - CA: Kanada, CA
  - GB: Vereinigtes Königreich, Großbritannien, Großbritannien, GB, Vereinigtes Königreich Großbritannien und Nordirland, Vereinigtes Königreich Großbritannien
  - AU: Australien, AU, Commonwealth of Australia
  - FR: – Frankreich, FR, Republik Frankreich
  - DE: Deutschland, Deutsch, Deutschland, Allemagne, DE, Bundesrepublik Deutschland, Republik Deutschland

## <a name="review-and-name-the-enrichment"></a>Überprüfen und benennen Sie die Anreicherung

Schließlich können Sie die Informationen überprüfen und einen Namen für die Anreicherung angeben.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Seite zur Überprüfung und Benennung von Interessen.":::

## <a name="refresh-enrichment"></a>Anreicherung aktualisieren

Führen Sie die Anreicherung aus, nachdem Sie Marken, Interessen und die Feldzuordnung für die Demografie konfiguriert haben. Um den Prozess zu starten, wählen Sie **Ausführen** auf der Seite der Marken- oder Interessenkonfiguration. Darüber hinaus können Sie das System die Anreicherung im Rahmen einer geplanten Aktualisierung automatisch ausführen lassen.

Abhängig von der Menge Ihrer Kundendaten kann es einige Minuten dauern, bis ein Anreicherungslauf abgeschlossen ist.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Anreicherungsergebnisse

Nachdem Sie den Anreicherungsprozess ausgeführt haben, gehen Sie zu **Meine Anreicherungen**, um die Gesamtzahl der angereicherten Kunden und eine Aufschlüsselung der Marken oder Interessen in den angereicherten Kundenprofilen zu überprüfen.

:::image type="content" source="media/my-enrichments.png" alt-text="Vorschau der Ergebnisse nach Ausführung des Anreicherungsprozesses.":::

Sie finden ein Diagramm mit der Anzahl der angereicherten Kundenprofile im Zeitverlauf und Vorschauen der angereicherten Entitäten. Überprüfen Sie die angereicherten Daten, indem Sie **Mehr anzeigen** in den Diagrammen **Affinitätsebene** oder **Share of Voice** auswählen. Angereicherte Daten für Marken gehen an die **BrandAffinityFromMicrosoft**- und **BrandShareOfVoiceFromMicrosoft**-Entitäten. Daten für Interessen befinden sich in denn Entitäten **InterestAffinityFromMicrosoft** und **InterestShareOfVoiceFromMicrosoft**. Sie finden diese Entitäten auch in der Gruppe **Anreicherung** unter **Daten** > **Entitäten**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Siehe Anreicherungsdaten auf der Kundenkarte

Marken- und Interessens-SoV können auch auf einzelnen Kundenkarten eingesehen werden. Gehen Sie zu **Kunden** und wählen Sie ein Kundenprofil. In der Kundenkarte finden Sie Diagramme für die Marken- oder Interessen-SoV zu den Personen im demografischen Profil dieses Kunden.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kundenkarte mit angereicherten Daten.":::

## <a name="next-steps"></a>Nächste Schritte,

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
