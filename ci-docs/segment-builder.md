---
title: Erstellen von komplexen Segmenten mithilfe des Segment-Builders
description: Erstellen Sie Kundensegmente, um sie basierend auf verschiedenen Attributen zu gruppieren, indem Sie den Segment-Builder oder Schnellsegmente verwenden.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 7f691fd0b2ea76a2960d5adf766a4b166f02ebb4
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304748"
---
# <a name="create-complex-segments-with-segment-builder"></a>Erstellen von komplexen Segmenten mithilfe des Segment-Builders

Sie können komplexe Filter mit Bezug zur einheitlichen Kundenentität oder für einen einheitlichen Kontakt und den verwandten Entitäten festlegen. Jedes Segment erstellt nach der Verarbeitung einen Satz von Kunden- oder Kontaktentitätsdatensätzen, die Sie exportieren und bearbeiten können.

> [!TIP]
> Segmente basierend auf **individuelle Kunden** schließen automatisch verfügbare Kontaktinformationen für Segmentmitglieder ein. Unter **Geschäftskonten** wählen Sie, sofern Sie beide Konten und Kontakte [vereinheitlicht](data-unification.md) haben, aus, ob das Segment auf Konten oder Geschäftskontakten basiert. Um an ein Ziel zu exportieren, das Kontaktinformationen erwartet, verwenden Sie ein Kontaktsegment. Um an ein Ziel zu exportieren, das Kontoinformationen erwartet, verwenden Sie ein Kontosegment.

## <a name="segment-builder"></a>Segmentgenerator

Die folgende Abbildung veranschaulicht die verschiedenen Aspekte des Segmentgenerators. Sie zeigt ein Segment, das zu einer Gruppe von Kunden führt. Die Kunden bestellten Waren in einem bestimmten Zeitrahmen und sammelten Prämienpunkte oder gaben einen bestimmten Geldbetrag aus.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elemente des Segment-Builders." lightbox="media/segment-builder-overview.png":::

1. Organisieren Sie Ihr Segment mit Regeln und Unterregeln. Jede Regel oder Unterregel besteht aus Bedingungen. Kombinieren Sie die Bedingungen mit logischen Operatoren.

1. Wählen Sie den [Beziehungspfad](relationships.md) zwischen Entitäten, die für eine Regel gelten. Der Beziehungspfad bestimmt, welche Attribute in einer Bedingung verwendet werden können.

1. Regeln und untergeordnete Regeln verwalten. Ändern Sie die Position einer Regel oder löschen Sie sie.

1. Fügen Sie Bedingungen hinzu und erstellen Sie mithilfe von Unterregeln die richtige Verschachtelungsebene.

1. Wenden Sie festgelegte Operationen auf verbundene Regeln an.

1. Verwenden Sie den Attributbereich, um verfügbare Entitätsattribute hinzuzufügen oder Bedingungen basierend auf Attributen zu erstellen. Der Bereich zeigt die Liste der Entitäten und Attribute basierend auf dem ausgewählten Beziehungspfad, die für die ausgewählte Regel verfügbar sind.

1. Fügen Sie Bedingungen basierend auf Attributen zu bestehenden Regeln und untergeordneten Regeln hinzu oder fügen Sie sie zu einer neuen Regel hinzu.

1. Machen Sie Änderungen beim Erstellen des Segments rückgängig und wiederholen Sie sie.

Das obige Beispiel veranschaulicht die Segmentierungsfunktion. Wir haben ein Segment für Kunden definiert, die Waren im Wert von mindestens $500 online gekauft haben *und* Interesse an der Softwareentwicklung haben.

## <a name="create-a-new-segment-with-segment-builder"></a>Erstellen von neuen Segmenten mithilfe des Segment-Builders

1. Gehen Sie zu **Segmente**.

1. Wählen Sie **Neu** > **Eigene erstellen**. Auf der Segment-Ersteller-Seite definieren oder erstellen Sie Regeln. Eine Regel besteht aus einer oder mehreren Bedingungen, die eine Menge von Kunden definieren.

   > [!NOTE]
   > Wählen Sie für Umgebungen, die auf Geschäftskonten basieren, **Neu** > **Segment der Konten** oder **Kontaktsegment (Vorschau)** basierend auf dem Segmenttyp, den Sie erstellen möchten. Wenn eine [Kontohierarchie](relationships.md#set-up-account-hierarchies) definiert wurde und Sie Regeln zum Herausfiltern von Daten basierend auf der Beziehung zwischen untergeordneten und übergeordneten Elementen erstellen möchten, wählen Sie **Hierarchie verwenden? (Vorschauversion)** und wählen Sie die Hierarchie aus und dann **anwenden**.
   >
   > :::image type="content" source="media/segment_acct_hierarchy.png" alt-text="Segment ausgewählter Kontenhierarchiebereich.":::

1. Wählen Sie **Details bearbeiten** neben Segment ohne Titel. Geben Sie einen Namen für Ihr Segment ein, und aktualisieren Sie den vorgeschlagenen **Ausgabeentitätsnamen** für das Segment. Fügen Sie optional eine Beschreibung und [Tags](work-with-tags-columns.md#manage-tags) zum Segment hinzu.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Dialogfeld „Details bearbeiten“":::

1. Wählen Sie im Abschnitt **Regel 1** ein Attribut einer Entität aus, nach der Sie Kunden filtern möchten. Es gibt zwei Möglichkeiten, Attribute auszuwählen:
   - Überprüfen Sie die Liste der verfügbaren Entitäten und Attribute im Bereich **Zu Regel hinzufügen**, und wählen Sie das Symbol **+** neben dem hinzuzufügenden Attribut aus. Wählen Sie aus, ob Sie das Attribut zu einer vorhandenen Regel hinzufügen oder zum Erstellen einer neuen Regel verwenden möchten.
   - Geben Sie den Namen des Attributs in den Regelabschnitt ein, um passende Vorschläge anzuzeigen.

1. Wählen Sie die Operatoren aus, um die übereinstimmenden Werte der Bedingung anzugeben. Ein Attribut kann einen von vier Datentypen als Wert haben: numerisch, Zeichenfolge, Datum oder boolesch. Je nach Datentyp des Attributs stehen unterschiedliche Operatoren zur Angabe der Bedingung zur Verfügung.

1. Wählen Sie **Bedingung hinzufügen**, um einer Regel weitere Bedingungen hinzuzufügen. Um eine Regel unter der aktuellen Regel zu erstellen, wählen Sie **Unterregel hinzufügen**.

1. Wenn eine Regel andere Entitäten als die *Kunden*-Entität (bzw. *ContactProfile* Entität für B-to-B) verwendet, wählen Sie **Beziehungspfad festlegen**, um die ausgewählte Entität der einheitlichen Kundenentität zuzuordnen. Wenn nur ein möglicher Beziehungspfad vorhanden ist, wählt das System diesen automatisch aus. Unterschiedliche [Beziehungspfade](relationships.md#relationship-paths) können zu unterschiedlichen Ergebnissen führen. Jede Regel kann einen eigenen Beziehungspfad haben.

   :::image type="content" source="media/relationship-path.png" alt-text="Potenzieller Beziehungspfad beim Erstellen einer Regel basierend auf einer Entität, die der vereinheitlichten Kundenentität zugeordnet ist.":::

1. Wenn eine Regel mehrere Bedingungen enthält, können Sie auswählen, welcher logische Operator sie verbindet.  
   - **UND**-Operator: Alle Bedingungen müssen erfüllt sein, um einen Datensatz in das Segment aufzunehmen. Verwenden Sie diese Option, wenn Sie Bedingungen für verschiedene Entitäten definieren.
   - **ODER**-Operator: Eine der Bedingungen muss erfüllt sein, um einen Datensatz in das Segment aufzunehmen. Verwenden Sie diese Option, wenn Sie mehrere Bedingungen für dieselbe Entität definieren.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regel mit zwei UND-Bedingungen.":::

   Bei Verwendung des ODER-Operators müssen alle Bedingungen auf Entitäten basieren, die im Beziehungspfad enthalten sind.

1. Erstellen Sie mehrere Regeln, um verschiedene Sätze von Kundendatensätzen zu erstellen. Sie können Gruppen kombinieren, um die Kunden einzuschließen, die für Ihren Geschäftsfall erforderlich sind. Insbesondere wenn Sie aufgrund des angegebenen Beziehungspfads keine Entität in eine Regel einschließen können, müssen Sie eine neue Regel erstellen, um Attribute daraus auszuwählen.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Fügen Sie einem Segment eine neue Regel hinzu, und wählen Sie den Mengenoperator.":::

   1. Wählen Sie **Regel hinzufügen** aus.
   1. Wählen Sie einen der eingestellten Operatoren aus: **Gesamtmenge**, **Überschneiden**, oder **Außer**.

      - **Vereinigen** vereinigt die beiden Gruppen.
      - **Überschneiden** überschneidet die beiden Gruppen. Nur Daten, die beiden Gruppen *angehören*, verbleiben in der vereinheitlichten Gruppe.
      - **Außer** kombiniert die beiden Gruppen. Nur Daten in Gruppe A, die *nicht* Daten in Gruppe B angehören, werden beibehalten.

1. Standardmäßig umfasst die Ausgabeentität alle Attribute von Kundenprofilen enthält, die den definierten Filtern entsprechen. In B-to-B bei Verwendung der *ContactProfile*-Entität ist die Konto-ID automatisch enthalten. Wenn ein Segment auf anderen Einheiten als der *Kunde*-Entität basiert oder weitere Attribute aus *ContactProfile* einschließen will, wählen Sie **Projektattribute**, um der Ausgabeentität weitere Attribute dieser Entitäten hinzuzufügen.
 
   Beispiel: Ein Segment basiert auf einer Entität, die Kaufdaten enthält, die sich auf die *Kunde* Entität bezieht. Das Segment sucht nach allen Kunden aus Spanien, die im laufenden Jahr Waren gekauft haben. Sie können Attribute wie den Preis der Ware oder das Kaufdatum an alle übereinstimmenden Kundendatensätze in der Ausgabeentität anhängen. Diese Informationen können nützlich sein, um saisonale Korrelationen zu den Gesamtausgaben zu analysieren.

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Beispiel für im Seitenbereich ausgewählte projizierte Attribute, die der Ausgabeentität hinzugefügt werden sollen.":::
 
   Eine Beispielausgabe für ein Segment basierend auf Geschäftskonten mit projizierten Attributen von Kontakten könnte wie folgt aussehen:

   |Kennung  |Firmenname  |Einnahmen  |Kontaktname  | Rolle des Kontakts|
   |---------|---------|---------|---------|---|
   |10021     | Contoso | 100K | [Abbie Moss, Ruth Soto]  | [CEO, Beschaffungsmanagement]

   > [!NOTE]
   > - **Projektattribute** funktioniert nur für Entitäten, die eine 1:n-Beziehung mit der *Kundenentität* oder *ContactProfile* Entität haben. Beispielsweise kann ein Kunde mehrere Abonnements haben.
   > - Wenn das Attribut, das Sie projizieren möchten, mehr als einen Hop von der Entität *Kunde* oder *ContactProfile* entfernt ist, wie durch die Beziehung definiert, sollte dieses Attribut in jeder Regel der Segmentabfrage verwendet werden, die Sie erstellen.
   > - Wenn das Attribut, das Sie projizieren möchten, nur einen Hop von der Entität *Kunde* oder *ContactProfile* entfernt ist, muss dieses Attribut nicht in jeder Regel der Segmentabfrage vorhanden sein, die Sie erstellen.
   > - **Projizierte Attribute** werden bei Verwendung von festgelegten Operatoren berücksichtigt.

1. Wählen Sie **Ausführen**, um Ihr Segment zu erstellen. Wählen Sie **Speichern** aus, wenn Sie die aktuelle Konfiguration beibehalten und das Segment später ausführen möchten. Die Seite **Segmente** wird angezeigt.

### <a name="segment-builder-tips"></a>Segmentgenerator Tipps

Beachten Sie beim Erstellen eines Segments mit dem Segment Builder die folgenden Tipps:

- Der Segmentgenerator schlägt beim Festlegen der Operatoren für die Bedingungen keine gültigen Werte aus Entitäten vor. Sie können zu **Daten** > **Entitäten** wechseln, und die Entitätsdaten herunterladen, um zu sehen, welche Werte verfügbar sind.
- Mit datumsbasierten Bedingungen können Sie zwischen festen Datumsangaben und einem variablen Datumsbereich wechseln.
- Wenn Sie mehrere Regeln für Ihr Segment haben, wird neben der Regel, die Sie bearbeiten, eine vertikale blaue Linie angezeigt.
- Sie können Regeln und Bedingungen an andere Stellen in der Segmentdefinition verschieben. Wählen Sie die vertikalen Auslassungspunkte (&vellip;) neben einer Regel oder Bedingung und wählen Sie aus, wie und wohin sie verschoben werden soll.
- Mit den Steuerelementen **Rückgängig machen** und **Wiederholen** in der Befehlsleiste können Sie Änderungen rückgängig machen.
- Nachdem Sie ein Segment erstellt haben, können Sie bei einigen Segmenten [die Nutzung des Segments verfolgen](segments.md#track-usage-of-a-segment).

## <a name="next-steps"></a>Nächste Schritte,

[Exportieren eines Segments](export-destinations.md) und erkunden der [Kundenkartenintegration](customer-card-add-in.md), um Segmente in anderen Anwendungen zu verwenden.

[!INCLUDE [footer-include](includes/footer-banner.md)]
