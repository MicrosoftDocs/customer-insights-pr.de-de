---
title: Mit APIs arbeiten
description: APIs verwenden und Einschränkungen verstehen.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 966db1a22e7dece1bcd89733880bce059151157f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267523"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="fe891-103">Arbeiten Sie mit Customer Insights APIs</span><span class="sxs-lookup"><span data-stu-id="fe891-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="fe891-104">Dynamics 365 Customer Insights stellt APIs zur Verfügung, mit denen Sie eigene Anwendungen auf Basis der Daten in Customer Insights erstellen können.</span><span class="sxs-lookup"><span data-stu-id="fe891-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fe891-105">Details zu diesen APIs, finden Sie in der [Customer Insights APIs Referenz](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="fe891-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="fe891-106">Sie enthalten zusätzliche Informationen über Operationen, Parameter und Antworten.</span><span class="sxs-lookup"><span data-stu-id="fe891-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="fe891-107">Dieser Artikel leitet Sie zum Zugriff auf die Customer Insights APIs an, erstellt eine Azure App-Registrierung und hilft Ihnen, mit den verfügbaren Client-Bibliotheken zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="fe891-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="fe891-108">Probieren Sie die Customer Insights APIs aus</span><span class="sxs-lookup"><span data-stu-id="fe891-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="fe891-109">[Anmelden](https://home.ci.ai.dynamics.com) bei Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fe891-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="fe891-110">Wenn Sie noch kein Abonnement haben, [anmelden Sie sich für einen Test von Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="fe891-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="fe891-111">Um APIs in Ihrer Customer Insights Umgebung zu aktivieren, gehen Sie zu **Admin** > **Berechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="fe891-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="fe891-112">Dazu benötigen Sie Admin-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="fe891-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="fe891-113">Gehen Sie zur Registerkarte **APIs** und wählen Sie die Schaltfläche **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="fe891-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="fe891-114">Das Aktivieren der APIs erstellt einen primären und sekundären Abonnementschlüssel für Ihre Instanz, der in den API-Anfragen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fe891-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="fe891-115">Sie können die Schlüssel neu generieren, indem Sie auf **Admin** > **Berechtigungen** > **APIs** die Option **Primär neu generieren** oder **Sekundär neu generieren** wählen.</span><span class="sxs-lookup"><span data-stu-id="fe891-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insights-APIs aktivieren":::

1. <span data-ttu-id="fe891-117">Wählen Sie **Erforsche unsere APIs**, um die APIs auszuprobieren.</span><span class="sxs-lookup"><span data-stu-id="fe891-117">Select **Explore our APIs** to try out the APIs.</span></span>

1. <span data-ttu-id="fe891-118">Wählen Sie eine API-Operation und wählen Sie **Ausprobieren**.</span><span class="sxs-lookup"><span data-stu-id="fe891-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="fe891-119">Setzen Sie im Seitenbereich den Wert im Dropdown-Menü **Authorisierung** auf **Implizit**.</span><span class="sxs-lookup"><span data-stu-id="fe891-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="fe891-120">Die Kopfzeile `Authorization` wird mit einem Bearer-Token versehen.</span><span class="sxs-lookup"><span data-stu-id="fe891-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="fe891-121">Ihr Abonnementschlüssel wird automatisch ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="fe891-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="fe891-122">Fügen Sie optional alle erforderlichen Abfrageparameter hinzu.</span><span class="sxs-lookup"><span data-stu-id="fe891-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="fe891-123">Scrollen Sie zum unteren Rand des Seitenfensters und wählen Sie **Senden**.</span><span class="sxs-lookup"><span data-stu-id="fe891-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="fe891-124">Die HTTP-Antwort wird gleich unten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fe891-124">The HTTP response will soon appear below.</span></span>

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="fe891-125">Erstellen Sie eine neue App-Registrierung im Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="fe891-125">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="fe891-126">Diese Schritte helfen Ihnen bei der Verwendung der Customer Insights APIs in einer Azure-Anwendung mit delegierten Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="fe891-126">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="fe891-127">Stellen Sie sicher, dass Sie zuerst den Abschnitt [Einführung](#get-started-trying-the-customer-insights-apis) abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="fe891-127">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="fe891-128">Melden Sie sich beim [Azure-Portal](https://portal.azure.com) mit dem Konto an, das auf die Customer Insights-Daten zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="fe891-128">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="fe891-129">Wählen Sie auf der linken Seite **App-Registrierungen**.</span><span class="sxs-lookup"><span data-stu-id="fe891-129">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="fe891-130">Wählen Sie **Neuregistrierung** geben Sie einen Anwendungsnamen an und wählen Sie den Kontotyp.</span><span class="sxs-lookup"><span data-stu-id="fe891-130">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="fe891-131">Fügen Sie optional eine Umleitungs-URL hinzu.</span><span class="sxs-lookup"><span data-stu-id="fe891-131">Optionally, add a redirect URL.</span></span> <span data-ttu-id="fe891-132">http://localhost ist ausreichend für die Entwicklung einer Anwendung auf Ihrem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="fe891-132">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="fe891-133">Gehen Sie bei Ihrer neuen App-Registrierung zu **API-Berechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="fe891-133">On your new App registration, go to **API permissions**.</span></span>

1. <span data-ttu-id="fe891-134">Wählen Sie **Eine Berechtigung hinzufügen** und wählen Sie **Customer Insights** im Seitenbereich.</span><span class="sxs-lookup"><span data-stu-id="fe891-134">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="fe891-135">Wählen Sie für **Berechtigungstyp** die Option **Delegierte Berechtigungen** und wählen Sie die Berechtigung **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="fe891-135">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="fe891-136">Wählen Sie **Berechtigungen hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="fe891-136">Select **Add permissions**.</span></span> <span data-ttu-id="fe891-137">Wenn Sie auf die API zugreifen müssen, ohne dass sich ein Benutzer anmeldet, lesen Sie den Abschnitt [Berechtigungen für Server-zu-Server-Anwendungen](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="fe891-137">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="fe891-138">Wählen Sie **Admin-Zustimmung erteilen für...**, um die Registrierung der App abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="fe891-138">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="fe891-139">Sie können die Anwendungs-/Client-ID für diese App-Registrierung mit der Microsoft Authentication Library (MSAL) verwenden, um ein Träger-Token zu erhalten, das Sie mit Ihrer Anfrage an die API senden.</span><span class="sxs-lookup"><span data-stu-id="fe891-139">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

<span data-ttu-id="fe891-140">Weitere Informationen über MSAL finden Sie unter [Übersicht über die Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="fe891-140">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="fe891-141">Weitere Informationen zur App-Registrierung in Azure finden Sie unter [Das neue Azure-Portal für die App-Registrierung](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="fe891-141">For more information about app registration in Azure, see [The new Azure portal app registration experience](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="fe891-142">Informationen zur Verwendung der APIs unserer Client-Bibliotheken finden Sie unter [Customer Insights Client-Bibliotheken](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="fe891-142">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="fe891-143">Server-zu-Server-Anwendungsberechtigungen</span><span class="sxs-lookup"><span data-stu-id="fe891-143">Server-to-server application permissions</span></span>

<span data-ttu-id="fe891-144">Der [Abschnitt App-Registrierung](#create-a-new-app-registration-in-the-azure-portal) beschreibt, wie Sie eine App registrieren, bei der sich ein Benutzer zur Authentifizierung anmelden muss.</span><span class="sxs-lookup"><span data-stu-id="fe891-144">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="fe891-145">Lernen Sie, wie Sie eine App-Registrierung erstellen, die keine Benutzerinteraktion benötigt und auf einem Server ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="fe891-145">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="fe891-146">Gehen Sie bei Ihrer App-Registrierung im Azure-Portal zu **API-Berechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="fe891-146">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="fe891-147">Wählen Sie **Eine Berechtigung hinzufügen** und wählen Sie **Customer Insights** im Seitenbereich.</span><span class="sxs-lookup"><span data-stu-id="fe891-147">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="fe891-148">Wählen Sie für **Berechtigungstyp** die **Anwendungsberechtigungen** und wählen Sie die Berechtigung **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="fe891-148">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="fe891-149">Wählen Sie **Berechtigungen hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="fe891-149">Select **Add permissions**.</span></span>

1. <span data-ttu-id="fe891-150">Um die Admin-Berechtigung für diese Anwendung zu erteilen, müssen Sie ein Service Principal hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fe891-150">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="fe891-151">Installieren Sie das Azure Active Directory (AD) PowerShell-Modul: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="fe891-151">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="fe891-152">Verbinden Sie sich mit Ihrem AD-Konto: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="fe891-152">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="fe891-153">Sie finden Ihre Mandanten-ID auf **Übersicht** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="fe891-153">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="fe891-154">Führen Sie den folgenden Befehl aus, um ein Azure AD Service Principal hinzuzufügen: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Der Parameter AppId bezieht sich auf die Customer Insights API App.</span><span class="sxs-lookup"><span data-stu-id="fe891-154">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Serviceprinzipal-Beispiel":::

1. <span data-ttu-id="fe891-156">Gehen Sie zurück zu **API-Berechtigungen** für Ihre App-Registrierung.</span><span class="sxs-lookup"><span data-stu-id="fe891-156">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="fe891-157">Wählen Sie **Admin-Zustimmung erteilen für...**, um die Registrierung der App abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="fe891-157">Select **Grant admin consent for...** to complete the app registration.</span></span>

1. <span data-ttu-id="fe891-158">Zum Abschluss müssen wir den Namen der App-Registrierung als Benutzer in Customer Insights hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fe891-158">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="fe891-159">Öffnen Sie Customer Insights, gehen Sie zu **Admin** > **Berechtigungen** und wählen Sie **Benutzer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="fe891-159">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="fe891-160">Suchen Sie nach dem Namen Ihrer App-Registrierung, wählen Sie ihn aus den Suchergebnissen und wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fe891-160">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="fe891-161">Customer Insights Client-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="fe891-161">Customer Insights client libraries</span></span>

<span data-ttu-id="fe891-162">Dieser Abschnitt hilft Ihnen bei den ersten Schritten mit den Client-Bibliotheken, die für die Customer Insights APIs verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="fe891-162">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span>

### <a name="c-nuget"></a><span data-ttu-id="fe891-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="fe891-163">C# NuGet</span></span>

<span data-ttu-id="fe891-164">Lernen Sie, wie Sie mit den C# Client-Bibliotheken von NuGet.org arbeiten können. Weitere Informationen über das NuGet-Paket finden Sie unter [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="fe891-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="fe891-165">Zurzeit zielt dieses Paket auf die Frameworks netstandard2.0 und netcoreapp2.0 ab.</span><span class="sxs-lookup"><span data-stu-id="fe891-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="fe891-166">Fügen Sie die C#-Client-Bibliothek zu einem C#-Projekt hinzu</span><span class="sxs-lookup"><span data-stu-id="fe891-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="fe891-167">Öffnen Sie in Visual Studio den **NuGet Paketmanager** für Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="fe891-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="fe891-168">Suchen Sie nach **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="fe891-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="fe891-169">Wählen Sie **Installieren**, um das Paket zum Projekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fe891-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="fe891-170">Führen Sie alternativ diesen Befehl in der **NuGet Paketmanager-Konsole** aus: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="fe891-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Hinzufügen von NuGet Paket zu Visual Studio Projekt":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="fe891-172">Verwenden Sie die C# Client-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="fe891-172">Use the C# client library</span></span>

1. <span data-ttu-id="fe891-173">Verwenden Sie die [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview), um eine `AccessToken` mit Ihrer bestehenden [Azure-App-Registrierung](#create-a-new-app-registration-in-the-azure-portal) zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fe891-173">Use the [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="fe891-174">Nach erfolgreicher Authentifizierung und dem Erwerb eines Tokens erstellen Sie eine neue oder verwenden eine bestehende `HttpClient`mit den zusätzlichen **DefaultRequestHeaders „Authorization“**, die auf **Bearer <access token>** und **Ocp-Apim-Subscription-Key** auf den [**Abonnementschlüssel** aus Ihrer Customer Insights Umgebung](#get-started-trying-the-customer-insights-apis) gesetzt sind.</span><span class="sxs-lookup"><span data-stu-id="fe891-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="fe891-175">Setzen Sie gegebenenfalls den **Autorisierung**-Header zurück.</span><span class="sxs-lookup"><span data-stu-id="fe891-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="fe891-176">Zum Beispiel, wann der Token abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="fe891-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="fe891-177">Übergeben Sie diese `HttpClient` in die Konstruktion des `CustomerInsights` Clients.</span><span class="sxs-lookup"><span data-stu-id="fe891-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Beispiel für httpclient":::

1. <span data-ttu-id="fe891-179">Rufen Sie mit dem Client die „Erweiterungsmethoden“ auf, zum Beispiel `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="fe891-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="fe891-180">Wenn der Zugriff auf die zugrundeliegende `Microsoft.Rest.HttpOperationResponse` bevorzugt wird, verwenden Sie die „http-Message-Methoden“, z. B. `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="fe891-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="fe891-181">Die Antwort wird wahrscheinlich vom Typ `object` sein, da die Methode mehrere Typen zurückgeben kann (zum Beispiel `IList<InstanceInfo>` und `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="fe891-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="fe891-182">Um den Rückgabetyp zu prüfen, können Sie die Objekte sicher in die Antworttypen umwandeln, die auf der [API-Detailseite](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) für diese Operation angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="fe891-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="fe891-183">Wenn mehr Informationen über die Anfrage benötigt werden, verwenden Sie die **http-Message-Methoden** für den Zugriff auf das raw response-Objekt.</span><span class="sxs-lookup"><span data-stu-id="fe891-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]