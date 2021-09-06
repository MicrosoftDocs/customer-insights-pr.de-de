---
title: Exportieren von Customer Insights-Daten nach LinkedIn Ads
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und einen Export nach LinkedIn Ads durchführen.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 2cfaa37fd0ac697f29665792bab27a925d8ea1eede0519d424524a7e5accbfeb
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034222"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Exportieren von Segmenten nach LinkedIn Ads (Vorschau)

Exportieren Sie Segmente einheitlicher Kundenprofilen nach LinkedIn Ads, um passende Zielgruppen zu erstellen. Verwenden Sie die passenden Zielgruppen für das Unternehmens- und das Kontakt-Targeting.

## <a name="prerequisites"></a>Anforderungen

-   Sie verfügen über ein [LinkedIn Campaign Manager-Konto](https://business.linkedin.com/marketing-solutions/ads) und entsprechende Administrator-Anmeldeinformationen.
-   Sie haben [Konfigurierte Segmente](segments.md) in Zielgruppen-Insights.
-   Kundenprofile in den exportierten Segmenten enthalten ein Feld mit einer E-Mail-Adresse.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Sie können bis zu 100.000 Profile pro Export nach LinkedIn Ads exportieren.
- Der Export nach LinkedIn Ads ist auf Segmente beschränkt.
- Das Exportieren von bis zu 100.000 Profilen nach LinkedIn Ads kann bis zu 10 Minuten dauern. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Einrichten der Verbindung mit LinkedIn Ads

1. Gehen Sie in Zielgruppenerkenntnissen zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und dann **LinkedIn Ads** aus, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, sind als Standard Administratoren ausgewählt. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie Ihre [LinkedIn Campaign Manager-Konto-ID](https://www.linkedin.com/help/lms/answer/a424270) an.

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Wählen Sie **Verbinden** aus, um die Verbindung zu Campaign Monitor zu initialisieren.

1. Wählen Sie **Mit LinkedIn authentifizieren** aus und geben Sie Ihre Administrator-Anmeldeinformationen für LinkedIn Campaign Manager an.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können einen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem LinkedIn Ads-Abschnitt aus. Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. Wählen Sie aus, ob Sie Daten für [Kontakt-Targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) oder [Unternehmens-Targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) auf LinkedIn exportieren möchten. 

1. Wählen Sie im Bereich **Datenabgleich** in Ihrem vereinheitlichten Kundenprofil das Feld aus, das die E-Mail-Adresse eines Kunden darstellt. Der Export nach LinkedIn Ads ist auf Segmente beschränkt.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten. Die passenden Zielgruppen in LinkedIn Campaign Manager werden automatisch mit dem Namen der Segmente erstellt, die Sie zum Exportieren ausgewählt haben. Jedes Segment führt zu einer separaten passenden Zielgruppe. 

1. Wählen Sie **Speichern** aus.

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt. Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten an LinkedIn Ads zu übertragen, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft überträgt diese Daten auf Ihre Anweisung. Sie sind jedoch dafür verantwortlich, dass LinkedIn Ads alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).

Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktion zu beenden.
