---
title: Anreicherung der Adressverbesserung
description: Bereichern und normalisieren Sie Adressinformationen von Kundenprofilen mit Microsoft-Modellen.
ms.date: 07/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: f56be1f4ecdac124ed76a0fb0eb1e313099248bf
ms.sourcegitcommit: 1565f4f7b4e131ede6ae089c5d21a79b02bba645
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2021
ms.locfileid: "7643395"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Anreicherung von Kundenprofilen mit erweiterten Adressen

Adressen in Ihren Daten können unstrukturiert, unvollständig oder falsch sein. Verwenden Sie die Modelle von Microsoft, um Ihre Adressen im [Common Data Model-Format](/common-data-model/schema/core/applicationcommon/address) für bessere Genauigkeit und Einsichten zu normalisieren und anzureichern.

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

Das Modell verwendet auf maschinellem Lernen basierende Techniken, um Adressen zu verbessern. Wir wenden zwar einen hohen Konfidenzschwellenwert an, wenn das Modell einen Eingabewert ändert, wie bei jedem auf maschinellem Lernen basierenden Modell, aber eine 100-prozentige Genauigkeit kann nicht garantiert werden.

## <a name="supported-countries-or-regions"></a>Unterstützte Länder oder Regionen

Wir unterstützen derzeit die Anreicherung von Adressen in diesen Ländern oder Regionen: 

- Australien
- Kanada
- Frankreich
- Deutschland
- Italien
- Japan
- Großbritannien
- Vereinigte Staaten

Adressen müssen einen Wert für ein Land / eine Region enthalten. Wir verarbeiten keine Adressen für Länder oder Regionen, die nicht unterstützt werden, und Adressen, für die kein Land oder keine Region angegeben ist.

## <a name="configure-the-enrichment"></a>Anreicherungskonfiguration

1. Gehen Sie zu **Daten** > **Anreicherung**.

1. Wählen Sie **Meine Daten anreichern** auf der Kachel **Erweiterte Adressen** aus.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Screenshot der Kachel Erweiterte Adressen.":::

1. Wählen Sie **Kunden-Dataset** und wählen Sie die Entität mit den Adressen aus, die Sie anreichern möchten. Sie können die Entität *Kunde* auswählen, um Adressen in all Ihren Kundenprofilen anzureichern, oder wählen Sie eine Segmententität aus, um Adressen nur in Kundenprofilen anzureichern, die in diesem Segment enthalten sind.

1. Wählen Sie aus, wie Adressen in Ihrem Datenset formatiert werden. Wählen Sie **Einzelattributadresse** aus, wenn Adressen in Ihren Daten ein einzelnes Feld verwenden. Wählen Sie **Mehrattributadresse** aus, wenn Adressen in Ihren Daten mehr als ein einzelnes Feld verwenden.

   > [!NOTE]
   > Das Land / die Region ist sowohl in Einzelattribut- als auch in Mehrfachattributadressen obligatorisch. Adressen, die keine gültigen oder unterstützten Länder-/Regionswerte enthalten, werden nicht angereichert.

1.  Ordnen Sie die Adressfelder Ihrer einheitlichen Kundenentität zu.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Erweiterte Adressfeld-Zuordnungsseite.":::

1. Wählen Sie **Weiter** aus, um die Feldzuordnung abzuschließen.

1. Geben Sie einen Namen für die Anreicherung und einen Namen für die Ausgabeentität an.

1. Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.

## <a name="enrichment-results"></a>Anreicherungsergebnisse

Wählen Sie **Ausführen** aus der Befehlsleiste aus, um den Anreicherungsprozess zu starten. Sie können das System die Anreicherung auch automatisch als Teil von einer [geplante Aktualisierung](system.md#schedule-tab) ausführen lassen. Die Bearbeitungszeit hängt von der Größe Ihrer Kundendaten ab.

Nach Abschluss des Anreicherungsprozesses können Sie die neu angereicherten Kundenprofildaten unter **Meine Anreicherungen** überprüfen. Außerdem finden Sie den Zeitpunkt des letzten Updates und die Anzahl der angereicherten Profile.

Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.

## <a name="next-steps"></a>Nächste Schritte,

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
