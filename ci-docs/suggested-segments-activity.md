---
title: Vorgeschlagene Segmente basierend auf Aktivität (Vorschauversion)
description: Mit Maschinellem Lernen können Sie anhand der Kundenaktivität neue und interessante Segmente finden.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170588"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Vorgeschlagene Segmente basierend auf Aktivität (Vorschauversion)

Entdecken Sie interessante Segmente Ihrer Kunden anhand von Kundenaktivitätsdaten, die in Customer Insights erfasst werden. Beispiele für Aktivitätsdaten sind Transaktionen, Support-Anrufdauer, Käufe oder Rückgaben. Um Segmente vorzuschlagen, werden Aktivitätsdaten auf Aktualität, Häufigkeit und Geldwert (oder Dauer) analysiert. Alternativ können Sie [vorgeschlagene Segmente generieren, um eine Kennzahl zu verbessern oder besser zu verstehen, was ein Attribut beeinflusst](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Registerkarte Vorgeschlagene Segmente mit Segmentvorschlägen für aktivitätsbasierte und attributbasierte Segmente.":::

## <a name="categorize-customers-by-activity"></a>Kategorisieren Sie Kunden nach Aktivität

Mit [Aktivitätsdaten](activities.md) in Customer Insights können wir Vorschläge generieren, die Kundengruppen repräsentieren:

- aktivsten Kunden 
- Kunden, die die meisten Einkäufe getätigt haben 
- Kunden, die den größten Umsatz erzielt haben 
- Kunden, die in letzter Zeit nicht aktiv waren 
- Kunden, die häufig mit Ihrem Unternehmen interagieren  

Wenn Sie ein Einzelhandelsgeschäft haben, können Sie herausfinden, welche Kunden die meisten Einnahmen erzielen, und sie mit einem Gutschein belohnen. Oder Sie können gelegentliche Kunden identifizieren und ihnen anbieten, an einem Prämienprogramm teilzunehmen, damit sie Ihr Unternehmen häufiger besuchen.
Wenn Sie öffentliche Gesundheitsversorgung anbieten und Ihr Ziel darin besteht, die Kosten für einzelne Patienten zu minimieren, könnten Sie versuchen, wiederkehrende Besuche zu reduzieren, indem Sie die bestmögliche Versorgung bei so wenig Besuchen wie möglich bieten. In diesem Fall ist es Ihr Ziel, die Besuchshäufigkeit niedrig zu halten und die wiederkehrenden Kosten für die Patienten zu minimieren. Oder Sie können Segmente von Patienten identifizieren, die häufige Termine und hohe wiederkehrende Kosten haben, und diese Fälle analysieren, um die Behandlung des Patienten zu verbessern.

## <a name="required-data"></a>Erforderliche Daten

Vorschläge werden basierend auf den ausgewählten Eingabedaten generiert.

- Kundenprofile: Alle Kunden oder Mitglieder eines bestimmten Segments.

- Zeitraum: Letzter Monat, letztes Jahr oder ein benutzerdefiniertes Zeitrahmen.

- Aktivitätsart: Einkäufe, Einzelhandelsgeschäfte, Online-Transaktionen, Kundenunterstützungsfälle, Abonnements usw.  

- Entität in Customer Insights, die die Aktivitätsdaten enthält: Die UnifiedActivity-Entität oder die Entität für eine bestimmte Aktivität.

- Zu berücksichtigende Dimensionen: Aktualität, Häufigkeit oder monetäre Dimension, abhängig von Ihren Geschäftsanforderungen.

## <a name="generate-suggested-segments"></a>Generieren Sie vorgeschlagene Segmente

1. Gehen Sie zu **Segmente** und wählen Sie die Registerkarte **Vorschläge (Vorschauversion)**.

1. Wählen Sie **Neue Vorschläge suchen** und wählen Sie **Kundenverhalten sehen oder antizipieren** aus. Wählen Sie **Start** aus.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Erster Schritt des Konfigurationsassistenten für ein vorgeschlagenes Segment basierend auf der Aktivität.":::

1. Geben Sie die erforderlichen Eingabedaten ein und wählen Sie **Weiter**.

   - Kunden auswählen: Alle Kunden oder ein bestimmtes Segment einbeziehen.
   - Aktivität auswählen: Wählen Sie den Aktivitätstyp und die Entitäten aus, die die Aktivität beschreiben.
   - Einstellungen: Legen Sie den zu berücksichtigenden Zeitraum und die Faktoren für Vorschläge fest und ordnen Sie die Attribute zu.

1. Überprüfen Sie Ihre Eingabe und wählen Sie **Ausführen**, um das Modell auszuführen und Vorschläge zu generieren.

Abhängig von der Anzahl der Kundenprofile und ausgewählten Aktivitäten kann der Vorgang einige Minuten dauern.

Nachdem Sie die Vorschläge generiert haben, können Sie sie nach der Dimension oder dem Wert filtern, an dem Sie am meisten interessiert sind.

## <a name="manage-suggested-segments"></a>Vorgeschlagene Segmente verwalten

Gehen Sie zu **Segmente** und wählen Sie die Registerkarte **Vorschläge (Vorschau)** aus. Wählen Sie im Abschnitt **Aktivitätsbasierte Vorschläge** ein vorgeschlagenes Segment aus, um verfügbare Aktionen anzuzeigen.

- **Vorschläge anzeigen** enthält Details für das Segment wie die Ausdehnung jeder Dimension im Vergleich zur Zielgruppe. Außerdem werden die Anzahl der potenziellen Mitglieder im Segment und der entsprechende Prozentsatz der Gesamtkunden hervorgehoben.
- **Segment erstellen** um den Vorschlag als Segment zu speichern. Es wird auf der Registerkarte **Alle Segmente** angezeigt und kann [aktualisiert oder gelöscht](segments.md) werden. Sie können die Segmentdetails nicht bearbeiten. Sie können jedoch die Eingabekriterien für die Vorschläge ändern und verschiedene Vorschläge generieren.
- **Vorschläge bearbeiten** um die konfigurierten Attribute zu ändern, die die aktuellen Vorschläge ersetzen.
- Wählen Sie **Vorschläge aktualisieren**, um die Vorschläge zu aktualisieren und gleichzeitig die konfigurierten Attribute beizubehalten.

[!INCLUDE [footer-include](includes/footer-banner.md)]
