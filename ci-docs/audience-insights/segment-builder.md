---
title: Erstellen von Segmenten mithilfe des Segment-Builders
description: Erstellen Sie Kundensegmente, um sie auf der Grundlage verschiedener Attribute zu gruppieren.
ms.date: 09/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f7bd0e7e581305836287bd503ef273a2d556bff
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494496"
---
# <a name="create-segments"></a>Segmente erstellen

Sie können komplexe Filter mit Bezug zur einheitlichen Kundenentität und den verwandten Entitäten festlegen. Jedes Segment erstellt nach der Verarbeitung eine Reihe von Kundendatensätzen, die Sie exportieren und für die Sie Maßnahmen ergreifen können. Segmente werden auf der Seite **Segmente** verwaltet. Sie können [neue Segmente erstellen](#create-a-new-segment) mit dem [Segmentgenerator](#segment-builder) oder aus anderen Bereichen der App [schnelle Segmente erstellen](#quick-segments).

## <a name="segment-builder"></a>Segmentgenerator

Die folgende Abbildung veranschaulicht die verschiedenen Aspekte des Segmentgenerators. Sie zeigt ein Segment, das zu einer Gruppe von Kunden führt. Die Kunden bestellten Waren in einem bestimmten Zeitrahmen und sammelten eine Reihe von Belohnungspunkten oder gaben einen bestimmten Geldbetrag aus. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elemente des Segment-Builders." lightbox="media/segment-builder-overview.png":::

1 - Organisieren Sie Ihr Segment mit Regeln und Unterregeln. Jede Regel oder Unterregel besteht aus Bedingungen. Kombinieren Sie die Bedingungen mit logischen Operatoren

2 - Wählen Sie den [Beziehungspfad](relationships.md) zwischen Entitäten, die für eine Regel gelten. Der Beziehungspfad bestimmt, welche Attribute in einer Bedingung verwendet werden können.

3 - Regeln und untergeordnete Regeln verwalten. Ändern Sie die Position einer Regel oder löschen Sie sie.

4 - Fügen Sie Bedingungen hinzu und erstellen Sie mithilfe von Unterregeln die richtige Verschachtelungsebene.

5 - Wenden Sie Set-Operationen auf verbundene Regeln an.

6 - Verwenden Sie den Attributbereich, um verfügbare Entitätsattribute hinzuzufügen oder Bedingungen basierend auf Attributen zu erstellen. Der Bereich zeigt die Liste der Entitäten und Attribute basierend auf dem ausgewählten Beziehungspfad, die für die ausgewählte Regel verfügbar sind.

7 - Fügen Sie Bedingungen basierend auf Attributen zu bestehenden Regeln und untergeordneten Regeln hinzu oder fügen Sie sie zu einer neuen Regel hinzu.

8 - Machen Sie Änderungen beim Erstellen des Segments rückgängig und wiederholen Sie sie.

Das obige Beispiel veranschaulicht die Segmentierungsfunktion. Wir haben ein Segment für Kunden definiert, die Waren im Wert von mindestens $500 online gekauft haben *und* Interesse an der Softwareentwicklung haben.

## <a name="create-a-new-segment"></a>Ein neues Segment erstellen

Es gibt mehrere Wege, ein neues Segment zu erstellen. In diesem Abschnitt wird beschrieben, wie Sie Ihr eigenes Segment von Grund auf neu erstellen. Sie können auch ein *schnelles Segment* basierend auf vorhandenen Entitäten erstellen oder Maschinelles Lernen-Modelle verwenden, um *vorgeschlagene Segmente* zu erhalten. Weitere Informationen: [Segmentübersicht](segments.md).

Während Sie ein Segment erstellen, können Sie einen Entwurf speichern. Es wird als inaktives Segment gespeichert und kann nicht aktiviert werden, wenn eine gültige Konfiguration vorliegt.

1. Gehen Sie zur Seite **Segmente**.

1. Wählen Sie **Neu** > **Eigene erstellen**.

1. Auf der Segmentgenerator-Seite definieren Sie die erste Regel. Eine Regel besteht aus einer oder mehreren Bedingungen und definiert eine Menge von Kunden.

1. Im Abschnitt **Regel 1** wählen Sie ein Attribut einer Entität aus, nach der Kunden gefiltert werden sollen. Es gibt zwei Möglichkeiten, Attribute auszuwählen: 
   - Überprüfen Sie die Liste der verfügbaren Entitäten und Attribute im Bereich **Zu Regel hinzufügen**, und wählen Sie das Symbol **+** neben dem hinzuzufügenden Attribut aus. Wählen Sie aus, ob Sie das Attribut zu einer vorhandenen Regel hinzufügen oder zum Erstellen einer neuen Regel verwenden möchten.
   - Geben Sie den Namen des Attributs in den Regelabschnitt ein, um passende Vorschläge anzuzeigen.

1. Wählen Sie die Operatoren aus, um die übereinstimmenden Werte der Bedingung anzugeben. Ein Attribut kann einen von vier Datentypen als Wert haben: numerisch, Zeichenfolge, Datum oder boolesch. Je nach Datentyp des Attributs stehen unterschiedliche Operatoren zur Angabe der Bedingung zur Verfügung. 

1. Wählen Sie **Bedingung hinzufügen**, um einer Regel weitere Bedingungen hinzuzufügen. Um eine Regel unter der aktuellen Regel zu erstellen, wählen Sie **Unterregel hinzufügen**.

1. Wenn eine Regel andere Entitäten als die Entität *Kunde* verwendet, müssen Sie den Beziehungspfad festlegen. Der Beziehungspfad ist erforderlich und teilt dem System mit, über welche Beziehungen auf die vereinheitlichten Kundenentität zugegriffen werden soll. Wählen Sie **Beziehungspfad festlegen**, um die ausgewählte Entität der vereinheitlichten Kundenentität zuzuordnen. Wenn nur ein möglicher Beziehungspfad vorhanden ist, wählt das System diesen automatisch aus. Unterschiedliche Beziehungspfade können zu unterschiedlichen Ergebnissen führen. Jede Regel kann einen eigenen Beziehungspfad haben.

   :::image type="content" source="media/relationship-path.png" alt-text="Potenzieller Beziehungspfad beim Erstellen einer Regel basierend auf einer Entität, die der vereinheitlichten Kundenentität zugeordnet ist.":::

   Zum Beispiel hat die Entität *eCommerce_eCommercePurchase* im Screenshot vier Optionen, die der Entität *Kunde* zugeordnet werden können: 
   - eCommerce_eCommercePurchases > eCommerce_eCommerceKontakte > Kunde
   - eCommerce_eCommercePurchases > Kunde
   - eCommerce_eCommercePurchases > eCommerce_eCommerceKontakte > POS_posPurchases > Kunde
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Customer ei Auswahl der letzten Option können wir Attribute aller aufgelisteten Entitäten in die Regelbedingungen aufnehmen. Wir werden wahrscheinlich weniger Ergebnisse erhalten, da die übereinstimmenden Kundendatensätze Teil aller Entitäten sein müssen. In diesem Beispiel müssen Sie Waren über E-Commerce (*eCommerce_eCommercePurchases*), an einer Verkaufsstelle (*POS_posPurchases*) gekauft haben und an unserem Treueprogrammen (*loyaltyScheme_loyCustomers*) teilnehmen. Bei der zweiten Option können wir nur Attribute aus *eCommerce_eCommercePurchases* und der Entität *Kunde* auswählen. Dies führt wahrscheinlich zu mehr Kundenprofilen.

1. Wenn eine Regel mehrere Bedingungen enthält, können Sie auswählen, welcher logische Operator sie verbindet.

   - **UND**-Operator: Alle Bedingungen müssen erfüllt sein, um einen Datensatz in das Segment aufzunehmen. Diese Option ist am nützlichsten, wenn Sie Bedingungen für verschiedene Entitäten definieren.

   - **ODER**-Operator: Eine der Bedingungen muss erfüllt sein, um einen Datensatz in das Segment aufzunehmen. Diese Option ist am nützlichsten, wenn Sie mehrere Bedingungen für dieselbe Entität definieren.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regel mit zwei UND-Bedingungen.":::

   Bei Verwendung des ODER-Operators müssen alle Bedingungen auf Entitäten basieren, die im Beziehungspfad enthalten sind.

   1. Sie können mehrere Regeln erstellen, um verschiedene Sätze von Kundendatensätzen zu erstellen. Sie können Gruppen kombinieren, um die Kunden einzuschließen, die für Ihren Geschäftsfall erforderlich sind. Wählen Sie **Regel hinzufügen** aus, um eine neue Regel zu erstellen. Insbesondere wenn Sie aufgrund des angegebenen Beziehungspfads keine Entität in eine Regel einschließen können, müssen Sie eine neue Regel erstellen, um Attribute daraus auszuwählen.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Fügen Sie einem Segment eine neue Regel hinzu, und wählen Sie den Mengenoperator.":::

   1. Wählen Sie einen der eingestellten Operatoren aus: **Gesamtmenge**, **Überschneiden**, oder **Außer**.

   - **Vereinigen** vereinigt die beiden Gruppen.

   - **Überschneiden** überschneidet die beiden Gruppen. Nur Daten, die *beiden Gruppen gemeinsam* sind, werden in der vereinigten Gruppe beibehalten.

   - **Außer** kombiniert die beiden Gruppen. Nur Daten in Gruppe A, die *nicht gemeinsam* mit Daten in Gruppe B sind, bleiben erhalten.

1. Segmente generieren standardmäßig die Ausgabeentität, die alle Attribute von Kundenprofilen enthält, die den definierten Filtern entsprechen. Wenn ein Segment auf anderen Entitäten als der Entität *Kunde* basiert, können Sie der Ausgabeentität weitere Attribute dieser Entitäten hinzufügen. Wählen Sie, **Projektattribute**, um die Attribute auszuwählen, die an die Ausgabeentität angehängt werden.  

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Beispiel für im Seitenbereich ausgewählte projizierte Attribute, die der Ausgabeentität hinzugefügt werden sollen.":::
  
   Beispiel: Ein Segment basiert auf einer Entität, die Kaufdaten enthält, die sich auf die Entität *Kunde* beziehen. Das Segment sucht nach allen Kunden aus Spanien, die im laufenden Jahr Waren gekauft haben. Sie können Attribute wie den Preis der Ware oder das Kaufdatum an alle übereinstimmenden Kundendatensätze in der Ausgabeentität anhängen. Diese Informationen können nützlich sein, um saisonale Korrelationen zu den Gesamtausgaben zu analysieren.

   > [!NOTE]
   > - Projizierte Attribute funktionieren nur für Entitäten, die eine Eins-zu-Viele-Beziehung zur Kundenentität haben. Beispielsweise kann ein Kunde mehrere Abonnements haben.
   > - Sie können nur Attribute einer Entität projizieren, die in jeder von Ihnen erstellten Segmentabfrageregel verwendet wird.
   > - Projizierte Attribute werden bei Verwendung von festgelegten Operatoren berücksichtigt.

1. Bevor Sie das Segment speichern und ausführen, wählen Sie **Details bearbeiten** neben dem Segmentnamen. Geben Sie einen Namen für Ihr Segment ein, und aktualisieren Sie den vorgeschlagenen **Ausgabeentitätsnamen** für das Segment. Sie können dem Segment auch eine Beschreibung hinzufügen.

1. Wählen Sie **Ausführen**, um Ihr Segment zu speichern und zu verarbeiten, wenn alle Anforderungen validiert sind. Andernfalls wird es als inaktiver Segmententwurf gespeichert.

1. Wählen Sie **Zurück zu Segmenten**, um zur Seite **Segmente** zurückzukehren.

> [!TIP]
> - Der Segmentgenerator schlägt beim Festlegen der Operatoren für die Bedingungen keine gültigen Werte aus Entitäten vor. Sie können zu **Daten** > **Entitäten** wechseln, und die Entitätsdaten herunterladen, um zu sehen, welche Werte verfügbar sind.
> - Mit datumsbasierten Bedingungen können Sie zwischen festen Datumsangaben und einem variablen Datumsbereich wechseln.
> - Wenn Sie mehrere Regeln für Ihr Segment haben, sehen Sie einen blauen Balken um die Regel, die Sie bearbeiten.
> - Sie können Regeln und Bedingungen an andere Stellen in der Segmentdefinition verschieben. Wählen Sie neben einer Regel oder Bedingung [...] aus, und legen Sie fest, wie und wohin sie verschoben werden soll.
> - Mit den Steuerelementen **Rückgängig machen** und **Wiederholen** in der Befehlsleiste können Sie Änderungen rückgängig machen.

## <a name="quick-segments"></a>Schnelle Segmente

Mit schnellen Segmenten können Sie schnell einfache Segmente mit einem einzigen Operator erstellen, um schnellere Einblicke zu erhalten.

1. Wählen Sie auf der Seite **Segment** aus und wählen Sie **Neu** > **Erstellen aus**.

   - Wählen Sie die Option **Profile**, um ein Segment zu erstellen, das auf der *einheitlichen Kundenentität* basiert.
   - Wählen Sie die Option **Maßnahmen** zum Erstellen eines Segments um zuvor erstellte Kennzahlen.
   - Wählen Sie die Option **Intelligenz** zum Erstellen eines Segments für eine der Ausgabeentitäten aus, die Sie mit einer der beiden Funktionen **Vorhersagen** oder **Benutzerdefinierte Modelle** generiert haben.

2. Wählen Sie im Dialogfeld **Neues schnelles Segment** ein Attribut aus der Dropdownliste **Feld** aus.

3. Das System bietet mehr Einblicke, die Ihnen helfen, bessere Segmente Ihrer Kunden zu erstellen.
   - Für kategoriale Felder werden 10 Top-Kundenzahlen angezeigt. Wählen Sie einen **Wert** und wählen Sie **Überprüfung**.

   - Bei einem numerischen Attribut zeigt das System an, welcher Attributwert unter das Perzentil des jeweiligen Kunden fällt. Wählen Sie einen **Bediener** und einen **Wert**, dann wählen Sie **Review**.

4. Das System liefert Ihnen eine **geschätzte Segmentgröße**. Sie können wählen, ob Sie das von Ihnen definierte Segment generieren oder es zunächst erneut aufrufen, um eine andere Segmentgröße zu erhalten.

    > [!div class="mx-imgBorder"]
    > ![Name und Schätzung für ein schnelles Segment.](media/quick-segment-name.png "Name und Schätzung für ein schnelles Segment")

5. Geben Sie einen **Name** für Ihr Segment an. Geben Sie optional einen **Anzeigename** ein.

6. Wählen Sie **Speichern**, um Ihr Segment zu erstellen.

7. Nachdem das Segment fertig bearbeitet wurde, können Sie es wie jedes andere von Ihnen erstellte Segment anzeigen.

## <a name="next-steps"></a>Nächste Schritte,

[Exportieren eines Segments](export-destinations.md) und erkunden der [Kundenkartenintegration](customer-card-add-in.md), um Segmente in anderen Anwendungen zu verwenden.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
