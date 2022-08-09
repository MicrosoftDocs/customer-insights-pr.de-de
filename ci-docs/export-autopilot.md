---
title: Segmente nach Autopilot exportieren (Vorschauversion)
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu Autopilot exportieren.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 449d2c5e32697e4a5d2c9dff4a5a1cbdb26aeb4d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195059"
---
# <a name="export-segments-to-autopilot-preview"></a>Segmente nach Autopilot exportieren (Vorschauversion)

Exportieren Sie Segmente einheitlicher Kundenprofile in Autopilot und verwenden Sie sie für E-Mail-Marketing in Autopilot.

## <a name="prerequisites-for-a-connection"></a>Voraussetzungen für die Verbindung

- Ein [Autopilot-Konto](https://www.autopilothq.com/) und entsprechende Anmeldeinformationen für den Administrator.
- Ein [AutoPilot-API-Schlüssel](https://autopilot.docs.apiary.io/#)
- [Konfigurierte Segmente](segments.md) in Customer Insights.
- Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Der Export von bis zu 100.000 Kundenprofilen nach Autopilot kann bis zu einigen Stunden dauern. Die Anzahl der Kundenprofile, die Sie nach Autopilot exportieren können, hängt von Ihrem Vertrag mit Autopilot ab.
- Nur Segmente.

## <a name="set-up-connection-to-autopilot"></a>Richten Sie die Verbindung mit Autopilot ein

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Autopilot**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie Ihren Autopilot-API-Schlüssel ein.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie **Verbinden**, um die Verbindung zu initialisieren.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Autopilot-Abschnitt aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt.

1. Exportieren Sie optional andere Felder wie **Vorname** und **Nachname**.

1. Wählen Sie die Segmente aus, die Sie exportieren möchten, indem Sie die bekannten Limitierungen berücksichtigen.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
