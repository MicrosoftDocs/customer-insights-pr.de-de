---
title: Erweiterte Web SDK-Szenarien
description: Erweiterte Szenarien, die bei der Instrumentierung Ihrer Website mit einem SDK berücksichtigt werden müssen.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036327"
---
# <a name="advanced-web-sdk-instrumentation"></a>Erweiterte Web SDK-Instrumentierung

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dieser Artikel führt Sie durch erweiterte Szenarien, die bei der [Instrumentierung Ihrer Website](instrument-website.md) mit einem SDK für die Funktion Kundenbindungserkenntnisse von Dynamics 365 Customer Insights berücksichtigt werden müssen.

## <a name="setting-user-details-for-your-event"></a>Festlegen von Benutzerdetails für Ihr Ereignis

Mit dem SDK können Sie Benutzerinformationen definieren, die mit jedem Ereignis gesendet werden können. Sie können die Benutzerdetails in einer Eigenschaft mit der Bezeichnung `user` (für diese Eigenschaft wird das `IUser`-Objekt erwartet) angeben, ähnlich wie `src`, `name` und `cfg` in der Konfiguration des Codeausschnitts.

Das `IUser`-Objekt hat die folgenden Zeichenfolgeneigenschaften:

- **localId**: Die lokale ID des Benutzers.
- **authId**: Die authentifizierte Benutzer-ID.
- **authType**: Der Authentifizierungstyp, mit dem die authentifizierte Benutzer-ID abgerufen wird.
- **name**: Der Name des Benutzers.
- **email**: Die E-Mail-Adresse des Benutzers.
    
Das folgende Beispiel zeigt einen Codeausschnitt, der Benutzerinformationen sendet. Wenn Sie Funktionen sehen, die mit dem Symbol „*“ gekennzeichnet sind, ersetzen Sie diese durch Ihre Implementierung des Aufrufs dieser Werte:  

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
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Sie können Benutzerinformationen auch angeben, indem Sie die API `setUser(user: IUser)` im SDK aufrufen. Nach dem Anruf der API `setUser API` gesendete Telemetrie enthält die Benutzerinformationen.

## <a name="adding-custom-properties-for-each-event"></a>Hinzufügen benutzerdefinierter Eigenschaften für jedes Ereignis

Mit dem SDK können Sie benutzerdefinierte Eigenschaften angeben, die mit jedem Ereignis gesendet werden können. Sie können die benutzerdefinierten Eigenschaften als Objekt angeben, das Schlüssel-Wert-Paare enthält (der Wert kann vom Typ `string | number | boolean` sein). Das Objekt kann in einer Eigenschaft mit der Bezeichnung `props` hinzugefügt werden, ähnlich wie `src`, `name` und `cfg` in der Konfiguration des Codeausschnitts. 

Das folgende Beispiel zeigt einen Codeausschnitt, der benutzerdefinierte Eigenschaften sendet:

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
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Sie können benutzerdefinierte Eigenschaften auch einzeln angeben, indem Sie die API `setProperty(name: string, value: string | number | boolean)` im SDK aufrufen.

## <a name="sending-custom-events"></a>Senden benutzerdefinierter Ereignisse

Mit dem SDK können Sie benutzerdefinierte Ereignisse senden. Sie müssen einen Namen für das Ereignis und die Eigenschaften angeben, die mit dem Ereignis gesendet werden sollen.

Das folgende Beispiel zeigt einen Codeausschnitt, der ein benutzerdefiniertes Ereignis nachverfolgt. „NAME“ ist der Wert im Schlüssel `name` in der Konfiguration des Ausschnitts. Der Wert ist außerdem der Variablenname im Fensterobjekt, in dem das SDK geladen wird.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]