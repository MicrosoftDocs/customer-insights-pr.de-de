---
title: Erstellen und Verwalten von Umgebungen
description: 'Erfahren Sie, wie Sie sich für den Dienst anmelden und wie Sie Umgebungen verwalten können.'
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
  - ci-system-about
  - customerInsights
---

# <a name="manage-environments"></a>Umgebungen verwalten

## <a name="switch-environments"></a>Umgebungen wechseln

Wählen Sie die Option **Umgebung** in der rechten oberen Ecke der Seite, um die Umgebung zu ändern.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Screenshot des Steuerelements zum Wechseln der Umgebung.":::

Administratoren können Umgebungen [erstellen](create-environment.md) und verwalten.

## <a name="edit-an-existing-environment"></a>So bearbeiten Sie eine bestehende Umgebung

Sie können einige Details vorhandener Umgebungen bearbeiten.

1.  Wählen Sie die **Umgebung**-Auswahl in der Kopfzeile der App aus.

2.  Wählen Sie das Symbol **Bearbeiten** aus.

3. In dem Kästchen **Umgebung bearbeiten** können Sie die Umgebungseinstellungen aktualisieren.

Weitere Informationen zu Umgebungseinstellungen finden Sie unter [Schaffen Sie eine neue Umgebung](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Mit Microsoft Dataverse verbinden
   
Mit dem **Microsoft Dataverse** Schritt können Sie Customer Insights mit Ihrer Dataverse Umgebung verbinden. 

Bieten Sie Ihre eigene Microsoft Dataverse-Umgebung, um Daten (Profile und Einblicke) mit auf Dataverse basierenden Geschäftsanwendungen zu teilen, wie Dynamics 365 Marketing oder modellgesteuerte Anwendungen in Power Apps.

Benutzen Sie [Standardmäßige Vorhersage-Modelle](predictions-overview.md#out-of-box-models), konfigurieren Sie Datenfreigaben mit Dataverse. Oder Sie können die Datenaufnahme aus lokale Datenquellen aktivieren, indem Sie die Microsoft Dataverse Umgebungs-URL bereitstellen, die Ihre Organisation verwaltet.

Beim Aktivieren der Datenfreigabe mit Microsoft Dataverse durch Aktivieren des Kontrollkästchens Datenfreigabe wird eine einmalige vollständige Aktualisierung Ihrer Datenquellen und aller anderen Prozesse ausgelöst.

> [!IMPORTANT]
> 1. Customer Insights und Dataverse müssen sich in derselben Region befinden, um die Datenfreigabe zu ermöglichen.
> 1. Sie müssen eine globale Administratorrolle in der Dataverse Umgebung haben. Überprüfen Sie, ob dieses [Dataverse Umfeld mit](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) bestimmten Sicherheitsgruppen verknüpft ist und stellen Sie sicher, dass Sie zu diesen Sicherheitsgruppen hinzugefügt werden.
> 1. Es ist noch keine vorhandene Customer Insights Umgebung mit dieser Dataverse Umgebung verknüpt. Lernen wie man eine [bestehende Verbindung in einer Dataverse Umgebung](#remove-an-existing-connection-to-a-dataverse-environment) entfernt.

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Konfigurationsoptionen zum Aktivieren der Datenfreigabe mit Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Datenfreigabe aktivieren mit Dataverse von Ihrem eigenen Azure Data Lake Storage (Vorschau)

Wenn Ihre Umgebung für die Verwendung Ihrer eigenen Azure Data Lake Storage konfiguriert ist, um Customer Insights-Daten zu speichern und den Datenaustausch mit zu ermöglichen, benötigt Microsoft Dataverse eine zusätzliche Konfiguration.

1. Erstellen Sie zwei Sicherheitsgruppen für Ihr Azure-Abonnement, nämlich eine **Leser** Sicherheitsgruppe und eine **Teilnehmer** Sicherheitsgruppe und legen Sie den Microsoft Dataverse Dienst als Besitzer für beide Sicherheitsgruppen fest.
2. Verwalten Sie die Zugriffssteuerungsliste (ACL) für den Customer Insights Container in Ihrem Speicherkonto über diese Sicherheitsgruppen. Ergänzen Sie den Microsoft Dataverse Dienst und alle Dataverse -basierten Geschäftsanwendungen wie Dynamics 365 Marketing an die **Leser** Sicherheitsgruppe mit der Berechtigung **schreibgeschützt**. Fügen Sie *nur* die Customers Insights-Anwendung der Sicherheitsgruppe **Mitwirkender** hinzu, um sowohl **Lese- wie auch Schreib-** Berechtigungen zum Schreiben von Profilen und Erkenntnissen zu gewähren.
   
#### <a name="prerequisites"></a>Anforderungen

Um die PowerShell-Skripte auszuführen, müssen Sie die folgenden drei Module importieren. 

1. Neueste Version von [Azure Active Directory PowerShell für Graph](/powershell/azure/active-directory/install-adv2).
   1. Wählen Sie auf Ihrem PC die Windows-Taste auf Ihrer Tastatur und suchen Sie nach **Windows PowerShell** und wählen Sie **Als Administrator ausführen**.
   1. Geben Sie in dem sich öffnenden PowerShell-Fenster `Install-Module AzureAD` ein.
2. Importieren Sie drei Module.
    1. Im Fenster PowerShell geben Sie `Install-Module -Name Az.Accounts` ein und folgen diesen Schritten. 
    1. Für `Install-Module -Name Az.Resources` und `Install-Module -Name Az.Storage` wiederholen.

#### <a name="configuration-steps"></a>Konfigurationsschritte

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
        - Dieses PowerShell-Skript fügt die erforderliche Tool-basierte Zugriffssteuerung (RBAC) für den Microsoft Dataverse Dienst und alle Dataverse-basierte Geschäftsanwendungen hinzu. Außerdem wird die Zugriffssteuerungsliste (ACL) im CustomerInsights-Container für die Sicherheitsgruppen, die mit dem `CreateSecurityGroups.ps1` Skript erstellt wurden aktualisiert. Die Gruppe Mitwirkender erhält die *rwx* Berechtigung, während die Lesergruppe nur die *r-x* Berechtigung erhält.
        - Führen Sie dieses PowerShell-Skript in Windows PowerShell aus, indem Sie die Azure-Abonnement-ID angeben, die Ihre Azure Data Lake Storage, Speicherkontoname, Ressourcengruppenname und die Leser und Teilnehmer Sicherheitsgruppen-ID-Werte enthält. Öffnen Sie das PowerShell-Skript in einem Editor, um zusätzliche Informationen und die implementierte Logik zu überprüfen.
        - Kopieren Sie die Ausgabezeichenfolge, nachdem Sie das Skript erfolgreich ausgeführt haben. Die Ausgabezeichenfolge sieht wie folgt aus: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Geben Sie die von oben kopierte Ausgabenzeichenfolge in das Feld **Berechtigungskennung** des Umgebungskonfigurationsschritts für Microsoft Dataverse ein.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigurationsoptionen zum Aktivieren der Datenfreigabe von Ihren eigenen Azure Data Lake Storage mit Microsoft Dataverse.":::

Customer Insights unterstützt die folgenden Datenfreigabe-Szenarien nicht:
- Wenn Sie die Datenfreigabe mit einem verwalteten Dataverse Data Lake aktivieren, können Sie keine [vorhergesagten oder fehlenden Werten in einer Entität erstellen](predictions.md).
- Wenn Sie die Datenfreigabe mit Dataverse aktivieren, können Sie keine optionalen PowerBI eingebettete-Berichte in Ihrer Customer Insights-Umgebung anzeigen.

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

## <a name="copy-the-environment-configuration"></a>Umgebungskonfiguration kopieren

Als Administrator können Sie die Konfiguration aus einer vorhandenen Umgebung kopieren, wenn Sie eine neue erstellen. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Screenshot der Einstellungsoptionen in den Umgebungseinstellungen.":::

Sie sehen eine Liste aller verfügbaren Umgebungen in Ihrer Organisation, aus der Sie Daten kopieren können.

Folgende Konfigurationseinstellungen werden kopiert:

- Aufgenommene/importierte Datenquellen
- Datenvereinheitlichung (Map, Match, Merge) Konfiguration
- Segmente
- Kennzahlen
- Beziehungen
- Aktivitäten
- Index suchen & filtern
- Exportziele
- Geplante Aktualisierung
- Anreicherungen
- Modell-Management
- Zuweisungen von Rollen

## <a name="set-up-a-copied-environment"></a>Einrichten einer kopierten Umgebung

Wenn Sie die Umgebungskonfiguration kopieren, sind die folgenden Daten *nicht* kopiert:

- Kundenprofile.
- Anmeldeinformationen für die Datenquelle. Sie müssen die Anmeldeinformationen für jede Datenquelle angeben und die Datenquellen manuell aktualisieren.
- Datenquellen aus dem Common Data Model-Ordner und Dataverse-verwalteter Data Lake. Sie müssen diese Datenquellen manuell mit demselben Namen wie in der Quellumgebung erstellen.
- Verbindungsgeheimnisse, die für Exporte und Anreicherungen verwendet werden. Sie müssen die Verbindungen erneut authentifizieren und anschließend Anreicherungen und Exporte erneut aktivieren. 

Wenn Sie eine Umgebung kopieren, wird eine Bestätigungsmeldung angezeigt, dass die neue Umgebung erstellt wurde. Wählen Sie **Gehen Sie zu Datenquellen**, um die Liste der Datenquellen anzuzeigen.

Alle Datenquellen zeigen einen Status **Anmeldeinformationen erforderlich**. Bearbeiten Sie die Datenquellen und geben Sie die Anmeldeinformationen ein, um sie zu aktualisieren.

:::image type="content" source="media/data-sources-copied.png" alt-text="Liste der Datenquellen, die kopiert wurden und eine Authentifizierung benötigen.":::

Nachdem Sie die Datenquellen aktualisiert haben, gehen Sie zu **Daten** > **Vereinheitlichen**. Hier finden Sie Einstellungen aus der Quellumgebung. Bearbeiten Sie sie nach Bedarf oder wählen Sie **Ausführen**, um den Datenvereinheitlichungsprozess zu starten und die einheitliche Kundenentität zu erstellen.

Wenn die Datenvereinheitlichung abgeschlossen ist, gehen Sie zu **Maßnahmen** und **Segmente**, um sie auch zu aktualisieren.

Bevor Sie Exporte und Anreicherungen reaktivieren, gehen Sie zu **Administrator** > **Verbindungen**, um die Verbindungen in Ihrer neuen Umgebung erneut zu authentifizieren.

## <a name="change-the-owner-of-an-environment"></a>Den Besitzer einer Umgebung ändern

Während mehrere Benutzer Administratorberechtigungen in Customer Insights haben können, ist nur ein Benutzer der Eigentümer einer Umgebung. Standardmäßig erstellt zunächst der Administrator eine Umgebung. Als Administrator einer Umgebung können Sie einem anderen Benutzer mit Administratorberechtigungen die Eigentümerschaft zuweisen.

1. Wählen Sie die **Umgebung**-Auswahl in der Kopfzeile der App aus.

1. Wählen Sie das Symbol **Bearbeiten** aus.

1. In dem Kästchen **Umgebung bearbeiten** gehen Sie zum Schritt **Grundinformation**.

1. In dem Feld **Eigentümer der Umgebung ändern** wählen Sie den neuen Eigentümer der Umgebung aus.  

1. Wählen Sie **Überprüfen und beenden** und dann **Aktualisieren**, um die Änderungen zu übernehmen. 

## <a name="claim-ownership-of-an-environment"></a>Beanspruchen Sie den Besitz einer Umgebung

Wenn der Eigentümer einer Umgebung die Organisation verlässt oder sein Benutzerkonto gelöscht wird, hat die Umgebung keinen Eigentümer. Ein Benutzer mit Administratorberechtigungen kann die Eigentümerschaft beanspruchen und der neue Eigentümer werden. Sie können weiterhin die Umwelt besitzen oder [den Besitz auf einen anderen Administrator übertragen](#change-the-owner-of-an-environment). 

Um den Besitz zu beanspruchen, wählen Sie die Schaltfläche **In Besitz nehmen** aus, die oben auf jeder Seite in Customer Insights angezeigt wird, wenn der ursprüngliche Eigentümer die Organisation verlassen hat.

## <a name="reset-an-existing-environment"></a>Zurücksetzen einer bestehenden Umgebung

Als Besitzer einer Umgebung können Sie eine Umgebung auf einen leeren Zustand zurücksetzen, wenn Sie nur die Konfigurationen und eingebundene Daten entfernen, die Umgebung jedoch behalten möchten.

1.  Wählen Sie die **Umgebung**-Auswahl in der Kopfzeile der App aus. 

2.  Wählen Sie die Umgebung aus, die Sie zurücksetzen möchten, und wählen Sie die Auslassungspunkte (**...**) aus. 

3. Wählen Sie die Option **Zurücksetzen** aus. 

4.  Um das Löschen zu bestätigen, geben Sie den Namen der Umgebung ein und wählen Sie **Zurücksetzen**.

## <a name="delete-an-existing-environment"></a>Löschen Sie eine vorhandene Umgebung

Als Besitzer einer Umgebung können Sie eine von Ihnen verwaltete Umgebung löschen.

1.  Wählen Sie die **Umgebung**-Auswahl in der Kopfzeile der App aus.

2.  Wählen Sie die Umgebung aus, die Sie zurücksetzen möchten, und wählen Sie die Auslassungspunkte (**...**) aus. 

3. Wählen Sie die Option **Löschen** aus. 

4.  Um das Löschen zu bestätigen, geben Sie den Namen der Umgebung ein und wählen Sie **Löschen**.

> [!NOTE]
> Das Löschen einer Umgebung entfernt nicht die Zuordnung zu einer Dataverse Umwelt. Erfahren Sie, wie Sie eine [Verbindung mit einer Dataverse Umgebung entfernen](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
