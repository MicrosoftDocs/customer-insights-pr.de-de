---
title: Power Automate Connector | Microsoft Docs
description: Flows in Microsoft Power Automate aus Dynamics 365 Customer Insights erstellen.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dc9bbe22b7f10cf92f06cae18fbece9808b87dce
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226713"
---
# <a name="power-automate-connector-preview"></a>Power Automate-Connector (Vorschau)

Lösen Sie bei Änderungen an den Daten automatisch bestimmte Ereignisse aus. Verwalten Sie komplexere Flows direkt in [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Power Automate Auslöser

Verwenden Sie Trigger, um Cloud-Flows zu erstellen und sich wiederholende Aufgaben wie Benachrichtigungen oder erweiterte Aktionen zu automatisieren. 

- Auslösen, wenn die Aktualisierung einer Datenquelle fehlschlägt. 
- Auslösen, wenn eine Datenquellenaktualisierung erfolgreich ist.
- Auslösen, wenn ein Schwellenwert in einem Segment überschritten wird. Der Auslöser ist auf das Überschreiten des Schwellenwerts beschränkt.
- Auslösen, wenn ein Schwellenwert bei einer Geschäftsmaßnahme überschritten wird. Nur Unternehmenskennzahlen ohne Dimension werden unterstützt. Der Auslöser ist auf das Überschreiten des Schwellenwerts beschränkt.
- Auslöser, wenn eine vollständige Aktualisierung von (Datenquellen, Segmenten, Kennzahlen,...) abgeschlossen ist.
- Wird ausgelöst, wenn eine Aktualisierung des Vereinigungsprozesses (Zuordnung, Übereinstimmung, Zusammenführung) abgeschlossen ist.

[Konfigurieren Sie Ihre Auslöser in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate-Aktionen

Der Power Automate-Anschluss bietet andere Aktionen als die verfügbaren Auslöser. Weitere Informationen finden Sie im [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Power Automate-Workflow erstellen

1. Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Ziele exportieren**.

1. Auf der **Power Automate**-Kachel wählen Sie **Einrichten**.

1. Der Customer Insights-Konnektor (Vorschau) in Power Automate wird geöffnet. **Anmelden** bei Power Automate.

1. Wählen Sie einen der verfügbaren Trigger und fügen Sie Ihrem neuen Flow weitere Schritte hinzu. Weitere Informationen finden Sie unter [Cloud-Flow in Power Automate erstellen](/power-automate/get-started-logic-flow).

Beispiele für die Verwendung von Flows: 
- Senden Sie eine Nachricht an den Microsoft Teams-Kanal, wenn eine Aktualisierung der Datenquelle fehlschlägt. 
- Senden Sie eine E-Mail an die Dateneigentümer, wenn ein Schwellenwert für ein Segment überschritten wird.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
