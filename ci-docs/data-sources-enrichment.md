---
title: Datenquellanreicherung
description: Reichern Sie Datenquellen an, bevor Sie den Datenvereinheitlichungsprozess durchlaufen.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 1225482c4bf432ed747537b2c9bec9ab0e692a51
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800280"
---
# <a name="enrichment-for-data-sources-preview"></a>Anreicherung für Datenquellen (Vorschau)

Verwenden Sie Daten aus Quellen wie Microsoft und anderen Partnern, um Ihre Kundendaten vor der Datenvereinheitlichung anzureichern. Datenquellen-Anreicherungen tragen zu einer höheren Datenvollständigkeit und -qualität bei, die dazu beitragen können, bessere Ergebnisse zu erzielen, sobald Sie Ihre Daten vereinheitlicht haben. Beispielsweise erhöht die Verwendung eines normalisierten und standardisierten Formats für Adressen die Qualität der Übereinstimmungsergebnisse. Eine Liste der unterstützten Anreicherungen finden Sie unter [unterstützte Datenquellen-Anreicherungsoptionen](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Eine Datenquelle anreichern

Sie müssen über Teilnehmer- oder Administrator-Berechtigungen verfügen, um Anreicherungen zu erstellen oder zu bearbeiten. Weitere Informationen finden Sie unter [Berechtigungen](permissions.md).  

1. Gehen Sie zu **Daten** > **Vereinheitlichen**. Wählen Sie die Entität aus, die Sie anreichern möchten, und wählen Sie ein Attribut als Primärschlüssel für die Entität aus. Weitere Informationen finden Sie unter [Primärschlüssel auswählen](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Wechseln Sie zu **Daten** > **Datenquellen**.

1. Wählen Sie die vertikalen Auslassungspunkte (&vellip;) neben dem Datenquelle aus, die Sie anreichern möchten und wählen Sie **Anreichern**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Datenquellanreicherungsseite.":::

   Die Registerkarte **Entdecken** zeigt die [unterstützten Datenquellen Anreicherungsoptionen](#supported-data-source-enrichments) an.

1. Wählen Sie **Bereichern Sie meine Daten**, um eine Datenquelle-Anreicherung zu konfigurieren. Der Ausgabeentitätsname wird automatisch aufgefüllt.

## <a name="supported-data-source-enrichments"></a>Unterstützte Datenquellenanreicherungen

Die folgenden Anreicherungen sind aktuell für Datenquellen verfügbar. Sehen Sie sich die detaillierten Schritte für die Anreicherung an, um zu erfahren, wie Sie sie konfigurieren.

- [Erweiterte Adressen](enrichment-enhanced-addresses.md)
- [Erweiterte Firmendaten](enrichment-enhanced-company-data.md)
- [Identifizierungsdaten aus LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Verwalten Sie vorhandene Datenquelle-Anreicherungen

Gehen Sie zur Registerkarte **Meine Anreicherungen**, um alle konfigurierten Anreicherungen anzuzeigen.

Wählen Sie die Anreicherung aus, um die verfügbaren Optionen anzuzeigen. Sie können auch die vertikalen Auslassungspunkte (&vellip;) auf einem Listenelement auswählen, um die Optionen anzuzeigen. Wenn Sie mehrere Anreicherungen konfiguriert haben, finden Sie diese schnell über das Suchfeld.

Sie können eine Datenquelle-Anreicherung anzeigen, bearbeiten, ausführen oder löschen. Weitere Informationen finden Sie unter [Verwaltung der vorhandenen Anreicherungen](enrichment-hub.md).
