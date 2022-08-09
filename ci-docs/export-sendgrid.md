---
title: Segmente nach SendGrid exportieren (Vorschauversion)
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu SendGrid exportieren.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f2990ad410dda0cbf952f82f3fc30b3a53a7bcd4
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196991"
---
# <a name="export-segments-to-sendgrid-preview"></a>Segmente nach SendGrid exportieren (Vorschauversion)

Exportieren Sie Segmente einheitlicher Kundenprofile in SendGrid-Kontaktlisten und verwenden Sie sie für Kampagnen und E-Mail-Marketing in SendGrid.

## <a name="prerequisites"></a>Anforderungen

- Ein [SendGrid-Konto](https://sendgrid.com/) und die entsprechenden Anmeldeinformationen.
- [Bestehende Kontaktlisten in SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) und die entsprechenden IDs.
- Ein [SendGrid-API-Schlüssel](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Konfigurierte Segmente](segments.md) in Customer Insights.
- Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Export von bis zu 100.000 Kundenprofilen an SendGrid kann bis zu einigen Stunden dauern. Die Anzahl der Kundenprofile, die Sie nach SendGrid exportieren können, hängt von Ihrem Vertrag mit SendGrid ab.
- Nur Segmente.

## <a name="set-up-connection-to-sendgrid"></a>Verbindung mit SendGrid einrichten

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **SendGrid**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie Ihren **SendGrid-API-Schlüssel** ein.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie **Verbinden**, um die Verbindung zu initialisieren.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem SendGrid-Abschnitt aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. Geben Sie Ihre **SendGrid-Listen-ID** ein.

1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt.

1. Für optionale Felder wie **Vorname**, **Nachname**, **Land / Region**, **Bundesland**, **Stadt** und **Postleitzahl** auswählen.

1. Wählen Sie die Segmente aus, die Sie exportieren möchten, indem Sie die bekannten Limitierungen.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
