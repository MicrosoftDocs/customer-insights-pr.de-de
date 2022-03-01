---
title: Hinzufügen von Code zu Ihrer Website
description: So fügen Sie einen Codeausschnitt hinzu, um Ereignisse auf Ihrer Website zu erfassen.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035093"
---
# <a name="install-the-code-snippet-on-a-website"></a>Installieren des Codeausschnitts auf einer Website

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dieser Artikel beschreibt, wie ein Administrator den Codeausschnitt auf einer Website installiert. Kurz nachdem Sie das Skript zu Ihrer Website hinzugefügt haben, werden Ereignisse in Ihrem Arbeitsbereich angezeigt. Weitere Informationen finden Sie unter [Verwalten von Arbeitsbereichen und Umgebungen](manage-environments-workspaces.md). Informationen zum Erfassen von Ereignissen in mobilen Apps finden Sie unter [Übersicht über Entwicklerressourcen](developer-resources.md).


### <a name="prerequisites"></a>Anforderungen

* Sie müssen über Administratorberechtigungen verfügen, damit der Arbeitsbereich die Daten speichern kann.
* Ihre Website oder Ihr Projekt muss online gehostet werden, um Aktivitätsdaten zu senden. Von einer lokalen Datei gesendete Daten werden vom Server nicht akzeptiert.


## <a name="add-code-to-your-website"></a>Hinzufügen von Code zu Ihrer Website
1.  Wechseln Sie zu **Administrator** > **Arbeitsbereich** und wählen Sie **Installationsanleitung** aus.
1. Wählen Sie **Code kopieren** aus, um den Codeausschnitt zu kopieren. Standardmäßig ist der Erfassungsschlüssel für Ihren Arbeitsbereich in den Codeausschnitt eingebettet.
:::image type="content" source="media/copy-code.png" alt-text="Screenshot der Seite mit dem Codeausschnitt.":::
3. Fügen Sie den kopierten Codeausschnitt zu Ihrer Website hinzu, und zwar nahe <head> dem Tag und vor jedem anderen Skript oder CSS-Tag.
4.  Veröffentlichen Sie Ihre aktualisierte Website und warten Sie einige Minuten, um den eingehenden Webverkehr zu erfassen.
5.  Um Ihre Daten anzuzeigen, wählen Sie Ihren Arbeitsbereich im Navigationsbereich des Arbeitsbereichsumschalters aus. Wählen Sie dann einen der Berichte im Bereich **Entdecken** aus.

## <a name="configuration-options"></a>Konfigurationsoptionen

Sie können die folgenden Konfigurationsoptionen im Codeausschnitt ändern:

- **ingestionKey**: Der Erfassungsschlüssel zum Senden von Ereignissen an Ihren Arbeitsbereich. Sie können den Erfassungsschlüssel ändern, um Ereignisse an einen anderen Arbeitsbereich zu senden. Ein Erfassungsschlüssel ist für jeden Arbeitsbereich eindeutig. 
- **autoCapture**: Gibt an, ob Seitenaufrufe und Interaktionen mit der Website erfasst werden. Es gibt zwei Optionen:
    - **view**: Auf *true* festlegen, um Seitenaufrufe zu erfassen. Seitenaufrufe werden als *Anzeige*[ereignisse](glossary.md#event) erfasst, ein Typ eines [Basisereignisses](glossary.md#base-event).
    - **click**: Auf *true* festlegen, um Besucherinteraktionen auf der Website zu erfassen. Interaktionen werden als *Aktions*[ereignisse](glossary.md#event) erfasst, ein Typ eines [Basisereignisses](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
