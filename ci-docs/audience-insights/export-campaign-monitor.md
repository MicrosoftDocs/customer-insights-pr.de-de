---
title: Exportieren Sie Customer Insights-Daten in Campaign Monitor
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zum Campaign Monitor exportieren.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 063de14c4ffd51b3afd89786606d7b37626695dc
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618980"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Exportieren von Segmenten nach Campaign Monitor (Vorschau)

Exportieren Sie Segmente einheitlicher Kundenprofile in Campaign Monitor und verwenden Sie sie für Marketingaktivitäten.

## <a name="prerequisites"></a>Anforderungen

-   Sie haben ein [Campaign Monitor-Konto](https://www.campaignmonitor.com/) und entsprechende Administrator-Anmeldeinformationen.
-   Sie haben [Konfigurierte Segmente](segments.md) in Zielgruppen-Insights.
-   Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Sie können bis zu 1 Million Kundenprofile pro Export nach Campaign Monitor exportieren.
- Der Export nach Campaign Monitor ist auf Segmente beschränkt.
- Der Export von Segmenten mit bis zu 1 Millionen Kundenprofilen nach Campaign Monitor kann bis zu 20 Minuten dauern. 
- Die Anzahl der Kundenprofile, die Sie nach Campaign Monitor exportieren können, hängt von Ihrem Vertrag mit Campaign Monitor ab.

## <a name="set-up-connection-to-campaign-monitor"></a>Verbindung mit Campaign Monitor einrichten

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und dann **Campaign Monitor** aus, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Wählen Sie **Verbinden** aus, um die Verbindung zu Campaign Monitor zu initialisieren.

1. Wählen Sie **Mit Campaign Monitor authentifizieren** aus, und geben Sie Ihre Administratoranmeldeinformationen für Campaign Monitor an.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Campaign Monitor-Abschnitt aus. Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. Geben Sie Ihre [**Campaign Monitor-Listen-ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id) ein.    
   [Generieren Sie den API-Schlüssel](https://www.campaignmonitor.com/api/getting-started/) über die **Kontoeinstellungen** in Campaign Monitor zuerst, um die API-Listen-ID anzuzeigen.  

1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt. Der Export nach Campaign Monitor ist auf Segmente beschränkt.

1. Wählen Sie **Speichern** aus.

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt. Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten an Campaign Monitor zu übertragen, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft überträgt diese Daten auf Ihre Anweisung. Sie sind jedoch dafür verantwortlich, dass Campaign Monitor alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).

Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.
