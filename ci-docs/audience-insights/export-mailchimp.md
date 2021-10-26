---
title: Exportieren von Customer Insights-Daten zu Mailchimp
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu Mailchimp exportieren.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 94a9fead56ce8c40b35d4eb41ebdc0d672798dce
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618612"
---
# <a name="export-segments-to-mailchimp-preview"></a>Exportieren von Segmenten nach Mailchimp (Vorschau)

Exportieren Sie Segmente von vereinheitlichten Kundenprofilen nach Mailchimp, um Newsletter und E-Mail-Kampagnen zu erstellen.

## <a name="prerequisites-for-connection"></a>Voraussetzungen für die Verbindung

-   Sie haben ein [Mailchimp-Konto](https://mailchimp.com/) und die entsprechenden Anmeldeinformationen.
-   Es gibt bestehende Zielgruppen in Mailchimp und die dazugehörigen IDs. Weitere Informationen finden Sie unter [Mailchimp-Zielgruppen](https://mailchimp.com/help/create-audience/).
-   Sie haben [Konfigurierte Segmente](segments.md)
-   Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Bis zu 1 Million Kundenprofile pro Export zu Mailchimp.
- Der Export zu Mailchimp ist auf Segmente beschränkt.
- Der Export von Segmenten mit 1 Million Kundenprofilen kann bis zu drei Stunden dauern. 
- Die Anzahl der Kundenprofile, die Sie nach Mailchimp exportieren können, hängt von Ihrem Vertrag mit Mailchimp ab.

## <a name="set-up-connection-to-mailchimp"></a>Verbindung mit Mailchimp einrichten

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Mailchimp**, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Wählen Sie **Verbinden** aus, um die Verbindung zu Mailchimp zu initialisieren.

1. Wählen Sie **Mit Mailchimp authentifizieren** und geben Sie Ihre Mailchimp Anmeldeinformationen an.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus. 

## <a name="configure-the-connector"></a>Den Konnektor konfigurieren

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten**> **Exporte**.

1. Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Mailchimp-Abschnitt aus. Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. Geben Sie Ihre **[Mailchimp-Zielgruppen-ID](https://mailchimp.com/help/find-audience-id/)** ein

1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt. 

1. Optional können Sie **Vorname** und **Nachname** exportieren, um personalisiertere E-Mails zu erstellen. Wählen Sie **Attribut hinzufügen**, um diese Felder zuzuordnen.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten. Sie können insgesamt bis zu 1 Mio. Kundenprofile zu Mailchimp exportieren.

1. Wählen Sie **Speichern** aus.

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt. Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Mailchimp aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird diese Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Mailchimp alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
