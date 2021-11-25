---
title: Neue Umgebung erstellen
description: Der Zweck einer Umgebung und wie Sie eine Neue erstellen.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 8ff04a6b2ffbd513a77f7f8a33358f3d8f559c7e
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673641"
---
# <a name="create-a-new-environment"></a>Neue Umgebung erstellen 

## <a name="overview"></a>Überblick

Eine Umgebung ist ein Bereich, in dem Sie Ihre Arbeitsbereiche und Verbindungen verwalten. Wie Sie Umgebungen nutzen, hängt von Ihrer Organisation und Ihrem Anwendungsfall ab. So können beispielsweise Folgendes erstellen:

- Eine einzelne Umgebung.
- Separate Test- und Produktionsumgebungen.
- Separate Umgebungen für bestimmte Teams oder Abteilungen in Ihrer Organisation, die relevante Ereignisse für jede Zielgruppe enthalten.
- Separate Umgebungen für verschiedene Niederlassungen Ihres Unternehmens.
- Verbindungen zur Funktion Zielgruppenerkenntnisse von Customer Insights.

## <a name="create-a-new-environment"></a>Neue Umgebung erstellen

1. Wählen Sie auf der rechten Seite des Hauptbanners die Umgebungsauswahl und dann **+Neu**.

   :::image type="content" source="media/environment-picker.png" alt-text="Wählen Sie die Umgebung aus.":::

1. In dem Bereich **Einrichten** geben Sie einen **Umgebungsnamen** ein.

1. Wählen Sie den **Typ** des Kontos aus, abhängig von Ihrem Plantyp.

1. Wählen Sie die **Region** und dann **Weiter** aus. 

1. Geben Sie einen **Arbeitsbereichsnamen** ein, mit dem Sie Daten für bestimmte Websites oder Apps sammeln können. Weitere Informationen finden Sie unter [Einen Arbeitsbereich erstellen](create-workspace.md).

1. Wählen Sie den **Arbeitsbereichstyp** (Web oder Mobil) aus, den Sie erstellen möchten. 

1. Wählen Sie **Erweiterte Einstellungen anzeigen**, um diese optionalen Einstellungen zu aktivieren oder zu deaktivieren:

   - Umschalten von **Unbekannt bis bekannt** auf aktiviert, um Webereignisse mit Benutzern zu verknüpfen, die sich zuvor authentifiziert haben. Weitere Informationen finden Sie unter [Erkennen Sie Webereignisse von zuvor authentifizierten Besuchern](unknown-to-known.md).
   - Umschalten von **Bot-Verkehr filtern** auf aktiviert, um den Webverkehr von Bots für diesen Arbeitsbereich zu entfernen. 

1. Wählen Sie **Abgeschlossen** aus, wenn Sie fertig sind. 

1. Installieren Sie den Codeausschnitt, um mit dem Empfang von Daten zu beginnen, und wählen Sie dann **Beenden**, um den Arbeitsbereich zu erstellen. Weitere Informationen finden Sie unter [Entwicklerressourcenübersicht](developer-resources.md).

> [!NOTE]
> Sie können jetzt Mitglieder hinzufügen und deren Berechtigungsstufe aus der Liste **Rolle** zuweisen. Weitere Informationen finden Sie unter [Rollen und Berechtigungen](user-roles.md). 

Weitere Informationen finden Sie unter [Verwalten von Umgebungen und Arbeitsbereichen](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Arbeiten Sie mit Ihrer neuen Umgebung

- [Erstellen Sie einen Arbeitsbereich](../engagement-insights/create-workspace.md) und fügen Sie Mitglieder hinzu.
- [Code zu Ihrer Website](../engagement-insights/instrument-website.md) oder [mobilen App](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps) hinzufügen.
- Einen [Echtzeitbericht](../engagement-insights/view-reports.md) anzeigen oder [benutzerdefinierte Berichte](../engagement-insights/custom-reports.md) erstellen.
- [Erstellen Sie verfeinerte Ereignisse](../engagement-insights/refined-events.md) für den Export.
- [Exportieren Sie die Daten](../engagement-insights/export-events.md) nach Data Lake Store.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
