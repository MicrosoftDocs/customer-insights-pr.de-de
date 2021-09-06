---
title: Verbinden Sie sich mit einem Azure Data Lake Storage Konto mithilfe eines Dienstprinzipals
description: Verwenden Sie einen Azure-Dienstprinzipal, um eine Verbindung zu Ihrem eigenen Data Lake herzustellen.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461147"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Verbinden Sie sich mit einem Azure Data Lake Storage Konto mithilfe eines Azure Dienstprinzipals
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
Automatisierte Tools, die Azure-Dienste nutzen, sollten immer eingeschränkte Berechtigungen haben. Anstatt dass sich Anwendungen als voll privilegierter Benutzer anmelden müssen, bietet Azure Dienstprinzipale an. Lesen Sie weiter, um zu erfahren, wie Sie Dynamics 365 Customer Insights mit einem Azure Data Lake Storage Konto mithilfe eines Azure Dienstprinzipals anstelle von Speicherkontoschlüsseln verbinden. 

Sie können den Dienstprinzipal verwenden, um sicher [einen Common Data Model Ordner als Datenquelle hinzuzufügen oder zu bearbeiten](connect-common-data-model.md), oder [eine Umgebung zu erstellen oder zu aktualisieren](get-started-paid.md).<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - Das Data Lake Storage-Konto verwendet<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> der Dienstprinzipal muss [hierarchische Namespace aktiviert haben](/azure/storage/blobs/data-lake-storage-namespace).
> - Sie benötigen Admin-Berechtigungen für Ihr Azure-Abonnement, um das Service-Prinzipal zu erstellen.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Erstellen eines Azure-Dienstprinzipals für Customer Insights

Bevor Sie einen neuen Dienstprinzipal für Zielgruppenerkenntnisse oder Bindungserkenntnisse erstellen, prüfen Sie, ob dieser bereits in Ihrer Organisation vorhanden ist.

### <a name="look-for-an-existing-service-principal"></a>Suchen Sie nach einem vorhandenen Service-Prinzipal

1. Gehen Sie zum [Azure-Admin-Portal](https://portal.azure.com) und melden Sie sich bei Ihrer Organisation an.

2. Wählen Sie unter **Azure-Dienste** **Azure Active Directory** aus.

3. Unter **Verwalten**, wählen Sie **Unternehmensanwendungen**.

4. Suchen Sie nach Microsoft<!--note from editor: Via Microsoft Writing Style Guide.--> Anwendungs-ID:
   - Zielgruppenerkenntnisse: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` namens `Dynamics 365 AI for Customer Insights`
   - Bindungserkenntnisse: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` namens `Dynamics 365 AI for Customer Insights engagement insights`

5. Wenn Sie einen übereinstimmenden Datensatz finden, bedeutet dies, dass der Dienstprinzipal bereits vorhanden ist. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Screenshot, der einen vorhandenen Dienstprinzipal zeigt.":::
   
6. Wenn keine Ergebnisse zurückgegeben werden, erstellen Sie einen neuen Dienstprinzipal.

>[!NOTE]
>Um die volle Kraft von Dynamics 365 Customer Insights zu nutzen, schlagen wir vor, dass Sie beide Apps zum Dienstprinzipal hinzufügen.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>Erstellen Sie ein neues Service-Prinzipal
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. Neueste Version von Azure Active Directory PowerShell für Graph. Weitere Informationen finden Sie unter [Installieren von Azure Active Directory PowerShell für Graph](/powershell/azure/active-directory/install-adv2).

   1. Wählen Sie auf Ihrem PC die Windows-Taste auf Ihrer Tastatur und suchen Sie nach **Windows PowerShell** und wählen Sie **Als Administrator ausführen**.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. Geben Sie in dem sich öffnenden PowerShell-Fenster `Install-Module AzureAD` ein.

2. Erstellen Sie den Dienstprinzipal für Customer Insights mit dem Azure AD PowerShell-Modul.

   1. Geben Sie im PowerShell-Fenster `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure` ein. *[Ihre Mandant-ID]* ersetzen<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> mit der tatsächlichen ID Ihres Mandanten, in dem Sie den Dienstprinzipal erstellen möchten. Der Parameter für den Umgebungsnamen `AzureEnvironmentName` ist optional.
  
   1. Geben Sie `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` ein. Dieser Befehl erstellt den Service Principal für Zielgruppen-Insights für den ausgewählten Mandanten. 

   1. Geben Sie `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"` ein. Dieser Befehl erstellt den Dienstprinzipal für Bindungserkenntnisse<!--note from editor: Edit okay?--> auf dem ausgewählten Mandanten.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Erteilen Sie dem Service Principal Berechtigungen für den Zugriff auf das Speicherkonto

Gehen Sie zum Azure-Portal, um dem Dienstprinzipal für das Speicherkonto, das Sie in Zielgruppen-Insights verwenden möchten, Berechtigungen zu erteilen.

1. Gehen Sie zum [Azure-Admin-Portal](https://portal.azure.com) und melden Sie sich bei Ihrer Organisation an.

1. Öffnen Sie das Speicherkonto, auf das der Service-Prinzipal für Zielgruppen-Insights Zugriff haben soll.

1. Wählen Sie im linken Navigationsbereich **Zugriffssteuerung (IAM)** und dann **Hinzufügen** >  **Rollenzuweisung hinzufügen** aus.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Screenshot, der das Azure-Portal beim Hinzufügen einer Rollenzuweisung zeigt.":::

1. Im Bereich **Rollenzuweisung hinzufügen** legen Sie die folgenden Eigenschaften fest:
   - Rolle: **Storage Blob Data Beitragender**
   - Weisen Sie den Zugriff zu: **Benutzer, Gruppe oder Prinzipal des Dienstes**
   - Wählen Sie **Dynamics 365 AI für Customer Insights** und **Dynamics 365 AI for Customer Insights Bindungserkenntnisse** (die zwei [Dienstprinzipale](#create-a-new-service-principal) dei Sie zuvor in diesem Verfahren erstellt haben)

1.  Wählen Sie **Speichern** aus.

Es kann bis zu 15 Minuten dauern, bis die Änderungen propagiert werden.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Geben Sie die Azure Ressourcen-ID oder die Azure Abonnementdetails im Anhang des Speicherkontos für Zielgruppenerkenntnisse ein

Sie können<!--note from editor: Edit suggested only if this section is optional.--> ein Data Lake Storage-Konto in Zielgruppenerkenntnissen anhängen um [Ausgabedaten zu speichern](manage-environments.md) oder [als Datenquelle zu nutzen](connect-common-data-service-lake.md). Mit dieser Option können Sie zwischen einem ressourcenbasierten oder einem abonnementbasierten Ansatz wählen. Befolgen Sie je nach gewähltem Ansatz das Verfahren in einem der folgenden Abschnitte.<!--note from editor: Suggested.-->

### <a name="resource-based-storage-account-connection"></a>Ressourcen-basierte Speicherkonto-Verbindung

1. Gehen Sie zum [Azure Admin-Portal](https://portal.azure.com), melden Sie sich bei Ihrem Abonnement an und öffnen Sie das Speicherkonto.

1. Gehen Sie im linken Bereich zu **Einstellungen** > **Eigenschaften**.

1. Kopieren Sie den Wert der Ressourcen-ID des Speicherkontos.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopieren Sie die Ressourcen-ID des Speicherkontos.":::

1. Geben Sie in Zielgruppenerkenntnis die Ressourcen-ID in das Ressourcenfeld ein, das auf dem Verbindungsbildschirm des Speicherkontos angezeigt wird.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Geben Sie die Ressourcen-ID des Speicherkontos ein.":::   

1. Fahren Sie mit den restlichen Schritten in Zielgruppen-Insights fort, um das Speicherkonto anzuhängen.

### <a name="subscription-based-storage-account-connection"></a>Abonnement-basierte Speicherkontoverbindung

1. Gehen Sie zum [Azure Admin-Portal](https://portal.azure.com), melden Sie sich bei Ihrem Abonnement an und öffnen Sie das Speicherkonto.

1. Gehen Sie im linken Bereich zu **Einstellungen** > **Eigenschaften**.

1. Überprüfen Sie das **Abonnement**, die **Ressourcengruppe** und den **Name** des Speicherkontos, um sicherzustellen, dass Sie die richtigen Werte in Zielgruppen-Insights auswählen.

1. Wählen Sie in Zielgruppenerkenntnis die Werte für die entsprechenden Felder aus, wenn Sie das Speicherkonto anhängen.

1. Fahren Sie mit den restlichen Schritten in Zielgruppen-Insights fort, um das Speicherkonto anzuhängen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]