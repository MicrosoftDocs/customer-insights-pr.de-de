---
title: Erstellen von Segmenten mithilfe des Segment-Builders
description: Erstellen Sie Kundensegmente, um sie auf der Grundlage verschiedener Attribute zu gruppieren.
ms.date: 10/18/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bd01edfe7d63d6c7712a808224171f1bb8ad8a2b
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673549"
---
# <a name="create-segments"></a>Segmente erstellen

Sie können komplexe Filter mit Bezug zur einheitlichen Kundenentität und den verwandten Entitäten festlegen. Jedes Segment erstellt nach der Verarbeitung eine Reihe von Kundendatensätzen, die Sie exportieren und für die Sie Maßnahmen ergreifen können. Segmente werden auf der Seite **Segmente** verwaltet. Sie können [neue Segmente erstellen](#create-a-new-segment) mit dem Segmentgenerator oder aus anderen Bereichen der App [schnell Segmente erstellen](#quick-segments). 

> [!TIP]
> - Schnelle Sgmente werden nur in Umgebungen für **individuelle Kunden** unterstützt.    
> - Segmente basierend auf **individuelle Kunden** schließen automatisch verfügbare Kontaktinformationen für Segmentmitglieder ein. In Umgebungen für **Geschäftskonten** basieren Seg,emte auf Konten (Gesellschaften oder Tochtergesellschaften). Um Kontaktinformationen in ein Segment aufzunehmen, verwenden Sie die **Projektattribute** Funktionalität im Segmentersteller.
>    - Stellen Sie sicher, dass die Kontaktdatenquellen [semantisch der ContactProfile-Entität zugeordnet](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping) werden.

## <a name="segment-builder"></a>Segmentgenerator

Die folgende Abbildung veranschaulicht die verschiedenen Aspekte des Segmentgenerators. Sie zeigt ein Segment, das zu einer Gruppe von Kunden führt. Die Kunden bestellten Waren in einem bestimmten Zeitrahmen und sammelten Prämienpunkte oder gaben einen bestimmten Geldbetrag aus. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elemente des Segment-Builders." lightbox="media/segment-builder-overview.png":::

1. Organisieren Sie Ihr Segment mit Regeln und Unterregeln. Jede Regel oder Unterregel besteht aus Bedingungen. Kombinieren Sie die Bedingungen mit logischen Operatoren

1. Wählen Sie den [Beziehungspfad](relationships.md) zwischen Entitäten, die für eine Regel gelten. Der Beziehungspfad bestimmt, welche Attribute in einer Bedingung verwendet werden können.

1. Regeln und untergeordnete Regeln verwalten. Ändern Sie die Position einer Regel oder löschen Sie sie.

1. Fügen Sie Bedingungen hinzu und erstellen Sie mithilfe von Unterregeln die richtige Verschachtelungsebene.

1. Wenden Sie festgelegte Operationen auf verbundene Regeln an.

1. Verwenden Sie den Attributbereich, um verfügbare Entitätsattribute hinzuzufügen oder Bedingungen basierend auf Attributen zu erstellen. Der Bereich zeigt die Liste der Entitäten und Attribute basierend auf dem ausgewählten Beziehungspfad, die für die ausgewählte Regel verfügbar sind.

1. Fügen Sie Bedingungen basierend auf Attributen zu bestehenden Regeln und untergeordneten Regeln hinzu oder fügen Sie sie zu einer neuen Regel hinzu.

1. Machen Sie Änderungen beim Erstellen des Segments rückgängig und wiederholen Sie sie.

Das obige Beispiel veranschaulicht die Segmentierungsfunktion. Wir haben ein Segment für Kunden definiert, die Waren im Wert von mindestens $500 online gekauft haben *und* Interesse an der Softwareentwicklung haben.

## <a name="create-a-new-segment"></a>Ein neues Segment erstellen

Es gibt mehrere Wege, ein neues Segment zu erstellen. In diesem Abschnitt wird beschrieben, wie Sie Ihr eigenes Segment von Grund auf neu erstellen. Sie können auch ein *schnelles Segment* basierend auf vorhandenen Entitäten erstellen oder Maschinelles Lernen-Modelle verwenden, um *vorgeschlagene Segmente* zu erhalten. Weitere Informationen finden Sie unter [Segmente-Übersicht](segments.md).

Während Sie ein Segment erstellen, können Sie einen Entwurf speichern. In der Entwurfsphase wird ein Segment als inaktives Segment gespeichert. Wenn Sie die Segmentkonfiguration abgeschlossen haben, führen Sie sie aus, um das Segment zu aktivieren. Sie können auch ein Segment über die **Alle Segmente**-Seite **aktivieren**.

1. Gehen Sie zur Seite **Segmente**.

1. Wählen Sie **Neu** > **Eigene erstellen**.

1. Auf der Segment-Ersteller-Seite definieren oder erstellen Sie Regeln. Eine Regel besteht aus einer oder mehreren Bedingungen, die eine Menge von Kunden definieren.

1. Im Abschnitt **Regel 1** wählen Sie ein Attribut einer Entität aus, nach der Kunden gefiltert werden sollen. Es gibt zwei Möglichkeiten, Attribute auszuwählen: 
   - Überprüfen Sie die Liste der verfügbaren Entitäten und Attribute im Bereich **Zu Regel hinzufügen**, und wählen Sie das Symbol **+** neben dem hinzuzufügenden Attribut aus. Wählen Sie aus, ob Sie das Attribut zu einer vorhandenen Regel hinzufügen oder zum Erstellen einer neuen Regel verwenden möchten.
   - Geben Sie den Namen des Attributs in den Regelabschnitt ein, um passende Vorschläge anzuzeigen.

1. Wählen Sie die Operatoren aus, um die übereinstimmenden Werte der Bedingung anzugeben. Ein Attribut kann einen von vier Datentypen als Wert haben: numerisch, Zeichenfolge, Datum oder boolesch. Je nach Datentyp des Attributs stehen unterschiedliche Operatoren zur Angabe der Bedingung zur Verfügung. Für Segmente mit Geschäftskonten stehen zwei spezielle Operatoren zur Verfügung, um potenzielle Hierarchien zwischen den aufgenommenen Konten einzubeziehen. Verwenden Sie die Operatoren *Untergeordnet von* und *Übergeordnet von*, um zugehörige Konten einzubeziehen. 

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

   - Sie können mehrere Regeln erstellen, um verschiedene Sätze von Kundendatensätzen zu erstellen. Sie können Gruppen kombinieren, um die Kunden einzuschließen, die für Ihren Geschäftsfall erforderlich sind. Wählen Sie **Regel hinzufügen** aus, um eine neue Regel zu erstellen. Insbesondere wenn Sie aufgrund des angegebenen Beziehungspfads keine Entität in eine Regel einschließen können, müssen Sie eine neue Regel erstellen, um Attribute daraus auszuwählen.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Fügen Sie einem Segment eine neue Regel hinzu, und wählen Sie den Mengenoperator.":::

   - Wählen Sie einen der eingestellten Operatoren aus: **Gesamtmenge**, **Überschneiden**, oder **Außer**.

      - **Vereinigen** vereinigt die beiden Gruppen.
      - **Überschneiden** überschneidet die beiden Gruppen. Nur Daten, die beiden Gruppen *angehören*, verbleiben in der vereinheitlichten Gruppe.
      - **Außer** kombiniert die beiden Gruppen. Nur Daten in Gruppe A, die *nicht* Daten in Gruppe B angehören, werden beibehalten.

1. Segmente generieren standardmäßig die Ausgabeentität, die alle Attribute von Kundenprofilen enthält, die den definierten Filtern entsprechen. Wenn ein Segment auf anderen Entitäten als der Entität *Kunde* basiert, können Sie der Ausgabeentität weitere Attribute dieser Entitäten hinzufügen. Wählen Sie, **Projektattribute**, um die Attribute auszuwählen, die an die Ausgabeentität angehängt werden. 

   > [!IMPORTANT]
   > Bei Segmenten, die auf Geschäftskonten basieren, müssen Details zu einem oder mehreren Kontakten jedes Kontos aus der *ContactProfile*-Entität in das Segment aufgenommen werden, damit dieses Segment aktiviert oder an Ziele exportiert werden kann, für die Kontaktinformationen erforderlich sind. Weitere Informationen über die *ContactProfile*-Entität finden Sie unter [Semantische Zuordnungen](semantic-mappings.md).
   > Eine Beispielausgabe für ein Segment basierend auf Geschäftskonten mit projizierten Attributen von Kontakten könnte wie folgt aussehen: 
   >
   > |Kennung  |Firmenname  |Einnahmen  |Kontaktname  | Rolle des Kontakts|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100K | [Abbie Moss, Ruth Soto]  | [CEO, Beschaffungsmanagement]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Beispiel für im Seitenbereich ausgewählte projizierte Attribute, die der Ausgabeentität hinzugefügt werden sollen.":::
  
   Beispiel: Ein Segment basiert auf einer Entität, die Kaufdaten enthält, die sich auf die *Kunde* Entität bezieht. Das Segment sucht nach allen Kunden aus Spanien, die im laufenden Jahr Waren gekauft haben. Sie können Attribute wie den Preis der Ware oder das Kaufdatum an alle übereinstimmenden Kundendatensätze in der Ausgabeentität anhängen. Diese Informationen können nützlich sein, um saisonale Korrelationen zu den Gesamtausgaben zu analysieren.

   > [!NOTE]
   > - **Projektattribute** funktioniert nur für Entitäten, die eine 1:n-Beziehung mit der Kundenentität haben. Beispielsweise kann ein Kunde mehrere Abonnements haben.
   > - Wenn das Attribut, das Sie projizieren möchten, mehr als einen Hop von der Entität *Kunde* entfernt ist, wie durch die Beziehung definiert, sollte dieses Attribut in jeder Regel der Segmentabfrage verwendet werden, die Sie erstellen. 
   > - Wenn das Attribut, das Sie projizieren möchten, nur einen Hop von der Entität *Kunde* entfernt ist, muss dieses Attribut nicht in jeder Regel der Segmentabfrage vorhanden sein, die Sie erstellen. 
   > - **Projizierte Attribute** werden bei Verwendung von festgelegten Operatoren berücksichtigt.

1. Bevor Sie das Segment speichern und ausführen, wählen Sie **Details bearbeiten** neben dem Segmentnamen. Geben Sie einen Namen für Ihr Segment ein, und aktualisieren Sie den vorgeschlagenen **Ausgabeentitätsnamen** für das Segment. Sie können dem Segment auch eine Beschreibung hinzufügen.

1. Wählen Sie **Ausführen**, um das Segment zu speichern, aktivieren Sie es und beginnen Sie mit der Verarbeitung Ihres Segments basierend auf allen Regeln und Bedingungen. Andernfalls wird es als inaktives Segment gespeichert.
   
1. Wählen Sie **Zurück zu Segmenten**, um zur Seite **Segmente** zurückzukehren.

1. Standardmäßig wird das Segment als dynamisches Segment erstellt. Dies bedeutet, dass das Segment während der Systemaktualisierung aktualisiert wird. Um die [automatische Aktualisierung anzuhalten](segments.md#manage-existing-segments), wählen Sie das Segment und dann die Option **Statisch machen** aus. Statische Segmente können jederzeit [manuell aktualisiert](segments.md#refresh-segments) werden.

> [!TIP]
> - Der Segmentgenerator schlägt beim Festlegen der Operatoren für die Bedingungen keine gültigen Werte aus Entitäten vor. Sie können zu **Daten** > **Entitäten** wechseln, und die Entitätsdaten herunterladen, um zu sehen, welche Werte verfügbar sind.
> - Mit datumsbasierten Bedingungen können Sie zwischen festen Datumsangaben und einem variablen Datumsbereich wechseln.
> - Wenn Sie mehrere Regeln für Ihr Segment haben, wird neben der Regel, die Sie bearbeiten, eine vertikale blaue Linie angezeigt. 
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
