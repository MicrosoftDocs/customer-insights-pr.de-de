---
title: Power Automate-Konnektor (Vorschauversion) | Microsoft-Dokumentation
description: Flows in Microsoft Power Automate aus Dynamics 365 Customer Insights erstellen.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196117"
---
# <a name="power-automate-connector-preview"></a>Power Automate-Connector (Vorschauversion)

Lösen Sie bei Änderungen an den Daten automatisch bestimmte Ereignisse aus. Verwalten Sie komplexere Flows direkt in [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Maximal 100 Anrufe pro 60 Sekunden. Sie können die API Endpunkt mehrmals aufrufen, indem Sie den [$skip-Parameter](/connectors/customerinsights/#get-items-from-an-entity) verwenden.

## <a name="power-automate-triggers"></a>Power Automate Auslöser

Verwenden Sie Trigger, um Cloud-Flows zu erstellen und sich wiederholende Aufgaben wie Benachrichtigungen oder erweiterte Aktionen zu automatisieren. Trigger verwenden wenn:

- Aktualisieren einer Datenquelle schlägt fehl.
- Aktualisieren einer Datenquelle erfolgreich.
- Ein Schwellenwert in einem Segment wird überschritten. Der Auslöser ist auf das Überschreiten des Schwellenwerts beschränkt.
- Ein Schwellenwert bei einer Geschäftsmaßnahme wird überschritten. Nur Unternehmenskennzahlen ohne Dimension werden unterstützt. Der Auslöser ist auf das Überschreiten des Schwellenwerts beschränkt.
- Eine vollständig geplante Aktualisierung ist abgeschlossen. Dieser Trigger funktioniert nicht für manuell gestartete Aktualisierungen.
- Eine Aktualisierung des Vereinheitlichungsprozesses ist abgeschlossen.

[Konfigurieren Sie Ihre Auslöser in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate-Aktionen

Der Power Automate-Anschluss bietet andere Aktionen als die verfügbaren Auslöser. Weitere Informationen finden Sie im [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Power Automate-Workflow erstellen

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Auf der **Power Automate**-Kachel wählen Sie **Einrichten**.

1. Der Customer Insights-Konnektor (Vorschauversion) in Power Automate wird geöffnet. **Anmelden** bei Power Automate.

1. Wählen Sie einen der verfügbaren Trigger und fügen Sie Ihrem neuen Flow weitere Schritte hinzu. Weitere Informationen finden Sie unter [Cloud-Flow in Power Automate erstellen](/power-automate/get-started-logic-flow).

Beispiele für die Verwendung von Flows: 
- Senden Sie eine Nachricht an den Microsoft Teams-Kanal, wenn eine Aktualisierung der Datenquelle fehlschlägt. 
- Senden Sie eine E-Mail an die Dateneigentümer, wenn ein Schwellenwert für ein Segment überschritten wird.

[!INCLUDE [footer-include](includes/footer-banner.md)]
