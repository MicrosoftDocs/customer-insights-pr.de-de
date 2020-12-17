---
title: Customer Insights Daten nach Marketo exportieren
description: Lernen Sie, wie Sie die Verbindung zu Marketo konfigurieren.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570402"
---
# <a name="connector-for-marketo-preview"></a>Konnektor für Marketo (Vorschau)

Exportieren Sie Segmente von vereinheitlichten Kundenprofilen, um Kampagnen zu erstellen, E-Mail-Marketing zu betreiben und bestimmte Kundengruppen mit Marketo zu nutzen.

## <a name="prerequisites"></a>Anforderungen

-   Sie haben ein [Marketo-Konto](https://login.marketo.com/) und die entsprechenden Anmeldeinformationen.
-   Es gibt bestehende Listen in Marketo und die entsprechenden IDs. Weitere Informationen finden Sie unter [Marketo-Listen](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Sie haben [Konfigurierte Segmente](segments.md).
-   Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="connect-to-marketo"></a>Verbinden mit Marketo

1. Gehen Sie zu **Administrator** > **Exportziele**.

1. Unter **Marketo**, wählen Sie **Einrichten**.

1. Geben Sie Ihrem Exportziel einen erkennbaren Namen im Feld **Anzeigename**.

1. Geben Sie Ihre **[Marketo Client ID, Client secret und REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)** ein.

1. Geben Sie Ihre **[Marketo-Listen-ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** ein. 

1. Wählen Sie **Ich stimme zu**, um die **Datenschutz und Compliance** zu bestätigen und wählen Sie **Verbinden**, um die Verbindung zu Marketo zu initialisieren.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Bildschirmfoto für Marketo-Verbindung exportieren":::

1. Wählen Sie **Weiter**, um die Konfiguration des Exports zu starten.

## <a name="configure-the-connector"></a>Konfigurieren Sie den Konnektor

1. Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** das Feld in Ihrem vereinheitlichten Kundenprofil, das die E-Mail-Adresse eines Kunden darstellt. 

1. Optional können Sie **Vorname**, **Nachname**, **Stadt**, **Bundesland** und **Land/Region** als zusätzliche Felder exportieren, um stärker personalisierte E-Mails zu erstellen. Wählen Sie **Attribut hinzufügen**, um diese Felder zuzuordnen.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten. Sie können insgesamt bis zu 1 Mio. Kundenprofile zu Marketo exportieren.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Wählen Sie Felder und Segmente für den Export nach Marketo":::

1. Wählen Sie **Speichern** aus.

## <a name="export-the-data"></a>Exportieren der Daten

Sie könenn [Daten nach Bedarf exportieren](export-destinations.md). Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt. In Marketo finden Sie Ihre Segmente jetzt unter [Marketo-Listen](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Bis zu 1 Million Profile pro Export zu Marketo.
- Der Export zu Marketo ist auf Segmente beschränkt.
- Das Exportieren von Segmenten mit insgesamt 1 Million Profilen kann bis zu 3 Stunden dauern. 
- Die Anzahl der Profile, die Sie zu Marketo exportieren können, hängt von Ihrem Vertrag mit Marketo ab und ist dort begrenzt.

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Marketo aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird diese Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Marketo alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.
