---
title: Hinzufügen von Code zu Ihrer Website
description: So fügen Sie einen Codeausschnitt hinzu, um Dynamics 365 Customer Insights-Ereignisse auf Ihrer Website zu erfassen.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ad835f762226d62fdb0f544627f2a76ff09a1ffd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558856"
---
# <a name="install-the-web-sdk-on-a-website"></a>Installieren des Web-SDK auf einer Website

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dieser Artikel beschreibt, wie ein Administrator das Web Software Development Toolkit (SDK) auf einer Website installiert. Kurz nach der Instrumentierung Ihrer Website werden Ereignisse in Ihrem Arbeitsbereich angezeigt. Weitere Informationen finden Sie unter [Verwalten von Arbeitsbereichen und Umgebungen](manage-environments-workspaces.md). Informationen zum Erfassen von Ereignissen in mobilen Apps finden Sie unter [Übersicht über Entwicklerressourcen](developer-resources.md).


### <a name="prerequisites"></a>Anforderungen

* Sie müssen über Administratorberechtigungen verfügen, damit der Arbeitsbereich die Daten speichern kann.
* Ihre Website oder Ihr Projekt muss online gehostet werden, um Aktivitätsdaten zu senden. Von einer lokalen Datei gesendete Daten werden vom Server nicht akzeptiert.


## <a name="add-web-sdk-to-your-website"></a>Hinzufügen des Web-SDK auf Ihrer Website

Wechseln Sie zu **Administrator** > **Arbeitsbereich** und wählen Sie **Installationsanleitung** aus. Zur Installation des Web-SDK stehen zwei Möglichkeiten zur Verfügung. Die erste besteht darin, einen Download-Link zu verwenden, und die zweite besteht darin, ein Node Package Manager (NPM)-Paket zu installieren.

### <a name="option-1-using-the-download-link"></a>Option 1: Verwenden des Downloadlinks

1. Wählen Sie **Code kopieren** aus, um den Codeausschnitt zu kopieren. Standardmäßig ist der Erfassungsschlüssel für Ihren Arbeitsbereich in den Codeausschnitt eingebettet.
  :::image type="content" source="media/copy-code.png" alt-text="Screenshot der Seite mit dem Codeausschnitt.":::

1. Fügen Sie den kopierten Code zu Ihrer Website hinzu, nahe <head> dem Tag und vor jedem anderen Skript oder CSS-Tag.
1. Veröffentlichen Sie Ihre aktualisierte Website und warten Sie einige Minuten, um den eingehenden Webverkehr zu erfassen.
1. Um Ihre Daten anzuzeigen, wählen Sie Ihren Arbeitsbereich im Navigationsbereich des Arbeitsbereichsumschalters aus. Wählen Sie dann einen der Berichte im Bereich **Entdecken** aus.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>Option 2: Verwenden des NPM-Pakets (empfohlen für JavaScript-basierte Web-Apps)

1. Gehen Sie zu unserem [NPM-Webpaket](https://www.npmjs.com/package/engagementinsights-web), und befolgen Sie die Anweisungen zum Installieren und Einrichten des Web-SDK-NPM-Pakets.
1. Veröffentlichen Sie Ihre aktualisierte Website und warten Sie einige Minuten, um den eingehenden Webverkehr zu erfassen.
1. Um Ihre Daten anzuzeigen, wählen Sie Ihren Arbeitsbereich im Navigationsbereich des Arbeitsbereichsumschalters aus. Wählen Sie dann einen der Berichte im Bereich **Entdecken** aus.

## <a name="configuration-options"></a>Konfigurationsoptionen

Sie können die folgenden Konfigurationsoptionen im Codeausschnitt ändern:

- **ingestionKey**: Der Erfassungsschlüssel zum Senden von Ereignissen an Ihren Arbeitsbereich. Sie können den Erfassungsschlüssel ändern, um Ereignisse an einen anderen Arbeitsbereich zu senden. Ein Erfassungsschlüssel ist für jeden Arbeitsbereich eindeutig.
- **autoCapture**: Gibt an, ob Seitenaufrufe und Interaktionen mit der Website erfasst werden. Es gibt zwei Optionen:
    - **view**: Auf *true* festlegen, um Seitenaufrufe zu erfassen. Seitenaufrufe werden als *Anzeige*[ereignisse](glossary.md#event) erfasst, ein Typ eines [Basisereignisses](glossary.md#base-event).
    - **click**: Auf *true* festlegen, um Besucherinteraktionen auf der Website zu erfassen. Interaktionen werden als *Aktions*[ereignisse](glossary.md#event) erfasst, ein Typ eines [Basisereignisses](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
