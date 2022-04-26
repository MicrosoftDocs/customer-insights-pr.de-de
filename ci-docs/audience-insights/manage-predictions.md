---
title: Geteilte Aufgaben für Vorhersageszenarien
description: Erfahren Sie, wie Sie Vorhersagen verwalten, Fehler beheben und verfeinern.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8ff8d70ffb8489def072e5d8a6e43d062594141a
ms.sourcegitcommit: 696ad9ab6e10046c00f1ac86a7e8fc37386e6fe7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2022
ms.locfileid: "8555312"
---
# <a name="manage-predictions"></a>Verwalten von Vorhersagen

In diesem Artikel werden einige Aufgaben behandelt, die die meisten Vorhersageszenarien teilen.

## <a name="troubleshoot-a-failed-prediction"></a>Fehlersuche bei einer fehlgeschlagenen Vorhersage

1. Gehen Sie zu **Intelligenz** > **Vorhersagen** und wählen Sie die Registerkarte **Meine Vorhersagen**.

1. Wählen Sie die vertikalen Auslassungspunkte neben der Vorhersage, für die Sie Fehlerprotokolle anzeigen möchten.

1. Wählen Sie **Logs**.

1. Überprüfen Sie alle Fehler. Es gibt verschiedene Arten von Fehlern, die auftreten können, und sie beschreiben, welcher Zustand den Fehler verursacht hat. Beispielsweise wird ein Fehler, für den nicht genügend Daten zur genauen Vorhersage vorhanden sind, in der Regel dadurch behoben, dass zusätzliche Daten in Customer Insights geladen werden.

## <a name="input-data-usability-report"></a>Eingabedaten-Nutzungsbericht

Der Eingabedaten-Nutzungsbericht bietet eine konsolidierte Ansicht der Fehler und Warnungen, die Ihre sofort einsatzbereiten Vorhersagen generieren. Er gibt auch Empfehlungen zur Verbesserung der Modellleistung.

Der Bericht ist verfügbar, nachdem ein Modell seinen Trainingsprozess abgeschlossen hat. Er wird für jedes Modell separat erstellt, unabhängig davon, ob es erfolgreich abgeschlossen wurde oder nicht.

### <a name="view-the-input-data-usability-report"></a>Anzeigen des Eingabedaten-Nutzungsberichts

Nachdem ein sofort einsatzbereites Modell seinen Trainingsschritt abgeschlossen hat, zeigen Sie den Bericht an:
- Wählen Sie die Auslassungspunkte neben dem Modellnamen aus und wählen Sie dann **Eingabedaten-Nutzungsbericht** aus.
- Wählen Sie den Status eines Modells aus. Wählen Sie **Eingabedaten-Nutzungsbericht anzeigen** im Seitenbereich aus.
- Wählen Sie eines der Modelle in der Liste aus und wählen Sie dann **Eingabedaten-Nutzungsbericht** in der Befehlsleiste aus.
- Öffnen Sie Modellergebnisseite und wählen Sie **Eingabedaten-Nutzungsbericht** in der Befehlsleiste aus.

### <a name="information-in-the-input-data-usability-report"></a>Im Eingabedaten-Nutzungsbericht enthaltene Informationen

Die folgenden Spalten im Bericht enthalten hilfreiche Informationen zur Verbesserung der Daten für das Modell.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Beispiel für einen Eingabedaten-Nutzungsbericht mit einer Tabelle mit Fehlern, Warnungen und Empfehlungen.":::

- **Name:** Ein beschreibender Name des Fehlers, der Warnung oder der Empfehlung.
- **Schritt:** Modellphase, Training oder Bewertung, auf die sich die Informationen beziehen.
- **Status:** Der Schweregrad der Information (Fehler, Warnung, Empfehlung).
- **Spaltenname:** Eine Spalte in einer Entität, die geändert werden muss, um die Modellleistung zu verbessern.
- **Entitätsname:** Der Name der Entität, die geändert werden muss, um die Modellleistung zu verbessern.
- **Details:** Details zu Fehlern, Warnungen oder Empfehlungen.

## <a name="refresh-a-prediction"></a>Aktualisieren einer Vorhersage

Vorhersagen werden automatisch zum gleichen [Zeitpunkt aktualisiert, zu dem Ihre Daten aktualisiert werden](system.md#schedule-tab), wie in den Einstellungen konfiguriert. Sie können sie auch manuell aktualisieren.

1. Gehen Sie zu **Intelligenz** > **Vorhersagen** und wählen Sie die Registerkarte **Meine Vorhersagen**.

1. Wählen Sie die vertikalen Auslassungspunkte neben der Vorhersage, die Sie aktualisieren möchten.

1. Wählen Sie **Aktualisieren** aus.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="delete-a-prediction"></a>Löschen einer Vorhersage

Das Löschen einer Vorhersage entfernt auch deren Ausgabe-Entität.

1. Gehen Sie zu **Intelligenz** > **Vorhersagen** und wählen Sie die Registerkarte **Meine Vorhersagen**.

1. Wählen Sie die vertikalen Auslassungspunkte neben der Vorhersage, die Sie löschen möchten.

1. Klicken Sie auf **Löschen**.
