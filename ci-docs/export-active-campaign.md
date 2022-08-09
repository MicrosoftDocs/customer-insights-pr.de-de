---
title: Segmente nach ActiveCampaign exportieren
description: Erfahren Sie, wie Sie die Verbindung und den Export zu ActiveCampaign konfigurieren.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 178d2df8edf1abcec72664e19d73a88f2b97f12d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195565"
---
# <a name="export-segments-to-activecampaign-preview"></a>Segmente nach ActiveCampaign exportieren (Vorschauversion)

Exportieren Sie Segmente von einheitlichen Kundenprofilen nach ActiveCampaign und verwenden Sie sie für Marketingaktivitäten.

## <a name="prerequisites"></a>Anforderungen

- Ein [ActiveCampaign-Konto](https://www.activecampaign.com/) und entsprechende Administrator-Anmeldeinformationen.
- Eine [ActiveCampaign-Listen-ID](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- Einen [ActiveCampaign API-Schlüssel](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) und und REST Endpunkt Hostname.
- [Konfigurierte Segmente](segments.md) in Customer Insights.
- Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Bis zu 1 Million Kundenprofile pro Export zu ActiveCampaign exportieren und die Fertigstellung kann bis zu 90 Minuten dauern. Die Anzahl der Kundenprofile, die Sie nach ActiveCampaign exportieren können, hängt von Ihrem Vertrag mit ActiveCampaign ab.
- Nur Segmente.

## <a name="set-up-connection-to-activecampaign"></a>Richten Sie die Verbindung mit ActiveCampaign ein.

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **ActiveCampaign**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie Ihren ActiveCampaign API-Schlüssel und REST Endpunkt Hostname ein. Der REST Endpunkt Hostname ist nur der Hostname ohne https://.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie **Verbinden**, um die Verbindung zu initialisieren.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. In dem Feld **Anschluss für Export** wählen Sie im Bereich ActiveCampaign eine Verbindung aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. Geben Sie Ihre **ActiveCampaign Listen-ID** ein.

1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt.

1. Optional können Sie **Vorname**, **Nachname**, und **Telefon** exportieren, um personalisiertere E-Mails zu erstellen. Wählen Sie **Attribut hinzufügen**, um diese Felder zuzuordnen.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
