---
title: Exportieren Sie Daten aus Customer Insights
description: Verwalten Sie Datenexporte, um Daten freizugeben.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 05485fc7def3d699d5179bcaa005ceb57024f840
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977966"
---
# <a name="exports-preview-overview"></a>Exporte (Vorschau) – Übersicht

Die Seite **Exporte** zeigt Ihnen alle konfigurierten Exporte. Exporte teilen bestimmte Daten mit verschiedenen Anwendungen. Sie können Kundenprofile, Entitäten, Schemata und Zuordnungsdetails enthalten. Jeder Export erfordert eine [Verbindung, die von einem Administrator eingerichtet wurde, um die Authentifizierung und den Zugriff zu verwalten](connections.md).

Gehen Sie zu **Daten** > **Exporte**, um die Exportseite anzuzeigen. Alle Benutzerrollen können konfigurierte Exporte anzeigen. Verwenden Sie das Suchfeld in der Befehlsleiste, um Exporte anhand ihres Namens, Verbindungsnamens oder Verbindungstyps zu suchen.

## <a name="export-types"></a>Exporttypen

Es gibt zwei Haupttypen für Exporte:  

- Mit **Daten-Out-Exporte** können Sie jede Art von Entität exportieren, die in Zielgruppenerkenntnissen verfügbar ist. Die für den Export ausgewählten Entitäten werden mit allen Datenfeldern, Metadaten, Schemas und Zuordnungsdetails exportiert. 
- **Segmentexporte** können Sie Segmententitäten aus Zielgruppenerkenntnissen exportieren. Segmente stellen eine Liste von Kundenprofilen dar. Bei der Konfiguration des Exports wählen Sie je nach Zielsystem, in das Sie Daten exportieren, die enthaltenen Datenfelder aus. 

### <a name="export-segments"></a>Segmente exportieren

**Exportieren von Segmenten in Umgebungen für Geschäftskonten (B2B) oder Verbraucher (B2C)**  
Die meisten Exportoptionen unterstützen beide Arten von Umgebungen. Der Export von Segmenten in verschiedene Zielsysteme stellt besondere Anforderungen. Im Allgemeinen enthält ein Segmentmitglied, das Kundenprofil, Kontaktinformationen. Während dies normalerweise bei Segmenten der Fall ist, die auf Verbrauchern basieren (B2C), ist dies nicht unbedingt der Fall bei Segmenten, die auf Geschäftskonten basieren (B2B). 

**Segmentexportumgebungen für Geschäftskonten (B2B)**  
- Segmente im Kontext von Umgebungen für Geschäftskonten bauen auf dem *Konto* juristische Person auf. Um Kontensegmente unverändert zu exportieren, muss das Zielsystem reine Kontensegmente unterstützen. Dies ist der Fall für [LinkedIn](export-linkedin-ads.md) wenn Sie die Option **Unternehmen** wählen, wenn Sie den Export definieren.
- Alle anderen Zielsysteme benötigen Felder aus der Kontaktentität. Um sicherzustellen, dass Firmensegmente Daten von verwandten Kontakten abrufen können, muss Ihre Segmentdefinition Attribute der Kontaktentität projizieren. Erfahren Sie mehr darüber, wie es geht, [Segmente und Projektattribute zu konfigurieren](segment-builder.md).

**Segmentexporte in Umgebungen für Verbraucher (B2C)**  
- Segmente im Kontext von Umgebungen für individuelle Kunden bauen auf der Entität *Vereinheitlichtes Kund*innenprofil* auf. Jedes Segment, das die Anforderungen der Zielsysteme erfüllt (z.B. eine E-Mail-Adresse), kann exportiert werden.

**Beschränkungen für Segmentexporte**  
- Zielsysteme von Drittanbietern können die Anzahl der Kundenprofile, die Sie exportieren können, einschränken. 
- Bei einzelnen Kunden sehen Sie die tatsächliche Anzahl der Segmentmitglieder, wenn Sie ein Segment für den Export auswählen. Sie erhalten eine Warnung, wenn ein Segment zu groß ist. 
- Bei Geschäftskonten sehen Sie die Anzahl der Konten in einem Segment. die Anzahl der Kontakte, die projiziert werden können, wird jedoch nicht angezeigt. In manchen Fällen kann dies dazu führen, dass das exportierte Segment tatsächlich mehr Kundenprofile enthält, als das Zielsystem akzeptiert. Bei Überschreitung der Grenzwerte der Zielsystemergebnisse wird der Export übersprungen. 

## <a name="set-up-a-new-export"></a>Einen neuen Export einrichten  
Um einen Export einzurichten oder zu bearbeiten, müssen Verbindungen verfügbar sein. Verbindungen hängen von Ihrer [Benutzerrolle](permissions.md) ab:
- **Administratoren** haben Zugriff auf alle Verbindungen. Sie können beim Einrichten eines Exports auch neue Verbindungen herstellen.
- **Mitwirkende** können auf bestimmte Verbindungen zugreifen. Sie hängen von Administratoren ab, um Verbindungen zu konfigurieren und gemeinsam zu nutzen. Die Exportliste zeigt den Mitwirkenden an, ob sie einen Export bearbeiten oder nur in der Spalte **Ihre Berechtigungen** anzeigen können. Weitere Informationen finden Sie unter [Erlauben Sie Mitwirkenden, eine Verbindung für Exporte zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Betrachter** kann nur vorhandene Exporte anzeigen, nicht erstellen.

### <a name="define-a-new-export"></a>Definieren eines neuen Exports

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen** aus, um einen neuen Export zu erstellen.

1. Im Bereich **Export einrichten** wählen Sie aus, welche Verbindung verwendet werden soll. [Verbindungen](connections.md) werden von Administratoren verwaltet. 

1. Geben Sie die erforderlichen Details ein und wählen Sie **Speichern**, um den Export zu erstellen.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Definieren eines neuen Exports basierend auf einem vorhandenen Export

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie in der Liste der Exporte den Export aus, den Sie duplizieren möchten.

1. Wählen Sie in der Befehlsleiste **Duplikat erstellen** aus, um den Bereich **Export einrichten** mit den Details des ausgewählten Exports zu öffnen.

1. Überprüfen und passen Sie den Export an und wählen Sie **Speichern** aus, um einen neuen Export zu erstellen.

### <a name="edit-an-export"></a>Einen Export bearbeiten

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie in der Liste der Exporte den Export aus, den Sie bearbeiten möchten.

1. Wählen Sie in der Befehlsleiste **Bearbeiten** aus.

1. Ändern Sie die gewünschten Werte zur Aktualisierung und wählen **Speichern** aus.

## <a name="view-exports-and-export-details"></a>Anzeigen von Exporten und Exportdetails

Nach dem Erstellen von Exportzielen werden diese unter **Daten** > **Exporte** aufgelistet. Alle Benutzer können sehen, welche Daten gemeinsam genutzt werden und welchen Status sie haben.

1. Gehen Sie zu **Daten** > **Exporte**.

1. Benutzer ohne Bearbeitungsberechtigungen wählen **Ansicht** anstatt **Bearbeiten**, um die Exportdetails anzuzeigen.

1. Der Seitenbereich zeigt die Konfiguration eines Exports an. Ohne Bearbeitungsberechtigungen können Sie keine Werte ändern. Wählen Sie **Schließen** aus, um zur Exportseite zurückzukehren.

## <a name="schedule-and-run-exports"></a>Planen und Ausführen von Exporten

Jeder von Ihnen konfigurierte Export verfügt über einen Aktualisierungszeitplan. Während einer Aktualisierung sucht das System nach neuen oder aktualisierten Daten, die in einen Export aufgenommen werden sollen. Standardmäßig werden Exporte als Teil einer jeden [geplanten Systemaktualisierung](system.md#schedule-tab) ausgeführt. Sie können den Aktualisierungszeitplan anpassen oder deaktivieren, um Exporte manuell auszuführen.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Exportzeitpläne hängen vom Status Ihrer Umgebung ab. Wenn Aktualisierungen in Bearbeitung von [Abhängigkeiten](system.md#refresh-processes) sind, wenn ein geplanter Export gestartet werden soll, führt das System zuerst die Aktualisierungen durch und führt dann den Export aus. In der Spalte **Aktualisiert** sehen Sie, wann ein Export letztmalig aktualisiert wurde.

### <a name="schedule-exports"></a>Planen von Exporten

Sie können benutzerdefinierte Aktualisierungszeitpläne für einzelne Exporte oder mehrere Exporte gleichzeitig definieren. Der aktuell definierte Zeitplan ist in der Spalte **Zeitplan** der Exportliste angegeben. Die Berechtigung zum Ändern des Zeitplans ist die gleiche wie für das [Bearbeiten und Definieren von Exporten](export-destinations.md#set-up-a-new-export). 

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie den Export aus, den Sie planen möchten.

1. Wählen Sie in der Befehlsleiste **Planen** aus.

1. Legen Sie im Bereich **Export planen** die Option **Zeitplanausführung** auf **Ein** fest, um den Export automatisch auszuführen. Legen Sie die Option auf **Aus** fest, um die Aktualisierung manuell durchzuführen.

1. Wählen Sie für automatisch aktualisierte Exporte einen Wert für **Wiederholung** aus und geben Sie die Details dafür an. Die definierte Zeit gilt für alle Wiederholungen. Dies ist der Zeitpunkt, an dem die Aktualisierung eines Exports beginnen sollte.

1. Übernehmen und aktivieren Sie Ihre Änderungen, indem Sie **Speichern** auswählen.

Wenn Sie den Zeitplan für mehrere Exporte bearbeiten, müssen Sie unter **Zeitpläne beibehalten oder überschreiben** eine Auswahl treffen:
- **Individuelle Zeitpläne beibehalten**: Behalten Sie den zuvor definierten Zeitplan für die ausgewählten Exporte bei und deaktivieren oder aktivieren Sie sie nur.
- **Neuen Zeitplan für alle ausgewählten Exporte definieren**: Überschreiben Sie die bestehenden Zeitpläne der ausgewählten Exporte.

### <a name="run-exports-on-demand"></a>Exporte Bedarfsgesteuert ausführen

Um Daten zu exportieren, ohne auf eine geplante Aktualisierung zu warten, gehen Sie zu **Daten** > **Exporte**.

- Um alle Exporte auszuführen, wählen Sie **Alle ausführen** in der Befehlsleiste aus. Diese Aktion führt nur Exporte aus, die über einen aktiven Zeitplan verfügen.
- Um einen einzelnen Export auszuführen, wählen Sie ihn in der Liste aus und wählen Sie dann in der Befehlsleiste **Ausführen** aus. So führen Sie Exporte ohne aktiven Zeitplan aus. 

## <a name="remove-an-export"></a>Einen Export entfernen

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie den Export aus, den Sie entfernen möchten.

1. Wählen Sie in der Befehlsleiste **Entfernen** aus.

1. Bestätigen Sie das Entfernen, indem Sie **Entfernen** auf dem Bestätigungsbildschirm wählen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
