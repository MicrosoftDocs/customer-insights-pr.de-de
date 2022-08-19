---
title: Systemkonfiguration anzeigen
description: Erfahren Sie mehr über die Systemeinstellungen in Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2498814a3d2e6330124fb97c036b9b310bcf1f7a
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246246"
---
# <a name="view-system-configuration"></a>Systemkonfiguration anzeigen

Anzeigen von Systeminformationen, Systemstatus und API-Nutzung.

## <a name="view-api-usage"></a>API-Nutzung anzeigen

Zeigen Sie Details zur Echtzeit-API-Verwendung an und sehen Sie, welche Ereignisse in einem bestimmten Zeitrahmen aufgetreten sind.

1. Gehen Sie zu **Admin** > **System** und wählen Sie die Registerkarte **API-Nutzung**.

1. Einen **Zeitrahmen auswählen** zum Anzeigen.

   Die Seite **API-Nutzung** enthält drei Abschnitte:

   - **API-Aufrufe** – Ein Diagramm, das die aggregierte Anzahl der Aufrufe der API im ausgewählten Zeitrahmen anzeigt.
   - **Datentransfer** – Ein Diagramm, das die Datenmenge zeigt, die über die API im ausgewählten Zeitrahmen übertragen wurde.
   - **Operationen** – eine Tabelle mit Zeilen für jede verfügbare API-Operation und Details zur Verwendung der Operationen. Wählen Sie einen Operationsnamen aus, um zur [API-Referenz](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) zu wechseln.

   Vorgänge, die [Echtzeit-Datenerfassung](real-time-data-ingestion.md) verwenden, enthalten ein Fernglassymbol, um die API-Nutzung in Echtzeit anzuzeigen.

   1. Wählen Sie das Fernglassymbol aus, um den Bereich mit Nutzungsdetails für die **Echtzeit-API-Nutzung** in der aktuellen Umgebung zu öffnen.
   1. Einen **Zeitrahmen auswählen** zum Anzeigen.
   1. Verwenden Sie das Feld **Gruppieren nach**, in dem Sie auswählen können, wie Sie Ihre Echtzeitinteraktionen am besten präsentieren möchten. Sie können die Daten nach API-**Methode**, **Qualifizierter Name der Entität** (aufgenommene Entität), **Erstellt von** (Quelle des Ereignisses), **Ergebnis** (Erfolg oder Misserfolg) oder **Fehlercodes** gruppieren. Die Daten stehen als Historiendiagramm und als Tabelle zur Verfügung.

## <a name="view-system-information"></a>Systeminformationen anzeigen

Zeigen Sie den Umgebungsanzeigename, ID, Region, Typ und Sitzungs-ID an.

1. Gehen Sie zu **Admin** > **System** und wählen Sie die Registerkarte **Info**.

1. Um die Sprache und das Land/die Region anzuzeigen, wählen Sie die Registerkarte **Allgemein**.

### <a name="update-preferred-language-or-countryregion"></a>Aktualisieren Sie die bevorzugte Sprache oder das Land/die Region

Customer Insights [unterstützt viele Sprachen](/dynamics365/get-started/availability). Die App verwendet Ihre Spracheinstellung, um Elemente wie das Menü, Label-Text und Systemmeldungen in Ihrer bevorzugten Sprache anzuzeigen.

Importierte Daten und Informationen, die Sie manuell eingegeben haben, werden nicht übersetzt.

1. Gehen Sie zu **Admin** > **System** und wählen Sie die Registerkarte **Allgemein**.

1. Um Ihre bevorzugte Sprache zu ändern, wählen Sie eine **Sprache** aus der Dropdownliste aus.

1. Verwenden Sie die Dropdownliste **Format für Land/Region**, um Ihre bevorzugte Formatierung für Datum, Uhrzeit und Zahlen zu ändern. Eine Formattierungsvorschau wird angezeigt. Das System wird automatisch eine Auswahl vorschlagen, wenn Sie eine neue Sprache wählen.

1. Wählen Sie **Save** (Speichern).

## <a name="view-system-status"></a>Systemstatus anzeigen

Verfolgen Sie den Fortschritt von Aufgaben, Datenerfassungen, Datenexporten und mehreren anderen wichtigen Produktprozessen nach. Überprüfen Sie die Informationen, um die Vollständigkeit Ihrer aktiven Aufgaben und Prozesse sicherzustellen.

1. Gehen Sie zu **Admin** > **System** und wählen Sie die Registerkarte **Status**.

   Status- und Verarbeitungsinformationen für verschiedene Prozesse werden angezeigt. Zeigen Sie den **Name** der Aufgabe und ihrer entsprechenden Entität, den **Status** ihres letzten Laufs und wann die **Letzte Aktualisierung** war, an.

1. Sie können die Details mehrerer letzter Ausführungen anzeigen, indem Sie den Aufgaben- oder Prozessnamen auswählen.

1. Um die Fortschrittsdetails für eine Aufgabe anzuzeigen, wählen Sie den Status aus. Der Bereich **Fortschrittsdetails** wird angezeigt.

   :::image type="content" source="media/system-progress-details.png" alt-text="Bereich mit den Details zum Systemfortschritt":::

1. Um Fortschrittsdetails für alle Aufgaben anzuzeigen, wählen Sie **Gesamter Workflow**.

### <a name="status-definitions"></a>Statusdefinitionen

Das System verwendet folgende Status für Aufgaben und Prozesse:

|Status  |Definition  |
|---------|---------|
|Abgesagt |Die Aufgabe oder der Prozess wurde vom Benutzer abgebrochen, bevor sie oder er abgeschlossen wurde.   |
|Fehlerhaft   |Bei Aufgabe oder Prozess sind Fehler aufgetreten.         |
|Fehler  |Aufgabe oder Prozess ist fehlgeschlagen.  |
|Nicht begonnen   |Die Datenquelle hat noch keine Daten aufgenommen oder die Aufgabe befindet sich noch im Entwurfsmodus.         |
|Wird verarbeitet...  |Aufgabe oder Prozess wird ausgeführt.  |
|Wird aktualisiert    |Aufgabe oder Prozess wird ausgeführt. Um diesen Vorgang abzubrechen, wählen Sie **Wird aktualisiert** und **Auftrag abbrechen** aus. Wenn Sie die Aktualisierung einer Aufgabe oder eines Prozesses stoppen, wird der letzte Aktualisierungsstatus wiederhergestellt.       |
|Übersprungen  |Aufgabe oder Prozess wurde übersprungen. Einer oder mehrere der nachgelagerten Prozesse, von denen diese Aufgabe abhängt, sind fehlgeschlagen oder wurden übersprungen.|
|Erfolgreich  |Aufgabe oder Prozess wurde erfolgreich abgeschlossen. Gibt bei Datenquellen an, dass die Daten erfolgreich aufgenommen wurden, wenn eine Zeit in der Spalte **Aktualisiert** angegeben ist.|
|In Warteschlange | Die Verarbeitung wird in die Warteschlange gestellt und beginnt, sobald alle Upstream-Aufgaben und -Prozesse abgeschlossen sind. Weitere Informationen finden Sie unter [Prozesse aktualisieren](#refresh-processes).|

### <a name="refresh-processes"></a>Prozesse aktualisieren

Die Aktualisierung für Aufgaben und Prozesse wird gemäß dem [konfigurierten Zeitplan](schedule-refresh.md) ausgeführt.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]
