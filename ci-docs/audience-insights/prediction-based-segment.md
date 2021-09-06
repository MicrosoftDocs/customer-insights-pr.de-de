---
title: Segmente basierend auf der Ausgabe von Vorhersage
description: Erstellen Sie Segmente basierend auf der Ausgabeentität eines Vorhersage-Modells.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b89754aea2b0da33f27dea5b26d212920f0c090885f951a37cf42ff11c7b6e93
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036418"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Erstellen Sie ein Segment basierend auf einem Vorhersage-Modell (Vorschau)

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

1. Wählen Sie die vertikalen Ellipsen neben dem Modell aus, das Sie überprüfen möchten, und wählen Sie **Ansicht** aus.

1. Wählen Sie auf der Ergebnisseite **Segment erstellen** aus. Weitere Informationen zur Ergebnisseite finden Sie im Artikel zum Modell.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Screenshot der Vorhersage-Ergebnisseite mit Hervorhebung der Aktion „Segment erstellen“.":::

1. Erstellen Sie ein neues Segment basierend auf der Ausgabeentität des gewählten Modells. Weitere Informationen finden Sie unter [Erstellen und Verwalten von Segmenten](segments.md).