---
title: Exportieren Sie Customer Insights-Daten in Constant Contact
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zum Constant Contact exportieren.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b25e4f11e21d059c2d867e925c0ae5635a87addc
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2021
ms.locfileid: "7619118"
---
# <a name="export-segments-to-constant-contact-preview"></a>Exportieren von Segmenten nach Constant Contact (Vorschau)

Exportieren Sie Segmente einheitlicher Kundenprofile in Constant Contact und verwenden Sie sie für Marketingaktivitäten. 

## <a name="prerequisites-for-a-connection"></a>Voraussetzungen für die Verbindung

-   Sie haben ein [Constant Contact-Konto](https://www.constantcontact.com/account-home) und entsprechende Administrator-Anmeldeinformationen.
-   Sie haben [Konfigurierte Segmente](segments.md) in Zielgruppen-Insights.
-   Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Sie können bis zu 1 Million Kundenprofile pro Export nach Constant Contact exportieren.
- Der Export nach Constant Contact ist auf Segmente beschränkt.
- Der Export von Segmenten mit bis zu 1 Millionen Kundenprofilen nach Constant Contact kann bis zu 1 Stunde dauern. 
- Die Anzahl der Kundenprofile, die Sie nach Constant Contact exportieren können, hängt von Ihrem Vertrag mit Constant Contact ab.

## <a name="set-up-connection-to-constant-contact"></a>Verbindung mit Constant Contact einrichten

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und dann **Constant Contact** aus, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Wählen Sie **Verbinden** aus, um die Verbindung zu Constant Contact zu initialisieren.

1. Wählen Sie **Mit Constant Contact authentifizieren** aus und geben Sie Ihre Administrator-Anmeldeinformationen für Constant Contact an. 

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Constant Contact-Abschnitt aus. Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. Geben Sie die [**ID der Constant Contact-Liste**](https://app.constantcontact.com/pages/contacts/ui#lists) ein. Öffnen Sie eine Liste in Constant Contact, um die Listen-ID in der URL zu finden.

1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt. Der Export nach Constant Contact ist auf Segmente beschränkt.

1. Optional können Sie Vorname und Nachname als zusätzliche Felder exportieren, um mehr personalisierte E-Mails zu erstellen. Wählen Sie **Attribut hinzufügen**, um diese Felder zuzuordnen.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten.

1. Wählen Sie **Speichern** aus.

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt. Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten an Constant Contact zu übertragen, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft überträgt diese Daten auf Ihre Anweisung. Sie sind jedoch dafür verantwortlich, dass Constant Contact alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).

Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.
