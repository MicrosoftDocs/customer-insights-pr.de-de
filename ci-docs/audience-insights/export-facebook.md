---
title: Customer Insights-Daten in den Facebook Ads Manager exportieren
description: Erfahren Sie, wie Sie die Verbindung zu einem Facebook Anzeigen-Manager konfigurieren.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643682"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Konnektor für Facebook Anzeigenmanager (Vorschau)

Exportieren Sie Segmente einheitlicher Kundenprofile in den Facebook Anzeigenmanager zum Erstellen von Kampagnen auf Facebook und Instagram.

## <a name="prerequisites"></a>Voraussetzungen

- Sie müssen ein [**Facebook Anzeigenkonto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) haben, das ein [**Facebook Geschäftskonto**](https://business.facebook.com/) enthält.
- Sie müssen ein Administrator auf dem [**Facebook Ad-Konto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) sein.

## <a name="connect-to-facebook-ads-manager"></a>Mit Facebook Anzeigenmanager verbinden

1. Gehen Sie zu **Administrator** > **Exportziele**.

1. Unter **Facebook Anzeigenmanager** wählen Sie **Konfiguration**.

1. Geben Sie Ihrem Exportziel einen erkennbaren Namen im Feld **Anzeigename**.

1. Wählen Sie **Weitermachen mit Facebook**, um sich bei Ihrem Facebook Anzeigenkonto anzumelden.

1. Erlauben Sie die Berechtigung **ads_management** nach der Authentifizierung mit Facebook.

1. Wählen Sie das **Facebook Ads Konto**, mit dem Sie arbeiten möchten.

1. Wählen Sie **vorhandenes benutzerdefiniertes Publikum** aus der Dropdown-Liste au oder erstellen Sie ein **Neues benutzerdefiniertes Publikum**. Weitere Informationen finden Sie unter [**Publikum in Facebook Anzeigenmanager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Wählen Sie **Weiter**, um die Konfiguration des Exports zu starten.

## <a name="configure-the-connector"></a>Konfigurieren Sie den Konnektor

1. Unter **Wählen Sie Ihr Schlüsselkennungsfeld** wählen Sie **E-Mail**, **Name und Adresse** oder **Telefon** aus und senden es an Facebook Anzeigenmanager.

1. Ordnen Sie die entsprechenden Attribute Ihrer einheitlichen Kundenentität der ausgewählten Schlüsselkennung zu.
   > [TIPP] Die besten Chancen für eine Übereinstimmung ergeben sich, wenn Sie **E-Mail** als Schlüsselkennung auswählen. Das Hinzufügen zusätzlicher Bezeichner kann die Übereinstimmung verbessern.

1. Wählen Sie **Attribute hinzufügen**, um zusätzliche Attribute zuzuordnen, die an den Facebook Anzeigenmanager gesendet werden sollen. Attribute vom Facebook Anzeigenmanager wird den folgenden benutzerfreundlichen Namen zugeordnet: **VN** = **Vorname**, **NN** = **Nachname**, **EI** = **Erste Initiale**, **TELEFON** = **Telefon**, **GEN** = **Geschlecht**, **GEB** = **Geburtsdatum**, **KT** = **Kanton**, **ORT** = **Stadt**, **PLZ** = **Postleitzahl**, **LAND** = **Land/Region**

1. Wählen Sie die Segemente aus, die Sie exportieren möchten.

1. Wählen Sie **Speichern** aus.

## <a name="export-the-data"></a>Exportieren der Daten

Sie könenn [Daten nach Bedarf exportieren](export-destinations.md). Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten an Facebook Ads Manager zu übertragen, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie persönlicher Daten. Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass die Facebook-Anzeigen alle Ihre Datenschutz- oder Sicherheitsverpflichtungen erfüllen. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.
