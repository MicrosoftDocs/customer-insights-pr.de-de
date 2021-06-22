---
title: Übersicht über unterstützte Vorhersageszenarien
description: Vorhersageszenarien und Optionen, die von der Anwendung Dynamics 365 Customer Insights abgedeckt werden.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095709"
---
# <a name="predictions-overview"></a><span data-ttu-id="8dd9e-103">Übersicht über Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="8dd9e-103">Predictions overview</span></span>

<span data-ttu-id="8dd9e-104">Dynamics 365 Customer Insights ist mit einer Vielzahl von Optionen ausgestattet, die KI und Machine Learning nutzen, um Daten vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="8dd9e-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="8dd9e-105">Sofort einsatzbereite Modelle</span><span class="sxs-lookup"><span data-stu-id="8dd9e-105">Out-of-box models</span></span>

<span data-ttu-id="8dd9e-106">Der einfachste Weg, um mit der Vorhersage von Daten zu beginnen, sind vordefinierte Modelle, die auch als sofort einsatzbereite Modelle bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="8dd9e-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="8dd9e-107">Sie benötigen nur bestimmte Daten und Strukturen, um schnell Erkenntnisse zu gewinnen.</span><span class="sxs-lookup"><span data-stu-id="8dd9e-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="8dd9e-108">Gegenwärtig sind die folgenden Modelle verfügbar:</span><span class="sxs-lookup"><span data-stu-id="8dd9e-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="8dd9e-109">[Langfristiger Kundenwert](predict-customer-lifetime-value.md) : Prognostiziert den potenziellen Umsatz eines Kunden während der gesamten Interaktion mit einem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="8dd9e-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="8dd9e-110">[Produktempfehlung](predict-product-recommendation.md) : Schlägt prädiktive Produktempfehlungen basierend auf dem Kaufverhalten und Kunden mit ähnlichen Kaufmustern vor.</span><span class="sxs-lookup"><span data-stu-id="8dd9e-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="8dd9e-111">[Abonnementabwanderung](predict-subscription-churn.md): Sagt vorher, ob das Risiko besteht, dass ein Kunde die Abonnementprodukte oder Services Ihres Unternehmens nicht länger verwendet.</span><span class="sxs-lookup"><span data-stu-id="8dd9e-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="8dd9e-112">[Transaktionsabwanderung](predict-transactional-churn.md) : Sagt vorher, ob ein Kunde Ihre Produkte oder Dienstleistungen in einem bestimmten Zeitrahmen nicht mehr kaufen wird.</span><span class="sxs-lookup"><span data-stu-id="8dd9e-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="8dd9e-113">Azure Machine Learning-Integration</span><span class="sxs-lookup"><span data-stu-id="8dd9e-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="8dd9e-114">Wenn eine Organisation bereits Machine Learning-Szenarien basierend auf Azure Machine Learning-Experimenten verwendet, hilft das Feature für benutzerdefinierte Modelle in Customer Insights, alles zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="8dd9e-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="8dd9e-115">Erstellen Sie Workflows, die Ihnen bei der Auswahl der Daten helfen, aus denen Sie Erkenntnisse generieren möchten, und bei der Zuordnung der Ergebnisse zu Ihren vereinheitlichten Kundenprofilen.</span><span class="sxs-lookup"><span data-stu-id="8dd9e-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="8dd9e-116">Weitere Informationen finden Sie unter [Benutzerdefinierte Machine Learning Modelle](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="8dd9e-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="8dd9e-117">AI Builder-Vorhersage</span><span class="sxs-lookup"><span data-stu-id="8dd9e-117">AI Builder prediction</span></span>

<span data-ttu-id="8dd9e-118">Manchmal sind Datensätze unvollständig und einige Werte fehlen.</span><span class="sxs-lookup"><span data-stu-id="8dd9e-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="8dd9e-119">Customer Insights kann helfen, fehlende Werte für die Kundenentität und die Segmente vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="8dd9e-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="8dd9e-120">Weitere Informationen finden Sie unter [Teildaten mit Vorhersagen ergänzen](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="8dd9e-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
