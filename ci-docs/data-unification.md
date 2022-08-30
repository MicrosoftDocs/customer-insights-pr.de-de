---
title: Eine umfassende Ansicht Ihrer Kunden erstellen
description: Führen Sie den Datenvereinigungsprozess mit Ihren Daten durch, um einen einzigen Master DataSet von Konten- oder Kundenprofilen zu erstellen.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304426"
---
# <a name="data-unification-overview"></a>Datenvereinheitlichungsübersicht

Nachdem [Sie die Datenquellen eingerichtet haben](data-sources.md), können Sie die Daten vereinheitlichen. Mit der Datenvereinheitlichung können Sie ehemals unterschiedliche Datenquellen in einem einzigen Master-DataSet vereinen, das eine einheitliche Ansicht dieser Daten bietet.

Für einzelne Verbraucher (B-to-C), bei denen sich die Daten auf einzelne Personen konzentrieren, bietet die Vereinheitlichung eine einheitliche Sicht auf Ihre Kunden. Für Geschäftskonten (B-to-B), bei denen sich die Daten auf Konten konzentrieren, bietet die Vereinheitlichung eine einheitliche Sicht auf Ihre Konten. [Kontaktvereinigung (Vorschauversion)](data-unification-contacts.md) ermöglicht es, Kontakte für diese Konten separat zu vereinheitlichen und den Konten zuzuordnen.

Daten können in einer einzelnen Entität oder mehreren Entitäten vereinheitlicht werden.

# <a name="individual-consumers-b-to-c"></a>[Einzelne Verbraucher (B2C)](#tab/b2c)

Der Vereinheitlichungsprozess ordnet Kundendaten aus Ihren Datenquellen zu, entfernt Duplikate, gleicht die Daten über Entitäten hinweg ab und erstellt ein einheitliches Profil. Die Vereinigung wird in der folgenden Reihenfolge durchgeführt:

1. [Quellfelder](map-entities.md) (früher Zuordnung genannt): Wählen Sie im Schritt Quellfelder Entitäten und Felder aus, die in den Vereinheitlichungsprozess eingeschlossen werden sollen. Ordnen Sie Felder einem gemeinsamen semantischen Typ zu, der den Zweck des Felds beschreibt.

1. [Doppelte Datensätze](remove-duplicates.md) (früher Teil von Abgleich): Definieren Sie im Schritt der doppelten Datensätze optional Regeln, um doppelte Kundendatensätze aus jeder Entität zu entfernen.

1. [Abgleich-Bedingungen](match-entities.md) (früher Abgleich genannt): Definieren Sie im Schritt der Abgleich-Bedingungen Regeln, die Kundendatensätze zwischen Entitäten abgleichen. Wenn ein Kunde in zwei oder mehr Entitäten gefunden wird, wird ein einzelner konsolidierter Datensatz mit allen Spalten und Daten von jeder Entität erstellt.

1. [Vereinheitlichte Kundenfelder](merge-entities.md) (früher Zusammenführen genannt): Bestimmen Sie im Schritt der vereinheitlichten Kundenfelder, welche Quellfelder in ein Unified customer profile aufgenommen, daraus ausgeschlossen oder darin zusammengeführt werden sollen.  

1. [Überprüfen Sie](review-unification.md) und erstellen Sie das vereinheitlichte Profil.

# <a name="business-accounts-b-to-b"></a>[Unternehmenskonten (B2B)](#tab/b2b)

Der Vereinheitlichungsprozess ordnet Kotodaten aus Ihren Datenquellen zu, entfernt Duplikate, gleicht die Daten über Entitäten hinweg ab und erstellt ein einheitliches Profil. Die Vereinigung wird in der folgenden Reihenfolge durchgeführt:

1. [Quellfelder](map-entities.md) (früher Zuordnung genannt): Wählen Sie im Schritt Quellfelder Entitäten und Felder aus, die in den Vereinheitlichungsprozess für Konten eingeschlossen werden sollen. Ordnen Sie Felder einem gemeinsamen semantischen Typ zu, der den Zweck des Felds beschreibt.

1. [Doppelte Datensätze](remove-duplicates.md) (früher Teil von Abgleich): Definieren Sie im Schritt der doppelten Datensätze optional Regeln, um doppelte Kontendatensätze aus jeder Entität zu entfernen.

1. [Abgleich-Bedingungen](match-entities.md) (früher Abgleich genannt): Definieren Sie im Schritt der Abgleich-Bedingungen Regeln, die Kontodatensätze zwischen Entitäten abgleichen. Wenn ein Konto in zwei oder mehr Entitäten gefunden wird, wird ein einzelner konsolidierter Datensatz mit allen Spalten und Daten von jeder Entität erstellt.

1. [Vereinheitlichte Kundenfelder](merge-entities.md) (früher Zusammenführen genannt): Bestimmen Sie im Schritt der vereinheitlichten Kundenfelder, welche Quellfelder in ein Unified customer profile aufgenommen, daraus ausgeschlossen oder darin zusammengeführt werden sollen.  

1. [Überprüfen Sie](review-unification.md) und erstellen Sie das vereinheitlichte Profil.

Nach dem vereinheitlichen der Konten können Sie optional für jene Konten [Kontakte vereinheitlichen (Vorschauversion)](data-unification-contacts.md) und Sie mit den vereinheitlichen Kontakten mit den vereinheitlichten Konten verknüpfen.

---

Nachdem Sie die Datenvereinigung abgeschlossen haben, können Sie optional:

- [Beziehungen zwischen Entitäten erstellen](relationships.md), um differenzierte Segmente zu erzeugen.
- [Ihre Daten aneichern](enrichment-hub.md), um ein breiteres Spektrum an Erkenntnissen über Ihre Kunden zu erhalten.
- [Aktivitäten definieren](activities.md) aus einigen der eingelesenen Attribute.
- [Kennzahlen erstellen](measures.md), um das Kundenverhalten und die Geschäftsleistung besser zu verstehen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
