---
title: Customer Insights-Daten nach Facebook-Werbeanzeigenmanager exportieren (enthält Video)
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zum Facebook Ads Manager exportieren.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 781cf10e1bb5ddaf82d4a17c7a77e0c43c41a1c2
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226494"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Segmentliste zum Facebook Ads Manager exportieren (Vorschau)

Exportieren Sie Segmente einheitlicher Kundenprofile in den Facebook Anzeigenmanager zum Erstellen von Kampagnen auf Facebook und Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites-for-connection"></a>Voraussetzungen für die Verbindung

- Sie benötigen ein [**Facebook Ads Konto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), das ein [**Facebook Business-Konto**](https://business.facebook.com/) enthält.
- Sie müssen ein Administrator auf dem [**Facebook Ads-Konto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) sein.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Bis zu 10 Millionen Kundenprofile pro Export nach Facebook Anzeigenmanager.
- Der Export zum Facebook Ads Manager ist auf Segmente beschränkt.
- Erstellen oder aktualisieren Sie in Facebook nur benutzerdefinierte Zielgruppen vom Typ *Kundenliste*.
- Der Export von Segmenten mit insgesamt 10 Millionen Kundenprofilen kann bis zu 90 Minuten dauern.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Verbindung herstellen zum Facebook Ads Manager

Bevor Benutzer einen Export erstellen können, muss ein Administrator die Verbindung zum Dienst konfigurieren und den Mitwirkenden die Verwendung der Verbindung ermöglichen.

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und dann **Facebook Ads Manager** aus, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Mithilfe von Facebook Ads authentifizieren: 

   1. Wählen Sie **Forfahren mit Facebook**, um sich bei Ihrem Facebook Anzeigenkonto anzumelden.

   1. Erlauben Sie die Berechtigung **ads_management** nach der Authentifizierung mit Facebook.

   1. Wählen Sie das **Facebook Ads Konto**, mit dem Sie arbeiten möchten.

   1. Wählen Sie eine **Bestehende benutzerdefinierte Zielgruppe** aus der Dropdown-Liste oder erstellen Sie eine **Neue benutzerdefinierte Zielgruppe**. Weitere Informationen finden Sie unter [**Publikum in Facebook Anzeigenmanager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Sie können in Facebook nur benutzerdefinierte Zielgruppen des Typs *Kundenliste* mit diesem Export erstellen oder aktualisieren. In einigen Fällen sehen Sie benutzerdefinierte Zielgruppen verschiedener Typen in der Dropdown-Liste. Auswahl eines anderen Typs als *Kundenliste* führt zu einem fehlgeschlagenen Export. 

1. Überprüfen Sie **Datenschutz und Konformität** und wählen **Ich stimme zu** aus.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen. 

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Abschnitt **Facebook Ads Manager** aus. Wenn dieser Abschnittsname nicht angezeigt wird, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. Unter **Wählen Sie Ihr Schlüsselkennungsfeld** wählen Sie **E-Mail**, **Name und Adresse** oder **Telefon** aus und senden es an Facebook Anzeigenmanager. 

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.

1. Ordnen Sie die entsprechenden Attribute Ihrer einheitlichen Kundenentität der ausgewählten Schlüsselkennung zu.
   > [!TIP]
   > Die besten Chancen für eine Übereinstimmung ergeben sich, wenn Sie **E-Mail** als Schlüsselkennung auswählen. Das Hinzufügen zusätzlicher Bezeichner kann die Übereinstimmung verbessern.

1. Wählen Sie **Attribute hinzufügen**, um weitere Attribute zuzuordnen, die an Facebook Ads Manager gesendet werden sollen. Attribute vom Facebook Ads Manager werden den folgenden benutzerfreundlichen Namen zugeordnet: **FN** = **Vorname**, **LN** = **Nachname**, **FI** = **Anfangsbuchstabe des Vornamens**, **PHONE** = **Telefon**, **GEN** = **Geshclecht**, **DOB** = **Geburtsdatum**, **ST** = **Bundesland**, **CT** = **Stadt**, **ZIP** = **Postleitzahl**, **COUNTRY** = **Land/Region**

1. Wählen Sie die Segemente aus, die Sie exportieren möchten.

1. Wählen Sie **Speichern** aus.

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt. 

Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten an Facebook Ads Manager zu übertragen, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie persönlicher Daten. Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass die Facebook-Anzeigen alle Ihre Datenschutz- oder Sicherheitsverpflichtungen erfüllen. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
