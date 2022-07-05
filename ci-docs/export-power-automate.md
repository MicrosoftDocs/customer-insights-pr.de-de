---
title: Power Automate-Konnektor (Vorschauversion) | Microsoft-Dokumentation
description: Flows in Microsoft Power Automate aus Dynamics 365 Customer Insights erstellen.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29a861dad926072f6f849d738d868f0f3b9306be
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081061"
---
# <a name="power-automate-connector-preview"></a>Power Automate-Connector (Vorschauversion)

Lösen Sie bei Änderungen an den Daten automatisch bestimmte Ereignisse aus. Verwalten Sie komplexere Flows direkt in [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Sie können maximal 100 Anrufe pro 60 Sekunden tätigen. Sie können die API Endpunkt mehrmals aufrufen, indem Sie den $skip-Parameter verwenden. [Erfahren Sie mehr über den $skip-Parameter](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Power Automate Auslöser

Verwenden Sie Trigger, um Cloud-Flows zu erstellen und sich wiederholende Aufgaben wie Benachrichtigungen oder erweiterte Aktionen zu automatisieren.

- Auslösen, wenn die Aktualisierung einer Datenquelle fehlschlägt.
- Auslösen, wenn eine Datenquellenaktualisierung erfolgreich ist.
- Auslösen, wenn ein Schwellenwert in einem Segment überschritten wird. Der Auslöser ist auf das Überschreiten des Schwellenwerts beschränkt.
- Auslösen, wenn ein Schwellenwert bei einer Geschäftsmaßnahme überschritten wird. Nur Unternehmenskennzahlen ohne Dimension werden unterstützt. Der Auslöser ist auf das Überschreiten des Schwellenwerts beschränkt.
- Auslöser, wenn eine vollständige Aktualisierung von (Datenquellen, Segmenten, Kennzahlen,...) abgeschlossen ist.
- Ein Trigger kann ausgelöst werden, wenn eine Aktualisierung des Vereinheitlichungsprozesses abgeschlossen ist.

[Konfigurieren Sie Ihre Auslöser in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate-Aktionen

Der Power Automate-Anschluss bietet andere Aktionen als die verfügbaren Auslöser. Weitere Informationen finden Sie im [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Power Automate-Workflow erstellen

1. Gehen Sie zu **Administrator** > **Exportziele**.

1. Auf der **Power Automate**-Kachel wählen Sie **Einrichten**.

1. Der Customer Insights-Konnektor (Vorschauversion) in Power Automate wird geöffnet. **Anmelden** bei Power Automate.

1. Wählen Sie einen der verfügbaren Trigger und fügen Sie Ihrem neuen Flow weitere Schritte hinzu. Weitere Informationen finden Sie unter [Cloud-Flow in Power Automate erstellen](/power-automate/get-started-logic-flow).

Beispiele für die Verwendung von Flows: 
- Senden Sie eine Nachricht an den Microsoft Teams-Kanal, wenn eine Aktualisierung der Datenquelle fehlschlägt. 
- Senden Sie eine E-Mail an die Dateneigentümer, wenn ein Schwellenwert für ein Segment überschritten wird.



[!INCLUDE [footer-include](includes/footer-banner.md)]
