---
title: Verwenden Sie Datenquellen zur Datenerfassung
description: Erfahren Sie, wie Daten aus unterschiedlichen Quellen importiert werden.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 780dc61a82d6ed9856a37dc8f164fa946d982bbe
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595946"
---
# <a name="data-sources-overview"></a>Übersicht über Datenquellen

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Die Funktionalität „Zielgruppen-Insights“ in Dynamics 365 Customer Insights verbindet sich mit Daten aus einer breiten Palette von Quellen. Das Herstellen einer Verbindung zu einem Datenquelle wird häufig als Prozess von *Datenerfassung* bezeichnet. Nach der Erfassung der Daten können Sie [vereinheitlichen](data-unification.md) und Aktionen durchführen.

## <a name="add-a-data-source"></a>Datenquelle hinzufügen

In den ausführlichen Artikeln erfahren Sie, wie Sie ein Datenquelle hinzufügen, je nachdem, welche Option Sie auswählen.

Sie können ein Datenquelle auf drei Arten hinzufügen:

- [Durch Dutzende von Power Query-Connectors](connect-power-query.md)
- [Aus einem Common Data Model-Ordner](connect-common-data-model.md)
- [Aus Ihrem eigenen Common Data Service-Lake](connect-common-data-service-lake.md)

> [!NOTE]
> Sie können noch keine Daten aus lokalen Datenquellen hinzufügen.

## <a name="review-ingested-data"></a>Eingebundene Daten überprüfen

Sie sehen den Namen jeder aufgenommenen Datenquelle, ihren Status und das letzte Mal, dass die Daten für diese Quelle aktualisiert wurden. Sie können die Liste der Datenquellen nach jeder Spalte sortieren.

> [!div class="mx-imgBorder"]
> ![Datenquelle hinzugefügt](media/configure-data-datasource-added.png "Datenquelle hinzugefügt")

|Status  |Beschreibung des Dataflows  |
|---------|---------|
|Erfolgreich   |Die Datenquelle wurde erfolgreich aufgenommen, wenn in der Spalte **Aufgefrischt** ein Zeitpunkt genannt wird.
|Nicht gestartet   |Die Datenquelle hat noch keine Datenerfassung oder ist noch im Entwurfsmodus.         |
|Wird aktualisiert    |Die Datenaufnahme ist im Gange. Sie können diesen Vorgang abbrechen, indem Sie **Aktualisierung beenden** in der Spalte **Aktionen** wählen. Wenn Sie die Aktualisierung einer Datenquelle stoppen, wird der letzte Aktualisierungsstatus wiederhergestellt.       |
|Fehlerhaft     |Bei der Dateneingabe sind Fehler aufgetreten.         |

Wählen Sie den Wert in der **Status**-Spalte einer beliebigen Datenquelle, um weitere Details zu überprüfen. Im **Fortschrittsdetails**-Bereich erweitern Sie **Datenquellen**. Wählen Sie **Details anzeigen**, um weitere Informationen zum Auffrischungsstatus zu prüfen, einschließlich Fehlerdetails und nachgelagerte Prozessaktualisierungen.

Das Laden von Daten kann einige Zeit dauern. Nach einer erfolgreichen Aktualisierung können die aufgenommenen Daten von der Seite **Entitäten** überprüft werden. Weitere Informationen finden Sie unter [Entitäten](entities.md).

## <a name="refresh-a-data-source"></a>Aktualisieren einer Datenquelle

Datenquellen können nach einem automatischen Zeitplan oder manuell bei Bedarf aufgefrischt werden. 

Gehen Sie zu **Admin** > **System** > [**Planen**](system.md#schedule-tab), um geplante Aktualisierungen aller Ihrer aufgenommenen Datenquellen zu konfigurieren.

Um eine Datenquelle bei Bedarf zu aktualisieren, folgen Sie diesen Schritten:

1. Gehen Sie in Zielgruppen-Insights zu **Daten** > **Datenquellen**

2. Wählen Sie die vertikalen Auslassungspunkte neben der Datenquelle, die Sie aktualisieren möchten, und wählen Sie **Auffrischen** aus der Dropdown-Liste.

3. Die Datenquelle wird jetzt für eine manuelle Aktualisierung ausgelöst. Das Aktualisieren einer Datenquelle aktualisiert sowohl das Entitätsschema als auch die Daten für alle Entitäten, die in der Datenquelle angegeben sind.

4. Wählen Sie **Auffrischung stoppen**, wenn Sie eine bestehende Auffrischung abbrechen wollen und die Datenquelle in ihren letzten Auffrischungsstatus zurückkehren soll.

## <a name="delete-a-data-source"></a>Löschen einer Datenquelle

1. Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.

2. Wählen Sie die vertikalen Auslassungspunkte neben der Datenquelle aus, die Sie entfernen möchten, und wählen Sie **Löschen** aus dem Dropdownmenü aus.

3. Bestätigen Sie den Löschvorgang.


[!INCLUDE[footer-include](../includes/footer-banner.md)]