---
title: Exportieren von Segmenten nach Omnisend (Vorschauversion)
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und nach Omnisend exportieren.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fb57e2bd70592f4ce4e1a13e21901dc69734f6bf
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725169"
---
# <a name="export-segments-to-omnisend-preview"></a>Exportieren von Segmenten nach Omnisend (Vorschauversion)

Exportieren Sie Segmente einheitlicher Kundenprofile nach Omnisend und verwenden Sie sie für Marketingaktivitäten.

## <a name="prerequisites"></a>Anforderungen

- Ein [Omnisend-Konto](https://www.omnisend.com/) und entsprechende Administrator-Anmeldeinformationen.
- Ein [Omnisend-API-Schlüssel](https://support.omnisend.com/en/articles/1061890-generating-api-key).
- [Konfigurierte Segmente](segments.md) in Customer Insights.
- Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Private Link in Kombination mit Bring Your Own Storage (BYOS) wird nicht unterstützt.
- Bis zu 1 Million Kundenprofile pro Export zu Omnisend exportieren und die Fertigstellung kann bis zu vier Stunden dauern. Die Anzahl der Kundenprofile, die Sie nach Omnisend exportieren können, hängt von Ihrem Vertrag mit Omnisend ab.
- Nur Segmente.

## <a name="set-up-connection-to-omnisend"></a>Einrichten einer Verbindung mit Omnisend

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Omnisend**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie Ihren Omnisend-API-Schlüssel ein.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie **Verbinden**, um die Verbindung zu initialisieren.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Omnisend-Abschnitt aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt.

1. Optional können Sie **Vorname**, **Nachname**, **Adresse**, **Bundesland/Region**, **Land**, **Stadt** und **Postleitzahl**, um personalisiertere E-Mails zu erstellen. Wählen Sie **Attribut hinzufügen**, um diese Felder zuzuordnen.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
