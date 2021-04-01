---
title: Verbinden Sie sich mit einem Azure Data Lake Storage Gen2-Konto mit einem Service-Prinzipal
description: Verwenden Sie ein Azure Service Prinzipal für Zielgruppenerkenntnisse, um eine Verbindung zu Ihrem eigenen Data Lake herzustellen, wenn Sie diesen mit Zielgruppenerkenntnisse verbinden.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c670b0065a2833a6dc311d9e86d2b351140382ce
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596498"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Verbinden Sie sich mit einem Azure Data Lake Storage Gen2-Konto mit einem Azure Service Prinzipal für Insights der Zielgruppe

Automatisierte Tools, die Azure-Dienste nutzen, sollten immer eingeschränkte Berechtigungen haben. Anstatt dass sich Anwendungen als voll privilegierter Benutzer anmelden müssen, bietet Azure Dienstprinzipale an. Lesen Sie weiter, um zu erfahren, wie Sie Zielgruppen-Insights mit einem Azure Data Lake Storage-Gen2-Konto verbinden, indem Sie ein Azure Service Prinzipal anstelle von Speicherkontoschlüsseln verwenden. 

Sie können das Dienstprinzipal verwenden, um auf sichere Weise [einen Common Data Model-Ordner als Datenquelle hinzuzufügen oder zu bearbeiten](connect-common-data-model.md) oder [eine neue Umgebung zu erstellen oder eine bestehende zu aktualisieren](manage-environments.md#create-an-environment-in-an-existing-organization).

> [!IMPORTANT]
> - Für das Azure Data Lake Gen2-Speicherkonto, das den Dienstprinzipal verwenden soll, muss der [Hierarchischer Namensraum (HNS) aktiviert](/azure/storage/blobs/data-lake-storage-namespace) sein.
> - Sie benötigen Admin-Berechtigungen für Ihr Azure-Abonnement, um das Service-Prinzipal zu erstellen.

## <a name="create-azure-service-principal-for-audience-insights"></a>Erstellen eines Azure Service Prinzipals für Zielgruppen-Insights

Bevor Sie ein neues Prinzipal für Zielgruppe Insights erstellen, prüfen Sie, ob es in Ihrer Organisation bereits existiert.

### <a name="look-for-an-existing-service-principal"></a>Suchen Sie nach einem vorhandenen Service-Prinzipal

1. Gehen Sie zum [Azure-Admin-Portal](https://portal.azure.com) und melden Sie sich bei Ihrer Organisation an.

2. Wählen Sie **Azure Active Directory** aus den Azure-Diensten.

3. Unter **Verwalten**, wählen Sie **Unternehmensanwendungen**.

4. Suchen Sie nach der Zielgruppe-Insights-First-Party-Applikations-ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` oder dem Namen `Dynamics 365 AI for Customer Insights`.

5. Wenn Sie einen übereinstimmenden Datensatz finden, bedeutet das, dass das Service Prinzipal für Zielgruppen-Insights existiert. Sie brauchen sie nicht neu zu erstellen.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Screenshot mit dem vorhandenen Service-Prinzipal.":::
   
6. Wenn keine Ergebnisse zurückgegeben werden, erstellen Sie einen neuen Dienstprinzipal.

### <a name="create-a-new-service-principal"></a>Erstellen Sie ein neues Service-Prinzipal

1. Installieren Sie die neueste Version der **Azure Active Directory PowerShell für Graph**. Weitere Informationen finden Sie unter [Installieren Sie Azure Active Directory PowerShell für Graph](/powershell/azure/active-directory/install-adv2).
   - Wählen Sie auf Ihrem PC die Windows-Taste auf Ihrer Tastatur und suchen Sie nach **Windows PowerShell** und **Als Administrator ausführen**.
   
   - Geben Sie in dem sich öffnenden PowerShell-Fenster `Install-Module AzureAD` ein.

2. Erstellen Sie den Service Principal für Zielgruppen-Insights mit dem Azure AD PowerShell-Modul.
   - Geben Sie im PowerShell-Fenster `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure` ein. Ersetzen Sie „Ihre Mandanten-ID“ durch die tatsächliche ID Ihres Mandanten, bei dem Sie das Prinzipal erstellen wollen. Der Parameter für den Umgebungsnamen `AzureEnvironmentName` ist optional.
  
   - Geben Sie `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` ein. Dieser Befehl erstellt den Service Principal für Zielgruppen-Insights für den ausgewählten Mandanten.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Erteilen Sie dem Service Principal Berechtigungen für den Zugriff auf das Speicherkonto

Gehen Sie zum Azure-Portal, um dem Dienstprinzipal für das Speicherkonto, das Sie in Zielgruppen-Insights verwenden möchten, Berechtigungen zu erteilen.

1. Gehen Sie zum [Azure-Admin-Portal](https://portal.azure.com) und melden Sie sich bei Ihrer Organisation an.

1. Öffnen Sie das Speicherkonto, auf das der Service-Prinzipal für Zielgruppen-Insights Zugriff haben soll.

1. Wählen Sie **Zugriffskontrolle (IAM)** aus dem Navigationsbereich und wählen Sie **Hinzufügen** > **Rollenzuweisung hinzufügen**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Screenshot mit Azure-Portal beim Hinzufügen einer Rollenzuweisung.":::
   
1. Stellen Sie im Bereich **Rollenzuweisung hinzufügen** die folgenden Eigenschaften ein:
   - Rolle: *Storage Blob Data Beitragender*
   - Weisen Sie den Zugriff zu: *Benutzer, Gruppe oder Prinzipal des Dienstes*
   - Wählen Sie: *Dynamics 365 AI für Customer Insights* (das [Service-Prinzipal, das Sie erstellt haben](#create-a-new-service-principal))

1.  Wählen Sie **Speichern** aus.

Es kann bis zu 15 Minuten dauern, bis die Änderungen propagiert werden.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Geben Sie die Azure-Ressourcen-ID oder die Azure-Abonnementdetails im Anhang des Speicherkontos zu Audience Insights ein.

Anhängen eines Azure Data Lake-Speicherkontos in Zielgruppen-Insights, um [Ausgabedaten zu speichern](manage-environments.md) oder [als Datenquelle zu verwenden](connect-common-data-service-lake.md). Wenn Sie die Option Azure Data Lake wählen, können Sie zwischen einem ressourcenbasierten oder einem abonnementbasierten Ansatz wählen.

Führen Sie die folgenden Schritte aus, um die erforderlichen Informationen für den gewählten Ansatz bereitzustellen.

### <a name="resource-based-storage-account-connection"></a>Ressourcen-basierte Speicherkonto-Verbindung

1. Gehen Sie zum [Azure Admin-Portal](https://portal.azure.com), melden Sie sich bei Ihrem Abonnement an und öffnen Sie das Speicherkonto.

1. Gehen Sie zu **Einstellungen** > **Eigenschaften** im Navigationsbereich.

1. Kopieren Sie den Wert der Ressourcen-ID des Speicherkontos.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopieren Sie die Ressourcen-ID des Speicherkontos.":::

1. Geben Sie in Zielgruppen-Insights die Ressourcen-ID in das Ressourcenfeld ein, das im Bildschirm für die Verbindung mit dem Speicherkonto angezeigt wird.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Geben Sie die Ressourcen-ID des Speicherkontos ein.":::   
   
1. Fahren Sie mit den restlichen Schritten in Zielgruppen-Insights fort, um das Speicherkonto anzuhängen.

### <a name="subscription-based-storage-account-connection"></a>Abonnement-basierte Speicherkontoverbindung

1. Gehen Sie zum [Azure Admin-Portal](https://portal.azure.com), melden Sie sich bei Ihrem Abonnement an und öffnen Sie das Speicherkonto.

1. Gehen Sie zu **Einstellungen** > **Eigenschaften** im Navigationsbereich.

1. Überprüfen Sie das **Abonnement**, die **Ressourcengruppe** und den **Name** des Speicherkontos, um sicherzustellen, dass Sie die richtigen Werte in Zielgruppen-Insights auswählen.

1. Wählen Sie in Zielgruppen-Insights die Werte oder für die entsprechenden Felder beim Anhängen des Speicherkontos.
   
1. Fahren Sie mit den restlichen Schritten in Zielgruppen-Insights fort, um das Speicherkonto anzuhängen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]