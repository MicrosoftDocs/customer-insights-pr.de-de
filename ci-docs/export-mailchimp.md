---
title: Exportieren von Segmenten nach Mailchimp (Vorschauversion)
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu Mailchimp exportieren.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d74672768afec94e899ff0aec8c118c2afcde368
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725031"
---
# <a name="export-segments-to-mailchimp-preview"></a>Exportieren von Segmenten nach Mailchimp (Vorschauversion)

Exportieren Sie Segmente von vereinheitlichten Kundenprofilen nach Mailchimp, um Newsletter und E-Mail-Kampagnen zu erstellen.

## <a name="prerequisites"></a>Anforderungen

- Ein [Mailchimp-Konto](https://mailchimp.com/) und die entsprechenden Anmeldeinformationen.
- [Bestehende Zielgruppen in Mailchimp](https://mailchimp.com/help/create-audience/) und die dazugehörigen [Zielgruppen-IDs](https://mailchimp.com/help/find-audience-id/).
- [Konfigurierte Segmente](segments.md).
- Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Private Link in Kombination mit Bring Your Own Storage (BYOS) wird nicht unterstützt.
- Bis zu 1 Million Kundenprofile pro Export zu Mailchimp exportieren und die Fertigstellung kann bis zu 3 Stunden dauern. Die Anzahl der Kundenprofile, die Sie nach Mailchimp exportieren können, hängt von Ihrem Vertrag mit Mailchimp ab.
- Nur Segmente.

## <a name="set-up-connection-to-mailchimp"></a>Verbindung mit Mailchimp einrichten

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Mailchimp**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie **Verbinden**, um die Verbindung zu initialisieren.

1. Wählen Sie **Mit Mailchimp authentifizieren** und geben Sie Ihre Mailchimp Anmeldeinformationen an.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Mailchimp-Abschnitt aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. Geben Sie Ihre **Mailchimp-Zielgruppen-ID** ein.

1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt.

1. Exportieren Sie optional **Vorname** und **Nachname** exportieren, um personalisiertere E-Mails zu erstellen. Wählen Sie **Attribut hinzufügen**, um diese Felder zuzuordnen.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
