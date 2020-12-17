---
title: Power Automate Connector | Microsoft Docs
description: Erstellen Sie in Microsoft Power Automate aus Dynamics 365 Customer Insights Flows.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405750"
---
# <a name="power-automate-connector-preview"></a>Power Automate-Connector (Vorschau)

Lösen Sie bei Änderungen an den Daten automatisch bestimmte Ereignisse aus. Verwalten Sie komplexere Flows direkt in [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Power Automate Auslöser

Sie können eine Vielzahl von Triggern verwenden, mit denen Sie Flows erstellen können, um sich wiederholende Aufgaben zu automatisieren, z. B. Benachrichtigungen oder fortgeschrittenere Aktionen. 

- Auslösen, wenn die Aktualisierung einer Datenquelle fehlschlägt. 
- Auslösen, wenn eine Datenquellenaktualisierung erfolgreich ist.
- Auslösen, wenn ein Schwellenwert in einem Segment überschritten wird. Der Auslöser ist auf das Überschreiten des Schwellenwerts beschränkt.
- Auslösen, wenn ein Schwellenwert bei einer Geschäftsmaßnahme überschritten wird. Der Auslöser ist auf das Überschreiten des Schwellenwerts beschränkt.
- Auslöser, wenn eine vollständige Aktualisierung von (Datenquellen, Segmenten, Kennzahlen,...) abgeschlossen ist.
- Wird ausgelöst, wenn eine Aktualisierung des Vereinigungsprozesses (Zuordnung, Übereinstimmung, Zusammenführung) abgeschlossen ist.

[Konfigurieren Sie Ihre Auslöser in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate-Aktionen
Der Power Automate-Anschluss bietet andere Aktionen als die verfügbaren Auslöser. Weitere Informationen finden Sie im [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Erstellen Sie einen Power Automate-Fluss in Zielgruppen-Insights

1. Gehen Sie in Zielgruppen-Insights zu **Admin** > **System**.

1. Wählen Sie auf der Seite **System** die Registerkarte **Status**.

1. Wählen Sie im Abschnitt **Datenquellen** die Option **Flows** und in der Dropdownliste die Option **Einen Flow erstellen** aus.
   > [!div class="mx-imgBorder"]
   > ![Power Automate-Conntector zeigt "Flow erstellen Aktion"](media/power-automate-connector-create-flow.png "Power Automate Connector, der die Aktion "Flow erstellen" anzeigt")

1. Wählen Sie in Power Automate einen der verfügbaren Trigger aus, um Ihren bevorzugten Flow zu erstellen. Wenn Sie Ihren ersten Flow erstellen, müssen Sie sich zuerst mit dem Power Automate Konnektor authentifizieren.
