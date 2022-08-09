---
title: Segmente nach MoEngage exportieren
description: Weitere Informationen zum Konfigurieren der Verbindung und zum Exportieren nach MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199119"
---
# <a name="export-segments-to-moengage-preview"></a>Segmente nach MoEngage exportieren (Vorschauversion)

Exportieren Sie Segmente einheitlicher Kundenprofile in MoEngage und verwenden Sie sie für E-Mail-Marketing in MoEngage.

## <a name="prerequisites-for-a-connection"></a>Voraussetzungen für die Verbindung

- Ein [MoEngage-Konto](https://www.moengage.com/) und die entsprechenden Anmeldeinformationen.
- MoEngage-API-Schlüssel aus Einstellungen > API in MoEngage.
- [Konfigurierte Segmente](segments.md) in Customer Insights.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Export von Segmenten mit bis zu 100.000 Kundenprofilen nach MoEngage kann bis zu 15 Minuten dauern. Die Anzahl der Kundenprofile, die Sie nach MoEngage exportieren können, hängt von Ihrem Vertrag mit MoEngage ab.
- Nur Segmente.

## <a name="set-up-connection-to-moengage"></a>Verbindung mit MoEngage einrichten

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **MoEngage**, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie Ihr [MoEngage Data API-ID und API-Schlüssel](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY) ein.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie **Verbinden** aus, um die Verbindung zu MoEngage zu initialisieren.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Um einen neuen Export zu erstellen, wählen Sie **Export hinzufügen** aus.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem MoEngage-Abschnitt aus. Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt. Wiederholen Sie die gleichen Schritte für andere optionale Felder.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten. Wir erstellen ein oder mehrere Segmente mit demselben Namen wie die ausgewählten Segmente in MoEngage unter **Segmente** > **Benutzerdefinierte Segmente**.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
