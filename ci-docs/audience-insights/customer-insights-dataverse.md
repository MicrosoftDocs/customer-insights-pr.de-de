---
title: Customer Insights-Daten in Microsoft Dataverse
description: Verwenden Sie Customer Insights-Entitäten als Tabellen in Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: bbbbf2a7f5edb81ee75f6e33988cd4721134b6e7
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547625"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Arbeiten mit Customer Insights-Daten in Microsoft Dataverse

Customer Insights bietet die Möglichkeit, Ausgabeentitäten in [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro) zur Verfügung zu stellen. Diese Integration ermöglicht durch einen Low-Code-/No-Code-Ansatz die einfache Datenfreigabe und eine benutzerdefinierte Entwicklung. Die [Ausgabeeinheiten](#output-entities) sind als Tabellen in einer Dataverse Umgebung verfügbar. Sie können die Daten für jede andere Anwendung auf der Grundlage von Dataverse Tabellen verwenden. Diese Tabellen ermöglichen Szenarien wie automatisierte Workflows durch Power Automate oder Apps erstellen mit Power Apps. Die aktuelle Implementierung unterstützt hauptsächlich Lookups, bei denen Daten aus den verfügbaren Customer Insights-Entitäten für eine bestimmte Kunden-ID abgerufen werden können.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Anhängen einer Dataverse-Umgebung an Customer Insights

**Vorhandene Organisation**

Administratoren können Customer Insights zum [Verwenden einer vorhandenen Dataverse Umgebung](create-environment.md) konfigurieren, wenn sie eine Customer Insights-Umgebung erstellen. Durch die Bereitstellung der URL zur Dataverse-Umgebung wird sie an ihre neue Umgebung für Zielgruppenerkenntnisse angehängt. Customer Insights und Dataverse Umgebungen müssen in derselben Region gehostet werden. 

Wenn Sie keine vorhandene Dataverse Umgebung verwenden möchten, erstellt das System eine neue Umgebung für die Customer Insights-Daten in Ihrem Mandanten. 

> [!NOTE]
> Wenn Ihre Organisationen Dataverse in ihrem Mandanten bereits verwendet, gilt es zu beachten, dass die [Dataverse-Umgebungserstellung von einem Administrator kontrolliert](/power-platform/admin/control-environment-creation) wird. Wenn Sie beispielsweise mit Ihrem Organisationskonto eine neue Umgebung für Zielgruppenerkenntnisse einrichten und der Administrator die Erstellung von Dataverse-Testumgebungen für alle Personen außer Administratoren deaktiviert hat, können Sie keine neue Testumgebung erstellen.
> 
> Die Dataverse-Testumgebungen, die in Customer Insights erstellt werden, belegen 3 GB Storage, der nicht auf die dem Mandanten zustehende Gesamtkapazität angerechnet wird. Bezahlte Abonnements erhalten eine Dataverse-Berechtigung von 15 GB für die Datenbank und 20 GB zur Speicherung von Dateien.

**Neue Organisation**

Wenn Sie beim Einrichten von Customer Insights eine neue Organisation erstellen, erstellt das System automatisch eine neue Dataverse Umgebung in Ihrer Organisation für Sie.

## <a name="output-entities"></a>Ausgabeentitäten

Einige Ausgabeentitäten aus Zielgruppenerkenntnissen sind als Tabellen in Dataverse verfügbar. In den folgenden Abschnitten wird das erwartete Schema dieser Tabellen beschrieben.

- [CustomerProfile](#customerprofile)
- [AlternateKeys](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Anreicherung](#enrichment)
- [Vorhersage](#prediction)
- [Segmentmitgliedschaft](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Diese Tabelle enthält das einheitliche Kundenprofil von Customer Insights. Das Schema für ein einheitliches Kundenprofil hängt von den Entitäten und Attributen ab, die bei der Zusammenführung verwendet werden. Ein Kundenprofilschema enthält normalerweise eine Teilmenge der Attribute aus der [Common Data Model-Definition von CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKeys

Die Tabelle „AlternateKey“ enthält Schlüssel der Entitäten, die an der Vereinheitlichung beteiligt waren.

|Column  |Art  |Beschreibung  |
|---------|---------|---------|
|DataSourceName    |String         | Der Name der Datenquelle. Beispiel: '`datasource5`'        |
|EntityName        | String        | Der Name der Entität in Zielgruppenerkenntnissen. Beispiel: '`contact1`'        |
|AlternateValue    |String         |Alternative ID, die der Kunden-ID zugeordnet wird. Beispiel: `cntid_1078`         |
|KeyRing           | Mehrzeiliger Text        | JSON-Wert  </br> Beispiel: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | Die ID des vereinheitlichten Kundenprofils.         |
|AlternateKeyId     | GUID         |  AlternateKey-deterministische GUID basierend auf msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Beispiel: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Diese Tabelle enthält Aktivitäten von Benutzern, die in Customer Insights verfügbar sind.

| Column            | Art        | Beschreibung                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | Kundenprofil-ID                                                                      |
| ActivityId        | String      | Interne ID der Kundenaktivität (Primärschlüssel)                                       |
| SourceEntityName  | String      | Name der Quellentität                                                                |
| SourceActivityId  | String      | Primärschlüssel von der Quellentität                                                       |
| ActivityType      | String      | Semantischer Aktivitätstyp oder Name der benutzerdefinierten Aktivität                                        |
| ActivityTimeStamp | DATETIME    | Aktivitätszeitstempel                                                                      |
| Titel             | String      | Titel oder Name der Aktivität                                                               |
| Beschreibung       | String      | Aktivitätsbeschreibung                                                                     |
| URL               | String      | Link zu einer externen URL, die für die Aktivität spezifisch ist                                         |
| SemanticData      | JSON-Zeichenfolge | Enthält eine Liste von Schlüssel-Wert-Paaren für semantische Mapping-Felder, die für den Aktivitätstyp spezifisch sind |
| RangeIndex        | String      | Unix-Zeitstempel, der zum Sortieren der Aktivitätszeitskala und der Abfragen des effektiven Bereichs verwendet wird |
| mydynci_unifiedactivityid   | GUID | Interne ID der Kundenaktivität (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Diese Tabelle enthält die Ausgabedaten von kundenattributbasierten Kennzahlen.

| Column             | Art             | Beschreibung                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | Kundenprofil-ID        |
| Kennzahlen           | JSON-Zeichenfolge      | Enthält eine Liste von Schlüssel-Wert-Paaren für Kennzahlnamen und -werte für den angegebenen Kunden | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | Kundenprofil-ID |


### <a name="enrichment"></a>Anreicherung

Diese Tabelle enthält die Ausgabe des Anreicherungsprozesses.

| Column               | Art             |  Beschreibung                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | Kundenprofil-ID                                 |
| EnrichmentProvider   | String           | Name des Anbieters für die Anreicherung                                  |
| EnrichmentType       | String           | Art der Anreicherung                                      |
| Werte               | JSON-Zeichenfolge      | Liste der durch den Anreicherungsprozess erzeugten Attribute |
| msdynci_enrichmentid | GUID             | Deterministische, aus msdynci_identifier generierte GUID |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Vorhersage

Diese Tabelle enthält die Ausgabe der Modellvorhersagen.

| Column               | Art        | Beschreibung                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | Kundenprofil-ID                                  |
| ModelProvider        | String      | Name des Anbieters des Modells                                      |
| Modell                | String      | Modellname                                                |
| Werte               | JSON-Zeichenfolge | Liste der vom Modell erzeugten Attribute |
| msdynci_predictionid | GUID        | Deterministische, aus msdynci_identifier generierte GUID | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Segmentmitgliedschaft

Diese Tabelle enthält Informationen zur Segmentmitgliedschaft der Kundenprofile.

| Column        | Type | Beschreibung des Dataflows                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Kundenprofil-ID        |
| SegmentProvider      | String       | App, die die Segmente veröffentlicht. Standard: Zielgruppenerkenntnisse         |
| SegmentMembershipType | String       | Typ des Kunden in diesem Segmentmitgliedschaftsdatensatz. Unterstützt mehrere Typen wie Kunde, Kontakt oder Konto. Standard: Kunde  |
| Segmente       | JSON-Zeichenfolge  | Liste einzigartiger Segmente, in denen das Kundenprofil Mitglied ist      |
| msdynci_identifier  | String   | Eindeutiger Bezeichner des Segmentmitgliedschaftsdatensatzes. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministische GUID aus `msdynci_identifier` erstellt          |
