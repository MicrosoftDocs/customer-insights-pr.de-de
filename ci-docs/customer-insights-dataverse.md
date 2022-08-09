---
title: Arbeiten mit Customer Insights-Daten in Microsoft Dataverse
description: Erfahren Sie, wie Sie Customer Insights und Microsoft Dataverse verbinden und die Ausgabeentitäten verstehen, die in Dataverse exportiert werden.
ms.date: 07/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 89ff629033230de3c6252b6a3a16816d9b3c1287
ms.sourcegitcommit: 85b198de71ff2916fee5500ed7c37c823c889bbb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2022
ms.locfileid: "9153403"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Arbeiten mit Customer Insights-Daten in Microsoft Dataverse

Customer Insights bietet die Option, Ausgabeentitäten als [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro) verfügbar zu machen. Diese Integration ermöglicht durch einen Low-Code-/No-Code-Ansatz die einfache Datenfreigabe und eine benutzerdefinierte Entwicklung. Die [Ausgabeeinheiten](#output-entities) sind als Tabellen in einer Dataverse Umgebung verfügbar. Sie können die Daten für jede andere Anwendung auf der Grundlage von Dataverse Tabellen verwenden. Diese Tabellen ermöglichen Szenarien wie automatisierte Workflows durch Power Automate oder Apps erstellen mit Power Apps.

Durch Verbindung zu Ihrer Dataverse-Umgebung können Sie auch [Daten aus lokalen Datenquellen mit Power Platform-Dataflows und Gateways erfassen](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Anforderungen

- Customer Insights und Dataverse Umgebungen müssen in derselben Region gehostet werden.
- Sie müssen eine globale Administratorrolle in der Dataverse Umgebung haben. Überprüfen Sie, ob dieses [Dataverse Umfeld mit](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) bestimmten Sicherheitsgruppen verknüpft ist und stellen Sie sicher, dass Sie zu diesen Sicherheitsgruppen hinzugefügt werden.
- Es ist noch keine andere Customer Insights Umgebung mit dieser Dataverse Umgebung verknüpt, die Sie verbinden möchten. Lernen wie man eine [bestehende Verbindung in einer Dataverse Umgebung](#remove-an-existing-connection-to-a-dataverse-environment) entfernt.
- Eine Microsoft Dataverse Umgebung kann nur eine Verbindung zu einem einzigen Speicherkonto herstellen. Dies gilt nur, wenn Sie die Umgebung entsprechend konfigurieren, dass Ihr [Azure Data Lake Storage](own-data-lake-storage.md) verwendet wird.

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse-Speicherkapazität, Anspruch

Ein Customer Insights-Abonnement berechtigt Sie zu zusätzlicher Kapazität für die vorhandene [Dataverse-Speicherkapazität](/power-platform/admin/capacity-storage). Die zusätzliche Kapazität hängt von der Anzahl der Profile ab, die Ihr Abonnement verwendet.

**Beispiel**:

Angenommen, Sie erhalten 15 GB Datenbankspeicher und 20 GB Dateispeicher pro 100.000 Kundenprofile. Wenn Ihr Abonnement 300.000 Kundenprofile umfasst, beträgt Ihre Gesamtspeicherkapazität 45 GB (3 x 15 GB) Datenbankspeicher und 60 GB Dateispeicher (3 x 20 GB). Wenn Sie ein B2B-Abonnement mit 30.000 Konten haben, beträgt Ihre Gesamtspeicherkapazität 45 GB (3 x 15 GB) Datenbankspeicher und 60 GB Dateispeicher (3 x 20 GB).

Die Protokollkapazität ist nicht inkrementell und für Ihre Organisation festgelegt.

Weitere Informationen zu Kapazitätsberechtigungen finden Sie im [Dynamics 365-Lizenzierungshandbuch](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Verbinden Sie eine Dataverse Umgebung mit Customer Insights

Der **Microsoft Dataverse**-Schritt lässt Sie Customer Insights mit Ihrer Dataverse Umgebung verbinden, während [eine Customer Insights-Umgebung erstellt wird](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Datenaustausch mit Microsoft Dataverse automatisch für neue Umgebungen aktiviert.":::

Administratoren können Customer Insights konfigurieren, um eine vorhandene Dataverse Umgebung zu verbinden. Indem Sie die URL der Dataverse-Umgebung bereitstellen, verbinden Sie sie mit ihrer neuen Customer Insights Umgebung. Nach dem Herstellen der Verbindung zwischen Customer Insights und Dataverse, ändern Sie nicht den Organisationsnamen für die Dataverse-Umgebung. Der Name der Organisation wird in der Dataverse-URL verwendet und ein geänderter Name unterbricht die Verbindung mit Customer Insights.

Wenn Sie keine vorhandene Dataverse Umgebung verwenden möchten, erstellt das System eine neue Umgebung für die Customer Insights-Daten in Ihrem Mandanten. [Power Platform Administratoren können kontrollieren, wer Umgebungen erstellen darf](/power-platform/admin/control-environment-creation). Wenn Sie eine neue Customer Insights-Umgebung einrichten und der Administrator die Erstellung von Dataverse-Umgebungen für alle außer Administratoren deaktiviert hat, können Sie möglicherweise keine neue Umgebung erstellen.

**Datenfreigabe aktivieren** mit Dataverse, indem Sie das Kontrollkästchen „Datenfreigabe“ aktivieren.

Wenn Sie Ihr eigenes Data Lake Storage-Konto verwenden, benötigen Sie auch die **Berechtigungskennung**. Weitere Informationen zum Abrufen der Berechtigungs-ID finden Sie im folgenden Abschnitt.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Datenfreigabe aktivieren mit Dataverse von Ihrem eigenen Azure Data Lake Storage (Vorschau)

Das Aktivieren der Datenfreigabe mit Microsoft Dataverse, wenn Ihre Umgebung [Ihr eigenes Azure Data Lake Storage-Konto verwendet](own-data-lake-storage.md), benötigt eine zusätzliche Konfiguration. Der Benutzer, der die Customer Insights-Umgebung einrichtet, muss mindestens **Datenleser des Speicher-Blobs**-Berechtigungen für den *CustomerInsights*-Container im Azure Data Lake Storage-Konto haben.

1. Erstellen Sie zwei Sicherheitsgruppen für Ihr Azure-Abonnement, nämlich eine **Leser** Sicherheitsgruppe und eine **Teilnehmer** Sicherheitsgruppe und legen Sie den Microsoft Dataverse Dienst als Besitzer für beide Sicherheitsgruppen fest.
2. Verwalten Sie die Zugriffssteuerungsliste (ACL) für den Customer Insights Container in Ihrem Speicherkonto über diese Sicherheitsgruppen. Ergänzen Sie den Microsoft Dataverse Dienst und alle Dataverse -basierten Geschäftsanwendungen wie Dynamics 365 Marketing an die **Leser** Sicherheitsgruppe mit der Berechtigung **schreibgeschützt**. Fügen Sie *nur* die Customers Insights-Anwendung der Sicherheitsgruppe **Mitwirkender** hinzu, um sowohl **Lese- wie auch Schreib-** Berechtigungen zum Schreiben von Profilen und Erkenntnissen zu gewähren.

### <a name="limitations"></a>Einschränkungen

Es gibt zwei Einschränkungen bei der Verwendung von Dataverse mit dem eigenen Azure Data Lake Storage-Konto:

- Es gibt eine Eins-zu-Eins-Zuordnung zwischen einer Dataverse Organisation und einem Azure Data Lake Storage Konto. Wenn eine Dataverse Organisation mit einem Speicherkonto verbunden ist, kann sie keine Verbindung mit einem anderen Speicherkonto herstellen. Diese Einschränkung verhindert, dass Dataverse nicht mehrere Speicherkonten füllt.
- Die Datenfreigabe funktioniert nicht, wenn eine Azure Private Link-Einrichtung erforderlich ist, um auf Ihr Azure Data Lake Storage Konto zuzugreifen, da es sich hinter einer Firewall befindet. Dataverse unterstützt derzeit keine Verbindung zu privaten Endpunkten über Private Link.

### <a name="set-up-powershell"></a>PowerShell einrichten

Um die PowerShell-Skripte auszuführen, müssen Sie PowerShell zunächst entsprechend einrichten.

1. Neueste Version von [Azure Active Directory PowerShell für Graph](/powershell/azure/active-directory/install-adv2).
   1. Wählen Sie auf Ihrem PC die Windows-Taste auf Ihrer Tastatur und suchen Sie nach **Windows PowerShell** und wählen Sie **Als Administrator ausführen**.
   1. Geben Sie in dem sich öffnenden PowerShell-Fenster `Install-Module AzureAD` ein.
2. Importieren Sie drei Module.
    1. Im Fenster PowerShell geben Sie `Install-Module -Name Az.Accounts` ein und folgen diesen Schritten.
    1. Für `Install-Module -Name Az.Resources` und `Install-Module -Name Az.Storage` wiederholen.

### <a name="configuration-steps"></a>Konfigurationsschritte

1. Laden Sie die beiden PowerShell-Skripts herunter, die Sie zum Ausführen vom [GitHub-Repository](https://github.com/trin-msft/byol) von unserem Techniker benötigen.
    1. `CreateSecurityGroups.ps1`
       - Zum Ausführen dieses PowerShell-Skrips benötigen Sie die *Mandand-Admin* Berechtigungen.
       - Dieses PowerShell-Skript erstellt zwei Sicherheitsgruppen in Ihrem Azure-Abonnement. Eine für die Gruppe Leser und eine für die Gruppe Mitwirkender. Microsoft Dataverse Dienst wird zum Besitzer für diese beiden Sicherheitsgruppen.
       - Führen Sie dieses PowerShell-Skript in Windows PowerShell aus, indem Sie die Azure-Abonnement-ID angeben, die Ihre Azure Data Lake Storage enthält. Öffnen Sie das PowerShell-Skript in einem Editor, um zusätzliche Informationen und die implementierte Logik zu überprüfen.
       - Speichern Sie beide von diesem Skript generierten Sicherheitsgruppen-ID-Werte, da wir sie im `ByolSetup.ps1` Skript verwenden.

        > [!NOTE]
        > Die Erstellung von Sicherheitsgruppen kann auf Ihrem Mandanten deaktiviert werden. In diesem Fall wäre eine manuelle Einrichtung erforderlich und Ihr Azure AD Administrator müsste[ die Erstellung von Sicherheitsgruppen aktivieren](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Sie brauchen die *Speicherblob-Datenbesitzer* Berechtigungen auf Speicherkonto-/Containerebene zum Ausführen dieses Skripts, oder dieses Skript erstellt eines für Sie. Ihre Rollenzuweisung kann nach erfolgreicher Ausführung des Skripts manuell entfernt werden.
        - Dieses PowerShell-Skript fügt die erforderliche rollenbasierte Zugriffssteuerung für den Microsoft Dataverse Dienst und alle Dataverse-basierte Geschäftsanwendungen hinzu. Außerdem wird die Zugriffssteuerungsliste (ACL) im CustomerInsights-Container für die Sicherheitsgruppen, die mit dem `CreateSecurityGroups.ps1` Skript erstellt wurden aktualisiert. Die Gruppe Mitwirkender erhält die *rwx* Berechtigung, während die Lesergruppe nur die *r-x* Berechtigung erhält.
        - Führen Sie dieses PowerShell-Skript in Windows PowerShell aus, indem Sie die Azure-Abonnement-ID angeben, die Ihre Azure Data Lake Storage, Speicherkontoname, Ressourcengruppenname und die Leser und Teilnehmer Sicherheitsgruppen-ID-Werte enthält. Öffnen Sie das PowerShell-Skript in einem Editor, um zusätzliche Informationen und die implementierte Logik zu überprüfen.
        - Kopieren Sie die Ausgabezeichenfolge, nachdem Sie das Skript erfolgreich ausgeführt haben. Die Ausgabezeichenfolge sieht wie folgt aus: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Geben Sie die von oben kopierte Ausgabenzeichenfolge in das Feld **Berechtigungskennung** des Umgebungskonfigurationsschritts für Microsoft Dataverse ein.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigurationsoptionen zum Aktivieren der Datenfreigabe von Ihren eigenen Azure Data Lake Storage mit Microsoft Dataverse.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Entfernen Sie eine bestehende Verbindung in einer Dataverse Umgebung

Beim Verbinden mit einer Dataverse Umgebung bedeutet die Fehlermeldung **Diese CDS-Organisation ist bereits mit einer anderen Customer Insights-Instanz verbunden**, dass die Dataverse Umgebung bereits in einer Customer Insights-Umgebung verwendet wird. Sie können die bestehende Verbindung als globale Administrator in der Dataverse Umgebung entfernen. Es kann einige Stunden dauern, bis die Änderungen ausgeführt sind.

1. Wechseln Sie zu [Power Apps](https://make.powerapps.com).
1. Wählen Sie die Umgebung aus der Umgebungsauswahl aus.
1. Wechseln Sie zu **Lösungen**
1. Deinstallieren oder löschen Sie die genannte Lösung **Dynamics 365 Customer Insights Kundenkarten-Add-In (Vorschau)**.

ODER

1. Öffnen Sie Ihre Dataverse Umgebung.
1. Gehen Sie zu **Erweiterte Einstellungen** > **Lösungen**.
1. Deinstallieren Sie die **CustomerInsightsCustomerCard** Lösung.

Wenn das Entfernen der Verbindung aufgrund von Abhängigkeiten fehlschlägt, müssen Sie auch die Abhängigkeiten entfernen. Weitere Informationen finden Sie unter [Abhängigkeiten entfernen](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Ausgabeentitäten

Einige Entitäten aus Customer Insights sind als Tabellen in Dataverse verfügbar. In den folgenden Abschnitten wird das erwartete Schema dieser Tabellen beschrieben.

- [CustomerProfile](#customerprofile)
- [AlternateKeys](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Anreicherung](#enrichment)
- [Vorhersage](#prediction)
- [Segmentmitgliedschaft](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Diese Tabelle enthält das einheitliche Kundenprofil von Customer Insights. Das Schema für ein Unified customer profile hängt von den Entitäten und Attributen ab, die im Datenvereinheitlichungsprozess verwendet werden. Ein Kundenprofilschema enthält normalerweise eine Teilmenge der Attribute aus der [Common Data Model-Definition von CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKeys

Die Tabelle „AlternateKey“ enthält Schlüssel der Entitäten, die an der Vereinheitlichung beteiligt waren.

|Column  |Art  |Beschreibung  |
|---------|---------|---------|
|DataSourceName    |String         | Der Name der Datenquelle. Beispiel: '`datasource5`'        |
|EntityName        | String        | Name der Entität in Customer Insights. Beispiel: '`contact1`'        |
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

| Column        | Type | Beschreibung des Dataflows                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Kundenprofil-ID        |
| SegmentProvider      | String       | App, die die Segmente veröffentlicht.      |
| SegmentMembershipType | String       | Typ des Kunden in diesem Segmentmitgliedschaftsdatensatz. Unterstützt mehrere Typen wie Kunde, Kontakt oder Konto. Standard: Kunde  |
| Segmente       | JSON-Zeichenfolge  | Liste einzigartiger Segmente, in denen das Kundenprofil Mitglied ist      |
| msdynci_identifier  | String   | Eindeutiger Bezeichner des Segmentmitgliedschaftsdatensatzes. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministische GUID aus `msdynci_identifier` erstellt          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
