---
title: Service-Limits
description: Grenzen und Einschränkungen verstehen.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2966f2ede1ddbe0245471771365cbf5b593be608764aa10ed28d962c52bb8067
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034863"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Service-Limits in Dynamics 365 Customer Insights Zielgruppen-Insights-Funktionalitäten

Dieser Artikel beschreibt die eingebauten Limits des Customer Insights-Dienstes, die die Zuverlässigkeit und Stabilität des Dienstes sicherstellen sollen. Sämtliche Anfordern von Änderungen können über das [Ideenforum](https://go.microsoft.com/fwlink/?linkid=2074172) vorgenommen werden. 
 
| Bereich  | Grenzwerte  | Hinweise |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmente und Maßnahmen | 100 Segmente oder Kennzahlen. | Die Gesamtzahl der aktiven [Segmente](segments.md) und [Kennzahlen](measures.md) zusammen kann 100 nicht überschreiten.  |
| Beziehungen | 20 Tiefenstufen für Beziehungen in Entitätspfaden. | Beim Erstellen von [Segmenten](segments.md) oder [Kennzahlen](measures.md) mit der Builder-Schnittstelle können Entitätspfade bis zu 20 Beziehungs-Hops zwischen der Startentität und der Zielentität aufweisen.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]