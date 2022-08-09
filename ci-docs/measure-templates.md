---
title: Kennzahlen aus Vorlagen erstellen
description: Definieren Sie Kennzahlen mithilfe von Vorlagen für gängige Anwendungsfälle.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170772"
---
# <a name="create-measures-from-templates"></a>Kennzahlen aus Vorlagen erstellen

Verwenden Sie vordefinierte Vorlagen häufig verwendeter [Kennzahlen](measures.md), um sie zu erstellen. Vorlagen bauen auf zugeordneten Daten aus der *Einheitliche Aktivität*-Entität auf. Stellen Sie also sicher, dass Sie [Kundenaktivitäten](activities.md) konfiguriert haben, bevor Sie eine Kennzahl aus einer Vorlage erstellen.

Kennzahlenvorlagen werden nur in Umgebungen für **individuelle Kunden** unterstützt. Informationen zum Erstellen benutzerdefinierter Kennzahlen oder um Kennzahlen für B2B zu erstellen finden Sie unter [Kennzahlen-Builder verwenden](measure-builder.md).

Verfügbare Kennzahlenvorlagen:
- Durchschnittlicher Transaktionswert (ATV)
- Transaktionswert insgesamt
- Durchschnittlicher täglicher Umsatz
- Durchschnittlicher monatlicher Umsatz
- Durchschnittlicher Jahresumsatz
- Transaktionsanzahl
- Erhaltene Treuepunkte
- Eingelöste Treuepunkte
- Treuepunktebilanz
- Aktive Kundenlebensdauer
- Dauer der Treuemitgliedschaft
- Zeit seit dem letzten Kauf

## <a name="build-a-new-measure-using-a-template"></a>Eine neue Kennzahl mithilfe einer Vorlage erstellen

1. Gehen Sie zu **Kennzahlen**.

1. Wählen Sie **Neu** und dann **Vorlage auswählen** aus.

   :::image type="content" source="media/measure-use-template.png" alt-text="Screenshot des Dropdown-Menüs beim Erstellen einer neuen Kennzahl mit Hervorhebung auf der Vorlage.":::

1. Suchen Sie die Vorlage, die Ihren Anforderungen entspricht, und wählen Sie **Vorlage auswählen** aus.

1. Überprüfen Sie die erforderlichen Daten und wählen Sie **Los geht's** aus, wenn Sie alle Daten an Ort und Stelle haben.

1. Wählen Sie **Details bearbeiten** neben Messungsname. Benennen Sie die Messung. Fügen Sie optional [Tags](work-with-tags-columns.md#manage-tags) zur Messung hinzu.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialogfeld „Details bearbeiten“":::

1. Wählen Sie **Fertig** aus.

1. Im Abschnitt **Zeitraum festlegen** definieren Sie den Zeitrahmen der zu verwendenden Daten. Wählen Sie aus, ob die neue Kennzahl das gesamte DataSet abdecken soll, indem Sie **Immer** oder **Spezifischen Zeitraum** auswählen, wenn Sie möchten, dass sich die Kennzahl nur auf einen bestimmten Zeitraum bezieht.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Screenshot mit dem Abschnitt zum Zeitraum beim Konfigurieren einer Kennzahl aus einer Vorlage.":::

1. Wählen Sie im nächsten Abschnitt **Daten hinzufügen** aus, um die Aktivitäten auszuwählen und die entsprechenden Daten von Ihrer *Einheitliche Aktivität*-Entität zuzuordnen.

    1. Schritt 1 von 2: Unter **Aktivitätstyp** wählen Sie den Typ der Entität, die Sie verwenden möchten. Für **Aktivitäten** wählen Sie die Objekte aus, die Sie zuordnen möchten, und klicken Sie auf **Weiter**.
    1. Schritt 2 von 2: Wählen Sie das Attribut aus der *Einheitliche Aktivität*-Entität für die von der Formel geforderte Komponente aus. Für den durchschnittlichen Transaktionswert ist dies beispielsweise das Attribut, das den Transaktionswert darstellt. Für **Aktivitätszeitstempel** wählen Sie das Attribut aus der Entität *Einheitliche Aktivität* aus, das Datum und Uhrzeit der Aktivität darstellt.
    1. Wählen Sie **Save** (Speichern).

    Sobald die Datenzuordnung erfolgt ist, wird der Status als **Abgeschlossen** und der Name der zugeordneten Aktivitäten und Attribute angezeigt.

1. Wählen Sie **Ausführen** aus, um die Ergebnisse der Messung zu berechnen. Wählen Sie **Entwurf speichern** aus, wenn Sie die aktuelle Konfiguration beibehalten und die Kennzahlmessung später ausführen möchten. Die Seite **Kennzahlen** wird angezeigt.

## <a name="next-step"></a>Nächster Schritt

Verwenden Sie vorhandene Maßnahmen, um [ein Kundensegment](segments.md) zu erstellen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
