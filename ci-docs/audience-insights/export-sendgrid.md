---
title: Exportieren von Customer Insights-Daten zu SendGrid
description: Lernen Sie, wie Sie die Verbindung zu SendGrid konfigurieren.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597280"
---
# <a name="connector-for-sendgrid-preview"></a>Konnektor für SendGrid (Vorschau)

Exportieren Sie Segmente einheitlicher Kundenprofile in SendGrid-Kontaktlisten und verwenden Sie sie für Kampagnen und E-Mail-Marketing in SendGrid. 

## <a name="prerequisites"></a>Anforderungen

-   Sie haben ein [SendGrid-Konto](https://sendgrid.com/) und die entsprechenden Anmeldeinformationen.
-   Es gibt bestehende Kontaktlisten in SendGrid und die entsprechenden IDs. Weitere Informationen finden Sie unter [SendGrid – Kontakte verwalten](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Sie haben [Konfigurierte Segmente](segments.md) in Zielgruppen-Insights.
-   Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="connect-to-sendgrid"></a>Herstellen einer Verbindung mit SendGrid

1. Gehen Sie zu **Administrator** > **Exportziele**.

1. Unter **SendGrid** wählen Sie **Einrichten**.

1. Geben Sie Ihrem Exportziel einen erkennbaren Namen im Feld **Anzeigename**.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGrid-Exportkonfigurationsbereich.":::

1. Geben Sie Ihren **SendGrid-API-Schlüssel** [SendGrid-API-Schlüssel](https://sendgrid.com/docs/ui/account-and-settings/api-keys/) ein.

1. Geben Sie Ihre **[SendGrid-Listen-ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** ein.

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Wählen Sie **Verbinden**, um die Verbindung zu SendGrid zu initialisieren.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie **Weiter**, um die Konfiguration des Exports zu starten.

## <a name="configure-the-connector"></a>Konfigurieren Sie den Konnektor

1. Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt. Wiederholen Sie die gleichen Schritte für andere optionale Felder wie **Vorname**, **Nachname**, **Land/Region**, **Bundesland/Kanton**, **Stadt** und **Postleitzahl**.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten. Es wird dringend **empfohlen, nicht mehr als 100.000 Kundenprofile insgesamt** an SendGrid zu exportieren. 

1. Wählen Sie **Speichern** aus.

## <a name="export-the-data"></a>Exportieren der Daten

Sie könenn [Daten nach Bedarf exportieren](export-destinations.md). Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Insgesamt bis zu 100.000 Profile an SendGrid.
- Der Export zu SendGrid ist auf Segmente beschränkt.
- Das Exportieren von bis zu 100.000 Profilen an SendGrid kann bis zu einigen Stunden dauern. 
- Die Anzahl der Profile, die Sie zu SendGrid exportieren können, hängt von Ihrem Vertrag mit SendGrid ab und ist dort begrenzt.

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an SendGrid aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass SendGrid alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]