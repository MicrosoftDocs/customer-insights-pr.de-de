---
title: Customer Insights-Daten zu Google Ads exportieren
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu Google Ads exportieren.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7a85237f7aff564d6b540b2c11553a52f875fac4
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523799"
---
# <a name="export-segments-to-google-ads-preview"></a>Segmente in Google Ads exportieren (Vorschau)

Exportieren Sie Segmente von einheitlichen Kundenprofilen in eine Google Ads Publikum-Liste und verwenden Sie sie, um in der Google-Suche, in Gmail, YouTube, und im Google Display-Netzwerk zu werben. 


## <a name="prerequisites-for-connection"></a>Voraussetzungen für die Verbindung

-   Sie haben ein [Google Ads-Konto](https://ads.google.com/) und die entsprechenden Anmeldeinformationen.
-   Sie erfüllen die Anforderungen der [Kunden-Übereinstimmungs-Richtlinie](https://support.google.com/adspolicy/answer/6299717).
-   Sie erfüllen die Anforderungen der [Remarketing-Listengrößen](https://support.google.com/google-ads/answer/7558048).
-   Sie haben [Konfigurierte Segmente](segments.md).
-   Einheitliche Kundenprofile in den exportierten Segmenten enthalten Felder, die eine E-Mail-Adresse, Telefonnummer, mobile Werbe-ID, Drittanbieter-Benutzer-ID oder Adresse darstellen.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Der Export zu Google Ads ist auf Segmente beschränkt.
- Der Export von Segmenten mit insgesamt 1 Million Kundenprofilen kann aufgrund von Einschränkungen auf Anbieterseite bis zu 30 Minuten dauern. 
- Der Abgleich in Google Ads kann bis zu 48 Stunden dauern.

## <a name="set-up-connection-to-google-ads"></a>Verbindung mit Google Ads einrichten

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und dann **Google Ads** aus, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie Ihre **[Google Ads Kunden-ID](https://support.google.com/google-ads/answer/1704344)** ein.

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Wählen Sie **Mit Google Ads authentifizieren** und geben Sie Ihre Google Ads Anmeldeinformationen an.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus. 

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Google Ads-Abschnitt aus. Wenn dieser Abschnittsname nicht angezeigt wird, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. Wenn Sie ein neues Publikum erstellen möchten, lassen Sie das Feld Google Zielgruppen-ID leer. Wir erstellen automatisch ein neues Publikum in Ihrem Google Ads-Konto und verwenden den Namen des exportierten Segments. Wenn Sie eine vorhandene Google Ads Zielgruppe aktualisieren möchten, geben Sie Ihre [Google Ads Zielgruppen-ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.) ein

1. In dem Abschnitt **Datenabgleich** wählen Sie im Abschnitt ein oder mehrere Datenfelder zum Exportieren aus und wählen Sie das Feld aus, das die entsprechenden Datenfelder in Customer Insights darstellt.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten. 

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt. 

Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Google Ads aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Google Ads alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
