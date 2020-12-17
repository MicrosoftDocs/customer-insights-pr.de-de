---
title: Anreichern von vereinheitlichten Kundenprofilen
description: Verwenden Sie Funktionalitäten, um Ihre Kundendaten anzureichern.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667093"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Anreicherung für Kundenprofile (Vorschau)

Nutzen Sie Daten aus Quellen wie Microsoft und anderen Partnern zur Anreicherung Ihrer Kundendaten.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Enrichment Hub-Seite":::

Gehen Sie in Zielgruppen-Insights zu **Daten** > **Anreicherung**, um mit Anreicherungsoptionen zu arbeiten.    
Um Anreicherungen erstellen oder bearbeiten zu können, benötigen Sie die Berechtigungen eines Teilnehmers oder Administrators. Weitere Informationen finden Sie unter [Berechtigungen](permissions.md).

Auf der Registerkarte **Entdecken** finden Sie die folgenden Anreicherungen:

- [Marken](enrichment-microsoft-graph.md) bereitgestellt von Microsoft Graph
- [Interessen](enrichment-microsoft-graph.md) bereitgestellt von Microsoft Graph
- [Unternehmensdaten](enrichment-leadspace.md) werden von Leadspace bereitgestellt
- [Demografische Daten](enrichment-experian.md) bereitgestellt von Experian
- [Standortdaten](enrichment-here.md), bereitgestellt von HERE Technologies
- [Kundendaten](enrichment-SFTP-custom-import.md) über Secure File Transfer Protocol (SFTP)

Auf der Registerkarte **Meine Anreicherungen** können Sie die von Ihnen konfigurierten Anreicherungen sehen und ihre Eigenschaften bearbeiten.

## <a name="manage-existing-enrichments"></a>Vorhandene Anreicherungen verwalten

Gehen Sie zu **Meine Anreicherungen**, um alle konfigurierten Anreicherungen zu sehen. Jede Anreicherung wird als Zeile dargestellt, die zusätzliche Informationen zur Anreicherung enthält.

Wählen Sie eine Anreicherung aus, um die verfügbaren Optionen anzuzeigen. Alternativ können Sie die Auslassungspunkte (...) in einem Listenelement auswählen, um die Optionen anzuzeigen.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Optionen zum Verwalten von Anreicherungen in der Liste der Anreicherungen":::

- **Anzeige** von Anreicherungsdetails mit der Anzahl der angereicherten Kundenprofile.
- **Bearbeiten** der Anreicherungskonfiguration.
- **Ausführen** der Bereicherung, um Kundenprofile mit den neuesten Daten zu aktualisieren.
- **Deaktivieren** einer vorhandenen Anreicherung, um zu verhindern, dass sie bei jeder geplanten Aktualisierung automatisch aktualisiert wird. Die Daten der letzten erfolgreichen Aktualisierung sind weiterhin verfügbar. **Aktivieren** eine inaktiven Anreicherung, um die automatische Aktualisierung bei jeder geplanten Aktualisierung neu zu starten.
- **Löschen** einer Anreicherung.

Sie können mehrere Anreicherungen gleichzeitig ausführen oder deaktivieren, indem Sie sie in der Liste auswählen. Anzeige- und Bearbeitungsoptionen sind nicht als Massenaktion verfügbar und funktionieren jeweils nur für eine Anreicherung.
