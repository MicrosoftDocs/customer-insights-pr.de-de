---
title: Anreichern von vereinheitlichten Kundenprofilen
description: Verwenden Sie Funktionalitäten, um Ihre Kundendaten anzureichern.
ms.date: 07/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: d12c0a9dd65d31f9ae8a9cafeafab2767d57893e
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555260"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Anreicherung für Kundenprofile (Vorschau)

Nutzen Sie Daten aus Quellen wie Microsoft und anderen Partnern zur Anreicherung Ihrer Kundendaten.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Enrichment Hub-Seite.":::

Gehen Sie in Zielgruppen-Insights zu **Daten** > **Anreicherung**, um mit Anreicherungsoptionen zu arbeiten.  

Um Anreicherungen erstellen oder bearbeiten zu können, benötigen Sie die Berechtigungen eines Teilnehmers oder Administrators. Weitere Informationen finden Sie unter [Berechtigungen](permissions.md).

Auf der Registerkarte **Entdecken** finden Sie die folgenden Anreicherungen:

- [Marken](enrichment-microsoft.md) bereitgestellt von Microsoft
- [Interessen](enrichment-microsoft.md) bereitgestellt von Microsoft
- [Erweiterte Adressen](enrichment-enhanced-addresses.md) bereitgestellt von Microsoft
- [Unternehmensdaten](enrichment-leadspace.md) werden von Leadspace bereitgestellt
- [Demografiedaten](enrichment-experian.md) von Experian bereitgestellt
- [Standortdaten](enrichment-here.md), bereitgestellt von HERE Technologies
- [Kundendaten](enrichment-SFTP-custom-import.md) über Secure File Transfer Protocol (SFTP)

Auf der Registerkarte **Meine Anreicherungen** können Sie die von Ihnen konfigurierten Anreicherungen sehen und ihre Eigenschaften bearbeiten.

## <a name="manage-existing-enrichments"></a>Vorhandene Anreicherungen verwalten

Gehen Sie zur Registerkarte **Meine Anreicherungen**, um alle konfigurierten Anreicherungen anzuzeigen. Jede Anreicherung wird als Zeile dargestellt, die zusätzliche Informationen zur Anreicherung enthält.

Wählen Sie die Anreicherung aus, um die verfügbaren Optionen anzuzeigen. Sie können auch die Auslassungspunkte (...) in einem Listenelement auswählen, um die Optionen anzuzeigen. Wenn Sie mehrere Anreicherungen konfiguriert haben, finden Sie diese schnell über das Suchfeld.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Optionen zum Verwalten von Anreicherungen in der Liste der Anreicherungen.":::

- **Anzeige** von Anreicherungsdetails mit der Anzahl der angereicherten Kundenprofile.
- **Bearbeiten** der Anreicherungskonfiguration.
- **Ausführen** der Bereicherung, um Kundenprofile mit den neuesten Daten zu aktualisieren.
- **Deaktivieren** einer vorhandenen Anreicherung, um zu verhindern, dass sie bei jeder geplanten Aktualisierung automatisch aktualisiert wird. Die Daten der letzten erfolgreichen Aktualisierung sind weiterhin verfügbar. **Aktivieren** eine inaktiven Anreicherung, um die automatische Aktualisierung bei jeder geplanten Aktualisierung neu zu starten.
- **Löschen** Sie die Anreicherung.

Führen Sie mehrere Anreicherungen gleichzeitig aus oder deaktivieren Sie sie, indem Sie sie in der Liste auswählen. Ansichts- und Bearbeitungsoptionen sind nicht als Massenaktion verfügbar. Sie funktionieren jeweils nur für eine Anreicherung.

## <a name="enrichments-and-connections"></a>Anreicherungen und Verbindungen

Anreicherungen von Drittanbietern werden mithilfe von [Verbindungen](connections.md) konfiguriert, die ein Administrator mit Anmeldeinformationen einrichtet und die Zustimmung zur Datenübertragung erteilt. Die Verbindung kann dann von Administratoren und Mitwirkenden zur Anreicherungskonfiguration verwendet werden.  

## <a name="multiple-enrichments-of-the-same-type"></a>Mehrfachanreicherungen des gleichen Typs

Die zu bereichernde Entität wird während der Anreicherungskonfiguration angegeben, sodass Sie nur eine Teilmenge Ihrer Profile anreichern können. Anreichern von Daten beispielsweise nur für ein bestimmtes Segment. Sie können mehrere Anreicherungen desselben Typs konfigurieren und dieselbe Verbindung wiederverwenden. Bei einigen Anreicherungen ist die Anzahl der Anreicherungen desselben Typs, die erstellt werden können, begrenzt. Die Grenzwerte und die aktuelle Verwendung sind auf der Seite **Anreicherung** zu sehen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
