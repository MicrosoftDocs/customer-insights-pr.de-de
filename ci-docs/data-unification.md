---
title: Eine umfassende Ansicht Ihrer Kunden erstellen
description: Führen Sie den Datenvereinigungsprozess mit Ihren Daten durch, um einen einzigen DataSet von Unified customer profiles zu erstellen.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: bb8da6f4b9f92f2b265ff9807e04638edae4f814
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755733"
---
# <a name="data-unification-overview"></a>Datenvereinheitlichungsübersicht

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Nachdem [Sie die Datenquellen eingerichtet haben](data-sources.md), können Sie die Daten vereinheitlichen. Mit der Datenvereinheitlichung können Sie ehemals unterschiedliche Datenquellen in einem einzigen Master-DataSet vereinen, das eine einheitliche Ansicht dieser Daten bietet. Für einzelne Verbraucher (B-to-C), bei denen sich die Daten auf einzelne Personen konzentrieren, bietet die Vereinheitlichung eine einheitliche Sicht auf Ihre Kunden. Für Geschäftskonten (B-to-B), bei denen sich die Daten auf Konten konzentrieren, bietet die Vereinheitlichung eine einheitliche Sicht auf Ihre Konten.

Daten können in einer einzelnen Entität oder mehreren Entitäten vereinheitlicht werden. Die Vereinigung wird in der folgenden Reihenfolge durchgeführt:

1. [Quellfelder](map-entities.md) (früher Zuordnung genannt): Wählen Sie im Schritt Quellfelder Entitäten und Felder aus, die in den Vereinheitlichungsprozess eingeschlossen werden sollen. Ordnen Sie Felder einem gemeinsamen semantischen Typ zu, der den Zweck des Felds beschreibt.

1. [Doppelte Datensätze](remove-duplicates.md) (früher Teil von Abgleich): Definieren Sie im Schritt der doppelten Datensätze optional Regeln, um doppelte Kundendatensätze aus jeder Entität zu entfernen.

1. [Abgleich-Bedingungen](match-entities.md) (früher Abgleich genannt): Definieren Sie im Schritt der Abgleich-Bedingungen Regeln, die Kundendatensätze zwischen Entitäten abgleichen. Wenn ein Kunde in zwei oder mehr Entitäten gefunden wird, wird ein einzelner konsolidierter Datensatz mit allen Spalten und Daten von jeder Entität erstellt.

1. [Vereinheitlichte Kundenfelder](merge-entities.md) (früher Zusammenführen genannt): Bestimmen Sie im Schritt der vereinheitlichten Kundenfelder, welche Quellfelder in ein Unified customer profile aufgenommen, daraus ausgeschlossen oder darin zusammengeführt werden sollen.  

1. [Überprüfen Sie](review-unification.md) und erstellen Sie das vereinheitlichte Profil.

Nachdem Sie die Datenvereinigung abgeschlossen haben, können Sie optional:

- [Beziehungen zwischen Entitäten erstellen](relationships.md), um differenzierte Segmente zu erzeugen.
- [Ihre Daten aneichern](enrichment-hub.md), um ein breiteres Spektrum an Erkenntnissen über Ihre Kunden zu erhalten.
- [Aktivitäten definieren](activities.md) aus einigen der eingelesenen Attribute.
- [Kennzahlen erstellen](measures.md), um das Kundenverhalten und die Geschäftsleistung besser zu verstehen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
