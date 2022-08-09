---
title: Segment-Insights (Vorschauversion)
description: Erhalten Sie Insights zu bestehenden Segmenten, um Unterschiede und Gemeinsamkeiten zu erkennen.
ms.date: 06/10/2020
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-insights
- customerInsights
ms.openlocfilehash: ccb33594a3a92e87d307f3300c77772ef8b4a82f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171002"
---
# <a name="segment-insights-preview"></a>Segment-Insights (Vorschauversion)

Entdecken Sie zusätzliche Informationen und Einblicke in Ihre vorhandenen Segmente. Finden Sie heraus, was zwei Segmente unterscheidet oder was sie gemeinsam haben.

## <a name="segment-overlap"></a>Segment-Überschneidung

Die Segmentüberlappungsanalyse zeigt, wie viele und welche Kunden zwei oder mehr Segmenten gemeinsam haben. Zum Beispiel, wie sich ein Segment häufiger Kunden mit einem Segment überschneidet, das Kunden enthält, die mit Ihrem Service oder Produkt zufrieden sind.
Sie können auch analysieren, wie sich die Überlappung für bestimmte Attribute ändert.

### <a name="run-an-overlap-analysis"></a>Führen Sie eine Überlappungsanalyse durch

1. Gehen Sie zu **Segmente** und wählen Sie die Registerkarte **Einblicke (Vorschauversion)**.

1. Wählen **Neu** und wählen Sie die Option **Überlappung** im Feld **Wählen Sie Insights-Typ**.

1. Wählen Sie die gewünschten Segmente aus und wählen Sie **Weiter**.

1. Wählen Sie optional ein oder mehrere interessierende Felder aus, um Überlappungen für jeden möglichen Feldwert zu analysieren, und wählen Sie **Weiter**.

1. Geben Sie einen Namen für Ihre Überlappungsanalyse, ein optionales Anzeigename und eine Beschreibung an.

1. Wählen Sie **Speichern**, um die Analyse zu starten. Die Überlappungsanalyse ist fertig, wenn sich der Status von Aktualisieren zu Erfolgreich ändert.

### <a name="view-and-optimize-an-overlap-analysis"></a>Anzeigen und Optimieren einer Überlappungsanalyse

1. Nach Abschluss der Analyse finden Sie Details zu diesem Einblick unter **Segmente** > **Erkenntnisse (Vorschauversion)**.

   :::image type="content" source="media/segment-overlap.png" alt-text="Erkenntnisdetails zur Segmentüberlappung.":::

1. Wählen Sie eine Erkenntnis aus, um die Analyseergebnisse anzuzeigen:

   - Die Anzahl der Mitglieder, die die für die Analyse ausgewählten Segmente überlappen.
   - Die Anzahl der Mitglieder, die in einem der Segmente enthalten sind, jedoch nicht in den übrigen Segmenten.
   - Wenn Sie beim Konfigurieren der Überlappungsanalyse Felder ausgewählt haben, finden Sie diese auf den entsprechenden Registerkarten. Sie können die Filter-Dropdown-Liste verwenden, um eine beliebige Attributebene auszuwählen, die von Interesse ist, und die Tabelle unten zeigt die entsprechenden Daten an.

## <a name="segment-differentiators"></a>Segment-Unterscheidungsmerkmale

Mithilfe von Segmentunterscheidungsmerkmalen können Sie herausfinden, was ein Segment vom Rest Ihrer Kunden oder von einem anderen Segment unterscheidet. Wählen Sie nur ein Segment aus, und das System identifiziert Profilattribute und Kennzahlen, die das ausgewählte Segment unterscheiden.

### <a name="run-a-differentiator-analysis"></a>Führen Sie eine Differenzierungsanalyse durch

1. Gehen Sie zu **Segmente** und wählen Sie die Registerkarte **Einblicke (Vorschauversion)**.

1. Wählen **Neu** und wählen Sie die Option **Unterscheidungsmerkmale** im Feld **Wählen Sie Insights-Typ**.

1. Wählen Sie das Segment aus, das Sie analysieren möchten als **Primärsegment** aus und wählen Sie **Weiter**.

1. Wählen Sie **Alle Kunden** oder ein **Sekundärsegment**, um Ihr primäres Segment mit zu vergleichen und wählen Sie **Weiter**.

1. Wählen Sie optional ein oder mehrere interessierende Felder aus, um die Analyse auf bestimmte Attribute zu konzentrieren, und wählen Sie **Weiter**.

1. Geben Sie einen Namen für Ihre Unterscheidungsmerkmaleanalyse, ein optionales Anzeigename und eine Beschreibung an.

1. Wählen Sie **Speichern**, um die Analyse zu starten. Die Unterscheidungsmerkmaleanalyse ist fertig, wenn sich der Status von Aktualisieren zu Erfolgreich ändert.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Anzeigen und Optimieren einer Differenzierungsanalyse

1. Nach Abschluss der Analyse wechseln Sie zu **Segmente** > **Erkenntnisse (Vorschauversion)**.

   :::image type="content" source="media/segment-differentiators.png" alt-text="Segmentdifferenziator Erkenntnisdetails.":::

1. Wählen Sie eine Erkenntnis aus, um die Analyseergebnisse anzuzeigen. Eine Unterscheidungsmerkmalanalyse enthält zwei Registerkarten. Die Registerkarte **Attribute** listet Profilattribute auf, die als Unterscheidungsmerkmale betrachtet werden. Die Registerkarte **Maßnahmen** listet Unterscheidungsmerkmale auf. Jede Registerkarte enthält die folgenden Details:

   - Rangliste der Unterscheidungsmerkmale, sortiert nach Differenzwerten.
   - Das **Differenzwert** für jedes Unterscheidungsmerkmal. Die Differenzbewertung gibt den Differenzgrad eines Attributs zwischen zwei Segmenten an. Je höher die Differenzbewertung ist, desto stärker unterscheiden sich die Attribute zwischen den beiden Segmenten. Wählen Sie einen Wert aus, um den Bereich **Differenzwert** mit den Werteverteilungen für dieses Attribut zu öffnen.

## <a name="manage-segment-insights"></a>Segmenterkenntnisse verwalten

Gehe zu **Segmente** > **Einblicke (Vorschau)** um Ihre Segmenteinblicke anzuzeigen und zu verwalten. Wählen Sie das Segmenteinblick aus, um verfügbare Aktionen anzuzeigen.

- **Anzeigen** die Einsichtsanalyse
- **Bearbeiten** des Einblicks, um seine Eigenschaften zu ändern
- **Aktualisierung** des Einblicks, um die Analyse erneut auszuführen
- **Umbenennen** des Einblicks
- **Löschen** des Einblicks

[!INCLUDE [footer-include](includes/footer-banner.md)]
