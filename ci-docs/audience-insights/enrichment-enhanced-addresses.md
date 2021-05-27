---
title: Anreicherung der Adressverbesserung
description: Bereichern und normalisieren Sie Adressinformationen von Kundenprofilen mit Microsoft-Modellen.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965577"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Anreicherung von Kundenprofilen mit erweiterten Adressen

Adressen in Ihren Daten können unstrukturiert, unvollständig oder falsch sein. Verwenden Sie die Modelle von Microsoft, um Ihre Adressen im [Common Data Model-Format](/common-data-model/schema/core/applicationcommon/address) für bessere Genauigkeit und Einsichten zu normalisieren und anzureichern.

## <a name="how-we-enhance-addresses"></a>Wie wir Adressen verbessern

Unser Modell durchläuft einen zweistufigen Prozess, um eine Adresse zu verbessern. Zunächst wird die Adresse analysiert, um die Komponenten zu identifizieren und in ein strukturiertes Format gebracht. Anschließend verwenden wir künstliche Intelligenz, um die Werte in der Adresse zu korrigieren, zu vervollständigen und zu standardisieren.

### <a name="example"></a>Beispiel

Adressinformationen haben möglicherweise ein nicht standardmäßiges Format und enthalten Rechtschreibfehler. Das Modell kann diese Probleme beheben und konsistente Adressen in einheitlichen Kundenprofilen erstellen.

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

Erweiterte Adressen funktionieren nur mit den Werten, die bereits in Ihren aufgenommenen Adressdaten vorhanden sind. Das Modell wird nicht: 

1. Überprüfen, ob die Adresse eine gültige Adresse ist.
2. Überprüfen, ob einer der Werte wie Postleitzahlen oder Straßennamen gültig ist.
3. Werte ändern, die nicht erkannt werden.

Das Modell verwendet auf maschinellem Lernen basierende Techniken, um Adressen zu verbessern. Während wir wie bei jedem ML-basierten Modell einen hohen Konfidenzschwellenwert anwenden, wenn das Modell einen Eingabewert ändert, ist eine 100% ige Genauigkeit nicht garantiert.

## <a name="supported-countries-or-regions"></a>Unterstützte Länder oder Regionen

Wir unterstützen derzeit bereichernde Adressen in diesen Ländern oder Regionen: 

- Australien
- Kanada
- Großbritannien
- Vereinigte Staaten

Adressen müssen einen Länder-/Regionswert enthalten. Wir verarbeiten keine Adressen für Länder oder Regionen, die nicht unterstützt werden, und Adressen, für die kein Land oder keine Region angegeben ist.

## <a name="configure-the-enrichment"></a>Anreicherungskonfiguration

1. Gehen Sie zu **Daten** > **Anreicherung**.

1. Wählen Sie **Meine Daten anreichern** auf der Kachel **Erweiterte Adressen** aus.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Screenshot der Kachel Erweiterte Adressen.":::

1. Wählen Sie **Kunden-Dataset** und wählen Sie die Entität mit den Adressen aus, die Sie anreichern möchten. Sie können die Entität *Kunde* auswählen, um Adressen in all Ihren Kundenprofilen anzureichern, oder wählen Sie eine Segmententität aus, um Adressen nur in Kundenprofilen anzureichern, die in diesem Segment enthalten sind.

1. Wählen Sie aus, wie Adressen in Ihrem Datenset formatiert werden. Wählen Sie **Einzelattributadresse** aus, wenn Adressen in Ihren Daten ein einzelnes Feld verwenden. Wählen Sie **Mehrattributadresse** aus, wenn Adressen in Ihren Daten mehr als ein einzelnes Feld verwenden.

   > [!NOTE]
   > Land/Region ist sowohl für Adressen mit einem als auch mit mehreren Attributen obligatorisch. Adressen, die keine gültigen oder unterstützten Länder-/Regionswerte enthalten, werden nicht angereichert

1.  Ordnen Sie die Adressfelder Ihrer einheitlichen Kundenentität zu.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Erweiterte Adressfeld-Zuordnungsseite.":::

1. Wählen Sie **Weiter** aus, um die Feldzuordnung abzuschließen.

1. Geben Sie einen Namen für die Anreicherung und einen Namen für die Ausgabeentität an.

1. Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.

## <a name="enrichment-results"></a>Anreicherungsergebnisse

Wählen Sie **Ausführen** aus der Befehlsleiste aus, um den Anreicherungsprozess zu starten. Sie können das System die Anreicherung auch automatisch als Teil von einer [geplante Aktualisierung](system.md#schedule-tab) ausführen lassen. Die Bearbeitungszeit hängt von der Größe Ihrer Kundendaten ab.

Nach Abschluss des Anreicherungsprozesses können Sie die neu angereicherten Kundenprofildaten unter **Meine Anreicherungen** überprüfen. Außerdem finden Sie den Zeitpunkt des letzten Updates und die Anzahl der angereicherten Profile.

Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.

## <a name="next-steps"></a>Nächste Schritte

Bauen Sie auf Ihren angereicherten Kundendaten auf. Erstellen Sie [Segmente](segments.md), [Maße](measures.md), und selbst [Exportdaten](export-destinations.md), um Ihren Kunden personalisierte Erlebnisse zu bieten.

[!INCLUDE[footer-include](../includes/footer-banner.md)]