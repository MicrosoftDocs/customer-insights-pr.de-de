---
title: Customer Insights-Daten nach DotDigital exportieren
description: Lernen Sie, wie Sie die Verbindung zu DotDigital konfigurieren.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269099"
---
# <a name="connector-for-dotdigital-preview"></a>Konnektor für DotDigital (Vorschau)

Exportieren Sie Segmente von vereinheitlichten Kundenprofilen in DotDigital-Adressbücher und verwenden Sie diese für Kampagnen, E-Mail-Marketing und zum Aufbau von Kundensegmenten mit DotDigital. 

## <a name="prerequisites"></a>Anforderungen

-   Sie haben ein [DotDigital-Konto](https://dotdigital.com/) und entsprechende Anmeldeinformationen für den Administrator.
-   Es gibt bestehende Adressbücher in DotDigital und die entsprechenden IDs. Die ID ist in der URL zu finden, wenn Sie ein Adressbuch auswählen und öffnen. Weitere Informationen finden Sie unter [DotDigital Adressbücher](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Sie haben [Konfigurierte Segmente](segments.md) in Zielgruppen-Insights.
-   Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="connect-to-dotdigital"></a>Verbinden mit DotDigital

1. Gehen Sie zu **Administrator** > **Exportziele**.

1. Wählen Sie unter **DotDigital** **Einrichten**.

1. Geben Sie Ihrem Exportziel einen erkennbaren Namen im Feld **Anzeigename**.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Konfigurationsbereich für DotDigital-Export.":::

1. Geben Sie Ihren **DotDigital-Benutzernamen und Ihr Kennwort** ein.

1. Geben Sie Ihre **[DotDigital-Adressbuch-ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** ein.

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Wählen Sie **Verbinden**, um die Verbindung zu DotDigital zu initialisieren.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie **Weiter**, um die Konfiguration des Exports zu starten.

## <a name="configure-the-connector"></a>Konfigurieren Sie den Konnektor

1. Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt. Wiederholen Sie die gleichen Schritte für andere optionale Felder wie **Vorname**, **Nachname**, **Voller Name**, **Geschlecht** und **Postleitzahl**.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten. Sie können insgesamt bis zu 1 Million Kundenprofile zu DotDigital exportieren.

1. Wählen Sie **Speichern** aus.

## <a name="export-the-data"></a>Exportieren der Daten

Sie könenn [Daten nach Bedarf exportieren](export-destinations.md). Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt. In DotDigital können Sie jetzt Ihre Segmente in [DotDigital Adressbüchern](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) finden.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Bis zu 1 Million Profile pro Export zu DotDigital.
- Das Exportieren zu DotDigital ist auf Segmente beschränkt.
- Das Exportieren von Segmenten mit insgesamt 1 Million Profilen kann aufgrund von Beschränkungen auf der Provider-Seite bis zu 3 Stunden dauern. 
- Die Anzahl der Profile, die Sie zu DotDigital exportieren können, ist abhängig und begrenzt von Ihrem Vertrag mit DotDigital.

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an DotDigital aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass DotDigital alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]