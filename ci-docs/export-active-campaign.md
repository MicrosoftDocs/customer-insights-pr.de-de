---
title: Exportieren Sie Customer Insights-Daten nach ActiveCampaign
description: Erfahren Sie, wie Sie die Verbindung und den Export zu ActiveCampaign konfigurieren.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d15b9bf7383d06070ac92d7a729fc6e6e00c9d7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646211"
---
# <a name="export-segments-to-activecampaign-preview"></a>Segmente nach ActiveCampaign exportieren (Vorschau)

Exportieren Sie Segmente von einheitlichen Kundenprofilen nach ActiveCampaign und verwenden Sie sie für Marketingaktivitäten.

## <a name="prerequisites"></a>Anforderungen

-   Sie haben ein [ActiveCampaign-Konto](https://www.activecampaign.com/) und entsprechende Administrator-Anmeldeinformationen.
-   Sie haben [Konfigurierte Segmente](segments.md) in Customer Insights.
-   Vereinheitlichte Kundenprofile in den exportierten Segmenten enthalten ein Feld mit einer E-Mail-Adresse.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Sie können bis zu 1 Million Kundenprofile pro Export zu ActiveCampaign exportieren und die Fertigstellung kann bis zu 90 Stunden dauern.
- Der Export nach ActiveCampaign ist auf Segmente beschränkt.
- Die Anzahl der Kundenprofile, die Sie nach ActiveCampaign exportieren können, hängt von Ihrem Vertrag mit ActiveCampaign ab.

## <a name="set-up-connection-to-activecampaign"></a>Richten Sie die Verbindung mit ActiveCampaign ein.

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **ActiveCampaign**, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie Ihren [ActiveCampaign API-Schlüssel und REST Endpunkt Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) ein. Der REST Endpunkt Hostname ist nur der Hostname ohne https://. 

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Wählen Sie **Verbinden**, um die Verbindungsauswahl zu ActiveCampaign zu bestätigen.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können einen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.

1. In dem Feld **Anschluss für Export** wählen Sie im Bereich ActiveCampaign eine Verbindung aus. Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. Geben Sie Ihre [**ActiveCampaign Listen-ID ein**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt. Es ist erforderlcih, Segmente nach ActiveCampaign zu exportieren. Optional können Sie Vorname, Nachname, und Telefon exportieren, um personalisiertere E-Mails zu erstellen. Wählen Sie Attribut hinzufügen, um diese Felder zuzuordnen.

1. Wählen Sie **Speichern** aus.

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt. Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten an ActiveCampaign zu übermitteln , erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogene Daten. Microsoft überträgt solche Daten auf Ihre Anweisung, aber Sie sind dafür verantwortlich, dass ActiveCampaign alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).

Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.
