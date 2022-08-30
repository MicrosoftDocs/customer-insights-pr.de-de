---
title: Verbinden Sie sich mit einem Azure Data Lake Storage Konto mithilfe eines Azure Dienstprinzipals
description: Verwenden Sie einen Azure-Dienstprinzipal, um eine Verbindung zu Ihrem eigenen Data Lake herzustellen.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: eba10068c48db5c147100c25a397bcc13b014784
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304196"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Verbinden Sie sich mit einem Azure Data Lake Storage Konto mithilfe eines Azure Dienstprinzipals

Dynamics 365 Customer Insights stellt eine Option bereit, um mit einem Azure Data Lake Storage Konto mithilfe eines Azure Dienstprinzipals anstelle von Speicherkontoschlüsseln zu verbinden.

Automatisierte Tools, die Azure-Dienste nutzen, sollten immer eingeschränkte Berechtigungen haben. Anstatt dass sich Anwendungen als voll privilegierter Benutzer anmelden müssen, bietet Azure Dienstprinzipale an. Sie können Dienstprinzipale zum sicheren [Hinzufügen oder Bearbeiten eines Common Data Model-Ordners als Datenquelle](connect-common-data-model.md) bzw. [Erstellen oder Aktualisieren einer Umgebung](create-environment.md) verwenden.

## <a name="prerequisites"></a>Anforderungen

- Für das Data Lake Storage-Konto, das den Dienstprinzipal verwendet, muss der hierarchische Namespace Gen2 lauten. Azure Data Lake Gen1-Speicherkonten werden nicht unterstützt.
- Bei dem Azure Data Lake Speicherkonto muss [hierarchischer Namespace aktiviert](/azure/storage/blobs/data-lake-storage-namespace) sein.
- Sie benötigen Administratorberechtigungen für Ihren Azure-Mandanten, um einen Dienstprinzipal zu erstellen.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Erstellen eines Azure-Dienstprinzipals für Customer Insights

Überprüfen Sie vor dem Erstellen eines neuen Dienstprinzipals für Customer Insights, ob dieser bereits in Ihrer Organisation vorhanden ist. In den meisten Fällen ist es bereits vorhanden.

### <a name="look-for-an-existing-service-principal"></a>Suchen Sie nach einem vorhandenen Service-Prinzipal

1. Gehen Sie zum [Azure-Admin-Portal](https://portal.azure.com) und melden Sie sich bei Ihrer Organisation an.

2. Wählen Sie unter **Azure-Dienste** **Azure Active Directory** aus.

3. Wählen Sie unter **Verwalten** **Microsoft-Anwendung** aus.

4. Fügen Sie einen Filter hinzu für **Anwendungs-ID beginnt mit** `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff`, oder suchen Sie nach dem Namen `Dynamics 365 AI for Customer Insights`.

5. Wenn Sie einen übereinstimmenden Datensatz finden, bedeutet dies, dass der Dienstprinzipal bereits vorhanden ist. [Berechtigung erteilen](#grant-permissions-to-the-service-principal-to-access-the-storage-account) für den Zugriff auf das Speicherkonto.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Screenshot, der einen vorhandenen Dienstprinzipal zeigt.":::

6. Wenn keine Ergebnisse zurückgegeben werden, [erstellen Sie einen neuen Dienstprinzipal](#create-a-new-service-principal).

### <a name="create-a-new-service-principal"></a>Erstellen Sie ein neues Service-Prinzipal

1. Neueste Version von Azure Active Directory PowerShell für Graph. Weitere Informationen finden Sie unter [Installieren von Azure Active Directory PowerShell für Graph](/powershell/azure/active-directory/install-adv2).

   1. Drücken Sie auf Ihrem PC die Windows-Taste auf Ihrer Tastatur und suchen Sie nach **Windows PowerShell** und wählen Sie **Als Administrator ausführen**.

   1. Geben Sie in dem sich öffnenden PowerShell-Fenster `Install-Module AzureAD` ein.

2. Erstellen Sie den Dienstprinzipal für Customer Insights mit dem Azure AD PowerShell-Modul.

   1. Geben Sie im PowerShell-Fenster `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure` ein. Ersetzen Sie *[Ihre Directory ID]* durch die tatsächliche Verzeichnis-ID Ihres Azure Abonnements, in dem Sie den Dienstprinzipal erstellen möchten. Der Parameter für den Umgebungsnamen `AzureEnvironmentName` ist optional.
  
   1. Geben Sie `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` ein. Mit diesem Befehl erstellen Sie das Dienstprinzipal für Customer Insights auf dem ausgewählten Azure Abonnement.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Erteilen Sie dem Service Principal Berechtigungen für den Zugriff auf das Speicherkonto

Um dem Dienstprinzipal Berechtigungen für das Speicherkonto zu erteilen, das Sie in Customer Insights verwenden möchten, muss dem Speicherkonto oder Container eine der folgenden Rollen zugewiesen werden:

|Anmeldeinformation|Anforderungen|
|----------|------------|
|Angemeldeter Benutzer|**Rolle**: Storage Blob-Datenleser, Storage Blob Teilnehmer oder Storage Blob Besitzer.<br>**Ebene**: Berechtigungen können für das Speicherkonto oder den Container erteilt werden.</br>|
|Customer Insights Dienstprinzipal -<br>Verwenden von Azure Data Lake Storage als Datenquelle</br>|Option 1<ul><li>**Rolle**: Storage Blob-Datenleser, Storage Blob Daten     Teilnehmer oder Storage Blob Datenbesitzer.</li><li>**Ebene**: Berechtigungen sollten für das Speicherkonto erteilt werden.</li></ul>Option 2 *(ohne den Dienstprinzipalzugriff auf das Speicherkonto freizugeben)*<ul><li>**Rolle 1**: Storage Blob-Datenleser, Storage Blob Datenteilnehmer oder Storage Blob Datenbesitzer.</li><li>**Ebene**: Berechtigungen sollten für den Container erteilt werden.</li><li>**Rolle 2**: Speicherblob-Datendelegator.</li><li>**Ebene**: Berechtigungen sollten für das Speicherkonto erteilt werden.</li></ul>|
|Customer Insights Dienstprinzipal - <br>Azure Data Lake Storage als Ausgang oder Ziel verwenden</br>|Option 1<ul><li>**Rolle**: Storage Blob-Mitwirkender oder Storage Blob Besitzer.</li><li>**Ebene**: Berechtigungen sollten für das Speicherkonto erteilt werden.</li></ul>Option 2 *(ohne den Dienstprinzipalzugriff auf das Speicherkonto freizugeben)*<ul><li>**Rolle**: Storage Blob-Mitwirkender oder Storage Blob Besitzer.</li><li>**Ebene**: Berechtigungen sollten für den Container erteilt werden.</li><li>**Rolle 2**: Speicherblob-Datendelegator.</li><li>**Ebene**: Berechtigungen sollten für das Speicherkonto erteilt werden.</li></ul>|

1. Gehen Sie zum [Azure-Admin-Portal](https://portal.azure.com) und melden Sie sich bei Ihrer Organisation an.

1. Öffnen Sie das Speicherkonto, auf das das Dienstprinzipal für Customer Insights Zugriff haben soll.

1. Wählen Sie im linken Navigationsbereich **Zugriffssteuerung (IAM)** und dann **Hinzufügen** >  **Rollenzuweisung hinzufügen** aus.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Screenshot, der das Azure-Portal beim Hinzufügen einer Rollenzuweisung zeigt.":::

1. Im Bereich **Rollenzuweisung hinzufügen** legen Sie die folgenden Eigenschaften fest:
   - **Rolle**: Storage Blob-Datenleser, Storage Blob Mitbesitzer oder Storage Blob Besitzer basierend auf Anmeldeinfromationen, die oben aufgeführt sind.
   - **Weisen Sie den Zugriff zu**: **Benutzer, Gruppe oder Dienstprinzipal**
   - **Wählen** Sie Mitglieder: **Dynamics 365 KI für Customer Insights** (das [Dienstprinzipal](#create-a-new-service-principal), das Sie zuvor in diesem Verfahren gesucht haben)

1. Wählen Sie **Überprüfen + zuweisen**.

Es kann bis zu 15 Minuten dauern, bis die Änderungen propagiert werden.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Geben Sie die Azure-Ressourcen-ID oder die Details des Azure-Abonnements in den Anhang des Speicherkontos für Customer Insights ein.

Ein Data Lake Storage-Konto in Customer Insights zu [Ausgabedaten speichern](manage-environments.md) oder [als Datenquelle nutzen](connect-dataverse-managed-lake.md) anhängen. Zwischen einem [ressourcenbasierten](#resource-based-storage-account-connection) oder einem [abonnementbasierten](#subscription-based-storage-account-connection) Ansatz wählen und wie folgt vorgehen.

### <a name="resource-based-storage-account-connection"></a>Ressourcen-basierte Speicherkonto-Verbindung

1. Gehen Sie zum [Azure Admin-Portal](https://portal.azure.com), melden Sie sich bei Ihrem Abonnement an und öffnen Sie das Speicherkonto.

1. Gehen Sie im linken Bereich zu **Einstellungen** > **Endpunkte**.

1. Kopieren Sie den Wert der Ressourcen-ID des Speicherkontos.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopieren Sie die Ressourcen-ID des Speicherkontos.":::

1. Fügen Sie in Customer Insights die Ressourcen-ID in das Ressourcenfeld ein, das auf dem Bildschirm für die Verbindung zum Speicherkonto angezeigt wird.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Geben Sie die Ressourcen-ID des Speicherkontos ein.":::

1. Fahren Sie mit den übrigen Schritten in Customer Insights fort, um das Speicherkonto anzuhängen.

### <a name="subscription-based-storage-account-connection"></a>Abonnement-basierte Speicherkontoverbindung

1. Gehen Sie zum [Azure Admin-Portal](https://portal.azure.com), melden Sie sich bei Ihrem Abonnement an und öffnen Sie das Speicherkonto.

1. Gehen Sie im linken Bereich zu **Einstellungen** > **Eigenschaften**.

1. Überprüfen Sie das **Abonnement**, die **Ressourcengruppe** und den **Name** des Speicherkontos, um sicherzustellen, dass Sie die richtigen Werte in Customer Insights auswählen.

1. Wählen Sie in Customer Insights beim Anhängen des Speicherkontos die Werte für die entsprechenden Felder.

1. Fahren Sie mit den übrigen Schritten in Customer Insights fort, um das Speicherkonto anzuhängen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
