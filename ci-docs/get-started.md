---
title: Erste Schritte mit Dynamics 365 Customer Insights
description: Ein Überblick über die Customer Insights Hilfsressourcen für einen schnellen Einstieg.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.subservice: audience-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: ce0336c4bf853bc81ec01c45410169a63b69eb03
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304610"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Erste Schritte mit Dynamics 365 Customer Insights

Customer Insights kann Ihnen helfen, Ihre Kunden besser zu verstehen. Verbinden Sie Daten aus verschiedenen Transaktions-, Verhaltens- und Beobachtungsquellen, um eine 360-Grad-Kundenansicht zu erstellen. Nutzen Sie diese Erkenntnisse, um damit kundenorientierte Erfahrungen und Prozesse zu fördern. Kundendaten vereinheitlichen und verstehen und für intelligente Insights und Aktionen nutzen.

## <a name="step-1-create-an-environment"></a>Schritt 1: Eine Umgebung erstellen

Erstellen Sie zunächst eine Umgebung, in der Sie arbeiten können. Wenn Ihre Organisation bereits eine Lizenz erworben hat, finden Sie mehr Informationen unter [Erstellen Sie eine Umgebung](create-environment.md). Um einen Test für Customer Insights zu starten, siehe [Einrichten einer Testumgebung](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Schritt 2: Erkunden Sie Customer Insights

Wenn Sie sich zum ersten Mal bei Customer Insights anmelden, können Sie Einstellungen festlegen und das Produkt erkunden.

1. [Melden Sie sich bei Customer Insights](https://home.ci.ai.dynamics.com) mit Ihrem Microsoft Azure Active Directory (AAD) Benutzerkonto an.

1. Ändern Sie die Umgebung, um Demodaten zu sehen und [erforschen Sie Customer Insights](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Schritt 3: Erfassen, vereinheitlichen und Beziehungen für Ihre Daten einrichten

Vereinheitlichte Profile sind die Grundlage, um Erkenntnisse zu gewinnen und Maßnahmen zu den Daten zu ergreifen. Bringen Sie Daten aus verschiedenen Quellen ein und führen Sie den Datenvereinheitlichungsprozess aus, um vereinheitlichte Profile zu kombinieren. Geben Sie Beziehungen zwischen den aufgenommenen Entitäten an und verwenden Sie Anreicherungsfunktionen, um Informationen zu den Profilen hinzuzufügen.

1. Erfassen Sie Daten, indem Sie Datenquellen aus mehreren Optionen erstellen. Wählen zwischen [Azure Data Lake Storage, inklusive Common Data Model](connect-common-data-model.md), [Azure Synapse Analytics](connect-synapse.md), [Microsoft Dataverse](connect-dataverse-managed-lake.md) oder [Power Query Konnektoren](connect-power-query.md).

1. Führen Sie den [Datenvereinheitlichungsprozess](data-unification.md) durch Identifizierung der [Quellfelder](map-entities.md) aus, entfernen Sie [Duplikate](remove-duplicates.md), [Abgleich-Bedingungen](match-entities.md) und [vereinheitlichende Felder](merge-entities.md).

1. Machen Sie sich mit den [vom System erstellten Entitäten](entities.md) vertraut, und erstellen Sie [Beziehungen zwischen den erfassten Entitäten](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Schritt 4: Verbessern Sie vereinheitlichten Profile mit Vorhersagen, Aktivitäten und Maßnahmen

Verbessern Sie mit der Einrichtung einheitlicher Profile Ihre Daten und erweitern Sie die bereitgestellten Informationen weiter.

1. Wählen Sie aus einer wachsenden Bibliothek von Anreicherungsanbietern, um [Ihre Kundendaten anzureichern](enrichment-hub.md).

1. Verwenden Sie [vorkonfigurierte Modelle](predictions-overview.md), um die Abwanderungswahrscheinlichkeit oder erwartete Umsätze vorherzusagen.

1. [Konfigurieren Sie Aktivitäten](activities.md) basierend auf erfassten Daten, und visualisieren Sie Interaktionen mit Ihren Kunden in einer chronologischen Zeitleiste.

1. [Erstellen Sie Kennzahlen](measures.md), um Ihre Geschäftsziele und KPIs zu messen.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Schritt 5: Segmente erstellen und Daten über verschiedene Exportoptionen aktivieren

Nachdem Ihre Daten nun vollständig sind und eine Vielzahl von Informationen über Ihre Kunden enthalten, suchen Sie nach Möglichkeiten, um diese Daten zu verarbeiten.

1. [Erstellen Sie Segmente](segments.md), also Teilmengen Ihres Kundenstamms, um sicherzustellen, dass Ihre Aktionen für die Zielkunden relevant sind.

1. Durchsuchen Sie den wachsenden Katalog von [Exportoptionen](export-destinations.md), wo Sie Kundendaten verwenden können. Sie können Daten beispielsweise verwenden, um Werbeaktionen zu verwalten und über digitales Marketing Kontakt aufzunehmen.

1. Prüfen Sie die Integrationsmöglichkeiten, z.B. zu anderen Dynamics 365 Apps mit dem [Kundenkarten-Add-In](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
