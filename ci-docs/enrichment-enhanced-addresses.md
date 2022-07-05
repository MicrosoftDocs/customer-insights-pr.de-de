---
title: Kundenprofile mit erweiterten Adressen anreichern (enthält Video)
description: Bereichern und normalisieren Sie Adressinformationen von Kundenprofilen mit Microsoft-Modellen.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 01f1c917c75e932cc69f4c7251e57524fc859dce
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080971"
---
# <a name="enrich-customer-profiles-with-enhanced-addresses"></a>Kundenprofile mit erweiterten Adressen anreichern

Adressen in Ihren Daten können unstrukturiert, unvollständig oder falsch sein. Verwenden Sie die Modelle von Microsoft, um Ihre Adressen im [Common Data Model-Format](/common-data-model/schema/core/applicationcommon/address) für bessere Genauigkeit und Einsichten zu normalisieren und anzureichern.

Sie können auch [Adressen auf Datenquellen anreichern](data-sources-enrichment.md), um die Übereinstimmungsgenauigkeit im Datenvereinheitlichungsprozess zu verbessern. 

## <a name="how-we-enhance-addresses"></a>Wie wir Adressen verbessern

Unser Modell durchläuft einen zweistufigen Prozess, um eine Adresse zu verbessern. Zuerst analysiert es die Adresse, um ihre Komponenten zu identifizieren, und bringt sie in ein strukturiertes Format. Dann verwenden wir KI, um die Werte in der Adresse zu korrigieren, zu vervollständigen und zu standardisieren.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Beispiel

Adressinformationen können in einem nicht standardmäßigen Format vorliegen und Rechtschreibfehler enthalten. Das Modell kann diese Probleme beheben und konsistente Adressen in einheitlichen Kundenprofilen erstellen.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Einschränkungen

Erweiterte Adressen funktionieren nur mit den Werten, die bereits in Ihren aufgenommenen Adressdaten vorhanden sind. Das Modell führt folgende Aktionen nicht aus:

1. Überprüfen, ob die Adresse eine gültige Adresse ist
2. Überprüfen, ob Werte wie Postleitzahlen oder Straßennamen gültig sind
3. Werte ändern, die nicht erkennt wurden

Das Modell verwendet auf maschinellem Lernen basierende Techniken, um Adressen zu verbessern. Wie bei jedem auf maschinellem Lernen basierenden Modell kann eine 100-prozentige Genauigkeit nicht garantiert werden.

## <a name="supported-countries-or-regions"></a>Unterstützte Länder oder Regionen

Wir unterstützen derzeit die Anreicherung von Adressen in diesen Ländern oder Regionen:

- Australien
- Kanada
- Frankreich
- Deutschland
- Italien
- Japan
- Großbritannien
- USA

## <a name="configure-the-enrichment"></a>Anreicherungskonfiguration

1. Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus.

1. Wählen Sie **Meine Daten anreichern** auf der Kachel **Erweiterte Adressen** aus.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Screenshot der Kachel Erweiterte Adressen.":::

1. Prüfen Sie die Übersicht und wählen Sie dann **Weiter** aus.

1. Wählen Sie das **Kunden Dataset** und wählen Sie das Profil oder Segment aus, das Sie anreichern möchten. Die Entität *Kunde* reichert alle Ihre Kundenprofile an, währen ein Segment nur Kundenprofile anreichert, die in diesem Segment enthalten sind.

1. Wählen Sie aus, wie Adressen in Ihrem Datenset formatiert werden. Wählen Sie **Einzelattributadresse** aus, wenn Adressen in Ihren Daten ein einzelnes Feld verwenden. Wählen Sie **Mehrattributadresse** aus, wenn Adressen in Ihren Daten mehr als ein einzelnes Feld verwenden.

1. Wählen Sie **Weiter** und ordnen Sie die Adressfelder Ihrer einheitlichen Kundenentität zu.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Erweiterte Adressfeld-Zuordnungsseite.":::

   > [!NOTE]
   > Das Land / die Region ist sowohl in Einzelattribut- als auch in Mehrfachattributadressen obligatorisch. Adressen, die keine gültigen oder unterstützten Länder-/Regionswerte enthalten, werden nicht angereichert.

1. Wählen Sie **Weiter** aus, um die Feldzuordnung abzuschließen.

1. Geben Sie einen **Namen** für die Anreicherung und einen Namen für die **Ausgabeentität** an.

1. Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.

## <a name="view-enrichment-results"></a>Anreicherungsergebnisse anzeigen

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Die **Anzahl der Kunden, angereichert nach Feld** stellt Detailinformationen zur Abdeckung jedes angereicherten Felds dar.

### <a name="overview-card"></a>Übersichtskarte

Die Karte **Kundenänderungen-Übersicht** zeigt Details zur Deckung der Anreicherung:

- **Adressen verarbeitet und geändert**: Die Anzahl der Kundenprofile mit Adressen, die erfolgreich angereichert wurden.
- **Adressen verarbeitet und nicht geändert**: Die Anzahl der Kundenprofile mit Adressen, die erfolgreich erkannt aber nicht geändert wurden. Dies geschieht typischerweise, wenn die Eingabedaten gültig sind und durch die Anreicherung nicht verbessert werden können.
- **Adressen nicht verarbeitet und nicht geändert**: Die Anzahl der Kundenprofile mit Adressen, die nicht erkannt wurden. Normalerweise für Eingabedaten, die ungültig sind oder von der Anreicherung nicht unterstützt werden.

## <a name="next-steps"></a>Nächste Schritte,

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
