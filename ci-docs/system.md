---
title: Systemkonfiguration
description: Erfahren Sie mehr über die Systemeinstellungen in Dynamics 365 Customer Insights.
ms.date: 04/21/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-schedule
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 0ef84d8e286d8135eb8938e72f1319925e948bed
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050670"
---
# <a name="system-configuration"></a>Systemkonfiguration

Um auf die Systemkonfigurationen zuzugreifen, gehen Sie zu **Admin** > **System**, um eine Liste der Systemaufgaben und -prozesse anzuzeigen.

Die Seite **System** enthält die folgenden Registerkarten:
- [Status](#status-tab)
- [Zeitplan](#schedule-tab)
- [API-Verwendung](#api-usage-tab)
- [Info](#about-tab)
- [Allgemein](#general-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Registerkarten für Einstellungen auf der Systemseite.":::

## <a name="status-tab"></a>Registerkarte „Status“

Die **Status-Registerkarte** lässt Sie den Fortschritt von Aufgaben, Datenerfassungen, Datenexporten und mehreren anderen wichtigen Produktprozessen nachverfolgen. Überprüfen Sie die Informationen auf dieser Registerkarte, um die Vollständigkeit Ihrer aktiven Aufgaben und Prozesse sicherzustellen.

Diese Registerkarte enthält Tabellen mit Status- und Verarbeitungsinformationen für verschiedene Prozesse. Jede Tabelle verfolgt den **Name** der Aufgabe und ihrer entsprechenden Entität, den **Status** ihres letzten Laufs und wann die **Letzte Aktualisierung** war. Sie können die Details mehrerer letzter Ausführungen anzeigen, indem Sie den Aufgaben- oder Prozessnamen auswählen. 

Wählen Sie den Status neben der Aufgabe oder dem Prozess in der Spalte **Status** aus, um den Bereich **Fortschrittsdetails** zu öffnen.

   :::image type="content" source="media/system-progress-details.png" alt-text="Bereich mit den Details zum Systemfortschritt":::

### <a name="status-definitions"></a>Statusdefinitionen

Das System verwendet folgende Status für Aufgaben und Prozesse:

|Status  |Definition  |
|---------|---------|
|Storniert |Die Verarbeitung wurde vom Benutzer abgebrochen, bevor sie abgeschlossen wurde.   |
|Fehlerhaft   |Bei der Dateneingabe sind Fehler aufgetreten.         |
|Fehler  |Die Verarbeitung ist fehlgeschlagen.  |
|Nicht begonnen   |Die Datenquelle hat noch keine Datenerfassung oder ist noch im Entwurfsmodus.         |
|Wird verarbeitet...  |Aufgabe oder Prozess wird ausgeführt.  |
|Wird aktualisiert    |Die Datenaufnahme ist im Gange. Sie können diesen Vorgang abbrechen, indem Sie **Aktualisierung beenden** in der Spalte **Aktionen** wählen. Wenn Sie die Aktualisierung einer Datenquelle stoppen, wird der letzte Aktualisierungsstatus wiederhergestellt.       |
|Übersprungen  |Aufgabe oder Prozess wurde übersprungen. Einer oder mehrere der nachgelagerten Prozesse, von denen diese Aufgabe abhängt, sind fehlgeschlagen oder wurden übersprungen.|
|Erfolgreich  |Aufgabe oder Prozess wurde erfolgreich abgeschlossen. Gibt bei Datenquellen an, dass die Daten erfolgreich aufgenommen wurden, wenn eine Zeit in der Spalte **Aktualisiert** angegeben ist.|
|In Warteschlange | Die Verarbeitung wird in die Warteschlange gestellt und beginnt, sobald alle Upstream-Aufgaben und -Prozesse abgeschlossen sind. Weitere Informationen finden Sie unter [Prozesse aktualisieren](#refresh-processes).|

### <a name="refresh-processes"></a>Prozesse aktualisieren

Die Aktualisierung für Aufgaben und Prozesse wird gemäß dem [konfigurierten Zeitplan](#schedule-tab) ausgeführt. 

|Verarbeiten  |Beschreibung  |
|---------|---------|
|Aktivität  |Wird manuell ausgeführt (einmalige Aktualisierung). Hängt vom Zusammenführungsprozess ab. Erkenntnisse hängen von der Verarbeitung ab.|
|Analyseverknüpfung |Wird manuell ausgeführt (einmalige Aktualisierung). Hängt von Segmenten ab.  |
|Analysevorbereitung |Wird manuell ausgeführt (einmalige Aktualisierung). Hängt von Segmenten ab.  |
|Datenvorbereitung   |Benötigt eine Entität zum Ausführen. Entitäten der Datenquelle hängen von der Einbindung ab. Angereicherte Entitäten hängen von Anreicherungen ab. Die Entität Kunde hängt von der Zusammenführung ab.  |
|Datenquellen   |Sie hängt von keinem anderen Prozess ab. Der Abgleich hängt vom erfolgreichen Abschluss dieses Prozesses ab.  |
|Anreicherungen   |Wird manuell ausgeführt (einmalige Aktualisierung). Hängt vom Zusammenführungsprozess ab. |
|Ziele für Exporte |Wird manuell ausgeführt (einmalige Aktualisierung). Hängt von Segmenten ab.  |
|Insights |Wird manuell ausgeführt (einmalige Aktualisierung). Hängt von Segmenten ab.  |
|Intelligenz   |Hängt von der Zusammenführung ab.   |
|Abgleichen |Hängt von der Verarbeitung der in der Abgleichdefinition verwendeten Datenquellen ab.      |
|Measures  |Wird manuell ausgeführt (einmalige Aktualisierung). Hängt vom Zusammenführungsprozess ab.  |
|Zusammenführen   |Hängt vom Abschluss des Abgleichvorgangs ab. Segmente, Kennzahlen, Anreicherung, Suchen, Aktivitäten, Vorhersagen und Datenaufbereitung hängen vom erfolgreichen Abschluss dieses Prozesses ab.   |
|Profile   |Wird manuell ausgeführt (einmalige Aktualisierung). Hängt vom Zusammenführungsprozess ab. |
|Search   |Wird manuell ausgeführt (einmalige Aktualisierung). Hängt vom Zusammenführungsprozess ab. |
|Segmente  |Wird manuell ausgeführt (einmalige Aktualisierung). Hängt vom Zusammenführungsprozess ab. Erkenntnisse hängen von der Verarbeitung ab.|
|System   |Hängt vom Abschluss des Abgleichvorgangs ab. Segmente, Kennzahlen, Anreicherung, Suchen, Aktivitäten, Vorhersagen und Datenaufbereitung hängen vom erfolgreichen Abschluss dieses Prozesses ab.   |
|User  |Wird manuell ausgeführt (einmalige Aktualisierung). Abhängig von Entitäten.  |

Wählen Sie den Status eines Prozesses aus, um die Fortschrittsdetails des gesamten Auftrags anzuzeigen, in dem er sich befand. Die oben genannten Aktualisierungsprozesse können Ihnen helfen zu verstehen, was Sie tun können, um eine Aufgabe oder einen Prozess mit dem Status **Übersprungen** oder **In Warteschlange** zu behandeln.

## <a name="schedule-tab"></a>Registerkarte „Zeitplan“

Verwenden Sie die Registerkarte **Zeitplan**, um automatische Aktualisierungen aller Ihrer [eingespeicherten Datenquellen](data-sources.md) zu planen. Automatische Aktualisierungen sorgen dafür, dass Aktualisierungen aus Ihren Datenquellen in Ihren einheitlichen Kundenprofilen berücksichtigt werden.

> [!NOTE]
> Von Ihnen verwaltete Datenquellen werden nach ihren eigenen Zeitplänen aktualisiert. Um die Aktualisierung der von Ihnen verwalteten Datenquellen zu planen, konfigurieren Sie die Aktualisierungseinstellungen für dieses bestimmte Datenquelle über die Seite **Datenquellen**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Dataflow-Aktualisierungseinstellungen.":::

1. Gehen Sie zu **Admin** > **System** und wählen Sie die Registerkarte **Planung**.

2. Der Standardstatus für die geplante Aktualisierung ist **Aus**. Um die zeitgesteuerte Aktualisierung zu aktivieren, ändern Sie den Schalter am oberen Bildschirmrand auf **Ein**.

3. Wählen Sie zwischen **Wöchentlich** (Standard) und **Täglich** Aktualisierung. Wenn Sie beabsichtigen, wöchentliche Aktualisierungen zu planen, wählen Sie einen oder mehrere Tage aus, an denen Sie die Aktualisierung ausführen möchten.

4. Stellen Sie Ihre **Zeitzone** ein und verwenden Sie dann die Dropdown-Liste **Zeit**, um Ihr Aktualisierungs-Timing einzustellen. Wenn Sie fertig sind, wählen Sie **Festlegen**. Wenn Sie mehrere Aktualisierungen an einem einzigen Tag planen möchten, wählen Sie **Andere Zeit hinzufügen**.

5. Wählen Sie **Speichern**, um Ihre Änderungen zu übernehmen.

## <a name="about-tab"></a>"Über" Registerkarte

Die Registerkarte **Info** enthält den **Displaynamen** Ihrer Organisation, die aktive **Umgebungs-ID**, die **Region** und Ihre **Sitzungs-ID**. Wenn Sie mehr als eine Arbeitsumgebung haben, sollten Sie jeder einen leicht identifizierbaren Anzeigenamen geben.

## <a name="general-tab"></a>Registerkarte „Allgemein“

Sie können die Sprache und das Länder-/Regionsformat auf der **Allgemein**-Registerkarte ändern.

Customer Insights [unterstützt viele Sprachen](/dynamics365/get-started/availability). Die App verwendet Ihre Spracheinstellung, um Elemente wie das Menü, Label-Text und Systemmeldungen in Ihrer bevorzugten Sprache anzuzeigen.

Importierte Daten und Informationen, die Sie manuell eingegeben haben, werden nicht übersetzt.

### <a name="update-the-settings"></a>Einstellungen aktualisieren

Um Ihre bevorzugte Sprache zu ändern, wählen Sie eine **Sprache** aus der Dropdownliste aus.

Verwenden Sie die Dropdownliste **Format für Land/Region**, um Ihre bevorzugte Formatierung für Datum, Uhrzeit und Zahlen zu ändern. Unter diesem Feld wird eine Formatierungsvorschau angezeigt. Das System wird automatisch eine Auswahl vorschlagen, wenn Sie eine neue Sprache wählen.

Wählen Sie **Speichern**, um Ihre Auswahl zu bestätigen.

## <a name="api-usage-tab"></a>Registerkarte API-Nutzung

Finden Sie Details zur Echtzeit-API-Verwendung und sehen Sie, welche Ereignisse in einem bestimmten Zeitrahmen aufgetreten sind. Sie wählen die Zeitrahmen im Dropdown-Menü **Wählen Sie einen Zeitrahmen**. 

Die **API-Nutzung** enthält drei Abschnitte: 
- **API-Aufrufe** – Ein Diagramm, das die aggregierte Anzahl der Aufrufe der API im ausgewählten Zeitrahmen anzeigt.

- **Datentransfer** – Ein Diagramm, das die Datenmenge zeigt, die über die API im ausgewählten Zeitrahmen übertragen wurde.

-  **Operationen** – eine Tabelle mit Zeilen für jede verfügbare API-Operation und Details zur Verwendung der Operationen. Sie können einen Operationsnamen auswählen, um zur [API-Referenz](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) zu wechseln.

   Vorgänge, die [Echtzeit-Datenerfassung](real-time-data-ingestion.md) verwenden, enthalten eine Schaltfläche mit einem Fernglassymbol, um die API-Nutzung in Echtzeit anzuzeigen. Wählen Sie die Schaltfläche, um einen Seitenbereich mit Nutzungsdetails für die Echtzeit-API-Nutzung in der aktuellen Umgebung zu öffnen.   
   Verwenden Sie das Feld **Gruppieren nach** im Bereich **Echtzeit-API-Nutzung**, in dem Sie auswählen können, wie Sie Ihre Echtzeitinteraktionen am besten präsentieren möchten. Sie können die Daten nach API-Methode, qualifiziertem Namen der Entität (aufgenommene Entität), erstellt von (Quelle des Ereignisses), Ergebnis (Erfolg oder Misserfolg) oder Fehlercodes gruppieren. Die Daten stehen als Historiendiagramm und als Tabelle zur Verfügung.


[!INCLUDE [footer-include](includes/footer-banner.md)]
