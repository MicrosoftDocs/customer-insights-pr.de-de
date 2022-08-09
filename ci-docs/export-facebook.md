---
title: Segmente exportieren zu Facebook Werbeanzeigenmanager (Vorschauversion) (enthält Video)
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zum Facebook Ads Manager exportieren.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01be1a075db0da05dc5536aea8a33093f9a2ea13
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195013"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Exportieren von Segmenten zu Facebook-Werbeanzeigenmanager (Vorschauversion)

Exportieren Sie Segmente einheitlicher Kundenprofile in den Facebook Anzeigenmanager zum Erstellen von Kampagnen auf Facebook und Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Anforderungen

- Ein [Facebook Ads Konto](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), das einen [Facebook Business-Konto](https://business.facebook.com/) umfasst.
- Administratorrechte für [Facebook Ads-Konto](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Bis zu 10 Million Kundenprofile pro Export zu Facebook Ads Manager exportieren und die Fertigstellung kann bis zu 90 Minuten dauern.
- Nur Segmente.
- Facebook *Kundenliste* geben Sie nur [benutzerdefinierte Zielgruppen](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) ein.
  > [!NOTE]
  > In einigen Fällen sehen Sie möglicherweise benutzerdefinierte Zielgruppen verschiedener Typen in der Dropdown-Liste. Auswahl eines anderen Typs als *Kundenliste* führt zu einem fehlgeschlagenen Export.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Verbindung herstellen zum Facebook Ads Manager

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und dann **Facebook Ads Manager** aus.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. [Ermöglichen Sie Mitwirkenden, eine Verbindung für die Exporte zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Mithilfe von Facebook Ads authentifizieren:

   1. Wählen Sie **Forfahren mit Facebook**, um sich bei Ihrem Facebook Anzeigenkonto anzumelden.

   1. Erlauben Sie die Berechtigung **ads_management** nach der Authentifizierung mit Facebook.

   1. Wählen Sie das **Facebook Ads Konto**, mit dem Sie arbeiten möchten.

   1. Wählen Sie eine **Bestehende benutzerdefinierte Zielgruppe** aus der Dropdown-Liste oder erstellen Sie eine **Neue benutzerdefinierte Zielgruppe**.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Abschnitt Facebook Ads Manager aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. Unter **Daten verbinden** wählen Sie **E-Mail**, **Name und Adresse** oder **Telefon** aus und senden es an Facebook Anzeigenmanager.

1. Ordnen Sie die entsprechenden Attribute Ihrer einheitlichen Kundenentität der ausgewählten Schlüsselkennung zu.
   > [!TIP]
   > Die besten Chancen für eine Übereinstimmung ergeben sich, wenn Sie **E-Mail** als Schlüsselkennung auswählen. Das Hinzufügen zusätzlicher Bezeichner kann die Übereinstimmung verbessern.

1. Wählen Sie **Attribute hinzufügen**, um weitere Attribute zuzuordnen, die an Facebook Ads Manager gesendet werden sollen. Attribute vom Facebook Ads Manager werden den folgenden benutzerfreundlichen Namen zugeordnet: **FN** = **Vorname**, **LN** = **Nachname**, **FI** = **Anfangsbuchstabe des Vornamens**, **PHONE** = **Telefon**, **GEN** = **Geshclecht**, **DOB** = **Geburtsdatum**, **ST** = **Bundesland**, **CT** = **Stadt**, **ZIP** = **Postleitzahl**, **COUNTRY** = **Land/Region**

1. Wählen Sie die Segemente aus, die Sie exportieren möchten.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
