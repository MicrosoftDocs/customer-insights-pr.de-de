---
title: 'Einfache Segmente mit einem Operator erstellen: Schnelles Segment'
description: Erstellen Sie einfache Segmente, um sie auf der Grundlage verschiedener Attribute zu gruppieren.
ms.date: 03/25/2022
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
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171133"
---
# <a name="create-simple-segments-with-quick-segments"></a>Einfache Segmente mit einem Operator erstellen: Schnelles Segment

Mit schnellen Segmenten können Sie schnell einfache Segmente mit einem einzigen Operator erstellen, um schnellere Einblicke zu erhalten. Schnelle Sgmente werden nur in Umgebungen für **individuelle Kunden** unterstützt.

## <a name="create-a-new-segment-with-quick-segments"></a>Einfache neue Segmente mit einem Operator erstellen: Schnelles Segment

1. Gehen Sie zu **Segmente**.

1. Wählen Sie **Neu** > **Erstellen von** aus.
   - Wählen Sie die Option **Profile**, um ein Segment zu erstellen, das auf der *einheitlichen Kundenentität* basiert.
   - Wählen Sie die Option **Maßnahmen** zum Erstellen eines Segments um zuvor erstellte Kennzahlen.
   - Wählen Sie die Option **Intelligenz** zum Erstellen eines Segments für eine der Ausgabeentitäten aus, die Sie mit einer der beiden Funktionen **Vorhersagen** oder **Benutzerdefinierte Modelle** generiert haben.

1. Wählen Sie im Dialogfeld **Neues schnelles Segment** ein Attribut aus der Dropdownliste **Feld** aus. Basierend auf Ihrer Auswahl liefert das System unterschiedliche Werte.
   - Für kategoriale Felder werden 10 Top-Kundenzahlen angezeigt. Wählen Sie einen **Wert** und wählen Sie **Überprüfung**.
   - Bei einem numerischen Attribut zeigt das System an, welcher Attributwert unter das Perzentil des jeweiligen Kunden fällt. Wählen Sie einen **Bediener** und einen **Wert**, dann wählen Sie **Review**.

1. Das System liefert Ihnen eine **geschätzte Segmentgröße**. Wählen Sie, ob Sie das von Ihnen definierte Segment generieren oder zurückgehen, um ein anderes Feld auszuwählen.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Name und Schätzung für ein schnelles Segment.":::

1. Geben Sie einen **Namen** und **Ausgabeentitätsname** für Ihr Segment ein. Fügen Sie optional [Tags](work-with-tags-columns.md#manage-tags) hinzu.

1. Wählen Sie **Speichern**, um Ihr Segment zu erstellen. Die Seite **Segmente** wird angezeigt.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Nächste Schritte,

[Exportieren eines Segments](export-destinations.md) und erkunden der [Kundenkartenintegration](customer-card-add-in.md), um Segmente in anderen Anwendungen zu verwenden.

[!INCLUDE [footer-include](includes/footer-banner.md)]
