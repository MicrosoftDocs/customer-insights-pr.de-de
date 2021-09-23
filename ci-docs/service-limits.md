---
title: Servicelimits in Dynamics 365 Customer Insights
description: Grenzen und Einschränkungen verstehen.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483667"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Servicegrenzen in Customer Insights-Funktionen

Dieser Artikel beschreibt die eingebauten Limits des Customer Insights-Dienstes, die die Zuverlässigkeit und Stabilität des Dienstes sicherstellen sollen. Sämtliche Anfordern von Änderungen können über das [Ideenforum](https://go.microsoft.com/fwlink/?linkid=2074172) vorgenommen werden. 

## <a name="audience-insights"></a>Zielgruppenerkenntnisse

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Service-Limits in Dynamics 365 Customer Insights Zielgruppen-Insights-Funktionalitäten

| Region  | Grenzwerte  | Anmerkungen |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmente und Maßnahmen | 100 Segmente oder Kennzahlen. | Die Gesamtzahl der aktiven [Segmente](audience-insights/segments.md) und [Kennzahlen](audience-insights/measures.md) zusammen kann 100 nicht überschreiten.  |
| Beziehungen | 20 Tiefenstufen für Beziehungen in Entitätspfaden. | Beim Erstellen von [Segmenten](audience-insights/segments.md) oder [Kennzahlen](audience-insights/measures.md) mit der Builder-Schnittstelle können Entitätspfade bis zu 20 Beziehungs-Hops zwischen der Startentität und der Zielentität aufweisen.  |


## <a name="engagement-insights"></a>Interaktionserkenntnisse

### <a name="workspace-and-event-quotas"></a>Arbeitsbereich- und Veranstaltungskontingente

Die Funktion Kundenbindungserkenntnisse ist eine hochgradig skalierbare Anwendung, die Millionen von Ereignissen pro Sekunde unterstützen kann. In der öffentlichen Vorschauversion ist die Menge der Ereignisse begrenzt. Die Anzahl der Arbeitsbereiche in einer Organisation ist ebenfalls begrenzt.

### <a name="engagement-insights-limits"></a>Grenzwerte für die Funktion Kundenbindungserkenntnisse

- Maximale Anzahl an Ereignissen pro Arbeitsbereich = 100 Ereignisse pro Sekunde

- Maximale Anzahl an Arbeitsbereichen pro Organisation = 100

Wenn Ereignisse den Grenzwert überschreiten, kann dies zu Datenverlust in Berichten führen, die auf diesen Ereignissen basieren. Sie können den [Support kontaktieren](https://go.microsoft.com/fwlink/?linkid=2145734), um eine Erhöhung der Anzahl anzufordern, bevor Sie die Grenzwerte überschreiten. Wir werden mit Ihnen zusammenarbeiten, um festzustellen, ob für Sie eine Erhöhung der Anzahl erforderlich ist, und Ihre Anfrage unterstützen.


[!INCLUDE[footer-include](includes/footer-banner.md)]