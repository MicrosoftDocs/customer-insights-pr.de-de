---
title: Erstellen von Segmenten auf Basis von Vorhersagenmodellen
description: Erstellen Sie Segmente basierend auf der Ausgabeentität eines Vorhersage-Modells.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ed9c6247a1f9148628dc9b5217484e98a576224e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610419"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Erstellen Sie ein Segment basierend auf einem Vorhersage-Modell (Vorschauversion)

Die Ergebnisse von Vorhersagen gelten manchmal nur für eine Teilmenge Ihrer Kunden. Erhöhen Sie die Personalisierung von Empfehlungen, indem Sie Segmente aus Ergebnissen von Vorhersage-Modellen erstellen. Beispielsweise möchten Sie Kunden, die eine bestimmte Art von Service bevorzugen, möglicherweise spezifische Empfehlungen geben.

## <a name="prerequisites"></a>Anforderungen

- Mindestens die [Berechtigung "Mitwirkender"](permissions.md) in Customer Insights.

- Eine in Customer Insights konfigurierte Produktempfehlung, Transaktionsabwanderung, Abonnementabwanderung oder ein Modell für den Wert der Kundenlebensdauer. Überprüfen Sie die Anforderungen zum Einrichten der verschiedenen Modelle:

  - [Produktempfehlungsmodell](predict-product-recommendation.md)
  - [Modell für Abonnementabwanderung](predict-subscription-churn.md)
  - [Abwanderungsmodell für Transaktionen](predict-transactional-churn.md)
  - [Kundenlebensdauerwert-Modell](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Erstellen von Kundensegmenten auf Basis von Vorhersagen

1. Gehen Sie zu **Intelligenz** > **Vorhersagen** und wählen Sie die Registerkarte **Meine Vorhersagen**.

1. Wählen Sie das Modell aus, das Sie bewerten möchten, und wählen Sie **Anzeigen** aus.

1. Wählen Sie auf der Ergebnisseite **Segment erstellen** aus. Weitere Informationen zur Ergebnisseite finden Sie im Artikel zum Modell.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Screenshot der Vorhersage-Ergebnisseite mit Hervorhebung der Aktion „Segment erstellen“.":::

1. Erstellen Sie ein neues Segment mithilfe der Attribute aus der Ausgabeentität des gewählten Modells. Weitere Informationen finden Sie unter [Erstellen und Verwalten von Segmenten](segments.md).

> [!TIP]
> Sie können auch ein Segment für ein Vorhersagemodell aus der Seite **Segmente** erstellen, indem Sie **Neu** und dann **Erstellen aus** > **Intelligenz** auswählen. Weitere Informationen finden Sie unter [Ein neues Segment mit Schnellsegmenten erstellen](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
