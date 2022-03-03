---
title: Erste Schritte mit der Zielgruppenerkenntnis-Funktion in Dynamics 365 Customer Insights
description: Eine Übersicht über Zielgruppenerkenntnisse hilft Ressourcen beim schnellen Einstieg.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 2776b2292560f9ea61a06d2b1b7bc7811d35c860
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353712"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Erste Schritte mit der Zielgruppenerkenntnis-Funktion von Dynamics 365 Customer Insights

Zielgruppenerkenntnisse können Ihnen helfen, ein tieferes Verständnis für Ihre Kunden aufzubauen. Verbinden Sie Daten aus verschiedenen Transaktions-, Verhaltens- und Beobachtungsquellen, um eine 360-Grad-Kundenansicht zu erstellen. Nutzen Sie diese Erkenntnisse, um damit kundenorientierte Erfahrungen und Prozesse zu fördern. Kundendaten vereinheitlichen und verstehen und für intelligente Insights und Aktionen nutzen.

## <a name="step-1-create-an-environment"></a>Schritt 1: Eine Umgebung erstellen

Um zu beginnen, müssen Sie zunächst eine Umgebung erstellen, in der Sie arbeiten können. Wenn Ihre Organisation bereits eine Lizenz erworben hat, finden Sie mehr Informationen unter [Erstellen Sie eine Umgebung](create-environment.md). Um eine Testversion für Zielgruppenerkenntnisse zu starten, siehe [Eine Testumgebung einrichten](../trial-signup.md). 

## <a name="step-2-explore-audience-insights"></a>Schritt 2: Zielgruppenerkenntnisse erkunden

Wenn Sie sich zum ersten Mal bei Zielgruppenerkenntnissen anmelden, können Sie Einstellungen konfigurieren und das Produkt erkunden.

1. [Melden Sie sich bei Zielgruppenerkenntnissen an](https://home.ci.ai.dynamics.com), indem Sie Ihr Microsoft Azure Active Directory (AAD)-Benutzerkonto verwenden.

1. [Ändern Sie die Umgebung](manage-environments.md#switch-environments), um Demodaten zu sehen und [Zielgruppenerkenntnisse zu erkunden](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Schritt 3: Erfassen, vereinheitlichen und Beziehungen für Ihre Daten einrichten

Vereinheitlichte Profile sind die Grundlage, um Erkenntnisse zu gewinnen und Maßnahmen zu den Daten zu ergreifen. Bringen Sie Daten aus verschiedenen Quellen ein und führen Sie den Datenvereinheitlichungsprozess aus, um vereinheitlichte Profile zu kombinieren. Geben Sie Beziehungen zwischen den aufgenommenen Entitäten an. Verwenden Sie Anreicherungsfunktionen, um den Profilen Informationen hinzuzufügen. 

1. Erfassen Sie Daten, indem Sie Datenquellen aus mehreren Optionen erstellen. Wählen zwischen [Power Query-Konnektoren](connect-power-query.md), einem [Common Data Model-Ordner](connect-common-data-model.md) oder [Microsoft Dataverse](/dynamics365/customer-insights/audience-insights/connect-dataverse-managed-lake). 

1. Führen Sie den [Datenvereinheitlichungsprozess](data-unification.md) aus, indem Sie die Phasen [Zuordnung](map-entities.md), [Abgleich](match-entities.md) und [Zusammenführung](merge-entities.md) durchlaufen.

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

1. Prüfen Sie Integrationsmöglichkeiten, zum Beispiel mit der [direkten Verbindung zu Interaktionserkenntnissen](../engagement-insights/integrate-audience-insights-engagement-insights.md) oder zu anderen Dynamics 365-Apps mit dem [Kundenkarten-Add-In](customer-card-add-in.md).  


[!INCLUDE[footer-include](../includes/footer-banner.md)]