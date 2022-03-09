---
title: Verbesserung von Unternehmensdaten
description: Verwenden Sie Modelle von Microsoft, um Unternehmensdaten anzureichern und zu normalisieren.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7a576621c71b925bd1563827aca10cad4ef9b4eb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229402"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Anreicherung von Unternehmensprofilen mit verbesserten Unternehmensdaten

Verwenden Sie Microsofts Modelle und zusammengestellte Unternehmensdaten, um Ihre Unternehmensprofile zu korrigieren, zu ergänzen und zu standardisieren. Wir werden das [Common Data Model-Format](/common-data-model/schema/core/applicationcommon/account) verwenden, um eine bessere Genauigkeit und bessere Einblicke zu erzielen.

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

Bei den erweiterten Daten gibt es einige Einschränkungen. Die Elemente in der Liste unten werden vom Modell nicht unterstützt.

1.  Bestätigung der Identität des Unternehmens. Wir überprüfen nicht, ob es sich bei der Eingabe um eine vorhandene Organisation handelt oder ob eine Firma die Ausgabe als Standardnamen verwendet.
2.  Umfassende Abdeckung von Unternehmen weltweit. Die von Microsoft zusammengestellten Unternehmensdaten haben eine globale Abdeckung, bieten jedoch die meisten Abdeckungen in Australien, Kanada, dem Vereinigten Königreich und den Vereinigten Staaten.
3.  Standardisieren Sie Firmenadressen weltweit. Wir unterstützen derzeit die Standardisierung von Adressen in diesen Ländern oder Regionen: Australien, Kanada, Frankreich, Deutschland, Italien, Japan, Vereinigtes Königreich und USA.
4.  Garantie für Korrektheit oder Aktualität der Daten. Da sich Unternehmensinformationen häufig ändern, können wir nicht garantieren, dass die bereitgestellten erweiterten Unternehmensdaten immer genau oder aktuell sind.

## <a name="configure-the-enrichment"></a>Anreicherungskonfiguration

1. Gehen Sie zu **Daten** > **Anreicherung**.

1. Wählen Sie **Meine Daten anreichern** auf der Kachel **Erweiterte Firmendaten** aus.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Anreicherungskachel im Anreicherungshub für Unternehmensdaten.":::

1. Wählen Sie **Kunden-Dataset** und wählen Sie die Entität mit den Adressen aus, die Sie anreichern möchten. Sie können die Entität *Kunde* auswählen, um Adressen in all Ihren Kundenprofilen anzureichern, oder wählen Sie eine Segmententität aus, um Adressen nur in Kundenprofilen anzureichern, die in diesem Segment enthalten sind.

1. Wählen Sie aus, welche Art von Feldern aus Ihren Unternehmensprofilen für den Abgleich mit den von Microsoft zusammengestellten Unternehmensdaten verwendet werden sollen. Diese Auswahl wirkt sich auf die Zuordnungsfelder aus, auf die Sie im nächsten Schritt zugreifen können.

1.  Ordnen Sie die Unternehmensfelder Ihrer einheitlichen Kundenentität zu. Je mehr Schlüsselkennungen und Felder Sie zuordnen, desto höher ist die Wahrscheinlichkeit einer höheren Übereinstimmungsrate.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Datenzuordnungsschritt bei der Konfiguration einer Unternehmensanreicherung.":::

1. Wählen Sie **Weiter** aus, um die Feldzuordnung abzuschließen.

1. Geben Sie einen Namen für die Anreicherung und einen Namen für die Ausgabeentität an.

1. Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.

## <a name="enrichment-results"></a>Anreicherungsergebnisse

Wählen Sie **Ausführen** aus der Befehlsleiste aus, um den Anreicherungsprozess zu starten. Sie können das System die Anreicherung auch automatisch als Teil von einer [geplante Aktualisierung](system.md#schedule-tab) ausführen lassen. Die Bearbeitungszeit hängt von der Größe Ihrer Kundendaten ab.

Nach Abschluss des Anreicherungsprozesses können Sie die neu angereicherten Kundenprofildaten unter **Meine Anreicherungen** überprüfen. Außerdem finden Sie den Zeitpunkt des letzten Updates und die Anzahl der angereicherten Profile.

Sie können ein Beispiel der angereicherten Daten in der Kachel **Vorschau der angereicherten Kunden** sehen. Wählen Sie **Mehr anzeigen** und die **Daten**-Registerkarte aus, um auf eine detaillierte Ansicht jedes angereicherten Profils zuzugreifen.

### <a name="overview-card"></a>Übersichtskarte

Die Übersichtskarte zeigt Details zur Deckung der Anreicherung. 

* **Unternehmen verarbeitet und geändert**: Die Anzahl der Kundenunternehmensprofile, die erfolgreich angereichert wurden.

* **Unternehmen verarbeitet und nicht geändert**: Die Anzahl der Kundenunternehmensprofile, die erfolgreich erkannt aber nicht geändert wurden. Dies geschieht typischerweise, wenn die Eingabedaten gültig sind und durch die Anreicherung nicht verbessert werden können.

* **Unternehmen nicht verarbeitet und nicht geändert**: Die Anzahl der Kundenunternehmensprofile, die nicht erkannt wurden. Dies geschieht üblicherweise bei Eingabedaten, die ungültig sind oder von der Anreicherung nicht unterstützt werden.

## <a name="next-steps"></a>Nächste Schritte

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
