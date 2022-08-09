---
title: Übereinstimmungsbedingungen für die Datenvereinheitlichung
description: Gleichen Sie Entitäten ab, um vereinheitlichte Kundenprofile zu erstellen.
recommendations: false
ms.date: 05/05/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: e3e4e37d5b4c9caf2520a789d5f78ef33b491793
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139702"
---
# <a name="match-conditions-for-data-unification"></a>Übereinstimmungsbedingungen für die Datenvereinheitlichung

Dieser Schritt der Vereinheitlichung definiert die Abgleichreihenfolge und -regeln für den entitätsübergreifenden Abglecih. Dieser Schritt erfordert mindestens zwei Entitäten.

> [!NOTE]
> Sobald Sie Ihre Vergleichsbedingungen erstellt und **Weiter** ausgewählt haben, können Sie eine ausgewählte Entität oder ein ausgewähltes Attribut nicht entfernen. Wählen Sie bei Bedarf **Zurück**, um die ausgewählten Entitäten und Attribute zu überprüfen, bevor Sie fortfahren.

## <a name="include-enriched-entities-preview"></a>Angereicherte Entitäten einschließen (Vorschauversion)

Wenn Sie Entitäten auf der Ebene der Datenquelle angereichert haben, um Ihre Vereinigungsergebnisse zu verbessern, wählen Sie sie aus. Weitere Informationen finden Sie unter [Anreicherungen für Datenquellen](data-sources-enrichment.md). Wenn Sie angereicherte Entitäten auf der Seite **Doppelte Datensätze** ausgewählt haben, müssen Sie sie nicht erneut auswählen.

1. Wählen Sie auf der Seite **Abgleich-Bedingungen** oben auf der Seite **Angereicherte Entitäten verwenden**.

1. Von dem Bereich **Verwenden Sie angereicherte Entitäten** wählen Sie im Bereich eine oder mehrere angereicherte Entitäten aus.

1. Wählen Sie **Fertig** aus.

## <a name="specify-the-match-order"></a>Geben Sie die Reihenfolge der Übereinstimmung an

Jede Übereinstimmung vereint zwei oder mehr Entitäten zu einer einzigen konsolidierten Entität. Gleichzeitig werden die eindeutigen Kundendatensätze geführt. Die Übereinstimmungsreihenfolge gibt die Reihenfolge an, in der das System versucht, die Datensätze abzugleichen.

> [!IMPORTANT]
> Die erste Entität in der Liste ist der Primärschlüssel. Die primäre Entität dient als Grundlage für Ihr DataSet der vereinheitlichten Profile. Weitere ausgewählte Entitäten werden dieser Entität hinzugefügt.
>
> Wichtige Überlegungen:
>
> - Wählen Sie die Entität mit den vollständigsten und zuverlässigsten Profildaten über Ihre Kunden als primäre Entität aus.
> - Wählen Sie die Entität, die mehrere Attribute mit anderen Entitäten gemeinsam hat (z. B. Name, Telefonnummer oder E-Mail-Adresse) als primäre Entität.

1. Auf der Seite **Abgleich-Bedingungen** verwenden Sie die Aufwärts- und Abwärtspfeile, um die Entitäten in der gewünschten Reihenfolge zu verschieben, oder ziehen Sie sie per Drag-and-Drop. Wählen Sie zum Beispiel **Contacts:eCommerce** als primäre Entität und **CustomerLoyalty:Loyalty** als zweite Entität.

1. Um alle Datensätze in der Entität als eindeutigen Kunden zu führen, unabhängig davon, ob eine Übereinstimmung gefunden wird, wählen Sie **Alle Datensätze berücksichtigen**. Alle Datensätze in dieser Entität, die nicht mit Datensätzen in anderen Entitäten übereinstimmen, werden in das einheitliche Profil aufgenommen. Datensätze ohne Übereinstimmung werden Singletons genannt.
  
Die primäre Entität *Contacts:eCommerce* wird mit der nächsten Entität *CustomerLoyalty:Loyalty* abgeglichen. Das DataSet, das sich aus dem ersten Vergleichsschritt ergibt, wird mit der folgenden Entität abgeglichen, wenn Sie mehr als zwei Entitäten haben.

:::image type="content" source="media/m3_match.png" alt-text="Screenshot der ausgewählten Abgleichreihenfolge für die Entitäten." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Regeln für das abgeglichene Paar definieren

Übereinstimmungsregeln legen die Logik fest, nach der ein bestimmtes Paar von Entitäten abgeglichen wird. Eine Regel besteht aus einer oder mehreren Bedingungen.

Die Warnung neben einem Entitätsnamen bedeutet, dass für ein Zuordnungspaar keine Vergleichsregel definiert ist.

1. Wählen Sie **Regel hinzufügen** für ein Entitätspaar zum Definieren von Vergleichsregeln aus.

1. In dem Bereich **Regel hinzufügen** konfigurieren Sie die Bedingungen für die Regel.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Screenshot des Bereichs „Regel hinzufügen“.":::

   - **Entität/Feld auswählen (erste Zeile)**: Wählen Sie eine zugehörige Entität und ein Attribut aus, um eine Datensatzeigenschaft anzugeben, die für einen Kunden wahrscheinlich eindeutig ist. Zum Beispiel eine Telefonnummer oder eine E-Mail-Adresse. Vermeiden Sie Übereinstimmungen nach Attributen des Aktivitätstyps. Beispielsweise findet eine Kauf-ID wahrscheinlich keine Übereinstimmung in anderen Datensatztypen.

   - **Entität/Feld auswählen (zweite Zeile)**: Wählen Sie ein Attribut aus, das sich auf das Attribut der in der ersten Zeile angegebenen Entität bezieht.

   - **Normalisieren**: Wählen Sie aus den folgenden Normalisierungsoptionen für die ausgewählten Attribute.
     - **Ziffern**: Konvertiert andere Zahlensysteme, z. B. römische Ziffern, in arabische Ziffern. *VIII* wird *8*.
     - **Symbole**: Entfernt alle Symbole und Sonderzeichen. *Head&Shoulder* wird *HeadShoulder*.
     - **Text in Kleinbuchstaben**: Konvertiert alle Zeichen in Kleinbuchstaben. *ALL CAPS und Erster Buchstabe groß* wird *all caps und erster buchstabe groß*.
     - **Typ (Telefon, Name, Adresse, Organisation)**: Standardisiert Namen, Titel, Telefonnummern, Adressen und Organisationen.
     - **Unicode in ASCII**: Konvertiert die Unicode-Notation in ASCII-Zeichen. */u00B2* wird *2*.
     - **Leerzeichen**: Entfernt alle Leerzeichen. *Hallo   Welt* wird *Hallo Welt*.

   - **Präzision**: Legen Sie die Genauigkeit fest, die für diese Bedingung gelten soll.
     - **Basic**: Wählen Sie *Niedrig (30 %)*, *Mittel (60 %)*, *Hoch (80 %)* und *Genau (100 %)*. Wählen Sie **Genau**, um nur Datensätze abzugleichen, die zu 100 Prozent übereinstimmen.
     - **Benutzerdefiniert**: Legen Sie einen Prozentsatz fest, mit dem Datensätze übereinstimmen müssen. Das System stimmt nur mit Datensätzen überein, die diesen Schwellenwert überschreiten.

   - **Name**: Der Name für die Regel.

1. Um Entitäten nur abzugleichen, wenn Attribute mehrere Bedingungen erfüllen, wählen Sie **Hinzufügen** > **Bedingung hinzufügen**, um einer Vergleichsregel weitere Bedingungen hinzuzufügen. Bedingungen sind mit einem logischen UND-Operator verbunden und werden daher nur ausgeführt, wenn alle Bedingungen erfüllt sind.

1. Berücksichtigen Sie optional erweiterte Optionen wie [Ausnahmen](#add-exceptions-to-a-rule) oder [benutzerdefinierte Vergleichsbedingungen](#specify-custom-match-conditions).

1. Wählen Sie **Fertig**, um die Regel abzuschließen.

1. Optional [weitere Regeln hinzufügen](#add-rules-to-a-match-pair).

1. Klicken Sie auf **Weiter**.

> [!div class="nextstepaction"]
> [Nächster Schritt: Felder vereinheitlichen](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Fügen Sie einem abgeglichenen Paar Regeln hinzu

Übereinstimmungsregeln repräsentieren Sätze von Bedingungen. Um Entitäten nach Bedingungen abzugleichen, die auf verschiedenen Attributen basieren, fügen Sie weitere Regeln hinzu.

1. Wählen Sie **Regel hinzufügen** für die Entität, der Sie Regeln hinzufügen möchten.

1. Befolgen Sie die Schritte in [Definieren Sie Regeln für Übereinstimmungspaare](#define-rules-for-match-pairs).

> [!NOTE]
> Die Reihenfolge der Regeln ist wichtig. Der Abgleichalgorithmus versucht, basierend auf der ersten Regel eine Übereinstimmung mit einem bestimmten Kundendatensatz zu finden, und fährt mit der zweiten Regel nur fort, wenn mit der ersten Regel keine Übereinstimmungen identifiziert wurden.

## <a name="advanced-options"></a>Erweiterte Optionen

### <a name="add-exceptions-to-a-rule"></a>Einer Regel Ausnahmen hinzufügen

In den meisten Fällen führt der Entitätsvergleich zu eindeutigen Kundenprofilen mit konsolidierten Daten. Um seltene Fälle von falsch positiven und falsch negativen Ergebnissen dynamisch anzugehen, können Sie Ausnahmen für eine Vergleichsregel definieren. Ausnahmen werden nach Verarbeitung der Vergleichsregeln angewendet und vermeiden den Vergleich aller Datensätze, die die Ausnahmekriterien erfüllen.

Wenn Ihre Vergleichsregel beispielsweise Nachname, Stadt und Geburtsdatum kombiniert, würde das System Zwillinge mit demselben Nachnamen, die in derselben Stadt leben, als dasselbe Profil identifizieren. Sie können eine Ausnahme angeben, die die Profile nicht vergleicht, wenn der Vorname in den von Ihnen kombinierten Entitäten nicht identisch sind.

1. Im Bereich **Regel bearbeiten** wählen Sie **Hinzufügen** > **Ausnahme hinzufügen**.

1. Geben Sie die Ausnahmekriterien an.

1. Wählen Sie **Abgeschlossen** und speichern Sie die Regel.

### <a name="specify-custom-match-conditions"></a>Benutzerdefinierte Vergleichsbedingungen angeben

Sie können Bedingungen angeben, die die standardmäßige Vergleichslogik überschreiben. Die folgenden vier Optionen sind verfügbar:

|Option  |Beschreibung des Dataflows |Beispiel  |
|---------|---------|---------|
|Immer übereinstimmen     | Definiert Werte, die immer übereinstimmen.         |  *Mike* und *MikeR* immer übereinstimmen.       |
|Nicht übereinstimmen     | Definiert Werte, die niemals übereinstimmen.        | *John* und *Jonathan* nie übereinstimmen.        |
|Benutzerdefinierte Umgehung     | Definiert Werte, die das System in der Übereinstimmungsphase immer ignorieren soll. |  Werte *11111* und *Unbekannt* während der Übereinstimmung ignorieren.        |
|Alias-Zuordnung    | Definieren von Werten, die das System als denselben Wert betrachten soll.         | *Joe* als gleich zu *Joseph* betrachten.        |

1. Wählen Sie **Benutzerdefiniert** aus.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Schaltfläche „Benutzerdefiniert“":::

1. Wählen Sie **Benutzerdefinierter Typ** und **Vorlage herunterladen**. Sie benötigen für jede Vergleichsoption eine separate Vorlage.

1. Öffnen Sie die heruntergeladene Vorlagendatei und geben Sie die Details ein. Die Vorlage enthält Felder zur Angabe der Entität und der Primärschlüsselwerte der Entität, die beim benutzerdefinierten Vergleich verwendet werden sollen. Wenn Sie bespielsweise einen Primärschlüssel *12345* von der Entität *Vertrieb* möchten, die immer mit dem Primärschlüssel *34567* der Entität *Kontakt* übereinstimmt, füllen Sie die Vorlage aus:
    - Entität1: Verkauf
    - Entity1Key: 12345
    - Entität2: Kontakt
    - Entity2Key: 34567

   Dieselbe Vorlagendatei kann benutzerdefinierte Match-Datensätze von mehreren Entitäten angeben.

   Wenn Sie eine benutzerdefinierte Übereinstimmung für die Deduplizierung einer Entität angeben möchten, geben Sie dieselbe Entität wie Entität1 und Entität2 an und legen Sie die verschiedenen Primärschlüsselwerte fest.

1. Nachdem Sie alle Überschreibungen hinzugefügt haben, speichern Sie die Vorlagendatei.

1. Gehen Sie zu **Daten** > **Datenquellen** und nehmen Sie die Vorlagedateien als neue Entitäten auf.

1. Wählen Sie nach dem Hochladen der Dateien die Option **Benutzerdefiniert** erneut. Wählen Sie die erforderlichen Entitäten aus dem Dropdownmenü und dann **Fertig** aus.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Screenshot des Dialogfelds zum Auswählen von Überschreibungen für ein benutzerdefiniertes Übereinstimmungsszenario.":::

1. Das Anwenden der benutzerdefinierten Übereinstimmung hängt von der Übereinstimmungsoption ab, die Sie verwenden möchten.

   - Für **Immer übereinstimmen** oder **Nie übereinstimmen** fahren Sie mit dem nächsten Schritt fort.
   - Für **Umgehen** oder **Alias-Zuordnung** wählen Sie **Bearbeiten** in einer vorhandenen Übereinstimmungsregel aus oder erstellen Sie eine neue Regel. Wählen Sie im Normalisierungen-Dropdownmenü die Option **Benutzerdefinierte Umgehung** oder **Alias-Zuordnung** und dann **Fertig** aus.

1. Wählen Sie **Fertig** im Bereich **Benutzerdefiniert**, um die benutzerdefinierte Übereinstimmungskonfiguration anzuwenden.

> [!div class="nextstepaction"]
> [Nächster Schritt: Felder vereinheitlichen](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
