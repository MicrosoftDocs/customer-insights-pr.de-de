---
title: Erste Schritte mit Geschäftskonten als primäre Zielgruppe
description: Mehr über Geschäftskonten als primäre Zielgruppe erfahren Dynamics 365 Customer Insights.
ms.date: 09/30/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ea036cf3a3623a314a6d0d7da85b2c30c030ccea
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2021
ms.locfileid: "7644987"
---
# <a name="work-with-business-accounts-in-audience-insights"></a>Mit Geschäftskonten in Zielgruppenerkenntnissen arbeiten

Mit der Zielgruppenerkenntnissen-Funktion in Dynamics 365 Customer Insights können Sie Ihre Umgebung für verschiedene primäre Zielgruppen konfigurieren: Einzelkunden (B2C) und Geschäftskonten (B2B). In B2C-Szenarien konzentrieren sich die Daten auf Einzelpersonen. Für B2B sind die primären Zielgruppen Konten – Organisationen oder Unternehmen – und Kontakte. Dieser Artikel hilft Ihnen bei den ersten Schritten mit einer Umgebung für Geschäftskonten. Es listet die Unterschiede für die Funktionsbereiche in Zielgruppenerkenntnissen auf, abhängig von Ihrem Umgebungsfokus. Weitere Informationen zu den Unterschieden finden Sie in der Dokumentation zu den Funktionsbereichen. 

## <a name="create-an-environment-for-business-accounts"></a>Eine Umgebung für Geschäftskonten erstellen

Administratoren können [eine Umgebung in einer bestehenden Organisation erstellen](create-environment.md). Ein Schritt beim Erstellen einer neuen Umgebung fragt Administratoren nach der primären Zielgruppe der Umgebung. Falls es sich um die Ersteinrichtung von Zielgruppenerkenntnissen nach dem Kauf einer Lizenz handelt, hilft eine geführte Erfahrung bei der Erstellung der ersten Umgebung.

Sie können dann für Geschäftskonten und zugehörige Kontakte als Datenquellen aus allen unterstützten Quellen [Daten erfassen](data-sources.md).

Nach der Vereinheitlichung der Daten, geben Sie [Kontohierarchien](relationships.md#set-up-account-hierarchies) als Teil der Beziehungskonfiguration an. Sie können auch [semantische Zuordnungen konfigurieren](semantic-mappings.md), um Kontakt- und Kontoentitäten zu verbinden. 

## <a name="switch-between-primary-target-audience"></a>Zwischen primärem Zielgruppen wechseln

Wenn Ihre Organisation Umgebungen für einzelne Kunden und Geschäftskonten unterhält, können Sie den Umschalter im linken Bereich verwenden, um die primäre Zielgruppe auszuwählen.

:::image type="content" source="media/switch-primary-target-audience.PNG" alt-text="Umschaltung zum Ändern der primären Zielgruppe zwischen Einzelkunden und Geschäftskonten.":::

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

