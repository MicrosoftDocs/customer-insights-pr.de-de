---
title: Exportieren Sie Customer Insights-Daten in Snapchat
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu Snapchat exportieren.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 171b8bf0f4a034c78e872b671602ae7653271da7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647143"
---
# <a name="export-segments-to-snapchat-preview"></a>Exportieren von Segmenten nach Snapchat (Vorschau)

Exportieren Sie Segmente einheitlicher Kundenprofile in Snapchat und verwenden Sie sie für Marketingaktivitäten. 

## <a name="prerequisites-for-a-connection"></a>Voraussetzungen für die Verbindung

-   Sie haben ein [Snapchat Business-Konto](https://business.snapchat.com/), ein [Snapchat Ads-Konto](https://ads.snapchat.com/) und entsprechende Administrator-Anmeldeinformationen.
-   Sie haben [Konfigurierte Segmente](segments.md) in Customer Insights.
-   Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Der Export nach Snapchat ist auf Segmente beschränkt.
- Der Export von Segmenten mit bis zu 1 Millionen Kundenprofilen nach Snapchat kann bis zu 15 Minuten dauern. 

## <a name="set-up-connection-to-snapchat"></a>Verbindung mit Snapchat einrichten

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und dann **Snapchat** aus, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Wählen Sie **Verbinden** aus, um die Verbindung zu Snapchat zu initialisieren.

1. Wählen Sie **Mit Snapchat authentifizieren** aus, und geben Sie Ihre Administratoranmeldeinformationen für Snapchat an. 

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Snapchat-Abschnitt aus. Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. Geben Sie die [**Snapchat-Zielgruppen-ID**](https://businesshelp.snapchat.com/s/article/custom-audiences) ein.

1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt. Der Export nach Snapchat ist auf Segmente beschränkt.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten. 

1. Wählen Sie **Speichern** aus.

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt. Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten an Snapchat zu übertragen, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft überträgt diese Daten auf Ihre Anweisung. Sie sind jedoch dafür verantwortlich, dass Snapchat alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).

Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.
