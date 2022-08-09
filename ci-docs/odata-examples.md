---
title: OData-Abfragebeispiele für Customer Insights-APIs
description: Häufig verwendete Beispiele für das Open Data Protocol (OData) zum Abfragen der Customer Insights-APIs zum Überprüfen von Daten.
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8843fc04e4e6eaba0019d932c54f62561ffbdb92
ms.sourcegitcommit: f3c12ad445d5f91a88f91a7bbc40790ebcfaa826
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2022
ms.locfileid: "9121561"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>OData-Abfragebeispiele für Customer Insights-APIs

Das Open Data Protocol (OData) ist ein Datenzugriffsprotokoll, das auf Kernprotokollen wie HTTP aufbaut. Es verwendet allgemein anerkannte Methoden wie REST für das Web. Es gibt verschiedene Arten von Bibliotheken und Tools, die zum Nutzen von OData-Diensten verwendet werden können.

Dieser Artikel listet einige häufig angeforderte Beispielabfragen auf, die Ihnen beim Erstellen Ihrer eigenen Implementierungen auf der Grundlage von [Customer Insights-APIs](apis.md) helfen sollen.

Sie müssen die Abfragebeispiele ändern, damit sie in den Zielumgebungen funktionieren: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data`, wobei {instanceId} die GUID der Customer Insights-Umgebung ist, die Sie abfragen möchten. Der [ListAllInstances-Vorgang](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) lässt Sie die {InstanceId} finden, auf die Sie Zugriff haben.
- {CID}: GUID eines einheitlichen Kundendatensatzes. Beispiel: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Identifikator des Primärschlüssels eines Kundendatensatzes in einer Datenquelle. Beispiel: `CNTID_1002`
- {DSname}: Zeichenfolge mit dem Entitätsnamen einer Datenquelle, die in Customer Insights aufgenommen wird. Beispiel: `Website_contacts`.
- {SegmentName}: Zeichenfolge mit dem Ausgabeentitätsnamen eines Segments in Customer Insights. Beispiel: `Male_under_40`.

## <a name="customer"></a>Kundin/Kunde

Die folgende Tabelle enthält eine Reihe von Beispielabfragen für die Entität *Kunde*.

|Abfragetyp |Beispiel  | Notiz  |
|---------|---------|---------|
|Einzelnen Kunden-ID     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Alternativschlüssel    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Alternative Schlüssel bleiben in der einheitlichen Kundenentität bestehen       |
|Auswählen   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|In    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Alternativschlüssel + In   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Suche  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Gibt die Top-10-Ergebnisse für eine Suchzeichenfolge zurück      |
|Segmentmitgliedschaft  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Gibt eine voreingestellte Anzahl von Zeilen aus der Segmentierungsentität zurück.      |
|Segmentzugehörigkeit für einen Kunden | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | Gibt das Kundenprofil zurück, wenn er Mitglied des angegebenen Segments ist     |

## <a name="unified-activity"></a>Vereinheitlichte Aktivität

Die folgende Tabelle enthält eine Reihe von Beispielabfragen für die Entität *UnifiedActivity*.

|Abfragetyp |Beispiel  | Notiz  |
|---------|---------|---------|
|Aktivität von CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Listet Aktivitäten eines bestimmten Kundenprofils auf |
|Aktivitätszeitrahmen    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Aktivitäten eines Kundenprofils in einem Zeitrahmen       |
|Aktivitätstyp    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Aktivität nach Anzeigename     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Aktivitätssortierung    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Sortieren von Aktivitäten in aufsteigender oder absteigender Reihenfolge       |
|Aktivität erweitert aus der Segmentmitgliedschaft  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Weitere Beispiele

Die folgende Tabelle enthält eine Reihe von Beispielabfragen für andere Entitäten.

|Abfragetyp |Beispiel  | Notiz  |
|---------|---------|---------|
|CID-Kennzahlen    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Angereicherte Marken von CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Angereicherte Interessen von CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-Klausel + Erweitern     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Nicht unterstützte OData-Abfragen

Die folgenden Abfragen werden von Customer Insights nicht unterstützt:

- `$filter` auf aufgenommenen Quellentitäten. Sie können $filter-Abfragen nur für Systementitäten ausführen, die Customer Insights erstellt.
- `$expand` aus einer `$search`-Abfrage. Beispiel: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` aus `$select`, wenn nur eine Teilmenge von Attributen ausgewählt ist. Beispiel: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` angereicherte Marken- oder Interessenaffinitäten für einen bestimmten Kunden. Beispiel: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Abfragen an Vorhersage-Modellausgabeentitäten über Alternativschlüssel. Beispiel: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
