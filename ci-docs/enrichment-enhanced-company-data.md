---
title: Anreichern von Unternehmensprofilen mit verbesserten Unternehmensdaten
description: Verwenden Sie Modelle von Microsoft, um Unternehmensdaten anzureichern und zu normalisieren.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 131ef3d1e123628779609ddec368cfef8f4d607e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054247"
---
# <a name="enrich-company-profiles-with-enhanced-company-data"></a>Anreichern von Unternehmensprofilen mit verbesserten Unternehmensdaten

Verwenden Sie Microsofts Modelle und zusammengestellte Unternehmensdaten, um Ihre Unternehmensprofile zu korrigieren, zu ergänzen und zu standardisieren. Wir werden das [Common Data Model-Format](/common-data-model/schema/core/applicationcommon/account) verwenden, um eine bessere Genauigkeit und bessere Einblicke zu erzielen.

Sie können auch [Unternehmensdaten auf Datenquellen anreichern](data-sources-enrichment.md), um die Übereinstimmungsgenauigkeit im Datenvereinheitlichungsprozess zu verbessern.

Für börsennotierte Firmen in den Vereinigten Staaten sind Informationen wie Umsatz, Börsenkürzel, Branche und mehr verfügbar.  

## <a name="how-we-enhance-company-data"></a>Verbessern von Unternehmensdaten

Unser Modell durchläuft einen zweistufigen Prozess, um ein Unternehmensprofil zu verbessern. Zunächst wird der Unternehmensname normalisiert. Zum Beispiel wird *Microsft Corp* korrigiert und auf *Microsoft Corporation* standardisiert. Es versucht, eine Übereinstimmung in den zusammengestellten Unternehmensdaten von Microsoft zu finden. Wird eine Übereinstimmung gefunden, reichern wir das Unternehmensprofil mit Informationen aus unseren zusammengestellten Unternehmensdaten an, einschließlich des Unternehmensnamens.

### <a name="example"></a>Beispiel

Ihre Unternehmensinformationen folgen möglicherweise keinem standardisierten Format und enthalten Rechtschreibfehler. Das Modell versucht, diese Probleme zu beheben und konsistente Informationen zu erstellen.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Einschränkungen

Das Modell führt folgende Aktionen nicht aus:

- Bestätigung der Identität des Unternehmens. Wir überprüfen nicht, ob es sich bei der Eingabe um eine vorhandene Organisation handelt oder ob eine Firma die Ausgabe als Standardnamen verwendet.
- Umfassende Abdeckung von Unternehmen weltweit. Die von Microsoft zusammengestellten Unternehmensdaten haben eine globale Abdeckung, bieten jedoch die meisten Abdeckungen in Australien, Kanada, dem Vereinigten Königreich und den Vereinigten Staaten.
- Standardisieren Sie Firmenadressen weltweit. Wir unterstützen derzeit die Standardisierung von Adressen in diesen Ländern oder Regionen: Australien, Kanada, Frankreich, Deutschland, Italien, Japan, Vereinigtes Königreich und USA.
- Garantie für Korrektheit oder Aktualität der Daten. Da sich Unternehmensinformationen häufig ändern, können wir nicht garantieren, dass die bereitgestellten erweiterten Unternehmensdaten immer genau oder aktuell sind.

## <a name="configure-the-enrichment"></a>Anreicherungskonfiguration

1. Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus.

1. Wählen Sie **Meine Daten anreichern** auf der Kachel **Erweiterte Firmendaten** aus.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Anreicherungskachel im Anreicherungshub für Unternehmensdaten.":::

1. Prüfen Sie die Übersicht und wählen Sie dann **Weiter** aus.

1. Wählen Sie das **Kunden Dataset** und wählen Sie das Profil oder Segment aus, das Sie anreichern möchten. Die Entität *Kunde* reichert alle Ihre Kundenprofile an, währen ein Segment nur Kundenprofile anreichert, die in diesem Segment enthalten sind.

1. Wählen Sie aus, welche Art von Feldern aus Ihren Unternehmensprofilen für den Abgleich mit den von Microsoft zusammengestellten Unternehmensdaten verwendet werden sollen. Diese Auswahl wirkt sich auf die Zuordnungsfelder aus, auf die Sie im nächsten Schritt zugreifen können.

1. Wählen Sie **Weiter** aus.

1. Ordnen Sie Ihre Firmenfelder den Firmendaten von Microsoft zu. Fügen Sie für eine höhere Übereinstimmungsgenauigkeit weitere Felder hinzu.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Datenzuordnungsschritt bei der Konfiguration einer Unternehmensanreicherung.":::

1. Wählen Sie **Weiter** aus, um die Feldzuordnung abzuschließen.

1. Geben Sie einen **Namen** für die Anreicherung und einen Namen für die **Ausgabeentität** an.

1. Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.

1. Wählen Sie **Ausführen**, um den Anreicherungsprozess zu starten oder zu schließen, um zur Seite **Anreicherung** zurückzukehren.

## <a name="view-enrichment-results"></a>Anreicherungsergebnisse anzeigen

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Übersichtskarte

Die Kachel **Kundenänderungen-Übersicht** zeigt Details zur Deckung der Anreicherung

- **Unternehmen verarbeitet und geändert**: Die Anzahl der Kundenunternehmensprofile, die erfolgreich angereichert wurden.
- **Unternehmen verarbeitet und nicht geändert**: Die Anzahl der Kundenunternehmensprofile, die erfolgreich erkannt aber nicht geändert wurden. Dies geschieht typischerweise, wenn die Eingabedaten gültig sind und durch die Anreicherung nicht verbessert werden können.
- **Unternehmen nicht verarbeitet und nicht geändert**: Die Anzahl der Kundenunternehmensprofile, die nicht erkannt wurden. Dies geschieht üblicherweise bei Eingabedaten, die ungültig sind oder von der Anreicherung nicht unterstützt werden.

## <a name="next-steps"></a>Nächste Schritte

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
