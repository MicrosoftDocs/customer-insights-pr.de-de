---
title: Segmente nach Sendinblue exportieren (Vorschauversion)
description: Erfahren Sie, wie Sie die Verbindung und den Export zu Sendinblue konfigurieren.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f6550b5c57866702631b4c294bb059279461bd6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081688"
---
# <a name="export-segments-to-sendinblue-preview"></a>Segmente nach Sendinblue exportieren (Vorschauversion)

Segmente von einheitlichen Kundenprofilen exportieren, um Kampagnen zu generieren, E-Mail-Marketing bereitzustellen und spezifische Kundengruppen mit Sendinblue zu nutzen.

## <a name="prerequisites-for-connection"></a>Voraussetzungen für die Verbindung

-   Sie haben ein [Sendinblue-Konto](https://www.sendinblue.com/) und entsprechende Administrator-Anmeldeinformationen.
-   Es gibt existierende Listen in Sendinblue und die entsprechenden IDs.
-   Sie haben [Konfigurierte Segmente](segments.md).
-   Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Bis zu 1 Million Kundenprofile pro Export zu Sendinblue.
- Der Export nach Sendinblue ist auf Segmente beschränkt.
- Der Export von Segmenten mit insgesamt 1 Million Kundenprofilen kann bis zu 90 Minuten dauern. 
- Die Anzahl der Kundenprofile, die Sie nach Sendinblue exportieren können, hängt von Ihrem Vertrag mit Sendinblue ab.

## <a name="set-up-connection-to-sendinblue"></a>Verbindung zu Sendinblue einrichten

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Sendinblue**, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie Ihren **[SendinbBlue API-Schlüssel ein](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Wählen Sie **Ich stimme zu**, um die **Privacy- und Datenschutzgesetze und Einhaltung** zu bestätigen und wählen Sie **Verbinden**, um die Verbindung zu Sendinblue zu initialisieren.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.

1. In dem Feld **Anschluss für Export** wählen Sie im Bereich Sendinblue eine Verbindung aus. Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. Geben Sie Ihre **SendinbBlue Listen-ID** ein 

1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt. 

1. Optional können Sie **Vorname**, **Nachname**, und **Telefon** exportieren, um personalisiertere E-Mails zu erstellen. Wählen Sie **Attribut hinzufügen**, um diese Felder zuzuordnen.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten. 

1. Wählen Sie **Speichern** aus.

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt. Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten an Sendinblue zu übermitteln , erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogene Daten. Microsoft überträgt solche Daten auf Ihre Anweisung, aber Sie sind dafür verantwortlich, dass Sendinblue alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.


[!INCLUDE [footer-include](includes/footer-banner.md)]
