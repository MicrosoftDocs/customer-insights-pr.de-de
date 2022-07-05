---
title: Verbinden Sie sich mit einem Azure Data Lake Storage Konto mithilfe eines Azure Dienstprinzipals
description: Verwenden Sie einen Azure-Dienstprinzipal, um eine Verbindung zu Ihrem eigenen Data Lake herzustellen.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 949caa73578dbe0a511726ec045c0fd5f4621de4
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081011"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Verbinden Sie sich mit einem Azure Data Lake Storage Konto mithilfe eines Azure Dienstprinzipals

In diesem Artikel wird erläutert, wie Sie Dynamics 365 Customer Insights mit einem Azure Data Lake Storage-Konto verbinden, indem Sie einen Azure-Dienstprinzipal anstelle von Speicherkontoschlüsseln verwenden.

Automatisierte Tools, die Azure-Dienste nutzen, sollten immer eingeschränkte Berechtigungen haben. Anstatt dass sich Anwendungen als voll privilegierter Benutzer anmelden müssen, bietet Azure Dienstprinzipale an. Sie können Dienstprinzipale zum sicheren [Hinzufügen oder Bearbeiten eines Common Data Model-Ordners als Datenquelle](connect-common-data-model.md) bzw. [Erstellen oder Aktualisieren einer Umgebung](create-environment.md) verwenden.

> [!IMPORTANT]
>
> - Das Data Lake Storage-Konto, das den Dienstprinzipal verwendet, muss Gen2 sein und [Hierarchischer Namespace aktiviert](/azure/storage/blobs/data-lake-storage-namespace) haben. Azure Data Lake Gen1-Speicherkonten werden nicht unterstützt.
> - Sie benötigen Administratorberechtigungen für Ihren Azure-Mandanten, um einen Dienstprinzipal zu erstellen.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Erstellen eines Azure-Dienstprinzipals für Customer Insights

Überprüfen Sie vor dem Erstellen eines neuen Dienstprinzipals für Customer Insights, ob dieser bereits in Ihrer Organisation vorhanden ist.

### <a name="look-for-an-existing-service-principal"></a>Suchen Sie nach einem vorhandenen Service-Prinzipal

1. Gehen Sie zum [Azure-Admin-Portal](https://portal.azure.com) und melden Sie sich bei Ihrer Organisation an.

2. Wählen Sie unter **Azure-Dienste** **Azure Active Directory** aus.

3. Wählen Sie unter **Verwalten** **Microsoft-Anwendung** aus.

4. Fügen Sie einen Filter hinzu für **Anwendungs-ID beginnt mit** `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff`, oder suchen Sie nach dem Namen `Dynamics 365 AI for Customer Insights`.

5. Wenn Sie einen übereinstimmenden Datensatz finden, bedeutet dies, dass der Dienstprinzipal bereits vorhanden ist.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Screenshot, der einen vorhandenen Dienstprinzipal zeigt.":::

6. Wenn keine Ergebnisse zurückgegeben werden, können Sie [einen neuen Dienstprinzipal erstellen](#create-a-new-service-principal). In den meisten Fällen ist er bereits vorhanden, und Sie müssen dem Dienstprinzipal nur Berechtigungen erteilen, um auf das Speicherkonto zuzugreifen.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Erteilen Sie dem Service Principal Berechtigungen für den Zugriff auf das Speicherkonto

Gehen Sie zum Azure-Portal, um Berechtigungen für das Dienstprinzipal für das Speicherkonto zu erteilen, das Sie in Customer Insights verwenden möchten. Dem Speicherkonto oder Container muss eine der folgenden Rollen zugewiesen werden:

|Anmeldeinformation|Anforderungen|
|----------|------------|
|Angemeldeter Benutzer|**Rolle**: Storage Blob-Datenleser, Storage Blob Teilnehmer oder Storage Blob Besitzer.<br>**Ebene**: Berechtigungen können für das Speicherkonto oder den Container erteilt werden.</br>|
|Customer Insights Dienstprinzipal -<br>Verwenden von Azure Data Lake Storage als Datenquelle</br>|Option 1<ul><li>**Rolle**: Storage Blob-Datenleser, Storage Blob Daten     Teilnehmer oder Storage Blob Datenbesitzer.</li><li>**Ebene**: Berechtigungen sollten für das Speicherkonto oder den Container erteilt werden.</li></ul>Option 2 *(ohne den Dienstprinzipalzugriff auf das Speicherkonto freizugeben)*<ul><li>**Rolle 1**: Storage Blob-Datenleser, Storage Blob Datenteilnehmer oder Storage Blob Datenbesitzer.</li><li>**Ebene**: Berechtigungen sollten für den Container erteilt werden.</li><li>**Rolle 2**: Speicherblob-Datendelegator.</li><li>**Ebene**: Berechtigungen sollten für das Speicherkonto oder den Container erteilt werden.</li></ul>|
|Customer Insights Dienstprinzipal - <br>Azure Data Lake Storage als Ausgang oder Ziel verwenden</br>|Option 1<ul><li>**Rolle**: Storage Blob-Mitwirkender oder Storage Blob Besitzer.</li><li>**Ebene**: Berechtigungen sollten für das Speicherkonto oder den Container erteilt werden.</li></ul>Option 2 *(ohne den Dienstprinzipalzugriff auf das Speicherkonto freizugeben)*<ul><li>**Rolle**: Storage Blob-Mitwirkender oder Storage Blob Besitzer.</li><li>**Ebene**: Berechtigungen sollten für den Container erteilt werden.</li><li>**Rolle 2**: Speicherblob-Datendelegator.</li><li>**Ebene**: Berechtigungen sollten für das Speicherkonto oder den Container erteilt werden.</li></ul>|

1. Gehen Sie zum [Azure-Admin-Portal](https://portal.azure.com) und melden Sie sich bei Ihrer Organisation an.

1. Öffnen Sie das Speicherkonto, auf das das Dienstprinzipal für Customer Insights Zugriff haben soll.

1. Wählen Sie im linken Navigationsbereich **Zugriffssteuerung (IAM)** und dann **Hinzufügen** >  **Rollenzuweisung hinzufügen** aus.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Screenshot, der das Azure-Portal beim Hinzufügen einer Rollenzuweisung zeigt.":::

1. Im Bereich **Rollenzuweisung hinzufügen** legen Sie die folgenden Eigenschaften fest:
   - Rolle: Storage Blob-Datenleser, Storage Blob Mitbesitzer oder Storage Blob Besitzer basierend auf Anmeldeinfromationen, die oben aufgeführt sind.
   - Weisen Sie den Zugriff zu: **Benutzer, Gruppe oder Prinzipal des Dienstes**
   - Wählen Sie Mitglieder: **Dynamics 365 AI Customer Insights** (das [Dienstprinzipal](#create-a-new-service-principal), das Sie zuvor in diesem Verfahren gesucht haben)

1. Wählen Sie **Überprüfen + zuweisen**.

Es kann bis zu 15 Minuten dauern, bis die Änderungen propagiert werden.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Geben Sie die Azure-Ressourcen-ID oder die Details des Azure-Abonnements in den Anhang des Speicherkontos für Customer Insights ein.

Sie können ein Data Lake Storage-Konto in Customer Insights anhängen, um [Ausgabedaten zu speichern](manage-environments.md) oder [als Datenquelle zu verwenden](connect-dataverse-managed-lake.md). Mit dieser Option können Sie zwischen einem ressourcenbasierten oder einem abonnementbasierten Ansatz wählen. Befolgen Sie je nach gewähltem Ansatz das Verfahren in einem der folgenden Abschnitte.

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

### <a name="create-a-new-service-principal"></a>Erstellen Sie ein neues Service-Prinzipal

1. Neueste Version von Azure Active Directory PowerShell für Graph. Weitere Informationen finden Sie unter [Installieren von Azure Active Directory PowerShell für Graph](/powershell/azure/active-directory/install-adv2).

   1. Drücken Sie auf Ihrem PC die Windows-Taste auf Ihrer Tastatur und suchen Sie nach **Windows PowerShell** und wählen Sie **Als Administrator ausführen**.

   1. Geben Sie in dem sich öffnenden PowerShell-Fenster `Install-Module AzureAD` ein.

2. Erstellen Sie den Dienstprinzipal für Customer Insights mit dem Azure AD PowerShell-Modul.

   1. Geben Sie im PowerShell-Fenster `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure` ein. Ersetzen Sie *[Ihre Directory ID]* durch die tatsächliche Verzeichnis-ID Ihres Azure Abonnements, in dem Sie den Dienstprinzipal erstellen möchten. Der Parameter für den Umgebungsnamen `AzureEnvironmentName` ist optional.
  
   1. Geben Sie `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` ein. Mit diesem Befehl erstellen Sie das Dienstprinzipal für Customer Insights auf dem ausgewählten Azure Abonnement.

[!INCLUDE [footer-include](includes/footer-banner.md)]
