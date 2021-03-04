---
title: Erstellen und Verwalten von Umgebungen
description: Erfahren Sie, wie Sie sich für den Dienst anmelden und wie Sie Umgebungen verwalten können.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 744f0bcbf5d2700363180f44e38d6dee9bf5df63
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270111"
---
# <a name="manage-environments"></a><span data-ttu-id="ea6d4-103">Umgebungen verwalten</span><span class="sxs-lookup"><span data-stu-id="ea6d4-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ea6d4-104">Dieser Artikel erklärt, wie Sie eine neue Organisation erstellen und wie Sie eine Umgebung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="ea6d4-105">Melden Sie sich an und erstellen Sie eine Organisation</span><span class="sxs-lookup"><span data-stu-id="ea6d4-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="ea6d4-106">Wechseln Sie zur Website von [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="ea6d4-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="ea6d4-107">Wählen Sie **Erste Schritte** aus.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="ea6d4-108">Wählen Sie Ihr bevorzugtes Anmeldeszenario und wählen Sie den entsprechenden Link aus.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="ea6d4-109">Akzeptieren Sie die allgemeinen Geschäftsbedingungen und wählen Sie **Fortsetzen** aus, um mit dem Erstellen der Organisation zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="ea6d4-110">Nachdem die Umgebung erstellt wurde, werden Sie zu [Customer Insights](https://home.ci.ai.dynamics.com) weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="ea6d4-111">Verwenden Sie die Demo-Umgebung, um die Anwendung zu erkunden, oder erstellen Sie eine neue Umgebung, indem Sie den Schritten im nächsten Abschnitt folgen.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="ea6d4-112">Nachdem Sie die Umgebungseinstellungen angegeben haben, wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="ea6d4-113">Nachdem die Umgebung erfolgreich erstellt wurde, werden Sie angemeldet.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="ea6d4-114">Eine Umgebung in einer vorhandenen Organisation erstellen</span><span class="sxs-lookup"><span data-stu-id="ea6d4-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="ea6d4-115">Beim Erstellen einer neuen Umgebung, gibt es zwei Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="ea6d4-116">Sie können entweder eine völlig neue Konfiguration angeben oder Sie können einige Konfigurationseinstellungen aus einer vorhandenen Umgebung kopieren.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="ea6d4-117">So erstellen Sie eine Umgebung:</span><span class="sxs-lookup"><span data-stu-id="ea6d4-117">To create an environment:</span></span>

1. <span data-ttu-id="ea6d4-118">Wählen Sie die **Umgebung**-Auswahl in der Kopfzeile der App aus.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="ea6d4-119">Wählen Sie **Neu**.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ea6d4-120">![Umgebungseinstellungen](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="ea6d4-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="ea6d4-121">Im **Neue Umgebung erstellen**-Dialog wählen Sie **Neue Umgebung** aus.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="ea6d4-122">Wenn Sie [Daten aus der aktuellen Umgebung kopieren](#additional-considerations-for-copy-configuration-preview) wollen, wählen Sie **Aus vorhandener Umgebung kopieren** aus.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="ea6d4-123">Sie sehen eine Liste aller verfügbaren Umgebungen in Ihrer Organisation, aus der Sie Daten kopieren können.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="ea6d4-124">Geben Sie die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="ea6d4-124">Provide the following details:</span></span>
   - <span data-ttu-id="ea6d4-125">**Name**: Der Name für diese Umgebung.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="ea6d4-126">Dieses Feld ist bereits ausgefüllt, wenn Sie eine bestehende Umgebung kopiert haben, aber Sie können es ändern.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="ea6d4-127">**Region**: Die Region, in der der Dienst bereitgestellt und gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="ea6d4-128">**Typ**: Wählen Sie, ob Sie eine Produktions- oder Sandbox-Umgebung erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="ea6d4-129">Optional können Sie **Erweiterte Einstellungen** auswählen:</span><span class="sxs-lookup"><span data-stu-id="ea6d4-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="ea6d4-130">**Sichern alle Daten**: Geben Sie an, wo Sie die aus Customer Insights generierten Ausgabedaten speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="ea6d4-131">Sie haben zwei Möglichkeiten: **Customer Insights-Speicherung** (ein vom Customer Insights-Team verwalteter Azure Data Lake) und **Azure Data Lake Storage Gen2** (Ihre eigene Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="ea6d4-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="ea6d4-132">Standardmäßig ist die Speicheroption „Customer Insights“ ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ea6d4-133">Durch die Speicherung von Daten in Azure Data Lake Storage erklären Sie sich damit einverstanden, dass die Daten an den für dieses Azure Storage-Konto geeigneten geografischen Ort übertragen und dort gespeichert werden. Dieser kann von dem Ort abweichen, an dem die Daten in Dynamics 365 Customer Insights gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="ea6d4-134">Weitere Informationen finden Sie im Microsoft Trust Center.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="ea6d4-135">Derzeit werden aufgenommene Entitäten immer im verwalteten Customer Insights Data Lake gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="ea6d4-136">Wir unterstützen nur Azure Data Lake Gen2-Speicherkonten aus derselben Azure-Region, die Sie beim Erstellen der Umgebung ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="ea6d4-137">Wir unterstützen nur Azure Data Lake Gen2 hierarchische Name Space (HNS) aktivierte Speicherkonten.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="ea6d4-138">Für die Option Azure Data Lake Storage Gen2 können Sie zwischen einer ressourcenbasierten Option und einer abonnementbasierten Option für die Authentifizierung wählen.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="ea6d4-139">Weitere Informationen finden Sie unter [Verbinden Sie Zielgruppen-Insights mit einem Azure Data Lake Storage Gen2-Konto mit einem Azure-Dienstprinzipal](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="ea6d4-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="ea6d4-140">Der **Container**-Name kann nicht geändert werden und wird „customerinsights“ lauten.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="ea6d4-141">Wenn Sie [Vorhersagen](predictions.md) verwenden möchten oder die Datenfreigabe mit Anwendungen und Lösungen basierend auf Microsoft Dataverse konfigurieren, stellen Sie die Microsoft Dataverse-Umgebungs-URL unter **Datenfreigabe mit Microsoft Dataverse konfigurieren und zusätzliche Funktionen aktivieren** bereit.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="ea6d4-142">Wählen Sie **Datenfreigabe aktivieren** aus, um die Ausgabedaten von Customer Insights mit einem verwalteten Microsoft Dataverse Data Lake zu teilen.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="ea6d4-143">Datenaustausch mit verwaltetem Microsoft Dataverse Data Lake wird derzeit nicht unterstützt, wenn Sie alle Daten in Ihrem eigenen Azure Data Lake Storage speichern.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="ea6d4-144">[Vorhersage fehlenden Werte in einer Entität](predictions.md) wird derzeit nicht unterstützt, wenn Sie die Datenfreigabe mit verwaltetem Microsoft Dataverse Data Lake aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="ea6d4-145">![Konfigurationsoptionen zum Aktivieren der Datenfreigabe mit Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="ea6d4-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="ea6d4-146">Wenn Sie Prozesse ausführen, wie z.B. die Datenerfassung oder die Segmenterstellung, werden entsprechende Ordner in dem oben angegebenen Speicherkonto erstellt.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="ea6d4-147">Datendateien und model.json-Dateien werden basierend auf dem von Ihnen ausgeführten Prozess erstellt und den jeweiligen Unterordnern hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="ea6d4-148">Wenn Sie mehrere Umgebungen von Customer Insights erstellen und die ausgegebenen Entitäten aus diesen Umgebungen in Ihrem Speicherkonto speichern möchten, werden für jede Umgebung separate Ordner mit ci_<environmentid> im Container erstellt.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="ea6d4-149">Zusätzliche Überlegungen zur Kopierkonfiguration (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="ea6d4-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="ea6d4-150">Folgende Konfigurationseinstellungen werden kopiert:</span><span class="sxs-lookup"><span data-stu-id="ea6d4-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="ea6d4-151">Konfigurationen von Funktionen</span><span class="sxs-lookup"><span data-stu-id="ea6d4-151">Feature configurations</span></span>
- <span data-ttu-id="ea6d4-152">Aufgenommene/importierte Datenquellen</span><span class="sxs-lookup"><span data-stu-id="ea6d4-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="ea6d4-153">Datenvereinheitlichung (Map, Match, Merge) Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ea6d4-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="ea6d4-154">Segmente</span><span class="sxs-lookup"><span data-stu-id="ea6d4-154">Segments</span></span>
- <span data-ttu-id="ea6d4-155">Kennzahlen</span><span class="sxs-lookup"><span data-stu-id="ea6d4-155">Measures</span></span>
- <span data-ttu-id="ea6d4-156">Beziehungen</span><span class="sxs-lookup"><span data-stu-id="ea6d4-156">Relationships</span></span>
- <span data-ttu-id="ea6d4-157">Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="ea6d4-157">Activities</span></span>
- <span data-ttu-id="ea6d4-158">Index suchen & filtern</span><span class="sxs-lookup"><span data-stu-id="ea6d4-158">Search & filter Index</span></span>
- <span data-ttu-id="ea6d4-159">Exportziele</span><span class="sxs-lookup"><span data-stu-id="ea6d4-159">Export destinations</span></span>
- <span data-ttu-id="ea6d4-160">Geplante Aktualisierung</span><span class="sxs-lookup"><span data-stu-id="ea6d4-160">Scheduled refresh</span></span>
- <span data-ttu-id="ea6d4-161">Ergänzungen</span><span class="sxs-lookup"><span data-stu-id="ea6d4-161">Enrichments</span></span>
- <span data-ttu-id="ea6d4-162">Modell-Management</span><span class="sxs-lookup"><span data-stu-id="ea6d4-162">Model management</span></span>
- <span data-ttu-id="ea6d4-163">Zuweisungen von Rollen</span><span class="sxs-lookup"><span data-stu-id="ea6d4-163">Role assignments</span></span>

<span data-ttu-id="ea6d4-164">Folgende Konfigurationseinstellungen werden *nicht* kopiert:</span><span class="sxs-lookup"><span data-stu-id="ea6d4-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="ea6d4-165">Kundenprofile.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-165">Customer profiles.</span></span>
- <span data-ttu-id="ea6d4-166">Anmeldeinformationen für die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-166">Data source credentials.</span></span> <span data-ttu-id="ea6d4-167">Sie müssen die Anmeldeinformationen für jede Datenquelle angeben und die Datenquellen manuell aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="ea6d4-168">Datenquellen aus dem Common Data Model-Ordner und Common Data Service verwalteter Lake.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="ea6d4-169">Sie müssen diese Datenquellen manuell mit demselben Namen wie in der Quellumgebung erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="ea6d4-170">Wenn Sie eine Umgebung kopieren, wird eine Bestätigungsmeldung angezeigt, dass die neue Umgebung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="ea6d4-171">Wählen Sie **Gehen Sie zu Datenquellen**, um die Liste der Datenquellen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="ea6d4-172">Alle Datenquellen zeigen einen Status **Anmeldeinformationen erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="ea6d4-173">Bearbeiten Sie die Datenquellen und geben Sie die Anmeldeinformationen ein, um sie zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ea6d4-174">![Datenquellen kopiert](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="ea6d4-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="ea6d4-175">Nachdem Sie die Datenquellen aktualisiert haben, gehen Sie zu **Daten** > **Vereinheitlichen**.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="ea6d4-176">Hier finden Sie Einstellungen aus der Quellumgebung.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="ea6d4-177">Bearbeiten Sie sie nach Bedarf oder wählen Sie **Ausführen**, um den Datenvereinheitlichungsprozess zu starten und die einheitliche Kundenentität zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="ea6d4-178">Wenn die Datenvereinheitlichung abgeschlossen ist, gehen Sie zu **Maßnahmen** und **Segmente**, um sie auch zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="ea6d4-179">So bearbeiten Sie eine bestehende Umgebung</span><span class="sxs-lookup"><span data-stu-id="ea6d4-179">Edit an existing environment</span></span>

<span data-ttu-id="ea6d4-180">Sie können einige Details vorhandener Umgebungen bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="ea6d4-181">Wählen Sie die **Umgebung**-Auswahl in der Kopfzeile der App aus.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="ea6d4-182">Wählen Sie das Symbol **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="ea6d4-183">Im Feld **Umgebung bearbeiten** können Sie den **Anzeigename** der Umgebung aktualisieren, Sie können jedoch nicht die **Region** oder den **Art** ändern.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="ea6d4-184">Wenn eine Umgebung zum Speichern von Daten in Azure Data Lake Storage Gen2 konfiguriert ist, können Sie den **Kontoschlüssel** aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="ea6d4-185">Sie können jedoch nicht den Namen **Kontoname** oder **Container** ändern.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="ea6d4-186">Optional können Sie von einer kontoschlüsselbasierten Verbindung zu einer ressourcenbasierten oder abonnementbasierten Verbindung aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="ea6d4-187">Nach der Aktualisierung können Sie nicht mehr zum Kontenschlüssel zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="ea6d4-188">Weitere Informationen finden Sie unter [Verbinden Sie Zielgruppen-Insights mit einem Azure Data Lake Storage Gen2-Konto mit einem Azure-Dienstprinzipal](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="ea6d4-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="ea6d4-189">Sie können die **Container**-Informationen beim Aktualisieren der Verbindung nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="ea6d4-190">Zurücksetzen einer bestehenden Umgebung</span><span class="sxs-lookup"><span data-stu-id="ea6d4-190">Reset an existing environment</span></span>

<span data-ttu-id="ea6d4-191">Als Administrator können Sie eine Umgebung auf einen leeren Zustand zurücksetzen, wenn Sie alle Konfigurationen löschen und die aufgenommenen Daten entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="ea6d4-192">Wählen Sie die **Umgebung**-Auswahl in der Kopfzeile der App aus.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="ea6d4-193">Wählen Sie die Umgebung aus, die Sie zurücksetzen möchten, und wählen Sie die Auslassungspunkte **...** aus.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="ea6d4-194">Wählen Sie die Option **Zurücksetzen** aus.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="ea6d4-195">Um das Löschen zu bestätigen, geben Sie den Namen der Umgebung ein und wählen Sie **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="ea6d4-196">Löschen Sie eine vorhandene Umgebung (nur für Administratoren verfügbar).</span><span class="sxs-lookup"><span data-stu-id="ea6d4-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="ea6d4-197">Als Administrator können Sie eine von Ihnen verwaltete Umgebung löschen.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="ea6d4-198">Wählen Sie die **Umgebung**-Auswahl in der Kopfzeile der App aus.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="ea6d4-199">Wählen Sie die Umgebung aus, die Sie zurücksetzen möchten, und wählen Sie die Auslassungspunkte **...** aus.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="ea6d4-200">Wählen Sie die Option **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="ea6d4-201">Um das Löschen zu bestätigen, geben Sie den Namen der Umgebung ein und wählen Sie **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="ea6d4-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]