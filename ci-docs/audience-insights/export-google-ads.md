---
title: Customer Insights-Daten zu Google Ads exportieren
description: Lernen Sie, wie Sie die Verbindung zu Google Ads konfigurieren.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598246"
---
# <a name="connector-for-google-ads-preview"></a>Konnektor für Google Ads (Vorschau)

Exportieren Sie Segmente von vereinheitlichten Kundenprofilen in die Google Ads Zielgruppenliste und nutzen Sie diese für Werbung in der Google Suche, Gmail, YouTube und im Google Display-Netzwerk. 

## <a name="prerequisites"></a>Anforderungen

-   Sie haben ein [Google Ads-Konto](https://ads.google.com/) und die entsprechenden Anmeldeinformationen.
-   Es gibt bestehende Zielgruppen in Google Ads und die dazugehörigen IDs. Weitere Informationen finden Sie unter [Google Ads-Zielgruppen](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Sie haben [Konfigurierte Segmente](segments.md)
-   Vereinheitlichte Kundenprofile in den exportierten Segmenten enthalten Felder, die eine E-Mail-Adresse, einen Vornamen und einen Nachnamen darstellen

## <a name="connect-to-google-ads"></a>Mit Google Ads verbinden

1. Gehen Sie zu **Administrator** > **Exportziele**.

1. Unter **Google Ads**, wählen Sie **Einrichten**.

1. Geben Sie Ihrem Exportziel einen erkennbaren Namen im Feld **Anzeigename**.

1. Geben Sie Ihre **[Google Ads Kunden-ID](https://support.google.com/google-ads/answer/1704344)** ein.

1. Geben Sie Ihr **[Google Ads genehmigtes Entwickler-Token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** ein.

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Geben Sie Ihre **[Google Ads Zielgruppen-ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** ein und wählen Sie **Verbinden**, um die Verbindung zu Google Ads zu initialisieren.

1. Wählen Sie **Mit Google Ads authentifizieren** und geben Sie Ihre Google Ads Anmeldeinformationen an.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Bildschirmfoto exportieren für Google Ads-Verbindung":::

1. Wählen Sie **Weiter**, um die Konfiguration des Exports zu starten.

## <a name="configure-the-connector"></a>Konfigurieren Sie den Konnektor

1. Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt. Wiederholen Sie die gleichen Schritte für die Felder **Vorname** und **Nachname**.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten. Sie können insgesamt bis zu 1 Million Kundenprofile zu Google Ads exportieren.

1. Wählen Sie **Speichern** aus.

## <a name="export-the-data"></a>Exportieren der Daten

Sie könenn [Daten nach Bedarf exportieren](export-destinations.md). Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt. In Google Ads finden Sie Ihre Segmente jetzt unter [Google Ads Zielgruppen](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Bis zu 1 Million Profile pro Export zu Google Ads.
- Der Export zu Google Ads ist auf Segmente beschränkt.
- Das Exportieren von Segmenten mit insgesamt 1 Million Profilen kann aufgrund von Beschränkungen auf der Anbieterseite bis zu 5 Minuten dauern. 
- Der Abgleich in Google Ads kann bis zu 48 Stunden dauern.

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Google Ads aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Google Ads alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]