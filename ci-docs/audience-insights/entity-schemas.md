---
title: Customer Insights Entitäts-Schemata im Common Data Model
description: Arbeiten Sie mit Entitäten im Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: e21f8a9422357fbc5c9425f91f3ba241c9dec9d8
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692304"
---
# <a name="entity-schemas-in-common-data-model"></a>Entitäten-Schema im Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](/common-data-model/) ist eine Spezifikation und Definition von Standardentitäten, die häufig verwendete Konzepte und Aktivitäten für eine Vielzahl von Geschäfts- und Anwendungsdomänen darstellen. Dieses Modell wird auch auf Beobachtungs- und Analysedaten ausgeweitet. Common Data Model bietet klar definierte, modulare und erweiterbare Geschäftsentitäten, wie z.B. Konto, Geschäftseinheit, Fall, Kontakt, Lead, Verkaufschance und Produkt sowie Interaktionen und Beziehungen zwischen Lieferanten, Arbeitern und Kunden, wie z.B. Aktivitäten und Vereinbarungen zum Servicelevel. Jeder kann auf Common Data Model-Definitionen aufbauen und diese erweitern, um zusätzliche geschäftsspezifische Ideen zu erfassen.

Dieses gemeinsam genutzte Datenmodell ermöglicht es Anwendungen und Datenintegratoren, leichter zusammenzuarbeiten, indem es eine einheitliche Datendefinition bereitstellt. Das Common Data Model enthält ein umfangreiches Metadatensystem mit Standardentitäten, Beziehungen, Hierarchien, Merkmalen und mehr. Es stammt aus Dynamics 365 Apps und ist Open-Source auf GitHub mit über 260 Standardentitäten. Ein großes System interner und externer Partner trägt branchenspezifische Konzepte zum Common Data Model bei.

Mehrere Systeme und Plattformen implementieren heute das Common Data Model, inklusive Power BI Dataflows und Azure Data Services. Es wird bereits in Microsoft Dataverse, Dynamics 365, Power Apps, Power BI und künftigen Azure Data Services unterstützt, was sich direkt auf den Wert, den die [Open Data Initiative](https://www.microsoft.com/open-data-initiative) schafft, auswirkt.

## <a name="customer-insights-entity-schemas"></a>Customer Insights Entitätschemas

Um eine 360-Grad-Ansicht des Kunden zu erstellen und Customer Insights-Modelle zur Erweiterung in Common Data Model verfügbar zu machen, haben wir die folgenden Entitätsschemata veröffentlicht:

| Entität | Beschreibung |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Eine Aktivität, die von einem Benutzer ausgeführt wird und einen Beobachtungswert für das Unternehmen hat. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Eine Person oder Organisation, die entweder Geschäftsaktivitäten durchgeführt hat oder das Potenzial hat, sich daran zu beteiligen. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definition von KPIs, die durch null oder mehr Dimensionen unterteilt sind (z.B. monatliche aktive Benutzer, Gesamtausgaben nach Kunde, durchschnittliche Kundenakquisitionskosten) |
|[Segment](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Definiert eine Gruppe von Mitgliedern mit gemeinsamen Merkmalen. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Mitglieder, die an einem bestimmten Segment teilnehmen. |

Weitere Informationen finden Sie in der Dokumentation unter [Customer Insights Entitätschemas im Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Anzeigen von Entitäten mithilfe des Common Data Model Entitätsnavigators

Sie können Entitäten im [Common Data Model Entity Navigator](https://microsoft.github.io/CDM/) anzeigen. Wählen Sie **Last von GitHub!** Schaltfläche und navigieren Sie zu **foundationCommon** > **crmCommon** > **Lösungen** > **customerInsights**, wo Sie die Liste der Customer Insights-Entitäten und deren Definitionen finden.
> [!div class="mx-imgBorder"]
> ![CDM-Entitätsnavigator mit CustomerActivity-Entität.](media/CDM-entity-navigator.png "CDM-Entitätsnavigator mit CustomerActivity-Entität")


[!INCLUDE[footer-include](../includes/footer-banner.md)]