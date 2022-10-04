---
title: Customer Insights Daten nach HubSpot exportieren
description: Erfahren Sie, wie Sie die Verbindung und den Export zu HubSpot konfigurieren.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588905"
---
# <a name="export-segments-to-hubspot-preview"></a>Segmente nach HubSpot exportieren (Vorschauversion)

Exportieren Sie Segmente von Vereinheitlichtem Kundenprofil zu HubSpot und verwenden Sie sie für Marketingaktivitäten.

## <a name="prerequisites-for-a-connection"></a>Voraussetzungen für die Verbindung

- Ein [HubSpot-Konto](https://www.hubspot.com/) und die entsprechenden Anmeldeinformationen.
- [API-Schlüssel](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) von HubSpot.
- [Konfigurierte Segmente](segments.md) in Customer Insights.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Bis zu 100.000 Kundenprofile pro Export nach HubSpot, was bis zu 15 Minuten dauern kann. Die Anzahl der Kundenprofile, die Sie nach HubSpot exportieren können, hängt von Ihrem Vertrag mit HubSpot ab.
- Nur Segmente.

## <a name="set-up-connection-to-hubspot"></a>Richten Sie die Verbindung mit HubSpot ein

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und dann **HubSpot** aus, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wenn Sie dazu aufgefordert werden, geben Sie Ihre HubSpot-Anmeldeinformationen ein.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie **Verbinden** aus, um die Verbindung zu HubSpot zu initialisieren.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Um einen neuen Export zu erstellen, wählen Sie **Export hinzufügen** aus.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem HubSpot-Abschnitt aus. Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt. Wiederholen Sie die gleichen Schritte für andere optionale Felder.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
