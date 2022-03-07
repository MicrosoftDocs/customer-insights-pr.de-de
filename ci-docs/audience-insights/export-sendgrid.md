---
title: Exportieren von Customer Insights-Daten zu SendGrid
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu SendGrid exportieren.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759764"
---
# <a name="export-segments-to-sendgrid-preview"></a>Segmente nach SendGrid exportieren (Vorschau)

Exportieren Sie Segmente einheitlicher Kundenprofile in SendGrid-Kontaktlisten und verwenden Sie sie für Kampagnen und E-Mail-Marketing in SendGrid. 

## <a name="prerequisites-for-a-connection"></a>Voraussetzungen für die Verbindung

-   Sie haben ein [SendGrid-Konto](https://sendgrid.com/) und die entsprechenden Anmeldeinformationen.
-   Es gibt bestehende Kontaktlisten in SendGrid und die entsprechenden IDs. Weitere Informationen finden Sie unter [SendGrid – Kontakte verwalten](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Sie haben [Konfigurierte Segmente](segments.md) in Zielgruppen-Insights.
-   Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Insgesamt bis zu 100.000 Profile an SendGrid.
- Der Export zu SendGrid ist auf Segmente beschränkt.
- Das Exportieren von bis zu 100.000 Profilen an SendGrid kann bis zu einigen Stunden dauern. 
- Die Anzahl der Profile, die Sie zu SendGrid exportieren können, hängt von Ihrem Vertrag mit SendGrid ab und ist dort begrenzt.

## <a name="set-up-connection-to-sendgrid"></a>Verbindung mit SendGrid einrichten

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und dann **SendGrid** aus, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie Ihren **SendGrid-API-Schlüssel** [SendGrid-API-Schlüssel](https://sendgrid.com/docs/ui/account-and-settings/api-keys/) ein.

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Wählen Sie **Verbinden**, um die Verbindung zu SendGrid zu initialisieren.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem SendGrid-Abschnitt aus. Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. Geben Sie Ihre **[SendGrid-Listen-ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** ein.

1. Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt. Wiederholen Sie die gleichen Schritte für andere optionale Felder wie **Vorname**, **Nachname**, **Land/Region**, **Bundesland/Kanton**, **Stadt** und **Postleitzahl**.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten. Es wird dringend **empfohlen, nicht mehr als 100.000 Kundenprofile insgesamt** an SendGrid zu exportieren. 

1. Wählen Sie **Speichern** aus.

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt. Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an SendGrid aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass SendGrid alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]