---
title: Exportieren von Segmenten nach Microsoft Advertising (Vorschauversion)
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und nach Microsoft Advertising exportieren.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196531"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Exportieren von Segmenten nach Microsoft Advertising (Vorschauversion)

Exportieren Sie Customer Insights-Segmente nach Microsoft Advertising, um Zielgruppen für Customer Match zu erstellen. Verwenden Sie diese Zielgruppen für Ihre Werbekampagnen.

## <a name="prerequisites"></a>Anforderungen

- Ein [Microsoft Advertising-Konto](https://ads.microsoft.com/) und entsprechende Administrator-Anmeldeinformationen.
- Kunden- und Konto-ID für Microsoft Advertising ein. Kunden-ID (`cid`) und die Konto-ID (`aid`) in den Parametern der URL, wenn Sie bei Microsoft Advertising angemeldet sind.
- Nutzungsbedingungen für Customer Match akzeptiert.
- [Konfigurierte Segmente](segments.md) in Customer Insights.
- Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Export von Segmenten mit bis zu 500.000 Kundenprofilen nach Microsoft Advertising kann bis zu 10 Minuten dauern.
- Nur Segmente.

## <a name="set-up-connection-to-microsoft-advertising"></a>Einrichten der Verbindung mit Microsoft Advertising

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Microsoft Advertising**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Als Standard sind Administratoren ausgewählt. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie **Kunden-ID für Microsoft Advertising** ein.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie **Verbinden**, um die Verbindung zu initialisieren.

1. Wählen Sie **Mit Microsoft Advertising authentifizieren** aus, und geben Sie Ihre Administratoranmeldeinformationen für Microsoft Advertising an.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Microsoft Advertising-Abschnitt aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. Wählen Sie die zu exportierenden Segmente aus. Die Zielgruppen für Customer Match in Microsoft Advertising werden automatisch mit dem Namen der für den Export ausgewählten Segmente erstellt. Jedes Segment führt zu einer separaten Zielgruppe für Customer Match.

1. Geben Sie Ihre **Kunden- und Konto-ID für Microsoft Advertising** ein.

1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld mit der E-Mail-Adresse eines Kunden aus.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
