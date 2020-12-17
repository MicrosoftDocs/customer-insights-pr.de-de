---
title: Erstellen und Verwalten von Umgebungen
description: Erfahren Sie, wie Sie sich für den Dienst anmelden und wie Sie Umgebungen verwalten können.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644132"
---
# <a name="manage-environments"></a><span data-ttu-id="37343-103">Umgebungen verwalten</span><span class="sxs-lookup"><span data-stu-id="37343-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="37343-104">Dieser Artikel erklärt, wie Sie eine neue Organisation erstellen und wie Sie eine Umgebung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="37343-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="37343-105">Melden Sie sich an und erstellen Sie eine Organisation</span><span class="sxs-lookup"><span data-stu-id="37343-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="37343-106">Wechseln Sie zur Website von [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="37343-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="37343-107">Wählen Sie **Erste Schritte** aus.</span><span class="sxs-lookup"><span data-stu-id="37343-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="37343-108">Wählen Sie Ihr bevorzugtes Anmeldeszenario und wählen Sie den entsprechenden Link aus.</span><span class="sxs-lookup"><span data-stu-id="37343-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="37343-109">Akzeptieren Sie die allgemeinen Geschäftsbedingungen und wählen Sie **Fortsetzen** aus, um mit dem Erstellen der Organisation zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="37343-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="37343-110">Nachdem die Umgebung erstellt wurde, werden Sie zu [Customer Insights](https://home.ci.ai.dynamics.com) weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="37343-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="37343-111">Verwenden Sie die Demo-Umgebung, um die Anwendung zu erkunden, oder erstellen Sie eine neue Umgebung, indem Sie den Schritten im nächsten Abschnitt folgen.</span><span class="sxs-lookup"><span data-stu-id="37343-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="37343-112">Nachdem Sie die Umgebungseinstellungen angegeben haben, wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="37343-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="37343-113">Nachdem die Umgebung erfolgreich erstellt wurde, werden Sie angemeldet.</span><span class="sxs-lookup"><span data-stu-id="37343-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="37343-114">Eine Umgebung in einer vorhandenen Organisation erstellen</span><span class="sxs-lookup"><span data-stu-id="37343-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="37343-115">Beim Erstellen einer neuen Umgebung, gibt es zwei Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="37343-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="37343-116">Sie können entweder eine völlig neue Konfiguration angeben oder Sie können einige Konfigurationseinstellungen aus einer vorhandenen Umgebung kopieren.</span><span class="sxs-lookup"><span data-stu-id="37343-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="37343-117">So erstellen Sie eine Umgebung:</span><span class="sxs-lookup"><span data-stu-id="37343-117">To create an environment:</span></span>

1. <span data-ttu-id="37343-118">Wählen Sie das Symbol **Einstellungen** in der Kopfzeile der App aus.</span><span class="sxs-lookup"><span data-stu-id="37343-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="37343-119">Wählen Sie **Neue Umgebung** aus.</span><span class="sxs-lookup"><span data-stu-id="37343-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="37343-120">![Umgebungseinstellungen](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="37343-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="37343-121">Im **Neue Umgebung erstellen**-Dialog wählen Sie **Neue Umgebung** aus.</span><span class="sxs-lookup"><span data-stu-id="37343-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="37343-122">Wenn Sie [Daten aus der aktuellen Umgebung kopieren](#additional-considerations-for-copy-configuration-preview) wollen, wählen Sie **Aus vorhandener Umgebung kopieren** aus.</span><span class="sxs-lookup"><span data-stu-id="37343-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="37343-123">Sie sehen eine Liste aller verfügbaren Umgebungen in Ihrer Organisation, aus der Sie Daten kopieren können.</span><span class="sxs-lookup"><span data-stu-id="37343-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="37343-124">Geben Sie die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="37343-124">Provide the following details:</span></span>
   - <span data-ttu-id="37343-125">**Name**: Der Name für diese Umgebung.</span><span class="sxs-lookup"><span data-stu-id="37343-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="37343-126">Dieses Feld ist bereits ausgefüllt, wenn Sie eine bestehende Umgebung kopiert haben, aber Sie können es ändern.</span><span class="sxs-lookup"><span data-stu-id="37343-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="37343-127">**Region**: Die Region, in der der Dienst bereitgestellt und gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="37343-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="37343-128">**Typ**: Wählen Sie, ob Sie eine Produktions- oder Sandbox-Umgebung erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="37343-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="37343-129">Optional können Sie **Erweiterte Einstellungen** auswählen:</span><span class="sxs-lookup"><span data-stu-id="37343-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="37343-130">**Sichern alle Daten**: Geben Sie an, wo Sie die aus Customer Insights generierten Ausgabedaten speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="37343-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="37343-131">Sie haben zwei Möglichkeiten: **Customer Insights-Speicherung** (ein vom Customer Insights-Team verwalteter Azure Data Lake) und **Azure Data Lake Storage Gen2** (Ihre eigene Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="37343-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="37343-132">Standardmäßig ist die Speicheroption „Customer Insights“ ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="37343-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="37343-133">Durch die Speicherung von Daten in Azure Data Lake Storage erklären Sie sich damit einverstanden, dass die Daten an den für dieses Azure Storage-Konto geeigneten geografischen Ort übertragen und dort gespeichert werden. Dieser kann von dem Ort abweichen, an dem die Daten in Dynamics 365 Customer Insights gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="37343-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="37343-134">Weitere Informationen finden Sie im Microsoft Trust Center.</span><span class="sxs-lookup"><span data-stu-id="37343-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="37343-135">Derzeit werden aufgenommene Entitäten immer im verwalteten Customer Insights Data Lake gespeichert.</span><span class="sxs-lookup"><span data-stu-id="37343-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="37343-136">Wir unterstützen nur Azure Data Lake Gen2-Speicherkonten aus derselben Azure-Region, die Sie beim Erstellen der Umgebung ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="37343-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="37343-137">Wir unterstützen nur Azure Data Lake Gen2 hierarchische Name Space (HNS) aktivierte Speicherkonten.</span><span class="sxs-lookup"><span data-stu-id="37343-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="37343-138">Für die Option Azure Data Lake Storage Gen2 können Sie zwischen einer ressourcenbasierten Option und einer abonnementbasierten Option für die Authentifizierung wählen.</span><span class="sxs-lookup"><span data-stu-id="37343-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="37343-139">Weitere Informationen finden Sie unter [Verbinden Sie Zielgruppen-Insights mit einem Azure Data Lake Storage Gen2-Konto mit einem Azure-Dienstprinzipal](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="37343-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="37343-140">Der **Container**-Name kann nicht geändert werden und wird „customerinsights“ lauten.</span><span class="sxs-lookup"><span data-stu-id="37343-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="37343-141">Wenn Sie [Vorhersagen](predictions.md) verwenden wollen, geben Sie die Common Data Service Instanz-URL im Feld **Serveradresse** unter **Vorhersagen verwenden** ein.</span><span class="sxs-lookup"><span data-stu-id="37343-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="37343-142">Wenn Sie Prozesse ausführen, wie z.B. die Datenerfassung oder die Segmenterstellung, werden entsprechende Ordner in dem oben angegebenen Speicherkonto erstellt.</span><span class="sxs-lookup"><span data-stu-id="37343-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="37343-143">Datendateien und model.json-Dateien werden basierend auf dem von Ihnen ausgeführten Prozess erstellt und den jeweiligen Unterordnern hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="37343-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="37343-144">Wenn Sie mehrere Umgebungen von Customer Insights erstellen und die ausgegebenen Entitäten aus diesen Umgebungen in Ihrem Speicherkonto speichern möchten, werden für jede Umgebung separate Ordner mit ci_<environmentid> im Container erstellt.</span><span class="sxs-lookup"><span data-stu-id="37343-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="37343-145">Zusätzliche Überlegungen zur Kopierkonfiguration (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="37343-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="37343-146">Folgende Konfigurationseinstellungen werden kopiert:</span><span class="sxs-lookup"><span data-stu-id="37343-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="37343-147">Konfigurationen von Funktionen</span><span class="sxs-lookup"><span data-stu-id="37343-147">Feature configurations</span></span>
- <span data-ttu-id="37343-148">Inegistrierte/importierte Datenquellen</span><span class="sxs-lookup"><span data-stu-id="37343-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="37343-149">Datenvereinheitlichung (Map, Match, Merge) Konfiguration</span><span class="sxs-lookup"><span data-stu-id="37343-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="37343-150">Segmente</span><span class="sxs-lookup"><span data-stu-id="37343-150">Segments</span></span>
- <span data-ttu-id="37343-151">Kennzahlen</span><span class="sxs-lookup"><span data-stu-id="37343-151">Measures</span></span>
- <span data-ttu-id="37343-152">Beziehungen</span><span class="sxs-lookup"><span data-stu-id="37343-152">Relationships</span></span>
- <span data-ttu-id="37343-153">Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="37343-153">Activities</span></span>
- <span data-ttu-id="37343-154">Index suchen & filtern</span><span class="sxs-lookup"><span data-stu-id="37343-154">Search & filter Index</span></span>
- <span data-ttu-id="37343-155">Exportziele</span><span class="sxs-lookup"><span data-stu-id="37343-155">Export destinations</span></span>
- <span data-ttu-id="37343-156">Geplante Aktualisierung</span><span class="sxs-lookup"><span data-stu-id="37343-156">Scheduled refresh</span></span>
- <span data-ttu-id="37343-157">Ergänzungen</span><span class="sxs-lookup"><span data-stu-id="37343-157">Enrichments</span></span>
- <span data-ttu-id="37343-158">Modell-Management</span><span class="sxs-lookup"><span data-stu-id="37343-158">Model management</span></span>
- <span data-ttu-id="37343-159">Zuweisungen von Rollen</span><span class="sxs-lookup"><span data-stu-id="37343-159">Role assignments</span></span>

<span data-ttu-id="37343-160">Folgende Konfigurationseinstellungen werden *nicht* kopiert:</span><span class="sxs-lookup"><span data-stu-id="37343-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="37343-161">Kundenprofile.</span><span class="sxs-lookup"><span data-stu-id="37343-161">Customer profiles.</span></span>
- <span data-ttu-id="37343-162">Anmeldeinformationen für die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="37343-162">Data source credentials.</span></span> <span data-ttu-id="37343-163">Sie müssen die Anmeldeinformationen für jede Datenquelle angeben und die Datenquellen manuell aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="37343-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="37343-164">Datenquellen aus dem Common Data Model-Ordner und Common Data Service verwalteter Lake.</span><span class="sxs-lookup"><span data-stu-id="37343-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="37343-165">Sie müssen diese Datenquellen manuell mit demselben Namen wie in der Quellumgebung erstellen.</span><span class="sxs-lookup"><span data-stu-id="37343-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="37343-166">Wenn Sie eine Umgebung kopieren, wird eine Bestätigungsmeldung angezeigt, dass die neue Umgebung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="37343-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="37343-167">Wählen Sie **Gehen Sie zu Datenquellen**, um die Liste der Datenquellen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="37343-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="37343-168">Alle Datenquellen zeigen einen Status **Anmeldeinformationen erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="37343-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="37343-169">Bearbeiten Sie die Datenquellen und geben Sie die Anmeldeinformationen ein, um sie zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="37343-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="37343-170">![Datenquellen kopiert](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="37343-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="37343-171">Nachdem Sie die Datenquellen aktualisiert haben, gehen Sie zu **Daten** > **Vereinheitlichen**.</span><span class="sxs-lookup"><span data-stu-id="37343-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="37343-172">Hier finden Sie Einstellungen aus der Quellumgebung.</span><span class="sxs-lookup"><span data-stu-id="37343-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="37343-173">Bearbeiten Sie sie nach Bedarf oder wählen Sie **Ausführen**, um den Datenvereinheitlichungsprozess zu starten und die einheitliche Kundenentität zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="37343-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="37343-174">Wenn die Datenvereinheitlichung abgeschlossen ist, gehen Sie zu **Maßnahmen** und **Segmente**, um sie auch zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="37343-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="37343-175">So bearbeiten Sie eine bestehende Umgebung</span><span class="sxs-lookup"><span data-stu-id="37343-175">Edit an existing environment</span></span>

<span data-ttu-id="37343-176">Sie können einige Details vorhandener Umgebungen bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="37343-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="37343-177">Wechseln Sie zu **Admin** > **System** > **Info**.</span><span class="sxs-lookup"><span data-stu-id="37343-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="37343-178">Wählen Sie **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="37343-178">Select **Edit**.</span></span>

3. <span data-ttu-id="37343-179">Sie können den **Anzeigename** der Umgebung aktualisieren, aber Sie können die **Region** oder **Typ** nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="37343-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="37343-180">Wenn eine Umgebung zum Speichern von Daten in Azure Data Lake Storage Gen2 konfiguriert ist, können Sie den **Kontoschlüssel** aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="37343-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="37343-181">Sie können jedoch nicht den Namen **Kontoname** oder **Container** ändern.</span><span class="sxs-lookup"><span data-stu-id="37343-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="37343-182">Optional können Sie von einer kontoschlüsselbasierten Verbindung zu einer ressourcenbasierten oder abonnementbasierten Verbindung aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="37343-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="37343-183">Nach der Aktualisierung können Sie nicht mehr zum Kontenschlüssel zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="37343-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="37343-184">Weitere Informationen finden Sie unter [Verbinden Sie Zielgruppen-Insights mit einem Azure Data Lake Storage Gen2-Konto mit einem Azure-Dienstprinzipal](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="37343-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="37343-185">Sie können die **Container**-Informationen beim Aktualisieren der Verbindung nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="37343-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="37343-186">Zurücksetzen einer bestehenden Umgebung</span><span class="sxs-lookup"><span data-stu-id="37343-186">Reset an existing environment</span></span>

<span data-ttu-id="37343-187">Sie können eine Umgebung auf einen leeren Zustand zurücksetzen, wenn Sie alle Konfigurationen löschen und die aufgenommenen Daten entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="37343-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="37343-188">Wechseln Sie zu **Admin** > **System** > **Info**.</span><span class="sxs-lookup"><span data-stu-id="37343-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="37343-189">Wählen Sie **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="37343-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="37343-190">Um das Löschen zu bestätigen, geben Sie den Namen der Umgebung ein und wählen Sie **Zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="37343-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="37343-191">Löschen Sie eine vorhandene Umgebung</span><span class="sxs-lookup"><span data-stu-id="37343-191">Delete an existing environment</span></span>

1. <span data-ttu-id="37343-192">Wechseln Sie zu **Admin** > **System** > **Info**.</span><span class="sxs-lookup"><span data-stu-id="37343-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="37343-193">Klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="37343-193">Select **Delete**.</span></span>

1. <span data-ttu-id="37343-194">Um das Löschen zu bestätigen, geben Sie den Namen der Umgebung ein und wählen Sie **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="37343-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>
