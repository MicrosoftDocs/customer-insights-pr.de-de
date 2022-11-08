---
title: Exportieren von Segmenten nach DotDigital (Vorschauversion)
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu DotDigital exportieren.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f3e3378dce9177c6645b91140884ae135540243
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724985"
---
# <a name="export-segments-to-dotdigital-preview"></a>Exportieren von Segmenten nach DotDigital (Vorschauversion)

Exportieren Sie Segmente von vereinheitlichten Kundenprofilen in DotDigital-Adressbücher und verwenden Sie diese für Kampagnen, E-Mail-Marketing und zum Aufbau von Kundensegmenten mit DotDigital.

## <a name="prerequisites"></a>Anforderungen

- Ein [DotDigital-Konto](https://dotdigital.com/) und ein [API-Benutzer](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- Eine DotDigital-ID von [Neu](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) oder bestehendes Adressbuch in DotDigital. Die ID ist in der URL zu finden, wenn Sie ein Adressbuch auswählen und öffnen.
- [Konfigurierte Segmente](segments.md) in Customer Insights.
- Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Private Link in Kombination mit Bring Your Own Storage (BYOS) wird nicht unterstützt.
- Bis zu 1 Million Kundenprofile pro Export nach DotDigital, was aufgrund von Einschränkungen auf Seiten des Anbieters bis zu drei Stunden dauern kann. Die Anzahl der Kundenprofile, die Sie nach DotDigital exportieren können, hängt von Ihrem Vertrag mit DotDigital ab.
- Nur Segmente.

## <a name="set-up-connection-to-dotdigital"></a>Verbindung mit DotDigital einrichten

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **DotDigital**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie Ihren **DotDigital API-Benutzernamen und Ihr Kennwort** ein.

1. Geben Sie Ihre **DotDigital-Adressbuch-ID** ein.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie **Verbinden**, um die Verbindung zu initialisieren.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem DotDigital-Abschnitt aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt.

1. Exportieren Sie optional **Vorname**, **Nachname**, **Vollständiger Name**, **Geschlecht**, und **Postleitzahl**.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

In DotDigital können Sie jetzt Ihre Segmente in [DotDigital Adressbüchern](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) finden.

[!INCLUDE [footer-include](includes/footer-banner.md)]
