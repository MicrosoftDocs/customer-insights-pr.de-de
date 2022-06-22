---
title: Service-Grenzwerte in Customer Insights
description: Verstehen Sie Beschränkungen und Einschränkungen in Customer Insights SaaS Service.
ms.date: 05/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6d1b761a5c9f67bfdc7c5b152132c618db3ea36a
ms.sourcegitcommit: 78ef22cd39a1ebd7525f96829cd79d95f34438b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2022
ms.locfileid: "8940667"
---
# <a name="service-limits-in-customer-insights"></a>Service-Grenzwerte in Customer Insights

Dieser Artikel beschreibt die eingebauten Limits des Customer Insights-Dienstes, die die Zuverlässigkeit und Stabilität des Dienstes sicherstellen sollen. Sämtliche Anfordern von Änderungen können über das [Ideenforum](https://go.microsoft.com/fwlink/?linkid=2074172) vorgenommen werden.

## <a name="customer-insights"></a>Customer Insights

| Region  | Grenzwerte  | Anmerkungen |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmente, Kennzahlen und Vorhersagen | 300  | Die volle Anzahl an [Segmenten](segments.md), [Kennzahlen](measures.md) und [Vorhersagen](predictions.md) zusammen darf 300 nicht überschreiten.  |
| Beziehungen | 20 Tiefenstufen für Beziehungen in Entitätspfaden. | Beim Erstellen von [Segmenten](segments.md) oder [Kennzahlen](measures.md) mit der Builder-Schnittstelle können Entitätspfade bis zu 20 Beziehungs-Hops zwischen der Startentität und der Zielentität aufweisen.  |

## <a name="fair-scheduling-of-jobs"></a>Faire Auftragsplanung

Customer Insights ist ein SaaS-Dienst, der gemeinsam genutzte Azure-Ressourcen verwendet. Kunden neigen dazu, Arbeitsbelastungen unterschiedlicher Intensität und mit unterschiedlichen Zeitplänen zu haben. Um einen fairen Zugriff auf die zugrunde liegenden Ressourcen zu gewährleisten, stellen wir sicher, dass Systemprozesse in fairer Reihenfolge ausgeführt werden. Beispiele für Systemprozesse sind Jobs im Zusammenhang mit Datenvereinheitlichung, Segmentaktualisierungen oder Kennzahlenberechnung. Die faire Planung schützt Sie vor Warteschlangen für Ressourcen, wenn es zu einer Spitze von angeforderten Jobs kommt. Gleichzeitig garantiert Customer Insights nicht, dass alle Aufträge, die Sie in die Warteschlange stellen, parallel verarbeitet werden.

[!INCLUDE [footer-include](includes/footer-banner.md)]
