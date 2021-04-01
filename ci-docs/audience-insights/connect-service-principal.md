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
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="a615b-103">Verbinden Sie sich mit einem Azure Data Lake Storage Gen2-Konto mit einem Azure Service Prinzipal für Insights der Zielgruppe</span><span class="sxs-lookup"><span data-stu-id="a615b-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="a615b-104">Automatisierte Tools, die Azure-Dienste nutzen, sollten immer eingeschränkte Berechtigungen haben.</span><span class="sxs-lookup"><span data-stu-id="a615b-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="a615b-105">Anstatt dass sich Anwendungen als voll privilegierter Benutzer anmelden müssen, bietet Azure Dienstprinzipale an.</span><span class="sxs-lookup"><span data-stu-id="a615b-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="a615b-106">Lesen Sie weiter, um zu erfahren, wie Sie Zielgruppen-Insights mit einem Azure Data Lake Storage-Gen2-Konto verbinden, indem Sie ein Azure Service Prinzipal anstelle von Speicherkontoschlüsseln verwenden.</span><span class="sxs-lookup"><span data-stu-id="a615b-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="a615b-107">Sie können das Dienstprinzipal verwenden, um auf sichere Weise [einen Common Data Model-Ordner als Datenquelle hinzuzufügen oder zu bearbeiten](connect-common-data-model.md) oder [eine neue Umgebung zu erstellen oder eine bestehende zu aktualisieren](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="a615b-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="a615b-108">Für das Azure Data Lake Gen2-Speicherkonto, das den Dienstprinzipal verwenden soll, muss der [Hierarchischer Namensraum (HNS) aktiviert](/azure/storage/blobs/data-lake-storage-namespace) sein.</span><span class="sxs-lookup"><span data-stu-id="a615b-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="a615b-109">Sie benötigen Admin-Berechtigungen für Ihr Azure-Abonnement, um das Service-Prinzipal zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a615b-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="a615b-110">Erstellen eines Azure Service Prinzipals für Zielgruppen-Insights</span><span class="sxs-lookup"><span data-stu-id="a615b-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="a615b-111">Bevor Sie ein neues Prinzipal für Zielgruppe Insights erstellen, prüfen Sie, ob es in Ihrer Organisation bereits existiert.</span><span class="sxs-lookup"><span data-stu-id="a615b-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="a615b-112">Suchen Sie nach einem vorhandenen Service-Prinzipal</span><span class="sxs-lookup"><span data-stu-id="a615b-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="a615b-113">Gehen Sie zum [Azure-Admin-Portal](https://portal.azure.com) und melden Sie sich bei Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="a615b-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="a615b-114">Wählen Sie **Azure Active Directory** aus den Azure-Diensten.</span><span class="sxs-lookup"><span data-stu-id="a615b-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="a615b-115">Unter **Verwalten**, wählen Sie **Unternehmensanwendungen**.</span><span class="sxs-lookup"><span data-stu-id="a615b-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="a615b-116">Suchen Sie nach der Zielgruppe-Insights-First-Party-Applikations-ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` oder dem Namen `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="a615b-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="a615b-117">Wenn Sie einen übereinstimmenden Datensatz finden, bedeutet das, dass das Service Prinzipal für Zielgruppen-Insights existiert.</span><span class="sxs-lookup"><span data-stu-id="a615b-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="a615b-118">Sie brauchen sie nicht neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a615b-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Screenshot mit dem vorhandenen Service-Prinzipal.":::
   
6. <span data-ttu-id="a615b-120">Wenn keine Ergebnisse zurückgegeben werden, erstellen Sie einen neuen Dienstprinzipal.</span><span class="sxs-lookup"><span data-stu-id="a615b-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="a615b-121">Erstellen Sie ein neues Service-Prinzipal</span><span class="sxs-lookup"><span data-stu-id="a615b-121">Create a new service principal</span></span>

1. <span data-ttu-id="a615b-122">Installieren Sie die neueste Version der **Azure Active Directory PowerShell für Graph**.</span><span class="sxs-lookup"><span data-stu-id="a615b-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="a615b-123">Weitere Informationen finden Sie unter [Installieren Sie Azure Active Directory PowerShell für Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="a615b-123">For more information, see [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="a615b-124">Wählen Sie auf Ihrem PC die Windows-Taste auf Ihrer Tastatur und suchen Sie nach **Windows PowerShell** und **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a615b-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="a615b-125">Geben Sie in dem sich öffnenden PowerShell-Fenster `Install-Module AzureAD` ein.</span><span class="sxs-lookup"><span data-stu-id="a615b-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="a615b-126">Erstellen Sie den Service Principal für Zielgruppen-Insights mit dem Azure AD PowerShell-Modul.</span><span class="sxs-lookup"><span data-stu-id="a615b-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="a615b-127">Geben Sie im PowerShell-Fenster `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure` ein.</span><span class="sxs-lookup"><span data-stu-id="a615b-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="a615b-128">Ersetzen Sie „Ihre Mandanten-ID“ durch die tatsächliche ID Ihres Mandanten, bei dem Sie das Prinzipal erstellen wollen.</span><span class="sxs-lookup"><span data-stu-id="a615b-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="a615b-129">Der Parameter für den Umgebungsnamen `AzureEnvironmentName` ist optional.</span><span class="sxs-lookup"><span data-stu-id="a615b-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="a615b-130">Geben Sie `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` ein.</span><span class="sxs-lookup"><span data-stu-id="a615b-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="a615b-131">Dieser Befehl erstellt den Service Principal für Zielgruppen-Insights für den ausgewählten Mandanten.</span><span class="sxs-lookup"><span data-stu-id="a615b-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="a615b-132">Erteilen Sie dem Service Principal Berechtigungen für den Zugriff auf das Speicherkonto</span><span class="sxs-lookup"><span data-stu-id="a615b-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="a615b-133">Gehen Sie zum Azure-Portal, um dem Dienstprinzipal für das Speicherkonto, das Sie in Zielgruppen-Insights verwenden möchten, Berechtigungen zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="a615b-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="a615b-134">Gehen Sie zum [Azure-Admin-Portal](https://portal.azure.com) und melden Sie sich bei Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="a615b-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="a615b-135">Öffnen Sie das Speicherkonto, auf das der Service-Prinzipal für Zielgruppen-Insights Zugriff haben soll.</span><span class="sxs-lookup"><span data-stu-id="a615b-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="a615b-136">Wählen Sie **Zugriffskontrolle (IAM)** aus dem Navigationsbereich und wählen Sie **Hinzufügen** > **Rollenzuweisung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a615b-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Screenshot mit Azure-Portal beim Hinzufügen einer Rollenzuweisung.":::
   
1. <span data-ttu-id="a615b-138">Stellen Sie im Bereich **Rollenzuweisung hinzufügen** die folgenden Eigenschaften ein:</span><span class="sxs-lookup"><span data-stu-id="a615b-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="a615b-139">Rolle: *Storage Blob Data Beitragender*</span><span class="sxs-lookup"><span data-stu-id="a615b-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="a615b-140">Weisen Sie den Zugriff zu: *Benutzer, Gruppe oder Prinzipal des Dienstes*</span><span class="sxs-lookup"><span data-stu-id="a615b-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="a615b-141">Wählen Sie: *Dynamics 365 AI für Customer Insights* (das [Service-Prinzipal, das Sie erstellt haben](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="a615b-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="a615b-142">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="a615b-142">Select **Save**.</span></span>

<span data-ttu-id="a615b-143">Es kann bis zu 15 Minuten dauern, bis die Änderungen propagiert werden.</span><span class="sxs-lookup"><span data-stu-id="a615b-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="a615b-144">Geben Sie die Azure-Ressourcen-ID oder die Azure-Abonnementdetails im Anhang des Speicherkontos zu Audience Insights ein.</span><span class="sxs-lookup"><span data-stu-id="a615b-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="a615b-145">Anhängen eines Azure Data Lake-Speicherkontos in Zielgruppen-Insights, um [Ausgabedaten zu speichern](manage-environments.md) oder [als Datenquelle zu verwenden](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="a615b-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="a615b-146">Wenn Sie die Option Azure Data Lake wählen, können Sie zwischen einem ressourcenbasierten oder einem abonnementbasierten Ansatz wählen.</span><span class="sxs-lookup"><span data-stu-id="a615b-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="a615b-147">Führen Sie die folgenden Schritte aus, um die erforderlichen Informationen für den gewählten Ansatz bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a615b-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="a615b-148">Ressourcen-basierte Speicherkonto-Verbindung</span><span class="sxs-lookup"><span data-stu-id="a615b-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="a615b-149">Gehen Sie zum [Azure Admin-Portal](https://portal.azure.com), melden Sie sich bei Ihrem Abonnement an und öffnen Sie das Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="a615b-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="a615b-150">Gehen Sie zu **Einstellungen** > **Eigenschaften** im Navigationsbereich.</span><span class="sxs-lookup"><span data-stu-id="a615b-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="a615b-151">Kopieren Sie den Wert der Ressourcen-ID des Speicherkontos.</span><span class="sxs-lookup"><span data-stu-id="a615b-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopieren Sie die Ressourcen-ID des Speicherkontos.":::

1. <span data-ttu-id="a615b-153">Geben Sie in Zielgruppen-Insights die Ressourcen-ID in das Ressourcenfeld ein, das im Bildschirm für die Verbindung mit dem Speicherkonto angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a615b-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Geben Sie die Ressourcen-ID des Speicherkontos ein.":::   
   
1. <span data-ttu-id="a615b-155">Fahren Sie mit den restlichen Schritten in Zielgruppen-Insights fort, um das Speicherkonto anzuhängen.</span><span class="sxs-lookup"><span data-stu-id="a615b-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="a615b-156">Abonnement-basierte Speicherkontoverbindung</span><span class="sxs-lookup"><span data-stu-id="a615b-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="a615b-157">Gehen Sie zum [Azure Admin-Portal](https://portal.azure.com), melden Sie sich bei Ihrem Abonnement an und öffnen Sie das Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="a615b-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="a615b-158">Gehen Sie zu **Einstellungen** > **Eigenschaften** im Navigationsbereich.</span><span class="sxs-lookup"><span data-stu-id="a615b-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="a615b-159">Überprüfen Sie das **Abonnement**, die **Ressourcengruppe** und den **Name** des Speicherkontos, um sicherzustellen, dass Sie die richtigen Werte in Zielgruppen-Insights auswählen.</span><span class="sxs-lookup"><span data-stu-id="a615b-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="a615b-160">Wählen Sie in Zielgruppen-Insights die Werte oder für die entsprechenden Felder beim Anhängen des Speicherkontos.</span><span class="sxs-lookup"><span data-stu-id="a615b-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="a615b-161">Fahren Sie mit den restlichen Schritten in Zielgruppen-Insights fort, um das Speicherkonto anzuhängen.</span><span class="sxs-lookup"><span data-stu-id="a615b-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]