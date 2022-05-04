---
title: Aktivitätsbasierte Segmentvorschläge.
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
ms.openlocfilehash: 85c3cef3a8d531b31b64a7e5decbdc122c4383fc
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647040"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Segmentvorschläge basierend auf Aktivitätsdaten (Vorschau)

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
Wenn Sie im Gesundheitswesen tätig sind und öffentliche Gesundheitsversorgung anbieten, ist es Ihr Ziel, die Kosten für einzelne Patienten zu minimieren. Eine Möglichkeit, dies zu tun, könnte darin bestehen, wiederkehrende Besuche zu reduzieren, indem bei möglichst wenigen Besuchen die bestmögliche Pflege bereitgestellt wird. In diesem Fall ist es Ihr Ziel, die Besuchshäufigkeit niedrig zu halten und die wiederkehrenden Kosten für die Patienten zu minimieren. Oder Sie können Segmente von Patienten identifizieren, die häufige Termine und hohe wiederkehrende Kosten haben, und diese Fälle analysieren, um die Behandlung des Patienten zu verbessern. 

## <a name="required-data"></a>Erforderliche Daten

Vorschläge werden basierend auf den ausgewählten Eingabedaten generiert. 

- Kundenprofile: Alle Kunden oder Mitglieder eines bestimmten Segments. 

- Zeitraum: Letzter Monat, letztes Jahr oder ein benutzerdefiniertes Zeitrahmen.

- Aktivitätsart: Einkäufe, Einzelhandelsgeschäfte, Online-Transaktionen, Kundenunterstützungsfälle, Abonnements usw.  

- Entität in Customer Insights, die die Aktivitätsdaten enthält: Die UnifiedActivity-Entität oder die Entität für eine bestimmte Aktivität. 

- Zu berücksichtigende Dimensionen: Aktualität, Häufigkeit oder monetäre Dimension, abhängig von Ihren Geschäftsanforderungen.

## <a name="generate-suggested-segments"></a>Generieren Sie vorgeschlagene Segmente

1. Gehen Sie zu **Segmente**.

1. Wählen Sie die Registerkarte **Vorschläge (Vorschau)** aus.

1. Wählen Sie **Neue Vorschläge suchen** und wählen Sie **Kundenverhalten sehen oder antizipieren** aus. Wählen Sie **Start** um die Anleitung zu befolgen.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Erster Schritt des Konfigurationsassistenten für ein vorgeschlagenes Segment basierend auf der Aktivität.":::

1. Geben Sie die erforderlichen Eingabedaten ein und wählen Sie **Weiter** zum Fortfahren.

   - Kunden auswählen: Alle Kunden oder ein bestimmtes Segment einbeziehen.
   - Aktivität auswählen: Wählen Sie den Aktivitätstyp und die Entitäten aus, die die Aktivität beschreiben.
   - Einstellungen: Legen Sie den zu berücksichtigenden Zeitraum und die Faktoren für Vorschläge fest und ordnen Sie die Attribute zu.

1. Überprüfen Sie Ihre Eingabe und wählen Sie **Ausführen**, um das Modell auszuführen und Vorschläge zu generieren.

1. Abhängig von der Anzahl der Kundenprofile und ausgewählten Aktivitäten kann der Vorgang einige Minuten dauern. 

Nachdem Sie die Vorschläge generiert haben, können Sie sie nach der Dimension oder dem Wert filtern, an dem Sie am meisten interessiert sind. 

## <a name="view-details-of-a-suggested-segment"></a>Vorgeschlagene Segmentdetails anzeigen

Sobald die Vorschläge generiert wurden, finden Sie sie unter **Segmente** > **Vorschläge (Vorschau)** in dem Bereich **Aktivitätsbasierte Vorschläge**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Erweiterter Seitenbereich mit detaillierten Daten eines vorgeschlagenen Segments.":::

Wählen Sie **Siehe Vorschlag** auf einem vorgeschlagenen Segment, um die Details dieses Segments anzuzeigen. Der Seitenbereich enthält Details wie die Ausdehnung jeder Dimension im Vergleich zur Zielgruppe. Außerdem werden die Anzahl der potenziellen Mitglieder im Segment und der entsprechende Prozentsatz der Gesamtkunden hervorgehoben. Wenn Sie den Vorschlag als Segment behalten möchten, wählen Sie **Segment erstellen**.    

## <a name="save-a-suggestion-as-a-segment"></a>Speichern Sie einen Vorschlag als Segment

1. Gehe Sie zu **Segmente** > **Vorschläge (Vorschau)**.

1. Wählen Sie das Segment aus, das Sie speichern möchten. 

1. Wählen Sie im Seitenbereich **Segment erstellen** aus. 

1. Nach dem Speichern des Segments wird es in der Liste der Segmente auf der Registerkarte **Alle Segmente** angezeigt. Es kann jetzt [wie jedes andere Segment aktualisiert oder gelöscht werden](segments.md). Sie können die Segmentdetails nicht bearbeiten. Sie können jedoch die Eingabekriterien für die Vorschläge ändern und verschiedene Vorschläge generieren.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Aktualisieren oder bearbeiten Sie eine Reihe von Vorschlägen

1. Gehen Sie zu **Segmente** > **Vorschläge (Vorschau)** und suchen Sie nach dem Segment in dem Bereich **Aktivitätsbasierte Vorschläge**.

1. Wählen Sie **Vorschläge aktualisieren**, um die Vorschläge zu aktualisieren und gleichzeitig die konfigurierten Attribute beizubehalten. Oder wählen Sie **Vorschläge bearbeiten**, um die konfigurierten Attribute zu ändern. Das System führt den Prozess erneut aus, generiert Segmentvorschläge basierend auf den neuesten Daten und ersetzt die aktuellen Vorschläge.

[!INCLUDE [footer-include](includes/footer-banner.md)]
