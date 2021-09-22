---
title: Verwalten von Cookies und Benutzereinwilligungen zum Speichern von Benutzerdaten
description: Verstehen Sie, wie Cookies und die Benutzereinwilligungen verwendet werden, um Website-Besucher zu identifizieren.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036737"
---
# <a name="manage-cookies-and-user-consent"></a>Verwalten von Cookies und Benutzereinwilligungen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Die Funktion Kundenbindungserkenntnisse von Dynamics 365 Customer Insights verwendet Cookies und lokalen Speicher (`localStorage`) um Website-Besucher zu identifizieren.

Cookies sind kleine Dateien, in denen Informationen zur Interaktionen eines Benutzers mit der Website gespeichert werden. Sie werden in Webbrowsern gespeichert. Wenn Benutzer eine Website besuchen, für die Ihre Benutzer Cookies gespeichert haben, sendet der Browser diese Informationen an den Server, der Informationen zurückgibt, die für den Benutzer eindeutig sind. Dies ist die Technologie, mit der beispielsweise ausgewählte Artikel selbst dann in einem Online-Warenkorb verbleiben können, wenn ein Benutzer die Website verlässt.

## <a name="user-consent"></a>Benutzereinwilligung

Die [Datenschutz-Grundverordnung (DSGVO)](/dynamics365/get-started/gdpr/) ist eine Verordnung der Europäischen Union (EU), die vorschreibt, wie Organisationen mit der Privatsphäre und Sicherheit ihrer Benutzer umgehen sollen. Cookies speichern oder sammeln häufig „persönliche Daten“, z. B. einen Online-Bezeichner, die von der DSGVO abgedeckt werden. Wenn Ihr Unternehmen EU-Datensubjekte beschäftigt und/oder an diese verkauft, wirkt sich die DSGVO auf Sie aus. [Erfahren Sie mehr darüber, wie Microsoft Sie bei der Einhaltung der DSGVO unterstützen kann](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Damit das SDK für die Funktion Kundenbindungserkenntnisse Cookies oder andere vertrauliche Informationen speichern kann, müssen Sie angeben, ob Ihre Benutzer hierzu ihre Einwilligung gegeben haben. Dies geschieht bei der Initialisierung des SDK.

Wenn Sie angeben, dass keine Benutzereinwilligung vorliegt, speichert das SDK keine Daten und sendet keine Ereignisse, mit denen das Benutzerverhalten verfolgt werden kann. Alle zuvor gespeicherten Daten werden aus dem Browser gelöscht.

Wenn kein Wert für die Benutzereinwilligung angegeben ist, geht das SDK davon aus, dass der Benutzer eingewilligt hat. Das bedeutet, dass Daten erfasst werden, wenn Sie (als unser Kunde) im SDK keinen Wert für die Benutzereinwilligung angeben. Wenn Sie jedoch angeben, dass der Wert für die Benutzereinwilligung „true“ sein muss, werden keine Daten erfasst, wenn ein Benutzer die ausdrückliche Einwilligung ablehnt oder nicht erteilt.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Speicherung von Besucherdaten in der Funktion Kundenbindungserkenntnisse

### <a name="cookies"></a>Cookies

- _msei
    - Speichert die anonyme Benutzer-ID. Dieses Cookie wird in der Kundendomäne gesetzt und läuft nach 365 Tagen ab.

### <a name="local-storage"></a>Lokaler Speicher

Die Funktion Kundenbindungserkenntnisse nutzt auch den lokalen Speicher (`localStorage`), um nicht vertrauliche Daten nachzuverfolgen. Diese Daten werden vollständig im Browser selbst gespeichert, ohne dass Datenverkehr an oder von Ihren Servern gesendet wird.

- *EISession.Id* 
    - Speichert Informationen über die laufende Benutzersitzung, z. B. die Sitzungs-ID, wann sie gestartet wurde und wann sie abläuft.
- *EISession.Previous*
    - Speichert die URL der zuvor besuchten Seite in der aktuellen Sitzung.
    
Schlüssel im lokalen Speicher laufen nicht automatisch ab. Sie werden während der nächsten Sitzung vom SDK zurückgesetzt.

## <a name="deleting-cookies"></a>Löschen von Cookies

Ihre Kunden können Cookies und Schlüssel im lokalen Speicher jederzeit manuell über die Einstellungen ihres Browsers löschen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]