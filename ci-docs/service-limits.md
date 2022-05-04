---
title: Servicelimits in Dynamics 365 Customer Insights
description: Grenzen und Einschränkungen verstehen.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641761"
---
# <a name="service-limits-in-customer-insights"></a>Service-Grenzwerte in Customer Insights

Dieser Artikel beschreibt die eingebauten Limits des Customer Insights-Dienstes, die die Zuverlässigkeit und Stabilität des Dienstes sicherstellen sollen. Sämtliche Anfordern von Änderungen können über das [Ideenforum](https://go.microsoft.com/fwlink/?linkid=2074172) vorgenommen werden. 

## <a name="customer-insights"></a>Customer Insights

| Region  | Grenzwerte  | Anmerkungen |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmente, Kennzahlen und Vorhersagen | 300  | Die volle Anzahl an [Segmenten](segments.md), [Kennzahlen](measures.md) und [Vorhersagen](predictions.md) zusammen darf 300 nicht überschreiten.  |
| Beziehungen | 20 Tiefenstufen für Beziehungen in Entitätspfaden. | Beim Erstellen von [Segmenten](segments.md) oder [Kennzahlen](measures.md) mit der Builder-Schnittstelle können Entitätspfade bis zu 20 Beziehungs-Hops zwischen der Startentität und der Zielentität aufweisen.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
