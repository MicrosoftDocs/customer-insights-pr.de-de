---
title: Vorgeschlagene Segmente auf Basis von maschinellem Lernen
description: Mit maschinellem Lernen können Sie neue und interessante Segmente anhand von Kundenattributen finden.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 44e46bb650b6f090afcab3bc940d03a304e9c375
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673182"
---
# <a name="suggested-segments-preview"></a>Vorgeschlagene Segmente (Vorschau)

Entdecken Sie mithilfe eines KI-Modells interessante Segmente Ihrer Kunden. Diese auf maschinellem Lernen basierende Funktion schlägt Segmente vor, die auf Kennzahlen oder Kundenattributen basieren. Dies kann dazu beitragen, Ihre KPIs zu verbessern oder den Einfluss von Attributen im Kontext anderer Attribute besser zu verstehen. 

> [!NOTE]
> Die vorgeschlagene Segmentfunktion verwendet Automatisierung, um Daten auszuwerten und Vorhersagen auf Grundlage dieser Daten zu treffen, und kann daher als Methode zur Profilerstellung verwendet werden, wie dieser Begriff in der Datenschutz-Grundverordnung („DSGVO“) definiert ist. Ihre Verwendung dieser Funktion zur Verarbeitung von Daten unterliegt möglicherweise der DSGVO oder anderen Gesetzen oder Vorschriften. Sie sind dafür verantwortlich, dass Ihre Dynamics 365 Customer Insights-Nutzung, einschließlich dieser Funktion, allen geltenden Gesetzen und Vorschriften entspricht, einschließlich Gesetzen in Bezug auf Privatsphäre, personenbezogene Daten, biometrische Daten, Datenschutz und Vertraulichkeit der Kommunikation.

:::image type="content" source="media/suggested-segments.png" alt-text="Seite „Vorgeschlagene Segmente“, die Details zu einem Vorschlag in einem Seitenbereich anzeigt.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Vorgeschlagene Segmente zur Verbesserung Ihrer KPIs

Als Benutzer von Zielgruppenerkenntnisse haben Sie wahrscheinlich eine Reihe von [Maßnahmen erstellt](measures.md), damit Sie Ihre Key Performance Indicators (KPIs) nachverfolgen können. Es ist wichtig zu verstehen, wie bestimmte Attribute diesen KPI beeinflussen, um Segmente zu erstellen und eine zielgerichtete Kampagne durchzuführen.   
Sie verfolgen beispielsweise eine Kennzahl mit dem Namen *TotalSpendPerCustomer*. Als Unternehmen möchten Sie, dass diese Zahl zunimmt. Wenn Sie eine Kennzahl als primäres Attribut auswählen, können Sie die Attribute auswählen, deren Einfluss Sie bewerten möchten. Gehen wir von *Mitgliedschaftsstufe*, *Mitgliedschaftszeitraum* und *Aufgabe* aus. Customer Insights kann dann ein Segment vorschlagen, das Ihnen sagt, wer den größten Einfluss auf diese Maßnahme hat. So sind zum Beispiel *Buchhalter*, die *Gold*-Mitglieder und seid *mindestens fünf Jahren* in Ihrem Unternehmen sind, die größten Einflussfaktoren von *TotalSpendPerCustomer*. Sie erhalten für jeden Vorschlag eine geschätzte Segmentgröße. Mit diesen Informationen können Sie Kampagnen für die Zielgruppen erstellen.

## <a name="understand-what-influences-a-customer-attribute"></a>Verstehen, was ein Kundenattribut beeinflusst

Sie können ein Kundenattribut anstelle einer Kennzahl als primäres Attribut auswählen. Basierend auf Ihrer Auswahl der Einflussattribute erstellt das KI-Modell eine Reihe von Vorschlägen, die zeigen, wie die ausgewählten Attribute das primäre Attribut beeinflussen.   
Zum Beispiel wählen Sie *Prämienmitglied (Ja/Nein)* als primäres Attribut. *Tenure*, *Beruf* und *Anzahl der Support-Tickets* werden als andere beeinflussende Attribute festgelegt. Das KI-Modell könnte Segmente vorschlagen, die darauf hinweisen, dass hauptsächlich IT-Experten mit einer Amtszeit von mehr als zwei Jahren Belohnungsmitglieder sind. Ein weiterer Vorschlag könnte hervorheben, dass Buchhalter mit einer Amtszeit von mehr als einem Jahr und weniger als drei Support-Tickets Belohnungsmitglieder sind. 

## <a name="artificial-intelligence-usage"></a>Künstliche Intelligenz nutzen

Unter Verwendung des primären Attributs und der Einflussattribute schlägt ein Entscheidungsbaumalgorithmus interessante Segmente vor. Die Vorschläge basieren auf Regeln oder Mustern, die vom KI-Algorithmus erfasst wurden. Als Vorschläge werden nur Segmente angezeigt, die sich erheblich von der Durchschnittsbevölkerung unterscheiden. Der Vergleich mit der Durchschnittsbevölkerung basiert auf dem ausgewählten Maß oder primären Attribut.

### <a name="responsible-ai"></a>Verantwortliche KI

Mit vorgeschlagenen Segmenten können Sie Attribute auswählen, um neue Segmente zu erstellen und die ausgewählten Daten zu verarbeiten. Bei der Auswahl von Attributen, einschließlich sensibler Attribute wie Ethnie, sexuelle Orientierung oder Geschlecht, müssen Sie sicherstellen, dass Sie diese Daten verarbeiten können und sollten. Sie sind dafür verantwortlich, alle für Ihre Organisation geltenden Gesetze einzuhalten und die Grundsätze und Datenschutzrichtlinien Ihrer Organisation einzuhalten.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Unterschiedliche Ergebnisse für primäre Attribute mit kategorialen und numerischen Werten

Segmentvorschläge unterscheiden sich, wenn Sie ein numerisches Attribut oder ein kategoriales Attribut als primäres Attribut auswählen. Werte in einem kategorialen Attribut enthalten zwei oder mehr Kategorien oder Typen. Ein numerisches Attribut enthält quantitative Daten und ist mit einem Messungssinn verbunden.

Mit einem numerischen Attribut wie *jährliches Einkommen* oder *Mitgliedschaftszeitraum* als primäres Attribut schlägt das System Segmente vor, die im Vergleich zu allen Kunden einen höheren oder niedrigeren Durchschnittswert des numerischen Attributs aufweisen.

Ein kategoriales Attribut wie *Kundenzufriedenheit* als primäres Attribut führt zu vorgeschlagenen Segmenten mit einem höheren oder niedrigeren Prozentsatz von Kunden, die zu einer bestimmten Kategorie gehören, verglichen mit dem Prozentsatz aller Kunden, die zu derselben Kategorie gehören. Zum Beispiel wird *Kundenzufriedenheit* als primäres Attribut ausgewählt und besteht aus drei Kategorien (*Niedrig*, *Mittel* und *Hoch*). Für jede Kategorie werden Segmente vorgeschlagen, die einen höheren oder niedrigeren Prozentsatz von Kunden dieser Kategorie im Vergleich zum Anteil aller Kunden in derselben Kategorie aufweisen. Wenn 22 % aller Kunden eine Zufriedenheit *Hoch* haben, werden nur Segmente, die einen höheren oder niedrigeren Anteil an Kunden mit *Hoch*-Zufriedenheit im Vergleich zu 22 %, für diese Kategorie vorgeschlagen. In ähnlicher Weise werden Segmente für jede der anderen Kategorien vorgeschlagen (*Niedrig* und *Mittel*), wenn sie statistisch signifikant sind.

> [!NOTE]
> Derzeit unterstützen wir nur primäre kategoriale Attribute mit bis zu 10 Kategorien. Wenn Sie Segmentvorschläge basierend auf einem primären Attribut mit mehr als 10 Kategorien anzeigen möchten, empfehlen wir, einige der Kategorien zu gruppieren, um die Anzahl der Kategorien auf 10 oder weniger zu reduzieren. Diese Einschränkung gilt nur für primäre Attribute. Zur Beeinflussung kategorialer Attribute unterstützen wir derzeit maximal 100 Kategorien.

## <a name="generate-suggested-segments"></a>Generieren Sie vorgeschlagene Segmente

1. Gehen Sie zu **Segmente**.

1. Wählen Sie die Registerkarte **Vorschläge (Vorschau)** aus.

1. Wählen Sie **Neue Vorschläge erhalten**, um die geführte Erfahrung zu beginnen.

1. Wählen Sie eine Messung oder ein Kundenattribut anstelle einer Kennzahl als primäres Attribut aus und dann **Weiter**.

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Auswählen des primären Attributs für Vorschläge zu den vorgeschlagenen Segmenten.":::

1. Wählen Sie die Einflussattribute aus und wählen Sie **Speichern**.
   
   > [!TIP]
   > Durch die Auswahl mehrerer Einflussattribute werden die Chancen verbessert, zu bewerten, wie sie das Primärattribut beeinflussen. Schließen Sie keine Attribute ein, die keinen Einfluss auf das primäre Attribut haben. Wenn beispielsweise alle Ihre Kunden aus einem bestimmten Land stammen, geben Sie nicht das *Land*-Attribut an, da es keine Auswirkungen auf die Ausgabe hat.

1. Abhängig von der Anzahl der Kundenprofile und ausgewählten Attribute kann die Verarbeitung der ausgewählten Attribute einige Minuten dauern. 

## <a name="view-details-of-a-suggested-segment"></a>Vorgeschlagene Segmentdetails anzeigen

Sobald das KI-Modell die Vorschläge generiert hat, finden Sie sie unter **Segmente** > **Vorschläge (Vorschau)**.
 
Wählen Sie ein vorgeschlagenes Segment aus, um die Details dieses Vorschlags zu überprüfen. Sie können auch die Attributwerte oder Regeln überprüfen, die das KI-Modell gelernt hat, um das ausgewählte Segment vorzuschlagen.

## <a name="save-a-suggestion-as-a-segment"></a>Speichern Sie einen Vorschlag als Segment

1. Gehe Sie zu **Segmente** > **Vorschläge (Vorschau)**.

1. Wählen Sie das Segment aus, das Sie speichern möchten. 

1. Wählen Sie im Seitenbereich **Als Segment speichern** aus. 

1. Nach dem Speichern des Segments wird es in der Liste der Segmente auf der Registerkarte **Alle Segmente** angezeigt. Es kann jetzt [wie jedes andere Segment aktualisiert, bearbeitet oder gelöscht werden](segments.md).

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Aktualisieren oder bearbeiten Sie eine Reihe von Vorschlägen

1. Gehe Sie zu **Segmente** > **Vorschläge (Vorschau)**.

1. Wählen Sie **Vorschläge aktualisieren**, um die Vorschläge zu aktualisieren und gleichzeitig die konfigurierten Attribute beizubehalten. Oder wählen Sie **Attribute bearbeiten**, um die konfigurierten Attribute zu ändern. Das System führt das KI-Modell erneut aus, generiert Segmentvorschläge basierend auf den neuesten Daten und ersetzt die aktuellen Vorschläge.

## <a name="limitations"></a>Einschränkungen

1. Nicht übereinstimmende geschätzte Segmentgröße: Wenn Sie ein primäres Attribut auswählen, das leere Werte enthält, kann dies die geschätzte Segmentgröße in den Segmentvorschlägen beeinflussen. Beim Speichern eines solchen Segments kann die tatsächliche Segmentgröße von der ursprünglichen Schätzung abweichen.
 
2. Primäre Attribute vom Booleschen Typ funktionieren nicht: Derzeit unterstützen wir nur Zeichenfolgentypen und numerische Datentypen als primäres Attribut.

3. Vorgeschlagene Segmente sind nicht deutlich genug: Beachten Sie, dass die ausgewählten Attribute und die Verteilung der Werte dieser Attribute die Ergebnisse beeinflussen. Sie können Ihre Einflussattribute oder sogar Ihr primäres Attribut ändern, um unterschiedliche Ergebnisse zu erzielen.



[!INCLUDE[footer-include](../includes/footer-banner.md)]