---
title: Exportieren von Customer Insights-Daten nach Microsoft Advertising
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und nach Microsoft Advertising exportieren.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124489"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Exportieren von Segmenten nach Microsoft Advertising (Vorschau)

Exportieren Sie Customer Insights-Segmente nach Microsoft Advertising, um Zielgruppen für Customer Match zu erstellen. Verwenden Sie diese Zielgruppen für Ihre Werbekampagnen.

## <a name="prerequisites"></a>Anforderungen

-   Ein [Microsoft Advertising-Konto](https://ads.microsoft.com/) und entsprechende Administrator-Anmeldeinformationen.
-   Sie haben die Nutzungsbedingungen für Customer Match akzeptiert. 
-   [Konfigurierte Segmente](segments.md) in Zielgruppenerkenntnissen.
-   Vereinheitlichte Kundenprofile in den exportierten Segmenten enthalten ein Feld mit einer E-Mail-Adresse.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Sie können bis zu 500.000 Profile pro Export nach Microsoft Advertising exportieren.
- Der Export nach Microsoft Advertising ist auf Segmente beschränkt.
- Das Exportieren von bis zu 500.000 Profilen nach Microsoft Advertising kann bis zu 10 Minuten dauern. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Einrichten der Verbindung mit Microsoft Advertising (Vorschau)

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und dann **Microsoft Advertising** aus, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Als Standard sind Administratoren ausgewählt. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Wählen Sie **Verbinden** aus, um die Verbindung zu Microsoft Advertising zu initialisieren.

1. Wählen Sie **Mit Microsoft Advertising authentifizieren** aus, und geben Sie Ihre Administratoranmeldeinformationen für Microsoft Advertising an.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Microsoft Advertising-Abschnitt aus. Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. Wählen Sie die zu exportierenden Segmente aus. Die Zielgruppen für Customer Match in Microsoft Advertising werden automatisch mit dem Namen der für den Export ausgewählten Segmente erstellt. Jedes Segment führt zu einer separaten Zielgruppe für Customer Match. 

1. Geben Sie Ihre **Kunden- und Konto-ID für Microsoft Advertising** ein. Sie finden die Kunden-ID (`cid`) und die Konto-ID (`aid`) in den Parametern der URL, wenn Sie bei Microsoft Advertising angemeldet sind.

1. Wählen Sie im Bereich **Datenabgleich** im Feld **E-Mail** in Ihrem vereinheitlichten Kundenprofil das Feld mit einer E-Mail-Adresse eines Kunden aus. Der Export nach Microsoft Advertising ist auf Segmente beschränkt.

1. Wählen Sie **Speichern** aus.

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt. Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten an Microsoft Advertising zu übertragen, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft überträgt diese Daten auf Ihre Anweisung. Sie sind jedoch dafür verantwortlich, dass Microsoft Advertising alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).

Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktion zu beenden.
