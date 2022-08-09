---
title: Anreicherung für Datenquellen (Vorschauversion)
description: Reichern Sie Datenquellen an, bevor Sie den Datenvereinheitlichungsprozess durchlaufen.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 98e9e330e7ef9cf085caa94a506fa788cebdd67b
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207182"
---
# <a name="enrichment-for-data-sources-preview"></a>Anreicherung für Datenquellen (Vorschauversion)

Verwenden Sie Daten aus Quellen wie Microsoft und anderen Partnern, um Ihre Kundendaten vor der Datenvereinheitlichung anzureichern. Datenquellen-Anreicherungen tragen zu einer höheren Datenvollständigkeit und -qualität bei, die dazu beitragen können, bessere Ergebnisse zu erzielen, sobald Sie Ihre Daten vereinheitlicht haben. Beispielsweise erhöht die Verwendung eines normalisierten und standardisierten Formats für Adressen die Qualität der Übereinstimmungsergebnisse. Eine Liste der unterstützten Anreicherungen finden Sie unter [unterstützte Datenquellen-Anreicherungsoptionen](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Eine Datenquelle anreichern

Sie müssen über Teilnehmer- oder Administrator-[Berechtigungen](permissions.md) verfügen, um Anreicherungen zu erstellen oder zu bearbeiten.  

1. Gehen Sie zu **Daten** > **Vereinheitlichen**. Wählen Sie die Entität aus, die Sie anreichern möchten, und wählen Sie ein Attribut als [Primärschlüssel](map-entities.md#select-primary-key-and-semantic-type-for-attributes) für die Entität aus.

1. Wechseln Sie zu **Daten** > **Datenquellen**.

1. Wählen Sie die vertikalen Auslassungspunkte (&vellip;) neben dem Datenquelle aus, die Sie anreichern möchten und wählen Sie **Anreichern**.

   :::image type="content" source="media/data_sources_enrich.png" alt-text="Datenquellenseite mit hervorgehobener Anreicherung":::

   Die Registerkarte **Entdecken** zeigt die [unterstützten Datenquellen Anreicherungsoptionen](#supported-data-source-enrichments) an.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Datenquellanreicherungsseite.":::

1. Wählen Sie **Bereichern Sie meine Daten**, um eine Datenquelle-Anreicherung zu konfigurieren. Der Ausgabeentitätsname wird automatisch aufgefüllt.

## <a name="supported-data-source-enrichments"></a>Unterstützte Datenquellenanreicherungen

Die folgenden Anreicherungen sind aktuell für Datenquellen verfügbar. Sehen Sie sich die detaillierten Schritte für die Anreicherung an, um zu erfahren, wie Sie sie konfigurieren.

- [Erweiterte Adressen](enrichment-enhanced-addresses.md)
- [Erweiterte Firmendaten](enrichment-enhanced-company-data.md)
- [Identifizierungsdaten aus LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Verwalten Sie vorhandene Datenquelle-Anreicherungen

Gehen Sie zu **Daten** > **Anreicherung**. Auf der Registerkarte **Meine Anreicherungen** werden konfigurierte Anreicherungen, deren Status, die Anzahl der angereicherten Kunden und den Zeitpunkt der letzten Aktualisierung der Daten angezeigt. Sie können die Liste der Anreicherungen nach einer beliebigen Spalte sortieren oder das Suchfeld verwenden, um die Anreicherung zu finden, die Sie verwalten möchten.

Wählen Sie die Anreicherung aus, um die verfügbaren Optionen anzuzeigen. Sie können auch die vertikalen Auslassungspunkte (&vellip;) auf einem Listenelement auswählen, um die Optionen anzuzeigen.

Sie können eine Datenquelle-Anreicherung anzeigen, bearbeiten, ausführen oder löschen. Weitere Informationen finden Sie unter [Verwaltung der vorhandenen Anreicherungen](enrichment-hub.md#manage-existing-enrichments).
