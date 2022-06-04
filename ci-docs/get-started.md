---
title: Erste Schritte mit Dynamics 365 Customer Insights
description: Ein Überblick über Customer Insights verhilft Ressourcen zu einem schnellen Einstieg.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1a19d83930d667bdca5301dcc5a3ffa5db6a7bdc
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741132"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Erste Schritte mit Dynamics 365 Customer Insights

Customer Insights kann Ihnen helfen, Ihre Kunden besser zu verstehen. Verbinden Sie Daten aus verschiedenen Transaktions-, Verhaltens- und Beobachtungsquellen, um eine 360-Grad-Kundenansicht zu erstellen. Nutzen Sie diese Erkenntnisse, um damit kundenorientierte Erfahrungen und Prozesse zu fördern. Kundendaten vereinheitlichen und verstehen und für intelligente Insights und Aktionen nutzen.

## <a name="step-1-create-an-environment"></a>Schritt 1: Eine Umgebung erstellen

Um zu beginnen, müssen Sie zunächst eine Umgebung erstellen, in der Sie arbeiten können. Wenn Ihre Organisation bereits eine Lizenz erworben hat, finden Sie mehr Informationen unter [Erstellen Sie eine Umgebung](create-environment.md). Um einen Test für Customer Insights zu starten, siehe [Einrichten einer Testumgebung](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Schritt 2: Erkunden Sie Customer Insights

Wenn Sie sich zum ersten Mal bei Customer Insights anmelden, können Sie Einstellungen festlegen und das Produkt erkunden.

1. [Melden Sie sich bei Customer Insights](https://home.ci.ai.dynamics.com) mit Ihrem Microsoft Azure Active Directory (AAD) Benutzerkonto an.

1. [Ändern Sie die Umgebung](manage-environments.md#switch-environments), um Demodaten zu sehen und [erforschen Sie Customer Insights](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Schritt 3: Erfassen, vereinheitlichen und Beziehungen für Ihre Daten einrichten

Vereinheitlichte Profile sind die Grundlage, um Erkenntnisse zu gewinnen und Maßnahmen zu den Daten zu ergreifen. Bringen Sie Daten aus verschiedenen Quellen ein und führen Sie den Datenvereinheitlichungsprozess aus, um vereinheitlichte Profile zu kombinieren. Geben Sie Beziehungen zwischen den aufgenommenen Entitäten an. Verwenden Sie Anreicherungsfunktionen, um den Profilen Informationen hinzuzufügen.

1. Erfassen Sie Daten, indem Sie Datenquellen aus mehreren Optionen erstellen. Wählen zwischen [Power Query-Konnektoren](connect-power-query.md), einem [Common Data Model-Ordner](connect-common-data-model.md) oder [Microsoft Dataverse](connect-dataverse-managed-lake.md). 

1. Führen Sie den [Datenvereinheitlichungsprozess](data-unification.md) durch Identifizierung der [Quellfelder](map-entities.md) aus, entfernen Sie [Duplikate](remove-duplicates.md), [Abgleich-Bedingungen](match-entities.md) und [vereinheitlichende Felder](merge-entities.md).

1. Machen Sie sich mit den [vom System erstellten Entitäten](entities.md) vertraut, und erstellen Sie [Beziehungen zwischen den erfassten Entitäten](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Schritt 4: Verbessern Sie vereinheitlichten Profile mit Vorhersagen, Aktivitäten und Maßnahmen

Mit der Einrichtung vereinheitlichter Profile können Sie Ihre Daten erweitern und die bereitgestellten Informationen weiter verbessern.

1. Wählen Sie aus einer wachsenden Bibliothek von Anreicherungsanbietern, um [Ihre Kundendaten anzureichern](enrichment-hub.md).

1. Verwenden Sie [vorkonfigurierte Modelle](predictions-overview.md), um die Abwanderungswahrscheinlichkeit oder erwartete Umsätze vorherzusagen.

1. [Konfigurieren Sie Aktivitäten](activities.md) basierend auf erfassten Daten, und visualisieren Sie Interaktionen mit Ihren Kunden in einer chronologischen Zeitleiste.

1. [Erstellen Sie Kennzahlen](measures.md), um Ihre Geschäftsziele und KPIs zu messen.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Schritt 5: Segmente erstellen und Daten über verschiedene Exportoptionen aktivieren

Da Ihre Daten nun vollständig sind und eine Vielzahl von Informationen über Ihre Kunden enthalten, ist es an der Zeit, nach Möglichkeiten zu suchen, diese Daten zu verarbeiten.

1. [Erstellen Sie Segmente](segments.md), also Teilmengen Ihres Kundenstamms, um sicherzustellen, dass Ihre Aktionen für die Zielkunden relevant sind.

1. Durchsuchen Sie den wachsenden Katalog von [Exportoptionen](export-destinations.md), wo Sie Kundendaten verwenden können. Sie können Daten beispielsweise verwenden, um Werbeaktionen zu verwalten und über digitales Marketing Kontakt aufzunehmen.

1. Prüfen Sie die Integrationsmöglichkeiten, z.B. zu anderen Dynamics 365 Apps mit dem [Kundenkarten-Add-In](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]