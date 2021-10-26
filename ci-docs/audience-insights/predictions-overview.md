---
title: Übersicht über unterstützte Vorhersageszenarien
description: Vorhersageszenarien und Optionen, die von der Anwendung Dynamics 365 Customer Insights abgedeckt werden.
ms.date: 09/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: be452e4f1515f637f6edbc3ae3aaf6a3d3471489
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618842"
---
# <a name="predictions-overview"></a>Übersicht über Vorhersagen

Dynamics 365 Customer Insights ist mit einer Vielzahl von Optionen ausgestattet, die KI und Machine Learning nutzen, um Daten vorherzusagen. 

## <a name="out-of-box-models"></a>Sofort einsatzbereite Modelle

Der einfachste Weg, um mit der Vorhersage von Daten zu beginnen, sind vordefinierte Modelle, die auch als sofort einsatzbereite Modelle bezeichnet werden. Sie benötigen nur bestimmte Daten und Strukturen, um schnell Erkenntnisse zu gewinnen. Gegenwärtig sind die folgenden Modelle verfügbar: 

# <a name="individual-customers-b2c"></a>[Einzelne Verbraucher (B2C)](#tab/b2c)

- [Langfristiger Kundenwert](predict-customer-lifetime-value.md) : Prognostiziert den potenziellen Umsatz eines Kunden während der gesamten Interaktion mit einem Unternehmen.
- [Produktempfehlung](predict-product-recommendation.md) : Schlägt prädiktive Produktempfehlungen basierend auf dem Kaufverhalten und Kunden mit ähnlichen Kaufmustern vor.
- [Abonnementabwanderung](predict-subscription-churn.md): Sagt vorher, ob das Risiko besteht, dass ein Kunde die Abonnementprodukte oder Services Ihres Unternehmens nicht länger verwendet.
- [Transaktionsabwanderung](predict-transactional-churn.md) : Sagt vorher, ob ein Kunde Ihre Produkte oder Dienstleistungen in einem bestimmten Zeitrahmen nicht mehr kaufen wird.

# <a name="business-accounts-b2b"></a>[Unternehmenskonten (B2B)](#tab/b2b)

- [Transaktionsabwanderung](predict-transactional-churn.md) : Sagt vorher, ob ein Kunde Ihre Produkte oder Dienstleistungen in einem bestimmten Zeitrahmen nicht mehr kaufen wird.

---


## <a name="azure-machine-learning-integration"></a>Azure Machine Learning-Integration

Wenn eine Organisation bereits Machine Learning-Szenarien basierend auf Azure Machine Learning-Experimenten verwendet, hilft das Feature für benutzerdefinierte Modelle in Customer Insights, alles zu verbinden. Erstellen Sie Workflows, die Ihnen bei der Auswahl der Daten helfen, aus denen Sie Erkenntnisse generieren möchten, und bei der Zuordnung der Ergebnisse zu Ihren vereinheitlichten Kundenprofilen. Weitere Informationen finden Sie unter [Benutzerdefinierte Machine Learning Modelle](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder-Vorhersage

Manchmal sind Datensätze unvollständig und einige Werte fehlen. Customer Insights kann helfen, fehlende Werte für die Kundenentität und die Segmente vorherzusagen. Weitere Informationen finden Sie unter [Teildaten mit Vorhersagen ergänzen](predictions.md).
