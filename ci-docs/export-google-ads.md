---
title: Segmente in Google Ads exportieren (Vorschauversion)
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu Google Ads exportieren.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: fd7498ecf17ef8a3a8f22dcc49ae204bef88b47f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196577"
---
# <a name="export-segments-to-google-ads-preview"></a>Segmente in Google Ads exportieren (Vorschauversion)

Exportieren Sie Segmente von einheitlichen Kundenprofilen in eine Google Ads Publikum-Liste und verwenden Sie sie, um in der Google-Suche, in Gmail, YouTube, und im Google Display-Netzwerk zu werben.

## <a name="prerequisites"></a>Anforderungen

- Ein [Google Ads-Konto](https://ads.google.com/) und die entsprechenden Anmeldeinformationen.
- Ein [Kunden-ID für Google Ads](https://support.google.com/google-ads/answer/1704344).
- Die Anforderungen der [Customer Match-Richtlinie](https://support.google.com/adspolicy/answer/6299717) sind erfüllt.
- Die Anforderungen der [Remarketing-Listengrößen](https://support.google.com/google-ads/answer/7558048) sind erfüllt.
- [Konfigurierte Segmente](segments.md).
- Einheitliche Kundenprofile in den exportierten Segmenten enthalten Felder, die eine E-Mail-Adresse, Telefonnummer, mobile Werbe-ID, Drittanbieter-Benutzer-ID oder Adresse darstellen.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Bis zu 1 Million Kundenprofile pro Export nach Google Ads esxportieren, was aufgrund von Einschränkungen auf Seiten des Anbieters bis zu 30 Minuten dauern kann.
- Nur Segmente.
- Der Abgleich in Google Ads kann bis zu 48 Stunden dauern.

## <a name="set-up-connection-to-google-ads"></a>Verbindung mit Google Ads einrichten

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Google Ads**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie Ihre Google Ads Kunden-ID ein.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie **Mit Google Ads authentifizieren** und geben Sie Ihre Google Ads Anmeldeinformationen an.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Google Ads-Abschnitt aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. Wählen Sie aus, ob Sie eine vorhandene Umgebung verwenden oder Sie eine neue erstellen.
   - Wenn Sie eine vorhandene Google Ads Zielgruppe aktualisieren möchten, geben Sie Ihre [Google Ads Zielgruppen-ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns) ein.
   - Wenn Sie eine neue Zielgruppe erstellen möchten, lassen Sie das Feld Google Zielgruppen-ID leer. Customer Insights erstellt automatisch ein neues Publikum in Ihrem Google Ads-Konto und verwenden den Namen des exportierten Segments.

1. In dem Abschnitt **Datenabgleich** wählen Sie im Abschnitt ein oder mehrere Datenfelder zum Exportieren aus und wählen Sie das Feld aus, das die entsprechenden Datenfelder in Customer Insights darstellt.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
