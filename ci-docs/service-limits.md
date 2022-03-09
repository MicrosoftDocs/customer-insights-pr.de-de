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
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350406"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Servicegrenzen in Customer Insights-Funktionen

Dieser Artikel beschreibt die eingebauten Limits des Customer Insights-Dienstes, die die Zuverlässigkeit und Stabilität des Dienstes sicherstellen sollen. Sämtliche Anfordern von Änderungen können über das [Ideenforum](https://go.microsoft.com/fwlink/?linkid=2074172) vorgenommen werden. 

## <a name="audience-insights"></a>Zielgruppenerkenntnisse

| Region  | Grenzwerte  | Anmerkungen |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmente, Kennzahlen und Vorhersagen | 300  | Die volle Anzahl an [Segmenten](audience-insights/segments.md), [Kennzahlen](audience-insights/measures.md) und [Vorhersagen](audience-insights/predictions.md) zusammen darf 300 nicht überschreiten.  |
| Beziehungen | 20 Tiefenstufen für Beziehungen in Entitätspfaden. | Beim Erstellen von [Segmenten](audience-insights/segments.md) oder [Kennzahlen](audience-insights/measures.md) mit der Builder-Schnittstelle können Entitätspfade bis zu 20 Beziehungs-Hops zwischen der Startentität und der Zielentität aufweisen.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
