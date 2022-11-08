---
title: Segmente nach Klaviyo exportieren (Vorschauversion)
description: Erfahren Sie, wie Sie die Verbindung und den Export zu Klaviyo konfigurieren.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 075e6758f2c6992a1185756f9beecf852fdd0a96
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724587"
---
# <a name="export-segments-to-klaviyo-preview"></a>Segmente nach Klaviyo exportieren (Vorschauversion)

Exportieren Sie Segmente von einheitlichen Kundenprofilen nach Klaviyo und verwenden Sie sie für Marketingaktivitäten.

## <a name="prerequisites"></a>Anforderungen

- Ein [Klaviyo Konto](https://www.klaviyo.com/) und entsprechende Administrator-Anmeldeinformationen.
- Ein [Klaviyo-API-Schlüssel](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys).
- Eine [Klaviyo-Listen-ID](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).
- [Konfigurierte Segmente](segments.md) in Customer Insights.
- Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Private Link in Kombination mit Bring Your Own Storage (BYOS) wird nicht unterstützt.
- Bis zu 1 Million Kundenprofile pro Export zu Klaviyo exportieren und die Fertigstellung kann bis zu 20 Stunden dauern. Die Anzahl der Kundenprofile, die Sie nach Klaviyo exportieren können, hängt von Ihrem Vertrag mit Klaviyo ab.
- Nur Segmente.

## <a name="set-up-connection-to-klaviyo"></a>Richten Sie die Verbindung mit Klaviyo ein

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Klaviyo**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie Ihre Klaviyo API-Schlüssel ein, um sich weiterhin anzumelden.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie **Verbinden**, um die Verbindung zu initialisieren.

1. Wählen Sie **Mit Klaviyo authentifizieren** aus und geben Sie Ihre Administrator-Anmeldeinformationen für Klaviyo an.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. In dem Feld **Anschluss für Export** wählen Sie im Bereich Klaviyo eine Verbindung aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. Geben Sie Ihre **Klaviyo Listen-ID** ein.

1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
