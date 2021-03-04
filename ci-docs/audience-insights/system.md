---
title: Systemkonfiguration in Zielgruppen-Insights
description: Lernen Sie die Systemeinstellungen der Dynamics 365 Customer Insights-Zielgruppen-Insights Funktionalität kennen.
ms.date: 02/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: a9c9e258da49b8f452550794539962d48b856829
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267339"
---
# <a name="system-configuration"></a>Systemkonfiguration

Die Seite **System** enthält die folgenden Registerkarten:
- [Status](#status-tab)
- [Zeitplan](#schedule-tab)
- [API-Verwendung](#api-usage-tab)
- [Info](#about-tab)
- [Allgemein](#general-tab)

> [!div class="mx-imgBorder"]
> ![Systemseite](media/system-tabs.png "System-Seite")

## <a name="status-tab"></a>Registerkarte „Status“

Auf der **Registerkarte Status** können Sie den Fortschritt der Datenaufnahme, des Datenexports und mehrerer anderer wichtiger Produktprozesse verfolgen. Überprüfen Sie die Informationen auf dieser Registerkarte, um die Vollständigkeit der aktiven Prozesse sicherzustellen.

Diese Registerkarte enthält Tabellen mit Status- und Verarbeitungsinformationen für verschiedene Prozesse. Jede Tabelle verfolgt den **Name** der Aufgabe und ihrer entsprechenden Entität, den **Status** ihres letzten Laufs und wann die **Letzte Aktualisierung** war.

Zeigen Sie die Details der letzten Durchläufe der Aufgaben an, indem Sie ihren Namen auswählen.

### <a name="status-types"></a>Statustypen

Es gibt sechs Arten von Status für Aufgaben. Die folgenden Statustypen werden auch auf den Seiten *Abgleichen*, *Zusammenführen*, *Datenquellen*, *Segmente*, *Maßnahmen*, *Anreicherung*, *Aktivitäten* und *Vorhersagen* angezeigt:

- **Wird bearbeitet:** Aufgabe ist in Bearbeitung. Der Status kann in „Erfolgreich“ oder „Fehlgeschlagen“ geändert werden.
- **Erfolgreich:** Aufgabe erfolgreich abgeschlossen.
- **Übersprungen:** Aufgabe wurde übersprungen. Einer oder mehrere der nachgelagerten Prozesse, von denen diese Aufgabe abhängt, sind fehlgeschlagen oder wurden übersprungen.
- **Fehler:** Die Verarbeitung der Aufgabe ist fehlgeschlagen.
- **Abgebrochen:** Die Verarbeitung wurde vom Benutzer abgebrochen, bevor sie abgeschlossen war.
- **In Warteschlange:** Die Verarbeitung wird in die Warteschlange gestellt und gestartet, sobald alle vorgelagerten Aufgaben abgeschlossen sind. Weitere Informationen finden Sie in den [Aktualisierungsrichtlinien](#refresh-policies).

### <a name="refresh-policies"></a>Aktualisierungsrichtlinien

Diese Liste zeigt die Aktualisierungsrichtlinien für jeden der Hauptprozesse:

- **Datenquellen:** Läuft nach dem [konfigurierten Zeitplan](#schedule-tab). Sie hängt von keinem anderen Prozess ab. Der Abgleich hängt vom erfolgreichen Abschluss dieses Prozesses ab.
- **Abgleich:** Läuft nach dem [konfigurierten Zeitplan](#schedule-tab). Hängt von der Verarbeitung der in der Abgleichdefinition verwendeten Datenquellen ab. Die Zusammenführung hängt vom erfolgreichen Abschluss dieses Prozesses ab.
- **Zusammenführen:** Läuft nach dem [konfigurierten Zeitplan](#schedule-tab). Hängt vom Abschluss des Abgleichvorgangs ab. Segmente, Kennzahlen, Anreicherung, Suchen, Aktivitäten, Vorhersagen und Datenaufbereitung hängen vom erfolgreichen Abschluss dieses Prozesses ab.
- **Segmente**: Läuft manuell (einmalige Aktualisierung) und gemäß dem [konfigurierten Zeitplan](#schedule-tab). Hängt von der Zusammenführung ab. Erkenntnisse hängen von der Verarbeitung ab.
- **Kennzahlen**: Läuft manuell (einmalige Aktualisierung) und gemäß dem [konfigurierten Zeitplan](#schedule-tab). Hängt von der Zusammenführung ab.
- **Aktivitäten**: Läuft manuell (einmalige Aktualisierung) und gemäß dem [konfigurierten Zeitplan](#schedule-tab). Hängt von der Zusammenführung ab.
- **Anreicherung**: Läuft manuell (einmalige Aktualisierung) und gemäß dem [konfigurierten Zeitplan](#schedule-tab). Hängt von der Zusammenführung ab.
- **Suchen**: Läuft manuell (einmalige Aktualisierung) und gemäß dem [konfigurierten Zeitplan](#schedule-tab). Hängt von der Zusammenführung ab.
- **Datenaufbereitung:** Läuft nach dem [konfigurierten Zeitplan](#schedule-tab). Hängt von der Zusammenführung ab.
- **Erkenntnisse**: Läuft manuell (einmalige Aktualisierung) und gemäß dem [konfigurierten Zeitplan](#schedule-tab). Kommt auf Segmente an.

Wählen Sie den Status einer Aufgabe aus, um die Fortschrittsdetails des gesamten Auftrags anzuzeigen, in dem sie ausgeführt wurde. Die oben genannten Aktualisierungsrichtlinien können Ihnen dabei helfen, zu verstehen, wie Sie eine Aufgabe von **Übersprungen** oder **In Warteschlange** angehen können.

## <a name="schedule-tab"></a>Registerkarte "Zeitplan

Verwenden Sie die Registerkarte **Zeitplan**, um automatische Aktualisierungen aller Ihrer [eingespeicherten Datenquellen](data-sources.md) zu planen. Automatische Aktualisierungen sorgen dafür, dass Aktualisierungen aus Ihren Datenquellen in Ihren einheitlichen Kundenprofilen berücksichtigt werden.

1. Gehen Sie in den Zielgruppen-Insights zu **Admin** > **System** und wählen Sie die Registerkarte **Zeitplan**.

2. Der Standardstatus für die geplante Aktualisierung ist **Aus**. Um die zeitgesteuerte Aktualisierung zu aktivieren, ändern Sie den Schalter am oberen Bildschirmrand auf **Ein**.

3. Wählen Sie zwischen **Wöchentlich** (Standard) und **Täglich** Aktualisierung. Wenn Sie beabsichtigen, wöchentliche Aktualisierungen zu planen, wählen Sie einen oder mehrere Tage aus, an denen Sie die Aktualisierung ausführen möchten.

4. Stellen Sie Ihre **Zeitzone** ein und verwenden Sie dann die Dropdown-Liste **Zeit**, um Ihr Aktualisierungs-Timing einzustellen. Wenn Sie fertig sind, wählen Sie **Festlegen**. Wenn Sie mehrere Aktualisierungen an einem einzigen Tag planen möchten, wählen Sie **Andere Zeit hinzufügen**.

5. Wählen Sie **Speichern**, um Ihre Änderungen zu übernehmen.

## <a name="about-tab"></a>"Über" Registerkarte

Die Registerkarte **Info** enthält den **Displaynamen** Ihrer Organisation, die aktive **Umgebungs-ID**, die **Region** und Ihre **Sitzungs-ID**. Wenn Sie mehr als eine Arbeitsumgebung haben, sollten Sie jeder einen leicht identifizierbaren Anzeigenamen geben.

## <a name="general-tab"></a>Registerkarte „Allgemein“

Es gibt zwei Optionen auf der Registerkarte **Allgemein**: **Sprache** und **Format für Land/Region**.

Die App [unterstützt eine Reihe von Sprachen](supported-languages.md). Um Ihre bevorzugte Sprache zu ändern, wählen Sie eine **Sprache** aus der Dropdownliste aus.

Verwenden Sie die Dropdownliste **Format für Land/Region**, um Ihre bevorzugte Formatierung für Datum, Uhrzeit und Zahlen zu ändern. Unter diesem Feld wird eine Formatierungsvorschau angezeigt. Das System wird automatisch eine Auswahl vorschlagen, wenn Sie eine neue Sprache wählen.

Wählen Sie **Speichern**, um Ihre Auswahl zu bestätigen.

## <a name="api-usage-tab"></a>Registerkarte API-Nutzung

Finden Sie Details zur Echtzeit-API-Verwendung und sehen Sie, welche Ereignisse in einem bestimmten Zeitrahmen aufgetreten sind. Sie wählen den Zeitrahmen im Dropdownmenü **Einen Zeitrahmen auswählen** aus. 

Die **API-Nutzung** enthält drei Abschnitte: 
- **API-Aufrufe** – Ein Diagramm, das die aggregierte Anzahl der Aufrufe der API im ausgewählten Zeitrahmen anzeigt.

- **Datentransfer** – Ein Diagramm, das die Datenmenge zeigt, die über die API im ausgewählten Zeitrahmen übertragen wurde.

-  **Operationen** – eine Tabelle mit Zeilen für jede verfügbare API-Operation und Details zur Verwendung der Operationen. Sie können einen Operationsnamen auswählen, um zur [API-Referenz](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) zu wechseln.

   Operationen, die [Datenerfassung in Echtzeit](real-time-data-ingestion.md) verwenden, enthalten eine Schaltfläche mit einem Fernglas-Symbol, um die API-Nutzung in Echtzeit anzuzeigen. Wählen Sie die Schaltfläche, um einen Seitenbereich mit Nutzungsdetails für die Echtzeit-API-Nutzung in der aktuellen Umgebung zu öffnen.   
   Verwenden Sie das Feld **Gruppieren nach** im Bereich **Echtzeit-API-Nutzung**, in dem Sie auswählen können, wie Sie Ihre Echtzeitinteraktionen am besten präsentieren möchten. Sie können die Daten nach API-Methode, qualifiziertem Namen der Entität (aufgenommene Entität), erstellt von (Quelle des Ereignisses), Ergebnis (Erfolg oder Misserfolg) oder Fehlercodes gruppieren. Die Daten stehen als Historiendiagramm und als Tabelle zur Verfügung.


[!INCLUDE[footer-include](../includes/footer-banner.md)]