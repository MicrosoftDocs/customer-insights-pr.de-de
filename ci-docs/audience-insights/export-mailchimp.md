---
title: Exportieren von Customer Insights-Daten zu Mailchimp
description: Lernen Sie, wie Sie die Verbindung zu Mailchimp konfigurieren.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: edff494f6edf26a8b641cb1d788a715389ddb346
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405756"
---
# <a name="connector-for-mailchimp-preview"></a>Konnektor für Mailchimp (Vorschau)

Exportieren Sie Segmente von vereinheitlichten Kundenprofilen nach Mailchimp, um Newsletter und E-Mail-Kampagnen zu erstellen.

## <a name="prerequisites"></a>Anforderungen

-   Sie haben ein [Mailchimp-Konto](https://mailchimp.com/) und die entsprechenden Anmeldeinformationen.
-   Es gibt bestehende Zielgruppen in Mailchimp und die dazugehörigen IDs. Weitere Informationen finden Sie unter [Mailchimp-Zielgruppen](https://mailchimp.com/help/create-audience/).
-   Sie haben [Konfigurierte Segmente](segments.md)
-   Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="connect-to-mailchimp"></a>Mit Mailchimp verbinden

1. Gehen Sie zu **Administrator** > **Exportziele**.

1. Unter **Mailchimp**, wählen Sie **Einrichten**.

1. Geben Sie Ihrem Exportziel einen erkennbaren Namen im Feld **Anzeigename**.

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Geben Sie Ihre **[Mailchimp Zielgruppen-ID](https://mailchimp.com/help/find-audience-id/)** ein und wählen Sie **Verbinden**, um die Verbindung zu Mailchimp zu initialisieren.

1. Wählen Sie **Mit Mailchimp authentifizieren** und geben Sie Ihre Mailchimp Anmeldeinformationen an.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Export-Screenshot für Mailchimp-Verbindung":::

1. Wählen Sie **Weiter**, um die Konfiguration des Exports zu starten.

## <a name="configure-the-connector"></a>Konfigurieren Sie den Konnektor

1. Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt. 

1. Optional können Sie **Vorname** und **Nachname** als zusätzliche Felder exportieren, um mehr personalisierte E-Mails zu erstellen. Wählen Sie **Attribut hinzufügen**, um diese Felder zuzuordnen.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten. Sie können insgesamt bis zu 1 Mio. Kundenprofile zu Mailchimp exportieren.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Wählen Sie Felder und Segmente für den Export nach Mailchimp":::

1. Wählen Sie **Speichern** aus.

## <a name="export-the-data"></a>Exportieren der Daten

Sie könenn [Daten nach Bedarf exportieren](export-destinations.md). Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt. In Mailchimp finden Sie Ihre Segmente jetzt unter [Mailchimp Zielgruppen](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Bis zu 1 Million Profile pro Export zu Mailchimp.
- Der Export zu Mailchimp ist auf Segmente beschränkt.
- Der Export von Segmenten mit insgesamt 1 Million Profilen kann aufgrund von Beschränkungen auf der Anbieterseite bis zu drei Stunden dauern. 
- Die Anzahl der Profile, die Sie zu Mailchimp exportieren können, hängt von Ihrem Vertrag mit Mailchimp ab und ist dort begrenzt.

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Mailchimp aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird diese Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Mailchimp alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.
