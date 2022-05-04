---
title: Erste Schritte mit Geschäftskonten als primäre Zielgruppe
description: Mehr über Geschäftskonten als primäre Zielgruppe erfahren Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: f16c8ad50ed290562fa9f223a3e8c86228e5331e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646250"
---
# <a name="work-with-business-accounts"></a>Mit Geschäftskonten arbeiten

Mit der Dynamics 365 Customer Insights können Sie Ihre Umgebung für verschiedene primäre Zielgruppen konfigurieren: Privatkunden (B-to-C) und Geschäftskunden (B-to-B). In B2C-Szenarien konzentrieren sich die Daten auf Einzelpersonen. Für B2B sind die primären Zielgruppen Konten – Organisationen oder Unternehmen – und Kontakte. Dieser Artikel hilft Ihnen bei den ersten Schritten mit einer Umgebung für Geschäftskonten. Sie listet die Unterschiede für die Funktionen in Customer Insights auf, je nachdem, worauf Sie sich in Ihrer Umgebung konzentrieren. Weitere Informationen zu den Unterschieden finden Sie in der Dokumentation zu den Funktionsbereichen. 

## <a name="create-an-environment-for-business-accounts"></a>Eine Umgebung für Geschäftskonten erstellen

Administratoren können [eine Umgebung in einer bestehenden Organisation erstellen](create-environment.md). Ein Schritt beim Erstellen einer neuen Umgebung fragt Administratoren nach der primären Zielgruppe der Umgebung. Falls es sich um die Ersteinrichtung nach dem Kauf einer Lizenz handelt, hilft eine Anleitung bei der Erstellung der ersten Umgebung.

Sie können dann für Geschäftskonten und zugehörige Kontakte als Datenquellen aus allen unterstützten Quellen [Daten erfassen](data-sources.md).

Nach der Vereinheitlichung der Daten, geben Sie [Kontohierarchien](relationships.md#set-up-account-hierarchies) als Teil der Beziehungskonfiguration an. Sie können auch [semantische Zuordnungen konfigurieren](semantic-mappings.md), um Kontakt- und Kontoentitäten zu verbinden. 

## <a name="switch-between-primary-target-audience"></a>Zwischen primärem Zielgruppen wechseln

Wenn Ihre Organisation Umgebungen für einzelne Kunden und Geschäftskonten unterhält, können Sie den Umschalter im linken Bereich verwenden, um die primäre Zielgruppe auszuwählen.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Umschaltung zum Ändern der primären Zielgruppe zwischen Einzelkunden und Geschäftskonten.":::

## <a name="supported-feature-areas"></a>Unterstützte Funktionsbereiche

- [Aktivitäten](activities.md): Unterstützung für Konten und zugehörige Kontakte, um Aktivitäten zu erstellen und in einer Zeitskala anzuzeigen.
- [Beziehungen](relationships.md): Der Aktivitätsassistent hilft beim Erstellen von Beziehungen zwischen den Entitäten, damit die Kontoansicht alle Aktivitäten von Kontakten anzeigen kann. Kontakte können einen Drillup durchführen, um die Kontaktansicht anzuzeigen, und Hierarchien können für die Aggregation von Kontoaktivitäten verwendet werden.
- [Measures](measures.md): Unterstützt Measure, die vom Measure-Builder mit einer Berechnung erstellt wurden. Eine optionale Einstellung ermöglicht das Hochrollen für Unterkonten beim Anlegen von Kennzahlen.
- [Segmente](segments.md) : Unterstützt Segmente, die mit dem Segment-Builder von Grund auf neu erstellt wurden. Neue Operatoren ermöglichen die Einbeziehung der Kontenhierarchie beim Erstellen von Segmenten.
- [Datenerfassung](data-sources.md): Alle Funktionen in diesem Bereich sind für Geschäftskonten und Privatkunden gleich.
- [Datenvereinheitlichung](data-unification.md): Alle Funktionen in diesem Bereich sind für Geschäftskonten und Privatkunden gleich.
- [Anreicherung](enrichment-hub.md): Einige Anreicherungsarten stehen nur für einzelne Kundenszenarien zur Verfügung, während andere ausschließlich für Geschäftskonten verfügbar sind.
- [Vorhersagen und Standard-Modelle](predictions-overview.md): Transaktionsabwanderungs-Vorhersage enthält zusätzliche Schritte für Geschäftskonten. Andere Vorhersagen sind nur für einzelne Kunden verfügbar.
- [Aktivierung und Export](export-destinations.md) : Exporte sind für Geschäftskonten und Privatkunden verfügbar. Einige Exporte erfordern zusätzliche Konfigurations- und Kontaktinformationen, die in den zugrunde liegenden Segmenten projiziert werden, um für Geschäftskonten gültig zu sein.
- [Systemeinstellungen](system.md) und [Benutzerverwaltung](permissions.md): Alle Funktionen in diesem Bereich sind für Geschäftskonten und Privatkunden gleich.

