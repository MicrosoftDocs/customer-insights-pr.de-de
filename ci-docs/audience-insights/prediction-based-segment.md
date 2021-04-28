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
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741428"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="5c3a6-103">Erstellen Sie ein Segment basierend auf einem Vorhersage-Modell (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="5c3a6-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="5c3a6-104">Die Ergebnisse von Vorhersagen gelten manchmal nur für eine Teilmenge Ihrer Kunden.</span><span class="sxs-lookup"><span data-stu-id="5c3a6-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="5c3a6-105">Erhöhen Sie die Personalisierung von Empfehlungen, indem Sie Segmente aus Ergebnissen von Vorhersage-Modellen erstellen.</span><span class="sxs-lookup"><span data-stu-id="5c3a6-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="5c3a6-106">Beispielsweise möchten Sie Kunden, die eine bestimmte Art von Service bevorzugen, möglicherweise spezifische Empfehlungen geben.</span><span class="sxs-lookup"><span data-stu-id="5c3a6-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="5c3a6-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5c3a6-107">Prerequisites</span></span>

- <span data-ttu-id="5c3a6-108">Mindestens die [Berechtigung "Mitwirkender"](permissions.md) in Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5c3a6-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="5c3a6-109">Eine in Customer Insights konfigurierte Produktempfehlung, Transaktionsabwanderung, Abonnementabwanderung oder ein Modell für den Wert der Kundenlebensdauer.</span><span class="sxs-lookup"><span data-stu-id="5c3a6-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="5c3a6-110">Überprüfen Sie die Anforderungen zum Einrichten der verschiedenen Modelle:</span><span class="sxs-lookup"><span data-stu-id="5c3a6-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="5c3a6-111">Produktempfehlungsmodell</span><span class="sxs-lookup"><span data-stu-id="5c3a6-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="5c3a6-112">Modell für Abonnementabwanderung</span><span class="sxs-lookup"><span data-stu-id="5c3a6-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="5c3a6-113">Abwanderungsmodell für Transaktionen</span><span class="sxs-lookup"><span data-stu-id="5c3a6-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="5c3a6-114">Kundenlebensdauerwert-Modell</span><span class="sxs-lookup"><span data-stu-id="5c3a6-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="5c3a6-115">Erstellen von Kundensegmenten auf Basis von Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="5c3a6-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="5c3a6-116">Gehen Sie zu **Intelligenz** > **Vorhersagen** und wählen Sie die Registerkarte **Meine Vorhersagen**.</span><span class="sxs-lookup"><span data-stu-id="5c3a6-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="5c3a6-117">Wählen Sie die vertikalen Ellipsen neben dem Modell aus, das Sie überprüfen möchten, und wählen Sie **Ansicht** aus.</span><span class="sxs-lookup"><span data-stu-id="5c3a6-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="5c3a6-118">Wählen Sie auf der Ergebnisseite **Segment erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="5c3a6-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="5c3a6-119">Weitere Informationen zur Ergebnisseite finden Sie im Artikel zum Modell.</span><span class="sxs-lookup"><span data-stu-id="5c3a6-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Screenshot der Vorhersage-Ergebnisseite mit Hervorhebung der Aktion „Segment erstellen“.":::

1. <span data-ttu-id="5c3a6-121">Erstellen Sie ein neues Segment basierend auf der Ausgabeentität des gewählten Modells.</span><span class="sxs-lookup"><span data-stu-id="5c3a6-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="5c3a6-122">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Segmenten](segments.md).</span><span class="sxs-lookup"><span data-stu-id="5c3a6-122">For more information, see [Create and manage segments](segments.md).</span></span>