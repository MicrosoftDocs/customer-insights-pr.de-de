---
title: Mit APIs arbeiten
description: APIs verwenden und Einschränkungen verstehen.
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 59161456914df84d7e72402ed1f5faf70a5119ba
ms.sourcegitcommit: a39e00a50ad3eda820fd756c5611081f0ca04662
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2021
ms.locfileid: "5873661"
---
# <a name="work-with-customer-insights-apis"></a>Arbeiten Sie mit Customer Insights APIs

Dynamics 365 Customer Insights stellt APIs zur Verfügung, mit denen Sie eigene Anwendungen auf Basis der Daten in Customer Insights erstellen können.

> [!IMPORTANT]
> Details zu diesen APIs, finden Sie in der [Customer Insights APIs Referenz](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Sie enthalten zusätzliche Informationen über Operationen, Parameter und Antworten.

Dieser Artikel leitet Sie zum Zugriff auf die Customer Insights APIs an, erstellt eine Azure App-Registrierung und hilft Ihnen, mit den verfügbaren Client-Bibliotheken zu arbeiten.

## <a name="get-started-trying-the-customer-insights-apis"></a>Probieren Sie die Customer Insights APIs aus

1. [Anmelden](https://home.ci.ai.dynamics.com) bei Customer Insights. Wenn Sie noch kein Abonnement haben, [anmelden Sie sich für einen Test von Customer Insights](https://aka.ms/tryci).

1. Um APIs in Ihrer Customer Insights Umgebung zu aktivieren, gehen Sie zu **Admin** > **Berechtigungen**. Dazu benötigen Sie Admin-Berechtigungen.

1. Gehen Sie zur Registerkarte **APIs** und wählen Sie die Schaltfläche **Aktivieren**.    
   Das Aktivieren der APIs erstellt einen primären und sekundären Abonnementschlüssel für Ihre Instanz, der in den API-Anfragen verwendet wird. Sie können die Schlüssel neu generieren, indem Sie auf **Admin** > **Berechtigungen** > **APIs** die Option **Primär neu generieren** oder **Sekundär neu generieren** wählen.

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insights-APIs aktivieren":::

1. Wählen Sie **Erforsche unsere APIs**, um [die APIs auszuprobieren](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Wählen Sie eine API-Operation und wählen Sie **Ausprobieren**.

1. Setzen Sie im Seitenbereich den Wert im Dropdown-Menü **Authorisierung** auf **Implizit**. Die Kopfzeile `Authorization` wird mit einem Bearer-Token versehen. Ihr Abonnementschlüssel wird automatisch ausgefüllt.
  
1. Fügen Sie optional alle erforderlichen Abfrageparameter hinzu.

1. Scrollen Sie zum unteren Rand des Seitenfensters und wählen Sie **Senden**.

Die HTTP-Antwort wird gleich unten angezeigt.


   :::image type="content" source="media/try-apis.gif" alt-text="Animiertes GIF, das zeigt, wie Sie die APIs auswählen.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Erstellen Sie eine neue App-Registrierung im Azure-Portal

Diese Schritte helfen Ihnen bei der Verwendung der Customer Insights APIs in einer Azure-Anwendung mit delegierten Berechtigungen. Stellen Sie sicher, dass Sie zuerst den Abschnitt [Einführung](#get-started-trying-the-customer-insights-apis) abgeschlossen haben.

1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) mit dem Konto an, das auf die Customer Insights-Daten zugreifen kann.

1. Wählen Sie auf der linken Seite **App-Registrierungen**.

1. Wählen Sie **Neuregistrierung** geben Sie einen Anwendungsnamen an und wählen Sie den Kontotyp.
   Fügen Sie optional eine Umleitungs-URL hinzu. http://localhost ist ausreichend für die Entwicklung einer Anwendung auf Ihrem lokalen Computer.

1. Gehen Sie bei Ihrer neuen App-Registrierung zu **API-Berechtigungen**.

   :::image type="content" source="media/app-registration-1.gif" alt-text="Animiertes GIF zum Festlegen der API-Berechtigung bei der App-Registrierung.":::

1. Wählen Sie **Eine Berechtigung hinzufügen** und wählen Sie **Customer Insights** im Seitenbereich.

1. Wählen Sie für **Berechtigungstyp** die Option **Delegierte Berechtigungen** und wählen Sie die Berechtigung **user_impersonation**.

1. Wählen Sie **Berechtigungen hinzufügen** aus. Wenn Sie auf die API zugreifen müssen, ohne dass sich ein Benutzer anmeldet, lesen Sie den Abschnitt [Berechtigungen für Server-zu-Server-Anwendungen](#server-to-server-application-permissions).

1. Wählen Sie **Admin-Zustimmung erteilen für...**, um die Registrierung der App abzuschließen.

Sie können die Anwendungs-/Client-ID für diese App-Registrierung mit der Microsoft Authentication Library (MSAL) verwenden, um ein Träger-Token zu erhalten, das Sie mit Ihrer Anfrage an die API senden.

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Animiertes GIF zur Erteilung der Administratoreinwilligung.":::

Weitere Informationen über MSAL finden Sie unter [Übersicht über die Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).

Weitere Informationen zur App-Registrierung in Azure finden Sie unter [Das neue Azure-Portal für die App-Registrierung](/azure/active-directory/develop/app-registration-portal-training-guide).

Informationen zur Verwendung der APIs unserer Client-Bibliotheken finden Sie unter [Customer Insights Client-Bibliotheken](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Server-zu-Server-Anwendungsberechtigungen

Der [Abschnitt App-Registrierung](#create-a-new-app-registration-in-the-azure-portal) beschreibt, wie Sie eine App registrieren, bei der sich ein Benutzer zur Authentifizierung anmelden muss. Lernen Sie, wie Sie eine App-Registrierung erstellen, die keine Benutzerinteraktion benötigt und auf einem Server ausgeführt werden kann.

1. Gehen Sie bei Ihrer App-Registrierung im Azure-Portal zu **API-Berechtigungen**.

1. Wählen Sie **Eine Berechtigung hinzufügen** und wählen Sie **Customer Insights** im Seitenbereich.

1. Wählen Sie für **Berechtigungstyp** die **Anwendungsberechtigungen** und wählen Sie die Berechtigung **CustomerInsights.Api.All**.

1. Wählen Sie **Berechtigungen hinzufügen** aus.

1. Um die Admin-Berechtigung für diese Anwendung zu erteilen, müssen Sie ein Service Principal hinzufügen.

   1. Installieren Sie das Azure Active Directory (AD) PowerShell-Modul: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. Verbinden Sie sich mit Ihrem AD-Konto: `Connect-AzureAD -TenantId <your tenant id>`. Sie finden Ihre Mandanten-ID auf **Übersicht** > **Azure Active Directory**.
   1. Führen Sie den folgenden Befehl aus, um ein Azure AD Service Principal hinzuzufügen: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Der Parameter AppId bezieht sich auf die Customer Insights API App.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Serviceprinzipal-Beispiel":::

1. Gehen Sie zurück zu **API-Berechtigungen** für Ihre App-Registrierung.

1. Wählen Sie **Admin-Zustimmung erteilen für...**, um die Registrierung der App abzuschließen.

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Animiertes GIF zur Erteilung der Administratoreinwilligung.":::

1. Zum Abschluss müssen wir den Namen der App-Registrierung als Benutzer in Customer Insights hinzufügen.    
   Öffnen Sie Customer Insights, gehen Sie zu **Admin** > **Berechtigungen** und wählen Sie **Benutzer hinzufügen**.

1. Suchen Sie nach dem Namen Ihrer App-Registrierung, wählen Sie ihn aus den Suchergebnissen und wählen Sie **Speichern**.

## <a name="customer-insights-client-libraries"></a>Customer Insights Client-Bibliotheken

Dieser Abschnitt hilft Ihnen bei den ersten Schritten mit den Client-Bibliotheken, die für die Customer Insights APIs verfügbar sind. Alle Quellcodes und Beispielanwendungen der Bibliothek finden Sie auf der [Customer Insights GitHub-Seite](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Lernen Sie, wie Sie mit den C# Client-Bibliotheken von NuGet.org arbeiten können. Weitere Informationen über das NuGet-Paket finden Sie unter [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Zurzeit zielt dieses Paket auf die Frameworks netstandard2.0 und netcoreapp2.0 ab.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Fügen Sie die C#-Client-Bibliothek zu einem C#-Projekt hinzu

1. Öffnen Sie in Visual Studio den **NuGet Paketmanager** für Ihr Projekt.

1. Suchen Sie nach **Microsoft.Dynamics.CustomerInsights.Api**.

1. Wählen Sie **Installieren**, um das Paket zum Projekt hinzuzufügen.
   Führen Sie alternativ diesen Befehl in der **NuGet Paketmanager-Konsole** aus: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Hinzufügen von NuGet Paket zu Visual Studio Projekt":::

#### <a name="use-the-c-client-library"></a>Verwenden Sie die C# Client-Bibliothek

1. Verwenden Sie die [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview), um eine `AccessToken` mit Ihrer bestehenden [Azure-App-Registrierung](#create-a-new-app-registration-in-the-azure-portal) zu erhalten.

1. Nach erfolgreicher Authentifizierung und dem Erwerb eines Tokens erstellen Sie eine neue oder verwenden eine bestehende `HttpClient`mit den zusätzlichen **DefaultRequestHeaders „Authorization“**, die auf **Bearer <access token>** und **Ocp-Apim-Subscription-Key** auf den [**Abonnementschlüssel** aus Ihrer Customer Insights Umgebung](#get-started-trying-the-customer-insights-apis) gesetzt sind.    
   Setzen Sie gegebenenfalls den **Autorisierung**-Header zurück. Zum Beispiel, wann der Token abgelaufen ist.

1. Übergeben Sie diese `HttpClient` in die Konstruktion des `CustomerInsights` Clients.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Beispiel für httpclient":::

1. Rufen Sie mit dem Client die „Erweiterungsmethoden“ auf, zum Beispiel `GetAllInstancesAsync`. Wenn der Zugriff auf die zugrundeliegende `Microsoft.Rest.HttpOperationResponse` bevorzugt wird, verwenden Sie die „http-Message-Methoden“, z. B. `GetAllInstancesWithHttpMessagesAsync`.

1. Die Antwort wird wahrscheinlich vom Typ `object` sein, da die Methode mehrere Typen zurückgeben kann (zum Beispiel `IList<InstanceInfo>` und `ApiErrorResult`). Um den Rückgabetyp zu prüfen, können Sie die Objekte sicher in die Antworttypen umwandeln, die auf der [API-Detailseite](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) für diese Operation angegeben sind.    
   Wenn mehr Informationen über die Anfrage benötigt werden, verwenden Sie die **http-Message-Methoden** für den Zugriff auf das raw response-Objekt.

### <a name="nodejs-package"></a>NodeJS-Paket

Verwenden Sie die über NPM verfügbaren NodeJS-Clientbibliotheken: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python-Paket

Verwenden Sie die über PyPi verfügbaren Python-Clientbibliotheken: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
