---
title: Exportieren von Segmenten nach Campaign Monitor (Vorschauversion)
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zum Campaign Monitor exportieren.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c04fc26dc690cf32b45913257e82b9a0f617185
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196301"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Exportieren von Segmenten nach Campaign Monitor (Vorschauversion)

Exportieren Sie Segmente einheitlicher Kundenprofile in Campaign Monitor und verwenden Sie sie für Marketingaktivitäten.

## <a name="prerequisites"></a>Anforderungen

- Ein [Campaign Monitor-Konto](https://www.campaignmonitor.com/) und entsprechende Administrator-Anmeldeinformationen.
- Eine [Campaign Monitor-Listen-ID](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- Ein [Generierter API-Schlüssel](https://www.campaignmonitor.com/api/getting-started/) über die **Kontoeinstellungen** in Campaign Monitor zuerst, um die API-Listen-ID zu erhalten.
- [Konfigurierte Segmente](segments.md) in Customer Insights.
- Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Export von Segmenten mit bis zu 1 Millionen Kundenprofilen pro Export nach Campaign Monitor kann bis zu 20 Minuten dauern. Die Anzahl der Kundenprofile, die Sie nach Campaign Monitor exportieren können, hängt von Ihrem Vertrag mit Campaign Monitor ab.
- Nur Segmente.

## <a name="set-up-connection-to-campaign-monitor"></a>Verbindung mit Campaign Monitor einrichten

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Campaign Monitor**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie **Verbinden** aus, um die Verbindung zu Campaign Monitor zu initialisieren.

1. Wählen Sie **Mit Campaign Monitor authentifizieren** aus, und geben Sie Ihre Administratoranmeldeinformationen für Campaign Monitor an.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Um einen neuen Export zu erstellen, wählen Sie **Export hinzufügen** aus.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Campaign Monitor-Abschnitt aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. Geben Sie Ihre **Campaign Monitor-Listen-ID** ein.

1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt. Der Export nach Campaign Monitor ist auf Segmente beschränkt.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
