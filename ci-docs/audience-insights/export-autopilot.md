---
title: Exportieren von Customer Insights-Daten zu Autopilot
description: Lernen Sie, wie Sie die Verbindung zu Autopilot konfigurieren.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269237"
---
# <a name="connector-for-autopilot-preview"></a>Konnektor für Autopilot (Vorschau)

Exportieren Sie Segmente einheitlicher Kundenprofile in Autopilot und verwenden Sie sie für E-Mail-Marketing in Autopilot. 

## <a name="prerequisites"></a>Anforderungen

-   Sie haben ein [Autopilot-Konto](https://www.autopilothq.com/) und entsprechende Anmeldeinformationen für den Administrator.
-   Sie haben [Konfigurierte Segmente](segments.md) in Zielgruppen-Insights.
-   Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="connect-to-autopilot"></a>Mit AutoPilot verbinden

1. Gehen Sie zu **Administrator** > **Exportziele**.

1. Unter **Autopilot**, wählen Sie **Einrichten**.

1. Geben Sie Ihrem Exportziel einen erkennbaren Namen im Feld **Anzeigename**.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Konfigurationsbereich für die Autopilot-Verbindung.":::

1. Geben Sie Ihren **Autopilot-API-Schlüssel** [Autopilot-API-Schlüssel](https://autopilot.docs.apiary.io/#) ein.

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Wählen Sie **Verbinden**, um die Verbindung zu Autopilot zu initialisieren.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie **Weiter**, um die Konfiguration des Exports zu starten.

## <a name="configure-the-connector"></a>Konfigurieren Sie den Konnektor

1. Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt. Wiederholen Sie die gleichen Schritte für andere optionale Felder wie **Vorname**, **Nachname**.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten. Es wird dringend **empfohlen, nicht mehr als 100.000 Kundenprofile insgesamt** an Autopilot zu exportieren. 

1. Wählen Sie **Speichern** aus.

## <a name="export-the-data"></a>Exportieren der Daten

Sie könenn [Daten nach Bedarf exportieren](export-destinations.md). Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Sie können insgesamt bis zu 100.000 Profile zu Autopilot exportieren.
- Der Export zu Autopilot ist auf Segmente beschränkt.
- Das Exportieren von bis zu 100.000 Profilen an Autopilot kann bis zu einigen Stunden dauern. 
- Die Anzahl der Profile, die Sie zu Autopilot exportieren können, hängt von Ihrem Vertrag mit Autopilot ab und ist dort begrenzt.

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Autopilot aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Autopilot alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]