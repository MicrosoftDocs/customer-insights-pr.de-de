---
title: Dynamics 365 Customer Insights mit Azure Monitor überwachen
description: Erfahren Sie, wie Sie Protokolle an Microsoft Azure Monitor senden.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 03169f0218dfad55cf20ecaf1c1596c652e5f601
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755261"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Protokollweiterleitung in Dynamics 365 Customer Insights mit Azure Monitor (Vorschauversion)

Dynamics 365 Customer Insights bietet eine direkte Integration in Azure Monitor. Mit Azure Monitor-Ressourcenprotokollen können Sie Protokolle überwachen und an [Azure Storage](https://azure.microsoft.com/services/storage/) bzw. [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) senden oder zu [Azur Event Hubs](https://azure.microsoft.com/services/event-hubs/) streamen.

Customer Insights sendet die folgenden Ereignisprotokolle:

- **Überwachungsereignisse**
  - **APIEvent** – ermöglicht Änderungsnachverfolgung über die Dynamics 365 Customer Insights-Benutzeroberfläche.
- **Betriebliche Ereignisse**
  - **WorkflowEvent** – Der Workflow ermöglicht die Einrichtung von [Datenquellen](data-sources.md), die [Vereinheitlichung](data-unification.md), die [Anreicherung](enrichment-hub.md) und schließlich den [Export](export-destinations.md) von Daten in andere Systeme. Alle diese Schritte können einzeln ausgeführt werden (z. B. einen einzelnen Export auslösen). Dies kann auch orchestriert ausgeführt werden (z. B. Datenaktualisierung aus Datenquellen, die den Vereinheitlichungsprozess auslöst, der Anreicherungen abruft und die Daten nach Abschluss in ein anderes System exportiert). Weitere Informationen finden Sie im [WorkflowEvent-Schema](#workflow-event-schema).
  - **APIEvent** – alle API-Aufrufe an die Kundeninstanz an Dynamics 365 Customer Insights. Weitere Informationen finden Sie im [APIEvent-Schema](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Diagnoseeinstellungen einrichten

### <a name="prerequisites"></a>Anforderungen

Zum Konfigurieren der Diagnose in Customer Insights müssen die folgenden Voraussetzungen erfüllt sein:

- Sie verfügen über ein aktives [Azure-Abonnement](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Sie verfügen über [Administrator](permissions.md#admin)-Berechtigungen in Customer Insights.
- Sie verfügen über die Rollen **Mitwirkender** und **Benutzerzugriffsadministrator** für die Zielressource in Azure. Die Ressource kann ein Azure Storage-Konto, ein Azure Event Hub oder ein Azure Log Analytics-Arbeitsbereich sein. Weitere Informationen finden Sie unter [Azure-Rollenzuweisungen über das Azure-Portal hinzufügen oder entfernen](/azure/role-based-access-control/role-assignments-portal).
- Die [Zielanforderungen](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) für Azure Storage, Azure Event Hub oder Azure Log Analytics sind erfüllt.
- Sie verfügen mindestens über die Rolle **Leser** in der Ressourcengruppe, zu der die Ressource gehört.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Diagnose mit Azure Monitor einrichten

1. Wählen Sie in Customer Insights **System** > **Diagnose** aus, um die für diese Instanz konfigurierten Diagnoseziele anzuzeigen.

1. Wählen Sie **Ziel hinzufügen** aus.

   > [!div class="mx-imgBorder"]
   > ![Diagnoseverbindung](media/diagnostics-pane.png "Diagnoseverbindung")

1. Geben Sie im Feld **Name für Diagnoseziel** einen Namen ein.

1. Wählen Sie den **Mandanten** des Azure-Abonnements mit der Zielressource und dann **Anmelden** aus.

1. Wählen Sie den **Ressourcentyp** (Speicherkonto, Event Hub oder Protokollanalyse) aus.

1. Wählen Sie das **Abonnement** für die Zielressource aus.

1. Wählen Sie die **Ressourcengruppe** für die Zielressource aus.

1. Wählen Sie die **Ressource** aus.

1. Bestätigen Sie die **Datenschutz und Compliance**-Anweisung.

1. Wählen Sie **Mit System verbinden** aus, um eine Verbindung zur Zielressource herzustellen. Die Protokolle werden nach 15 Minuten im Ziel angezeigt, wenn die API verwendet wird und Ereignisse generiert.

### <a name="remove-a-destination"></a>Ziel entfernen

1. Wechseln Sie zu **System** > **Diagnose**.

1. Wählen Sie das Diagnoseziel aus der Liste aus.

1. Wählen Sie in der Spalte **Aktionen** das Symbol **Löschen** aus.

1. Bestätigen Sie den Löschvorgang, um die Protokollweiterleitung zu beenden. Die Ressource im Azure-Abonnement wird nicht gelöscht. Sie können den Link in der Spalte **Aktionen** auswählen, um das Azure-Portal für die ausgewählte Ressource zu öffnen und dort zu löschen.

## <a name="log-categories-and-event-schemas"></a>Protokollkategorien und Ereignisschemas

Derzeit werden [API-Ereignisse](apis.md) und Workflow-Ereignisse unterstützt, und es gelten die folgenden Kategorien und Schemas.
Das Protokollschema folgt dem [allgemeinen Schema von Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategorien

Customer Insights bietet zwei Kategorien:

- **Überwachungsereignisse**: [API-Ereignisse](#api-event-schema) zum Nachverfolgen der Konfigurationsänderungen für den Dienst. `POST|PUT|DELETE|PATCH`-Vorgänge fallen in diese Kategorie.
- **Betriebsereignisse**: [API-Ereignisse](#api-event-schema) oder [Workflow-Ereignisse](#workflow-event-schema), die während der Nutzung des Dienstes generiert werden.  Beispielsweise `GET`-Anforderungen oder die Ausführungsereignisse eines Workflows.

## <a name="configuration-on-the-destination-resource"></a>Konfiguration für die Zielressource

Die folgenden Schritte werden basierend auf Ihrer Auswahl des Ressourcentyps automatisch angewendet:

### <a name="storage-account"></a>Storage account

Der Customer Insights-Dienstprinzipal erhält die Berechtigung **Speicherkontomitwirkender** für die ausgewählte Ressource und erstellt zwei Container unter dem ausgewählten Namespace:

- `insight-logs-audit` mit **Überwachungsereignissen**
- `insight-logs-operational` mit **Betriebsereignissen**

### <a name="event-hub"></a>Ereignis-Hub

Der Customer Insights-Dienstprinzipal erhält die Berechtigung **Azure Event Hubs-Datenbesitzer** für die Ressource und erstellt zwei Event Hubs unter dem ausgewählten Namespace:

- `insight-logs-audit` mit **Überwachungsereignissen**
- `insight-logs-operational` mit **Betriebsereignissen**

### <a name="log-analytics"></a>Log Analytics

Der Customer Insights-Dienstprinzipal erhält die Berechtigung **Log Analytics-Mitwirkender** für die Ressource. Die Protokolle sind unter **Protokolle** > **Tabellen** > **Protokollverwaltung** im ausgewählten Log Analytics-Arbeitsbereich verfügbar. Erweitern Sie die Lösung **Protokollverwaltung**, und lokalisieren Sie die Tabellen `CIEventsAudit` und `CIEventsOperational`.

- `CIEventsAudit` mit **Überwachungsereignissen**
- `CIEventsOperational` mit **Betriebsereignissen**

Erweitern Sie unter dem Fenster **Abfragen** die Lösung **Überwachung**, und suchen Sie die bereitgestellten Beispielabfragen, indem Sie nach `CIEvents`.

## <a name="event-schemas"></a>Ereignisschemas

API-Ereignisse und Workflow-Ereignisse haben eine gemeinsame Struktur und unterschiedliche Details. Weitere Informationen finden Sie unter [API-Ereignisschema](#api-event-schema) oder [Workflow-Ereignisschema](#workflow-event-schema).

### <a name="api-event-schema"></a>API-Ereignisschema

| Feld             | Datentyp  | erforderlich/optional | Beschreibung des Dataflows       | Beispiel        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Zeitstempel | Erforderlich          | Zeitstempel des Ereignisses (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Erforderlich          | ResourceId der Instanz, die das Ereignis ausgegeben hat         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Erforderlich          | Name des Vorgangs, der durch dieses Ereignis dargestellt wird.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Erforderlich          | Protokollkategorie des Ereignisses Entweder `Operational` oder `Audit`. Alle POST/PUT/PATCH/DELETE HTTP-Anforderungen sind mit `Audit` gekennzeichnet, alles andere mit `Operational`. | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Erforderlich          | Status des Ereignisses `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Optional          | Ergebnisstatus des Ereignisses Wenn der Vorgang einem REST-API-Aufruf entspricht, ist dies der HTTP-Statuscode.        | `200`             |
| `durationMs`      | Lang      | Optional          | Dauer des Vorgangs in Millisekunden     | `133`     |
| `callerIpAddress` | String    | Optional          | IP-Adresse des Aufrufers, wenn der Vorgang einem API-Aufruf entspricht, der von einer öffentlich verfügbaren IP-Adresse stammt.                                                 | `144.318.99.233`         |
| `identity`        | String    | Optional          | JSON-Objekt, das die Identität des Benutzers oder der Anwendung beschreibt, die den Vorgang ausgeführt hat.       | Weitere Informationen finden Sie im Abschnitt [Identität](#identity-schema).     |  
| `properties`      | String    | Optional          | JSON-Objekt mit mehr Eigenschaften für die jeweilige Ereigniskategorie.      | Weitere Informationen finden Sie im Abschnitt [Eigenschaften](#api-properties-schema).    |
| `level`           | String    | Erforderlich          | Schweregrad des Ereignisses    | `Informational`, `Warning`, `Error` oder `Critical`.           |
| `uri`             | String    | Optional          | Absoluter Anforderungs-URI    |               |

#### <a name="identity-schema"></a>Identitätsschema

Das `identity`-JSON-Objekt hat die folgende Struktur.

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Feld                         | Beschreibung des Dataflows                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Zugewiesene Rolle für den Benutzer oder die App Weitere Informationen finden Sie unter [Benutzerberechtigungen](permissions.md).                                     |
| `Authorization.RequiredRoles` | Erforderliche Rollen zum Ausführen des Vorgangs `Admin`-Rolle darf alle Operationen ausführen.                                                    |
| `Claims`                      | Ansprüche des Benutzers oder der App JSON Web Token (JWT). Die Anspruchseigenschaften variieren je nach Organisation und Azure Active Directory-Konfiguration. |

#### <a name="api-properties-schema"></a>API-Eigenschaftenschema

[API-Ereignisse](apis.md) haben die folgenden Eigenschaften.

| Feld                        | Beschreibung des Dataflows                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Immer `ApiEvent`, wodurch das Protokollereignis als API-Ereignis markiert wird.                                                                 |
| `properties.userAgent`       | Browser-Agent, der die Anfrage oder `unknown` sendet.                                                                        |
| `properties.method`          | HTTP-Methode: `GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Relativer Pfad der Anforderung                                                                                          |
| `properties.origin`          | URI, die angibt, woher ein Abruf kommt, oder `unknown`.                                                                  |
| `properties.operationStatus` | `Success` für einen HTTP-Statuscode < 400 <br> `ClientError` für einen HTTP-Statuscode < 500 <br> `Error` für einen HTTP-Status >= 500 |
| `properties.tenantId`        | Organisations-ID                                                                                                        |
| `properties.tenantName`      | Name der Organisation.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory-ObjectId des Aufrufers.                                                                         |
| `properties.instanceId`      | Customer Insights-`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Workflow-Ereignisschema

Der Workflow enthält mehrere Schritte. [Datenquellen einbinden](data-sources.md), Daten [vereinheitlichen](data-unification.md), [anreichern](enrichment-hub.md) und [exportieren](export-destinations.md). Alle diese Schritte können einzeln oder mit folgenden Prozessen orchestriert ausgeführt werden.

#### <a name="operation-types"></a>Vorgangstypen

| OperationType     | Gruppieren                                     |
| ----------------- | ----------------------------------------- |
| Erfassung         | [Datenquellen](data-sources.md)           |
| DataPreparation   | [Datenquellen](data-sources.md)           |
| Zuordnung               | [Datenvereinigung](data-unification.md)   |
| Abgleichen             | [Datenvereinigung](data-unification.md)   |
| Merge             | [Datenvereinigung](data-unification.md)   |
| ProfileStore      | [Kundenprofile](customer-profiles.md) |
| Suche            | [Kundenprofile](customer-profiles.md) |
| Aktivität          | [Aktivitäten](activities.md)                  |
| AttributeMeasures | [Segmente und Kennzahlen](segments.md)      |
| EntityMeasures    | [Segmente und Kennzahlen](segments.md)      |
| Measures          | [Segmente und Kennzahlen](segments.md)      |
| Segmentierung      | [Segmente und Kennzahlen](segments.md)      |
| Anreicherung        | [Anreicherung](enrichment-hub.md)                                          |
| Intelligenz      | [Vorhersagen](predictions-overview.md)                                          |
| AiBuilder         | [Vorhersagen](predictions-overview.md)                                          |
| Insights          | [Vorhersagen](predictions-overview.md)                                          |
| Export            | [Exporte](export-destinations.md)                                          |
| ModelManagement   | [Vorhersagen](custom-models.md)                                           |
| Relationship      | [Datenvereinigung](relationships.md)                                           |

#### <a name="field-description"></a>Feldbeschreibung

| Feld           | Datentyp  | erforderlich/optional | Beschreibung des Dataflows                                                                                                                                                   | Beispiel                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Zeitstempel | Erforderlich          | Zeitstempel des Ereignisses (UTC)                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Erforderlich          | ResourceId der Instanz, die das Ereignis ausgegeben hat                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Erforderlich          | Name des Vorgangs, der durch dieses Ereignis dargestellt wird. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Weitere Informationen finden Sie unter [Vorgangstypen](#operation-types). | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Erforderlich          | Protokollkategorie des Ereignisses Immer `Operational` für Workflow-Ereignisse                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Erforderlich          | Status des Ereignisses `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Lang      | Optional          | Dauer des Vorgangs in Millisekunden                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Optional          | JSON-Objekt mit mehr Eigenschaften für die jeweilige Ereigniskategorie.                                                                                        | Weitere Informationen finden Sie im Unterabschnitt [Workflow-Eigenschaften](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Erforderlich          | Schweregrad des Ereignisses                                                                                                                                  | `Informational`, `Warning` oder `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Eigenschaftenschema für Workflows

Workflow-Ereignisse haben die folgenden Eigenschaften.

| Feld              | Workflow | Task | Beschreibung des Dataflows            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Ja      | Ja  | Immer `WorkflowEvent`, wodurch das Ereignis als Workflow-Ereignis markiert wird.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Ja      | Ja  | Bezeichner der Workflowausführung Alle Workflow- und Aufgabenereignisse innerhalb der Workflow-Ausführung haben dieselbe `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Ja      | Ja  | Bezeichner des Vorgangs, siehe [Vorgangstypen](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Ja      | Nr.   | Nur Workflow Anzahl der vom Workflow ausgelösten Aufgaben                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Ja      | Nr.   | Optional. Nur Workflow-Ereignisse Die Azure Active Directory [objectId des Benutzers](/azure/marketplace/find-tenant-object-id#find-user-object-id), der den Workflow ausgelöst hat, siehe auch `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Ja      | Nr.   | `full` oder `incremental` Aktualisierung.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Ja      | Nr.   | `OnDemand` oder `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Ja      | Nr.   | `Running` oder  `Successful`                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Ja      | Ja  | UTC-Zeitstempel`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Ja      | Ja  | UTC-Zeitstempel`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Ja      | Ja  | UTC-Zeitstempel`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Ja      | Ja  | Customer Insights-`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | Nr.       | Ja  | - Für OperationType = `Export` ist der Bezeichner die GUID der Exportkonfiguration. <br> - Für OperationType =`Enrichment` ist es die GUID der Anreicherung <br> - Für OperationType `Measures` und `Segmentation` ist der Bezeichner der Entitätsname. |
| `properties.friendlyName`                    | Nr.       | Ja  | Benutzerfreundlicher Name des Exports oder der verarbeiteten Entität                                                                                                                                                                                           |
| `properties.error`                           | Nr.       | Ja  | Optional. Fehlermeldung mit mehr Details                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | Nr.       | Ja  | Optional. Nur für den OperationType `Export` Gibt den Typ des Exports an Weitere Informationen finden Sie unter [Übersicht über Exportziele](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | Nr.       | Ja  | Optional. Nur für den OperationType `Export` Enthält eine Liste der konfigurierten Entitäten im Export                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | Nr.       | Ja  | Optional. Nur für den OperationType `Export` Detaillierte Meldung für den Export                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | Nr.       | Ja  | Optional. Nur für den OperationType `Segmentation` Gibt die Gesamtzahl der Mitglieder des Segments an.                                                                                                                                                    |
