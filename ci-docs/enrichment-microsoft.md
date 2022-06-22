---
title: Reichern Sie Kundenprofile mit Marken- und Interessendaten von Microsoft an
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
ms.openlocfilehash: 61262980cafdcd130430e200e466ce7da6cc4d07
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953764"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Anreichern von Kundenprofilen mit Affinitäten und Share of Voice (Vorschau)

Verwenden Sie proprietäre Daten von Microsoft, um Ihre Kundendaten mit Markenaffinitäten, Interessenaffinitäten und Share of Voice (SoV) anzureichern. Diese Affinitäten und SoV basieren auf Daten von Personen in ähnlichen Bevölkerungsgruppen wie Ihre Kunden. Diese Informationen helfen Ihnen, Ihre Kunden basierend auf ihren Affinitäten oder SoV zu bestimmten Marken und Interessen besser zu verstehen und zu segmentieren.

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

## <a name="configure-the-enrichment"></a>Anreicherungskonfiguration

1. Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus.

   - Um Markenaffinitäten und SoV-Anreicherung zu konfigurieren, gehen Sie zur Kachel **Meine Daten anreichern** auf der **Marken**-Kachel.

   - Um Interessenaffinitäten und SoV-Anreicherung zu konfigurieren, gehen Sie zur Kachel **Meine Daten anreichern** auf der **Interessen**-Kachel.

   > [!div class="mx-imgBorder"]
   > ![Marken- und Interessenkacheln.](media/BrandsInterest-tile-Hub.png "Marken und Interessenkacheln")

1. Prüfen Sie die Übersicht und wählen Sie dann **Weiter** aus.

1. Um Ihr Land oder Ihre Region zu ändern, wählen Sie **Ändern** neben **Land/Region** aus. In dem **Länder-/Regionseinstellungen** Bereich, wählen Sie ein [unterstütztes Land/eine Region](#supported-countriesregions) und wählen Sie **Anwenden**.

   > [!NOTE]
   > Wenn Sie Ihre eigenen Marken auswählen, liefert das System Vorschläge basierend auf dem ausgewählten Land oder der ausgewählten Region. Wenn Sie eine Branche auswählen, erhalten Sie die relevantesten Marken oder Interessen basierend auf dem ausgewählten Land oder der ausgewählten Region.

1. Wählen Sie bis zu fünf Marken oder Interessen mit einer oder beiden dieser Optionen aus:

   - **Branche**: Wählen Sie Ihre Branche aus der Dropdown-Liste aus und wählen Sie dann aus den Top-Marken oder -Interessen für diese Branche aus.
   - **Eigene auswählen**: Geben Sie eine Marke oder ein Interesse ein, die bzw. das für Ihr Unternehmen relevant ist, und wählen Sie dann aus den passenden Vorschlägen aus. Wenn wir keine Marke oder kein Interesse auflisten, nach dem Sie suchen, senden Sie uns Feedback über den Link **Vorschlagen**.

1. Wählen Sie **Weiter** und überprüfen Sie Ihre standardmäßigen Anreicherungseinstellungen und aktualisieren Sie sie nach Bedarf.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Screenshot des Fensters „Anreicherungseinstellungen“.":::

1. Wählen Sie **Weiter** aus.

1. Wählen Sie **Kunden Dataset** und wählen Sie das Profil oder Segment aus, das Sie mit Daten von Microsoft anreichern möchten. Die Entität *Kunde* reichert alle Ihre Kundenprofile an, währen ein Segment nur Kundenprofile anreichert, die in diesem Segment enthalten sind.

1. Wählen Sie **Weiter** aus.

1. Ordnen Sie Ihre Felder aus Ihrer einheitlichen Kundenentität den Microsoft-Daten zu.

   > [!NOTE]
   > Es sind mindestens die Attribute Geburtsdatum oder Geschlecht erforderlich. Land/Region und mindestens Stadt (und Staat/Provinz) oder Postleitzahl sind erforderlich. Wir empfehlen, dass das Geburtsdatum während der Datenerfassung in den DateTime-Typ konvertiert wird. Alternativ kann es eine Zeichenfolge im [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) Format yyyy-MM-dd oder yyyy-MM-ddTHH:mm:ss sein.

1. Wählen Sie **Weiter** aus, um die Feldzuordnung abzuschließen.

1. Benennen Sie die Anreicherung. Der **Ausgabeentitätsname** wird automatisch ausgewählt.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Seite zur Überprüfung und Benennung von Interessen.":::

1. Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.

1. Wählen Sie **Ausführen**, um den Anreicherungsprozess zu starten oder zu schließen, um zur Seite **Anreicherung** zurückzukehren.

   Wenn Sie Profile anreichern, reichern wir alle Kundenprofile an, für die wir Daten für die ausgewählten Marken und Interessen erhalten, einschließlich Profile, die sich nicht in dem ausgewählten Land oder der ausgewählten Region befinden. Wenn Sie beispielsweise Deutschland ausgewählt haben, bereichern wir Profile in den USA, wenn Daten für die ausgewählten Marken und Interessen in den USA verfügbar sind.

## <a name="enrichment-results"></a>Anreicherungsergebnisse

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Vorschau der Ergebnisse nach Ausführung des Anreicherungsprozesses.":::

Zu den Ergebnissen gehören **Affinitätsebene** oder **Voice teilen** Diagramme.

Die aus den Anreicherungen entstandenen Entitäten sind in der Gruppe **Anreicherung** unter **Daten** > **Entitäten** aufgeführt. Angereicherte Daten für Marken gehen an die **BrandAffinityFromMicrosoft**- und **BrandShareOfVoiceFromMicrosoft**-Entitäten. Daten für Interessen befinden sich in denn Entitäten **InterestAffinityFromMicrosoft** und **InterestShareOfVoiceFromMicrosoft**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Siehe Anreicherungsdaten auf der Kundenkarte

Marken- und Interessens-SoV können auch auf einzelnen Kundenkarten eingesehen werden. Gehen Sie zu **Kunden** und wählen Sie ein Kundenprofil. In der Kundenkarte finden Sie Diagramme für die Marken- oder Interessen-SoV zu den Personen im demografischen Profil dieses Kunden.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kundenkarte mit angereicherten Daten.":::

## <a name="next-steps"></a>Nächste Schritte,

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
