---
title: Exportieren von Segmenten nach Snapchat (Vorschauversion)
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu Snapchat exportieren.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195381"
---
# <a name="export-segments-to-snapchat-preview"></a>Exportieren von Segmenten nach Snapchat (Vorschauversion)

Exportieren Sie Segmente einheitlicher Kundenprofile in Snapchat und verwenden Sie sie für Marketingaktivitäten.

## <a name="prerequisites"></a>Anforderungen

- Ein [Snapchat Business-Konto](https://business.snapchat.com/), ein [Snapchat Ads-Konto](https://ads.snapchat.com/) und entsprechende Administrator-Anmeldeinformationen. Sie müssen mindestens Mitglied eines Organisationskontos und Datenmanager eines bestimmten Werbekontos sein.
- Sie haben mindestens eine Zielgruppe im Snapchat Audience Manager vom Typ SAM (Snap Audience Match).
- Die [Snapchat-Segment/Audience-ID](https://businesshelp.snapchat.com/s/article/custom-audiences). Die ID der Zielgruppe finden Sie in der URL nach Auswahl der Zielgruppe im Snapchat Audience Manager.
- [Konfigurierte Segmente](segments.md) in Customer Insights.
- Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Export von Segmenten mit bis zu 1 Millionen Kundenprofilen kann bis zu 15 Minuten dauern.
- Nur Segmente.

## <a name="set-up-connection-to-snapchat"></a>Verbindung mit Snapchat einrichten

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Snapchat**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie **Verbinden**, um die Verbindung zu initialisieren.

1. Wählen Sie **Mit Snapchat authentifizieren** aus, und geben Sie Ihre Administratoranmeldeinformationen für Snapchat an.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Snapchat-Abschnitt aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. Geben Sie die **Snapchat-Segment/Audience-ID** ein.

1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
