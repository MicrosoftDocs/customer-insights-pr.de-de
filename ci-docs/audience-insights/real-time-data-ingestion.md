---
title: Datenerfassung in Echtzeit und Einschränkungen
description: Allgemeine Informationen zu den Funktionalitäten von Zielgruppen-Insights in Echtzeit.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2fe5279eee1b3b30f5bc21464c85fe5f86d342a0
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355474"
---
# <a name="real-time-data-ingestion-preview"></a>Datenerfassung in Echtzeit (Vorschau)

Mit der Echtzeitfunktion können Sie innerhalb von Sekunden die aktuellen Interaktionen anzeigen, die Ihre Kunden mit Ihren Produkten oder Dienstleistungen durchgeführt haben.

[Geplante Aktualisierungen](system.md#schedule-tab) umfassen eine große Anzahl von Datensätzen und mehrere komplexe Operationen. Zunächst werden die Daten aus der Datenquelle gezogen. Dann werden die Daten vereinheitlicht und mit zusätzlichen Informationen angereichert. Jeder Durchlauf dieses Vorgangs kann Minuten bis Stunden dauern.

Die Echtzeit-Funktionalität stellt die Daten sofort zum Verbrauch bereit, bis die nachfolgende geplante Aktualisierung diese Daten aus der Datenquelle zieht.

Echtzeitaktualisierungen haben eine Ablaufzeit, nach der sie den Wert aus Datenquelle nicht mehr überschreiben:

- Profilaktualisierungen werden 4 Stunden lang aufbewahrt
- Aktivitäten werden 30 Tage lang aufbewahrt

Diese Werte sind API-Aufrufparameter, die Sie ändern können. Sie sollen sicherstellen, dass Ihre Quelldaten eine vertrauenswürdige Quelle bleiben. Wenn Sie möchten, dass Echtzeit-Updates länger berücksichtigt werden, müssen Sie sie zu einer Datenquelle hinzufügen, damit sie bei der nächsten geplanten Aktualisierung gezogen werden.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Echtzeitaktualisierung der Felder des vereinheitlichten Kundenprofils

Aktualisierte Profile werden innerhalb weniger Sekunden in der Kundenkartenansicht oder einer anderen Visualisierung angezeigt.

Da Echtzeitvorgänge nach der Datenvereinheitlichung stattfinden, gelten sie nur für die vereinheitlichten Kundenprofile. Folglich werden keine Maßnahmen, Segmentmitgliedschaften oder Anreicherungen durch Änderungen des Echtzeitprofils aktualisiert.

### <a name="limitations"></a>Einschränkungen

- Kundenprofile können aktualisiert, aber nicht erstellt oder gelöscht werden.
- Das Exportieren von Echtzeitaktualisierungen auf externe Systeme wie Power BI ist momentan nicht möglich.

## <a name="real-time-creation-of-activities"></a>Erstellung von Aktivitäten in Echtzeit

Mit der Echtzeit-API können Sie eine neue Aktivität aus Ihrem Quellsystem (einen einzelnen Quelldatensatz) in einem einheitlichen Kundenprofil veröffentlichen. Die neue Aktivität wird innerhalb von Sekunden als vereinheitlichte Aktivität in der Zeitleiste dieses vereinheitlichten Kundenprofils verfügbar sein. Sie können die Zeitleiste in der Kundenkartenansicht oder einer anderen von Ihnen konfigurierten Zeitleistenintegration sehen.

> [!NOTE]
>
> - Aktivitäten sind unveränderlich. Sie ändern sich nicht, wenn sie einmal erstellt wurden.
> - Derzeit werden Segmente und Kennzahlen nicht basierend auf der neuen Aktivität aktualisiert.
> - Aktivitäten, die nur über die Echtzeit-API hinzugefügt werden, sind nicht Teil des Exports und werden in PowerBI nicht angezeigt.

Es gibt zwei Möglichkeiten, sich mit der Echtzeit-API zu verbinden:

- [indirekt](#connect-via-the-dynamics-365-customer-insights-connector) unter Verwendung des [Dynamics 365 Customer Insights-Connectors](/connectors/customerinsights/)
- [direkt](#connect-directly-to-the-real-time-api) mit Code

Die folgenden Voraussetzungen gelten für beide Methoden:

- Eine Customer Insights-Umgebung
- Vereinheitlichte Kundenprofile
- Aktivitäten konfiguriert und ausgeführt
- Mitwirkender- oder Administratorberechtigungen zur Authentifizierung Ihres Kontos

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Über den Dynamics 365 Customer Insights-Connector verbinden

Die Echtzeit-API kann Daten von einem dedizierten Power Platform-Connector, dem [Dynamics 365 Customer Insights-Connector](/connectors/customerinsights/), erfassen, ohne dass Code geschrieben und bereitgestellt werden muss.    
Der Connector kann dieselben Echtzeitaktionen wie die API ausführen. Sie benötigen eine gültige Lizenz für Premium-Connectors. Weitere Informationen finden Sie unter [FAQs zur Power Apps- und Power Automate-Lizenzierung](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps und/oder Power Automate](/connectors/)
- Azure [Logic Apps](/azure/connectors/apis-list)

Einzelheiten zum Erstellen von Flows finden Sie in der [Power Automate-Dokumentation](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Eine direkte Verbindung zur Echtzeit-API herstellen

Sie können die Funktionalitäten in Echtzeit nutzen, indem Sie Ihre eigene Pipeline erstellen und sich direkt mit der Echtzeit-API verbinden.    
Sie können eine Aktivität im Format Ihres Quellsystems oder im UnifiedActivity-Format veröffentlichen. Rufen Sie das Format ab, indem Sie einen API-Aufruf an /api/instances/{instanceId}/manage/entities/UnifiedActivity senden.

Details zu dieser API, einschließlich Parameter und Antworten, finden Sie im Abschnitt **EntityData** auf der [Customer Insights APIs-Referenz](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Weitere Informationen finden Sie unter [Arbeiten mit Customer Insights APIs](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Verstehen Sie Ihre Echtzeit-Nutzung mit Telemetrie

Erhalten Sie einen Überblick über das Volumen der Anfragen an die Echtzeit-API und Informationen über mögliche Probleme des Systems. Sie können [auf die Echtzeit-Telemetrie zugreifen](system.md#api-usage-tab). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]