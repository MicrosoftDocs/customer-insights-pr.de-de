---
title: Exporte (Vorschauversion) – Übersicht
description: Verwalten Sie Datenexporte, um Daten freizugeben.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: a70aadda4fc0eff3ddb4c89665506762613c291a
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9194967"
---
# <a name="exports-preview-overview"></a>Exporte (Vorschauversion) – Übersicht

 Exporte ermöglichen das Teilen bestimmter Daten mit verschiedenen Anwendungen. Sie können Kundenprofile, Entitäten, Schemata und Zuordnungsdetails enthalten. Jeder Export erfordert eine [Verbindung, die von einem Administrator eingerichtet wurde, um die Authentifizierung und den Zugriff zu verwalten](connections.md). Die Seite **Exporte** zeigt Ihnen alle konfigurierten Exporte.

## <a name="export-types"></a>Exporttypen

Es gibt zwei Haupttypen für Exporte:  

- **Mit Datenexporten**: Sie können jede Art von Entität exportieren, die in Customer Insights verfügbar ist. Die für den Export ausgewählten Entitäten werden mit allen Datenfeldern, Metadaten, Schemas und Zuordnungsdetails exportiert.
- **Segmentexporte**: ermöglichen es Ihnen, Entitäten aus Customer Insights zu exportieren. Segmente stellen eine Liste von Kundenprofilen dar. Bei der Konfiguration des Exports wählen Sie je nach Zielsystem, in das Sie Daten exportieren, die enthaltenen Datenfelder aus.

### <a name="export-segments"></a>Segmente exportieren

**Exportieren von Segmenten in Umgebungen für Geschäftskonten (B2B) oder Verbraucher (B2C)**  
Die meisten Exportoptionen unterstützen beide Arten von Umgebungen. Der Export von Segmenten in verschiedene Zielsysteme stellt besondere Anforderungen. 

**Segmentexporte in Umgebungen für Verbraucher (B2C)**  
- Segmente im Kontext von Umgebungen für individuelle Kunden bauen auf der Entität *Vereinheitlichtes Kund*innenprofil* auf. Jedes Segment, das die Anforderungen der Zielsysteme erfüllt (z.B. eine E-Mail-Adresse), kann exportiert werden.

**Segmentexportumgebungen für Geschäftskonten (B2B)**  
- Segmente im Kontext von Umgebungen für Geschäftskonten bauen auf dem *Konto* juristische Person auf. Um Kontensegmente unverändert zu exportieren, muss das Zielsystem reine Kontensegmente unterstützen. Dies ist der Fall für [LinkedIn](export-linkedin-ads.md) wenn Sie die Option **Unternehmen** wählen, wenn Sie den Export definieren.
- Alle anderen Zielsysteme benötigen Felder aus der Kontaktentität. Um sicherzustellen, dass Firmensegmente Daten von verwandten Kontakten abrufen können, muss Ihre Segmentdefinition Attribute der Kontaktentität projizieren. Erfahren Sie mehr darüber, wie es geht, [Segmente und Projektattribute zu konfigurieren](segment-builder.md).

**Beschränkungen für Segmentexporte**  
- Zielsysteme von Drittanbietern können die Anzahl der Kundenprofile, die Sie exportieren können, einschränken. 
- Bei einzelnen Kunden sehen Sie die tatsächliche Anzahl der Segmentmitglieder, wenn Sie ein Segment für den Export auswählen. Sie erhalten eine Warnung, wenn ein Segment zu groß ist. 
- Bei Geschäftskonten sehen Sie die Anzahl der Konten in einem Segment. die Anzahl der Kontakte, die projiziert werden können, wird jedoch nicht angezeigt. In manchen Fällen kann dies dazu führen, dass das exportierte Segment tatsächlich mehr Kundenprofile enthält, als das Zielsystem akzeptiert. Bei Überschreitung der Grenzwerte der Zielsystemergebnisse wird der Export übersprungen.

## <a name="set-up-a-new-export"></a>Einen neuen Export einrichten

Um einen Export einzurichten oder zu bearbeiten, müssen richtige Verbindungen verfügbar sein. Verbindungen hängen von Ihrer [Benutzerrolle](permissions.md) ab:
- **Administratoren** haben Zugriff auf alle Verbindungen. Sie können beim Einrichten eines Exports auch neue Verbindungen herstellen.
- **Mitwirkende** können auf bestimmte Verbindungen zugreifen. Sie hängen von Administratoren ab, um Verbindungen zu konfigurieren und gemeinsam zu nutzen. Die Exportliste zeigt den Mitwirkenden an, ob sie einen Export bearbeiten oder nur in der Spalte **Ihre Berechtigungen** anzeigen können. Weitere Informationen finden Sie unter [Erlauben Sie Mitwirkenden, eine Verbindung für Exporte zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Betrachter** kann nur vorhandene Exporte anzeigen, nicht erstellen.

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen** aus, um einen neuen Export zu erstellen.

1. Im Bereich **Export einrichten** wählen Sie aus, welche [Verbindung](connections.md) verwendet werden soll.

1. Geben Sie die erforderlichen Details ein und wählen Sie **Speichern**, um den Export zu erstellen. Die erforderlichen Details finden Sie in der Customer Insights-Dokumentation für den jeweiligen Export.

## <a name="manage-existing-exports"></a>Vorhandene Exporte verwalten

Gehen Sie zu **Daten** > **Exporte**, um die Exporte, ihren Verbindungsnamen, Verbindungstyp und Status anzuzeigen. Alle Benutzerrollen können konfigurierte Exporte anzeigen. Sie können die Liste der Exporte nach einer beliebigen Spalte sortieren oder das Suchfeld verwenden, um die Exporte zu finden, die Sie verwalten möchten.

Wählen Sie einen Export aus, um verfügbare Aktionen anzuzeigen.

:::image type="content" source="media/exports_showmore.png" alt-text="Exportseite":::

- **Ansehen** oder **Bearbeiten** des Exports. Benutzer ohne Bearbeitungsberechtigungen wählen **Ansicht** anstatt **Bearbeiten**, um die Exportdetails anzuzeigen.
- **Ausführen** des Exports, um die neuesten Daten zu exportieren.
- **Duplikat erstellen** eines Exports.
- **[Planen](#schedule-and-run-exports)** des Exports.
- **Verbindung trennen** um die Verbindung für diesen Export zu entfernen. Trennen entfernt nicht die Verbindung, sondern deaktiviert den Export. Die Spalte **Verbindung verwendet** zeigt Keine Verbindung an.
- **Entfernen** Sie den Export.

## <a name="schedule-and-run-exports"></a>Planen und Ausführen von Exporten

Jeder von Ihnen konfigurierte Export verfügt über einen Aktualisierungszeitplan. Während einer Aktualisierung sucht das System nach neuen oder aktualisierten Daten, die in einen Export aufgenommen werden sollen. Standardmäßig werden Exporte als Teil einer jeden [geplanten Systemaktualisierung](system.md#schedule-tab) ausgeführt. Sie können den Aktualisierungszeitplan anpassen oder deaktivieren, um Exporte manuell auszuführen.

Exportzeitpläne hängen vom Status Ihrer Umgebung ab. Wenn Aktualisierungen in Bearbeitung von [Abhängigkeiten](system.md#refresh-processes) sind, wenn ein geplanter Export gestartet werden soll, führt das System zuerst die Aktualisierungen durch und führt dann den Export aus. In der Spalte **Aktualisiert** wird angezeigt, wann ein Export letztmalig aktualisiert wurde.

### <a name="schedule-exports"></a>Planen von Exporten

Definieren Sie benutzerdefinierte Aktualisierungszeitpläne für einzelne Exporte oder mehrere Exporte gleichzeitig. Der aktuell definierte Zeitplan ist in der Spalte **Zeitplan** der Exportliste angegeben. Die Berechtigung zum Ändern des Zeitplans ist die gleiche wie für das [Bearbeiten und Definieren von Exporten](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie den Export aus, den Sie planen möchten.

1. Klicken Sie auf **Zeitplan**.

1. Legen Sie im Bereich **Export planen** die Option **Zeitplanausführung** auf **Ein** fest, um den Export automatisch auszuführen. Legen Sie die Option auf **Aus** fest, um die Aktualisierung manuell durchzuführen.

1. Wählen Sie für automatisch aktualisierte Exporte einen Wert für **Wiederholung** aus und geben Sie die Details dafür an. Die definierte Zeit gilt für alle Wiederholungen. Dies ist der Zeitpunkt, an dem die Aktualisierung eines Exports beginnen sollte.

1. Wählen Sie **Save** (Speichern).

Wenn Sie den Zeitplan für mehrere Exporte bearbeiten, müssen Sie unter **Zeitpläne beibehalten oder überschreiben** eine Auswahl treffen:

- **Individuelle Zeitpläne beibehalten**: Behalten Sie den zuvor definierten Zeitplan für die ausgewählten Exporte bei und deaktivieren oder aktivieren Sie sie nur.
- **Neuen Zeitplan für alle ausgewählten Exporte definieren**: Überschreiben Sie die bestehenden Zeitpläne der ausgewählten Exporte.

### <a name="run-exports-on-demand"></a>Exporte Bedarfsgesteuert ausführen

Um Daten zu exportieren, ohne auf eine geplante Aktualisierung zu warten, gehen Sie zu **Daten** > **Exporte**.

- Um alle Exporte auszuführen, wählen Sie **Alle ausführen** in der Befehlsleiste aus. Nur Exporte werden ausgeführt, die über einen aktiven Zeitplan verfügen. Um einen nicht aktiven Export auszuführen, führen Sie einen einzelnen Export aus.
- Um einen einzelnen Export auszuführen, wählen Sie ihn in der Liste aus und wählen Sie dann in der Befehlsleiste **Ausführen** aus.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
