---
title: Anzeigen und Erstellen von Segmenten
description: So erstellen, bearbeiten, löschen und verwenden Sie Segmente.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: cedcd58373428dd35ba29ce8fdd00007257f8fa59b0d25bc584b4e832df13604
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036147"
---
# <a name="view-and-create-segments"></a>Anzeigen und Erstellen von Segmenten

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Mit Segmenten können Sie Teilmengen von Besuchern anhand von Merkmalen oder Interaktionen auf der Website identifizieren. Mit Segmenten können Sie Filter anwenden und diese Teilmengen analysieren. Die Analyse kann helfen, Trends in Ihrem Unternehmen zu untersuchen und darauf zu reagieren. 

:::image type="content" source="media/segments-page.png" alt-text="Screenshot der Anwendung für Interaktionserkenntnisse mit der Liste bestehender Segmente in einem Arbeitsbereich.":::

## <a name="view-segments"></a>Anzeigen von Segmenten

1. Wechseln Sie zu **Daten** im linken Navigationsbereich. 

1. Wählen Sie die Registerkarte **Segmente** aus, um eine Liste aller Segmente im Arbeitsbereich anzuzeigen. 

## <a name="create-a-segment"></a>Segment erstellen

Segmente bestehen aus Regeln und Bedingungen, die mit logischen Operatoren verbunden sind. Bedingungen wenden Filter auf eine ausgewählte Dimension an. Jedes Segment kann bis zu fünf Dimensionen verwenden.

Das folgende Beispiel zeigt ein Segment mit zwei Bedingungen in einer Regel. Es filtert alle Ereignisse auf der Website, bei denen Chrome als Browser und die Betriebssysteme iOS oder Android verwendet wurden.

:::image type="content" source="media/segment-sample.png" alt-text="Beispielsegmente mit zwei Bedingungen in einer Regel zum Filtern nach Ereignissen auf der Website.":::

In diesem Abschnitt wird beschrieben, wie Sie ein *leeres Segment* von Grund auf neu erstellen.

1. Wechseln Sie zu **Daten** > **Segmente**.

1. Wählen Sie **Neues Segment**.

1. Wählen Sie in der **Ressourcenbibliothek** das Attribut aus, nach dem Sie filtern möchten. Derzeit können Sie nur Segmente basierend auf Dimensionen erstellen.

1. Wählen Sie einen Operator und einen Wert für das ausgewählte Attribut. Die folgenden Vorgänge werden nicht unterstützt.
   - **Ist**: Erfordert eine genaue Übereinstimmung, um Werte einzuschließen. Verwendet **Entspricht** für einen einzelnen Wert oder **Eines von** für mehrere Werte.
   - **Ist nicht**: Erfordert eine genaue Übereinstimmung, um Werte auszuschließen. Verwendet **Entspricht** für einen einzelnen Wert oder **Eines von** für mehrere Werte.
   - **Beginnt mit**: Eine Zeichenfolge, mit der die übereinstimmenden Werte beginnen.
   - **Endet mit**: Eine Zeichenfolge, mit der die übereinstimmenden Werte enden.
   - **Enthält**: Eine Zeichenfolge, die in übereinstimmenden Werten enthalten ist.

1. Um weitere Bedingungen zu einer Gruppe hinzuzufügen, können Sie zwei logische Operatoren verwenden. Projizierte Attribute werden bei Verwendung von festgelegten Operatoren berücksichtigt.
   - **AND** Operator: Beide Bedingungen müssen als Teil des Segmentierungsprozesses erfüllt sein. Diese Option ist am nützlichsten, wenn Sie Bedingungen für verschiedene Entitäten definieren.
   - **OR**-Operator: Jede der beiden Bedingungen muss als Teil des Segmentierungsprozesses erfüllt sein. Diese Option ist am nützlichsten, wenn Sie mehrere Bedingungen für dieselbe Entität definieren.

1. Wählen Sie **Speichern** aus und geben Sie dem Segment einen Namen. 

Das Segment wird auf der Seite „Segmente“ aufgelistet und Sie können es auf alle Berichte und Verkaufstrichter im Arbeitsbereich anwenden.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Verwenden eines Segments in einem Bericht oder Verkaufstrichter

Sie können Segmente auf einen Bericht oder einen Verkaufstrichter anwenden, um sie basierend auf den Bedingungen im Segment zu filtern. Sie können jedoch keine Segmente auf den Echtzeit-Nutzungsbericht anwenden.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Ein Bericht zu Seitenaufrufen mit einer erweiterten Dropdown-Liste zur Auswahl der anzuwendenden Segmente.":::

Um ein Segment anzuwenden, öffnen Sie den Bericht oder Verkaufstrichter. Wählen Sie **Bedingung hinzufügen** aus und wählen Sie dann **Nach Segment filtern** aus. Wählen Sie aus der Liste das Segment aus, das Sie anwenden möchten. Das Segment wird auf den Bericht angewendet. Wenn ein Diagramm das Segment nicht unterstützt, wird ein Fehler angezeigt.
 
Sie können *bis zu drei Segmente* auf einen Bericht oder Verkaufstrichter anwenden.

## <a name="edit-a-segment"></a>Bearbeiten eines Segments

1. Wechseln Sie zu **Daten** > **Segmente**.
1. Wählen Sie das Segment in der Liste aus, um es zu öffnen. 
1. Ändern oder fügen Sie Werte nach Bedarf hinzu.
1. Wählen Sie **Speichern**, um Ihre Änderungen zu übernehmen.

## <a name="change-the-name-of-a-segment"></a>Ändern des Segmentnamens

1. Wechseln Sie zu **Daten** > **Segmente**.
1. Wählen Sie in der Segmentliste **Mehr [...]** aus. 
1. Wählen Sie aus der Dropdown-Liste **Namen bearbeiten**.
1. Geben Sie den neuen Namen ein und wählen Sie **Umbenennen** aus.

## <a name="delete-a-segment"></a>Löschen eines Segments

1. Wechseln Sie zu **Daten** > **Segmente**.
1. Wählen Sie in der Segmentliste **Mehr [...]** aus. 
1. Wählen Sie aus der Dropdown-Liste **löschen**.
1. Wählen Sie zum Bestätigen **Löschen** aus.

[!INCLUDE[footer-include](../includes/footer-banner.md)]