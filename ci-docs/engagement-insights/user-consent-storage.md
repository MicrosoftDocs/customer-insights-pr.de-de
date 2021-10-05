---
title: Cookies verwalten und Zustimmung des Benutzers zum Speichern von Benutzerdaten in Dynamics 365 Customer Insights
description: Verstehen Sie, wie Cookies und die Benutzereinwilligungen verwendet werden, um Website-Besucher zu identifizieren.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c824e50b723fe7f3b421048bb6ab96b7a9efc31f
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558870"
---
# <a name="manage-cookies-and-user-consent"></a>Verwalten von Cookies und Benutzereinwilligungen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Die Interaktionserkenntnisse-Funktion von Dynamics 365 Customer Insights verwendet Cookies und Schlüssel (`localStorage`) zur Identifizierung von Websitebesuchern.

Cookies sind kleine Dateien, in denen Informationen zur Interaktionen eines Benutzers mit der Website gespeichert werden. Sie werden in Webbrowsern gespeichert. Wenn Benutzer eine Website besuchen, für die Ihre Benutzer Cookies gespeichert haben, sendet der Browser diese Informationen an den Server, der Informationen zurückgibt, die für den Benutzer eindeutig sind. Dies ist die Technologie, mit der beispielsweise ausgewählte Artikel selbst dann in einem Online-Warenkorb verbleiben können, wenn ein Benutzer die Website verlässt.

## <a name="user-consent"></a>Benutzereinwilligung

Die [Datenschutz-Grundverordnung (DSGVO)](/dynamics365/get-started/gdpr/) ist eine Verordnung der Europäischen Union (EU), die vorschreibt, wie Organisationen mit der Privatsphäre und Sicherheit ihrer Benutzer umgehen sollen. Cookies speichern oder sammeln häufig „persönliche Daten“, z. B. einen Online-Bezeichner, die von der DSGVO abgedeckt werden. Wenn Ihr Unternehmen EU-Datensubjekte beschäftigt und/oder an diese verkauft, wirkt sich die DSGVO auf Sie aus. [Erfahren Sie mehr darüber, wie Microsoft Sie bei der Einhaltung der DSGVO unterstützen kann](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Damit das SDK für die Funktion Kundenbindungserkenntnisse Cookies oder andere vertrauliche Informationen speichern kann, müssen Sie angeben, ob Ihre Benutzer hierzu ihre Einwilligung gegeben haben. Dies geschieht bei der Initialisierung des SDK durch Festlegen des Feldes `userConsent` in der Konfiguration.

Wenn Sie angeben, dass keine Benutzereinwilligung vorliegt, speichert das SDK keine Daten und sendet keine Ereignisse, mit denen das Benutzerverhalten verfolgt werden kann. Alle zuvor gespeicherten Daten werden aus dem Browser gelöscht.

Wenn kein Wert für die Benutzereinwilligung angegeben ist, geht das SDK davon aus, dass der Benutzer eingewilligt hat. Das bedeutet, dass Daten erfasst werden, wenn Sie (als unser Kunde) im SDK keinen Wert für die Benutzereinwilligung angeben. Wenn Sie jedoch angeben, dass der Wert für die Benutzereinwilligung „true“ sein muss, werden keine Daten erfasst, wenn ein Benutzer die ausdrückliche Einwilligung ablehnt oder nicht erteilt.

Nachfolgend steht ein Codeausschnitt zum Initialisieren des Web-SDK mit Zustimmung des Benutzers:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Speicherung von Besucherdaten in der Funktion Kundenbindungserkenntnisse

### <a name="cookies"></a>Cookies

- _msei
    - Speichert die anonyme Benutzer-ID. Dieses Cookie wird in der Kundendomäne gesetzt und läuft nach 365 Tagen ab.

### <a name="local-storage"></a>Lokaler Speicher

Die Interaktionserkenntnisse-Funktion nutzt auch Schlüssel (`localStorage`), um nicht sensible Daten zu verfolgen. Diese Daten werden vollständig im Browser selbst gespeichert, ohne dass Datenverkehr an oder von Ihren Servern gesendet wird.

- *EISession.Id*
    - Speichert Informationen über die laufende Benutzersitzung, z. B. die Sitzungs-ID, wann sie gestartet wurde und wann sie abläuft.
- *EISession.Previous*
    - Speichert die URL der zuvor besuchten Seite in der aktuellen Sitzung.

Schlüssel im lokalen Speicher laufen nicht automatisch ab und werden während der nächsten SDK-Sitzung zurückgesetzt.

## <a name="deleting-cookies"></a>Löschen von Cookies

Ihre Kunden können Cookies und Schlüssel im lokalen Speicher jederzeit manuell über die Einstellungen ihres Browsers löschen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
