---
title: Datenquellanreicherung
description: Reichern Sie Datenquellen an, bevor Sie den Datenvereinheitlichungsprozess durchlaufen.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 56f6a8ad20224922f9968f0ad3b6a0e0a400214b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646011"
---
# <a name="enrichment-for-data-sources-preview"></a>Anreicherung für Datenquellen (Vorschau)

Verwenden Sie Daten aus Quellen wie Microsoft und anderen Partnern, um Ihre Kundendaten vor der Datenvereinheitlichung anzureichern. Datenquellen-Anreicherungen tragen zu einer höheren Datenvollständigkeit und -qualität bei, die dazu beitragen können, bessere Ergebnisse zu erzielen, sobald Sie Ihre Daten vereinheitlicht haben. Beispielsweise erhöht die Verwendung eines normalisierten und standardisierten Formats für Adressen die Qualität der Übereinstimmungsergebnisse. Eine Liste der unterstützten Anreicherungen finden Sie unter [unterstützte Datenquellen-Anreicherungsoptionen](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Eine Datenquelle anreichern

Sie müssen über Teilnehmer- oder Administrator-Berechtigungen verfügen, um Anreicherungen zu erstellen oder zu bearbeiten. Weitere Informationen finden Sie unter [Berechtigungen](permissions.md).  

1. Gehen Sie zu **Daten** > **Vereinheitlichen**. Wählen Sie die Entität aus, die Sie anreichern möchten, und wählen Sie ein Attribut als Primärschlüssel für die Entität aus. Weitere Informationen finden Sie unter [Primärschlüssel auswählen](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Wechseln Sie zu **Daten** > **Datenquellen**.
 
1. Wählen Sie die vertikalen Auslassungspunkte neben dem Datenquelle aus, die Sie anreichern möchten und wählen Sie **Anreichern**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Datenquellanreicherungsseite.":::

   Die Registerkarte **Entdecken** zeigt die [unterstützten Datenquellen Anreicherungsoptionen](#supported-data-source-enrichments) an.

1. Wählen Sie **Bereichern Sie meine Daten**, um eine Datenquelle-Anreicherung zu konfigurieren. Der Ausgabeentitätsname wird automatisch aufgefüllt.

## <a name="supported-data-source-enrichments"></a>Unterstützte Datenquellenanreicherungen

Die folgenden Anreicherungen sind aktuell für Datenquellen verfügbar. Sehen Sie sich die detaillierten Schritte für die Anreicherung an, um zu erfahren, wie Sie sie konfigurieren.

- [Erweiterte Adressen](enrichment-enhanced-addresses.md)
- [Erweiterte Firmendaten](enrichment-enhanced-company-data.md)

## <a name="manage-existing-data-source-enrichments"></a>Verwalten Sie vorhandene Datenquelle-Anreicherungen

Gehen Sie zur Registerkarte **Meine Anreicherungen**, um alle konfigurierten Anreicherungen anzuzeigen.

Wählen Sie die Anreicherung aus, um die verfügbaren Optionen anzuzeigen. Sie können auch die Auslassungspunkte (...) in einem Listenelement auswählen, um die Optionen anzuzeigen. Wenn Sie mehrere Anreicherungen konfiguriert haben, finden Sie diese schnell über das Suchfeld.

Sie können eine Datenquelle-Anreicherung anzeigen, bearbeiten, ausführen oder löschen. Weitere Informationen finden Sie unter [Verwaltung der vorhandenen Anreicherungen](enrichment-hub.md).
