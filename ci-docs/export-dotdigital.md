---
title: Exportieren von Segmenten nach DotDigital (Vorschauversion)
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu DotDigital exportieren.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: af0cce4edb9d47247c79ae08491366349da98b1c
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081609"
---
# <a name="export-segments-to-dotdigital-preview"></a>Exportieren von Segmenten nach DotDigital (Vorschauversion)

Exportieren Sie Segmente von vereinheitlichten Kundenprofilen in DotDigital-Adressbücher und verwenden Sie diese für Kampagnen, E-Mail-Marketing und zum Aufbau von Kundensegmenten mit DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Voraussetzungen für die Verbindung

-   Sie haben ein [DotDigital-Konto](https://dotdigital.com/) und erstellten einen [API-Benutzer](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user). Sie müssen die API-Benutzeranmeldeinformationen verwenden, um eine Verbindung herzustellen
-   Es gibt bestehende Adressbücher in DotDigital und die entsprechenden IDs. Die ID ist in der URL zu finden, wenn Sie ein Adressbuch auswählen und öffnen. Weitere Informationen finden Sie unter [DotDigital Adressbücher](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Sie haben [Konfigurierte Segmente](segments.md) in Customer Insights.
-   Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Bis zu 1 Million Kundenprofile pro Export zu DotDigital.
- Das Exportieren zu DotDigital ist auf Segmente beschränkt.
- Der Export von Segmenten mit insgesamt 1 Million Kundenprofilen kann aufgrund von Einschränkungen auf Anbieterseite bis zu 3 Stunden dauern. 
- Die Anzahl der Kundenprofile, die Sie nach DotDigital exportieren können, hängt von Ihrem Vertrag mit DotDigital ab.

## <a name="set-up-connection-to-dotdigital"></a>Verbindung mit DotDigital einrichten

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und dann **DotDigital** aus, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie Ihren **DotDigital API-Benutzernamen und Ihr Kennwort** ein. 

1. Geben Sie Ihre **[DotDigital-Adressbuch-ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** ein.

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Wählen Sie **Verbinden**, um die Verbindung zu DotDigital zu initialisieren.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus. 

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem DotDigital-Abschnitt aus. Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.


1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt. Wiederholen Sie die gleichen Schritte für andere optionale Felder wie **Vorname**, **Nachname**, **Voller Name**, **Geschlecht** und **Postleitzahl**.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten. Sie können insgesamt bis zu 1 Million Kundenprofile zu DotDigital exportieren.

1. Wählen Sie **Speichern** aus.

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt. Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand). 
 
In DotDigital können Sie jetzt Ihre Segmente in [DotDigital Adressbüchern](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) finden.


## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an DotDigital aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass DotDigital alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.


[!INCLUDE [footer-include](includes/footer-banner.md)]
