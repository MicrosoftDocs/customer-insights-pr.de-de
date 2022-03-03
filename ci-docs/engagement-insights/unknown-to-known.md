---
title: Webereignisse von zuvor authentifizierten Besuchern mit „Unbekannt nach bekannt“ anerkennen
description: Die Funktion „Unbekannt nach bekannt“ ermöglicht es Ihnen, Ereignisse auf einer Website mit Besuchern zu verknüpfen, die sich zuvor authentifiziert haben.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: 75ce776fd5be1c426508ae6f5c239c86bdd3ec39
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230679"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Webereignisse von zuvor authentifizierten Besuchern anerkennen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Die Funktion **Unbekannt nach bekannt** in der Funktion „Interaktionserkenntnisse“ ermöglicht es, Ereignisse auf einer Website mit Besuchern zu verknüpfen, die sich zuvor authentifiziert haben. Wenn die Funktion deaktiviert ist, werden Besucher, die sich bei einem früheren Besuch authentifiziert und dann die Funktion verlassen haben, nicht identifiziert, wenn sie sich bei der Rückkehr nicht erneut authentifizieren. 

Beispiel: Jemand hat letzte Woche eine Website besucht, sich bei seinem Benutzerkonto auf der Website angemeldet und den Produktkatalog durchsucht. Die Person kehrt in der folgenden Woche zurück, um weitere Produkte zu durchsuchen, ohne sich bei seinem Konto anzumelden. Der Websitebesitzer, der die Funktion **Unbekannt nach bekannt** Funktion benutzt, weiß, dass dieselbe Person zurückgekehrt ist und was sie auf der Website getan hat. Dies ermöglicht eine genauere Berichterstattung und Analyse der Website-Aktivitäten.

## <a name="enable-unknown-to-known"></a>„Unbekannt nach bekannt“ aktivieren

Sie müssen ein [Arbeitsbereichsadministrator](user-roles.md) sein, um diese Funktion zu aktivieren. 

1. Gehen Sie in den Interaktionserkenntnissen zu **Administrator** > **Arbeitsbereich**. 
2. Wählen Sie die Registerkarte **Einstellungen** aus.
3. Stellen Sie im Abschnitt **Unbekannt nach bekannt** den Schalter auf **Aktiviert**.

![„Unbekannt nach bekannt“ aktivieren](media/U2Ktoggle.png "„Unbekannt nach bekannt“ aktivieren")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>JavaScript-Code zum Nachverfolgungsausschnitt Ihrer Website hinzufügen

Eine Website kann die **Benutzer-AuthId** mit dem folgenden JavaScript-Beispiel mit dem [Web-SDK der Interaktionserkenntnisse](advanced-SDK-implementation.md) erfassen. Damit die Funktion **Unbekannt nach bekannt** funktioniert, müssen Sie AuthId erfassen *und* userMapping:True in Ihrem JavaScript Ausschnitt wie im Beispiel unten aktivieren.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
