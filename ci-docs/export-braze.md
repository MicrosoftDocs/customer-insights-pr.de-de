---
title: Segmente nach Braze exportieren (Vorschauversion)
description: Weitere Informationen zum Konfigurieren der Verbindung und zum Exportieren nach Braze.
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a3967008ec166cb6f099659b0791f1318126c0da
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725215"
---
# <a name="export-segments-to-braze-preview"></a>Segmente nach Braze exportieren (Vorschauversion)

Exportieren Sie Segmente von Unified customer Profiles nach Braze und verwenden Sie sie für Marketingaktivitäten.

## <a name="prerequisites"></a>Anforderungen

- Ein [Braze-Konto](https://www.braze.com/) und die entsprechenden Administrator-Anmeldeinformationen.
- Ein [Braze-API-Schlüssel](https://www.braze.com/docs/api/basics/)
- Ihr [Braze REST Endpunkt](https://www.braze.com/docs/api/basics/#api-definitions) 
- [Konfigurierte Segmente](segments.md) in Customer Insights.
- Einheitliche Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse und eine Braze-Kunden-ID darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Private Link in Kombination mit Bring Your Own Storage (BYOS) wird nicht unterstützt.
- Export von Segmenten mit bis zu 1 Millionen Kundenprofilen nach Braze kann bis zu 40 Minuten dauern. Die Anzahl der Kundenprofile, die Sie nach Braze exportieren können, hängt von Ihrem Vertrag mit Braze ab.
- Nur Segmente.
- Azure Private Link wird für den Braze-Export nicht unterstützt.

## <a name="set-up-connection-to-braze"></a>Richten Sie die Verbindung mit Braze ein

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Braze**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Stellen Sie Ihren Braze API-Schlüssel bereit, um sich weiterhin anzumelden.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie **Verbinden**, um die Verbindung zu initialisieren.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. Wählen Sie im Feld **Verbindung für Export** eine Verbindung aus dem Braze-Abschnitt aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie Ihren REST Endpunkt in das Feld **Hostname** im folgenden Format ein: `rest.iad-03.braze.com`.

1. Geben Sie einen Namen für den Export ein.

1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt. Wählen Sie das Feld für die Kunden-Braze-ID im Feld **Kunden-ID** aus. Die Segmente in Braze werden mit dem gleichen Namen des Segments wie in Dynamics 365 Customer Insights erstellt. Sie können zusätzliche, optionale Felder für übereinstimmende Daten auswählen.

1. Wählen Sie die Entitäten für die zu exportierenden Segmente.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
