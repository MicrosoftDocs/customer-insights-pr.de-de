---
title: Segmente nach Sendinblue exportieren (Vorschauversion)
description: Erfahren Sie, wie Sie die Verbindung und den Export zu Sendinblue konfigurieren.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 816a3b242fadaa5a75db878adf0a76baf638e41c
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196945"
---
# <a name="export-segments-to-sendinblue-preview"></a>Segmente nach Sendinblue exportieren (Vorschauversion)

Segmente von einheitlichen Kundenprofilen exportieren, um Kampagnen zu generieren, E-Mail-Marketing bereitzustellen und spezifische Kundengruppen mit Sendinblue zu nutzen.

## <a name="prerequisites"></a>Anforderungen

- Ein [Sendinblue-Konto](https://www.sendinblue.com/) und entsprechende Administrator-Anmeldeinformationen.
- Ein [SendinBlue-API-Schlüssel](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- Existierende Listen in Sendinblue und die entsprechenden IDs.
- [Konfigurierte Segmente](segments.md).
- Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Bis zu 1 Million Kundenprofile pro Export zu Sendinblue exportieren und die Fertigstellung kann bis zu 90 Minuten dauern. Die Anzahl der Kundenprofile, die Sie nach Sendinblue exportieren können, hängt von Ihrem Vertrag mit Sendinblue ab.
- Nur Segmente.

## <a name="set-up-connection-to-sendinblue"></a>Verbindung zu Sendinblue einrichten

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Sendinblue**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie Ihren **SendinBlue API-Schlüssel** ein.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie **Verbinden**, um die Verbindung zu initialisieren.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. In dem Feld **Anschluss für Export** wählen Sie im Bereich Sendinblue eine Verbindung aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. Geben Sie Ihre **SendinBlue Listen-ID** ein.

1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt.

1. Optional können Sie **Vorname**, **Nachname**, und **Telefon** exportieren, um personalisiertere E-Mails zu erstellen. Wählen Sie **Attribut hinzufügen**, um diese Felder zuzuordnen.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
