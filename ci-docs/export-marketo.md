---
title: Segmente nach Marketo exportieren (Vorschauversion)
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu Marketo exportieren.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f57cdfbb24df8a8ffa1670b426d50dbba2c5f40f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195243"
---
# <a name="export-segments-to-marketo-preview"></a>Segmente nach Marketo exportieren (Vorschauversion)

Exportieren Sie Segmente von vereinheitlichten Kundenprofilen, um Kampagnen zu erstellen, E-Mail-Marketing zu betreiben und bestimmte Kundengruppen mit Marketo zu nutzen.

## <a name="prerequisites"></a>Anforderungen

- Ein [Marketo-Konto](https://login.marketo.com/) und die entsprechenden Anmeldeinformationen.
- Ein [Marketo Client ID, Client secret und REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/).
- [Bestehende Listen in Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) und die entsprechenden IDs.
- [Konfigurierte Segmente](segments.md).
- Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Bis zu 1 Million Kundenprofile pro Export zu Marketo exportieren und die Fertigstellung kann bis zu 3 Stunden dauern. Die Anzahl der Kundenprofile, die Sie nach Marketo exportieren können, hängt von Ihrem Vertrag mit Marketo ab.
- Nur Segmente.

## <a name="set-up-connection-to-marketo"></a>Richten Sie die Verbindung mit Marketo ein

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Marketo**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie Ihre **Marketo Client ID, Client secret und REST Endpoint Hostname** ein. Der REST Endpunkt Hostname ist nur der Hostname ohne https://. Beispiel: xyz-abc-123.mktorest.com.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie **Verbinden**, um die Verbindung zu initialisieren.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Marketo-Abschnitt aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. Geben Sie Ihre **Marketo-Listen-ID** ein. Die Listen-ID ist ein rein numerischer Wert. Wenn Ihre Marketo-Listen-ID beispielsweise ST12345A7 lautet, entfernen Sie das Zeichen vor und nach den Ziffern und geben Sie *12345* ein.

1. In dem Abschnitt **Datenabgleich** wählen Sie mindestens ein Feld aus, das die E-Mail-Adresse eines Kunden oder die Marketo-ID eines Kunden darstellt.

1. Optional exportieren Sie **Vorname**, **Nachname**, **Stadt**, **Bundesland** und **Land / Region**, um personalisiertere E-Mails zu erstellen. Wählen Sie **Attribut hinzufügen**, um diese Felder zuzuordnen.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

In Marketo finden Sie Ihre Segmente jetzt unter [Marketo-Listen](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
