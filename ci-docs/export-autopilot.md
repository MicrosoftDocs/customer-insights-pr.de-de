---
title: Exportieren von Customer Insights-Daten zu Autopilot
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu Autopilot exportieren.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01fb04cd1f0acfee1fcc9243269f967942580891
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646230"
---
# <a name="export-segments-to-autopilot-preview"></a>Segmente nach Autopilot exportieren (Vorschau)

Exportieren Sie Segmente einheitlicher Kundenprofile in Autopilot und verwenden Sie sie für E-Mail-Marketing in Autopilot. 

## <a name="prerequisites-for-a-connection"></a>Voraussetzungen für die Verbindung

-   Sie haben ein [Autopilot-Konto](https://www.autopilothq.com/) und entsprechende Anmeldeinformationen für den Administrator.
-   Sie haben [Konfigurierte Segmente](segments.md) in Customer Insights.
-   Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Sie können bis zu 100'000 Kundenprofile pro Export nach Autopilot exportieren.
- Der Export zu Autopilot ist auf Segmente beschränkt.
- Der Export von bis zu 100'000 Kundenprofilen nach Autopilot kann bis zu einigen Stunden dauern. 
- Die Anzahl der Kundenprofile, die Sie nach Autopilot exportieren können, hängt von Ihrem Vertrag mit Autopilot ab.

## <a name="set-up-connection-to-autopilot"></a>Richten Sie die Verbindung mit Autopilot ein

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und dann **Autopilot** aus, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie Ihren [Autopilot-API-Schlüssel](https://autopilot.docs.apiary.io/#) ein.

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Wählen Sie **Verbinden**, um die Verbindung zu Autopilot zu initialisieren.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Autopilot-Abschnitt aus. Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt. Wiederholen Sie die gleichen Schritte für andere optionale Felder wie **Vorname**, **Nachname**.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten. Es wird dringend **empfohlen, nicht mehr als 100.000 Kundenprofile insgesamt** an Autopilot zu exportieren. 

1. Wählen Sie **Speichern** aus.

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt. Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Autopilot aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Autopilot alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.


[!INCLUDE [footer-include](includes/footer-banner.md)]
