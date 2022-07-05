---
title: Segmente nach Marketo exportieren (Vorschauversion)
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu Marketo exportieren.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8cd24cf436bd5fdfd4ec3834d35baa1495e37ca4
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053204"
---
# <a name="export-segments-to-marketo-preview"></a>Segmente nach Marketo exportieren (Vorschauversion)

Exportieren Sie Segmente von vereinheitlichten Kundenprofilen, um Kampagnen zu erstellen, E-Mail-Marketing zu betreiben und bestimmte Kundengruppen mit Marketo zu nutzen.

## <a name="prerequisites-for-connection"></a>Voraussetzungen für die Verbindung

-   Sie haben ein [Marketo-Konto](https://login.marketo.com/) und die entsprechenden Anmeldeinformationen.
-   Es gibt bestehende Listen in Marketo und die entsprechenden IDs. Weitere Informationen finden Sie unter [Marketo-Listen](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Sie haben [Konfigurierte Segmente](segments.md).
-   Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Bis zu 1 Million Kundenprofile pro Export zu Marketo.
- Der Export zu Marketo ist auf Segmente beschränkt.
- Der Export von Segmenten mit insgesamt 1 Million Kundenprofilen kann bis zu drei Stunden dauern. 
- Die Anzahl der Kundenprofile, die Sie nach Marketo exportieren können, hängt von Ihrem Vertrag mit Marketo ab.

## <a name="set-up-connection-to-marketo"></a>Richten Sie die Verbindung mit Marketo ein

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und dann **Marketo** aus, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie Ihre **[Marketo Client ID, Client secret und REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)** ein. Der REST Endpunkt Hostname ist nur der Hostname ohne `https://`. Beispiel: `xyz-abc-123.mktorest.com`. 

1. Wählen Sie **Ich stimme zu**, um die **Datenschutz und Compliance** zu bestätigen und wählen Sie **Verbinden**, um die Verbindung zu Marketo zu initialisieren.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Marketo-Abschnitt aus. Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. Geben Sie Ihre **[Marketo-Listen-ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** ein. Die Listen-ID ist ein rein numerischer Wert. Wenn Ihre Marketo-Listen-ID beispielsweise ST12345A7 lautet, entfernen Sie das Zeichen vor und nach den Ziffern und geben Sie `12345` ein. 

1. In dem Abschnitt **Datenabgleich** wählen Sie mindestens ein Feld aus, das die E-Mail-Adresse eines Kunden oder die Marketo-ID eines Kunden darstellt. 

1. Optional können Sie **Vorname**, **Nachname**, **Stadt**, **Bundesland** und **Land / Region** exportieren, um personalisiertere E-Mails zu erstellen. Wählen Sie **Attribut hinzufügen**, um diese Felder zuzuordnen.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten. Sie können insgesamt bis zu 1 Mio. Kundenprofile zu Marketo exportieren.

1. Wählen Sie **Speichern** aus.

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt. Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand). In Marketo finden Sie Ihre Segmente jetzt unter [Marketo-Listen](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Marketo aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird diese Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Marketo alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.


[!INCLUDE [footer-include](includes/footer-banner.md)]
