---
title: Verwenden Sie Datenquellen zur Datenerfassung
description: Erfahren Sie, wie Daten aus unterschiedlichen Quellen importiert werden.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304695"
---
# <a name="data-sources-overview"></a>Übersicht über Datenquellen

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Die Funktionalität „Zielgruppen-Insights“ in Dynamics 365 Customer Insights verbindet sich mit Daten aus einer breiten Palette von Quellen. Das Herstellen einer Verbindung zu einem Datenquelle wird häufig als Prozess von *Datenerfassung* bezeichnet. Nach der Erfassung der Daten können Sie [vereinheitlichen](data-unification.md) und Aktionen durchführen.

## <a name="add-a-data-source"></a>Datenquelle hinzufügen

In den ausführlichen Artikeln erfahren Sie, wie Sie ein Datenquelle hinzufügen, je nachdem, welche Option Sie auswählen.

Sie können ein Datenquelle auf drei Arten hinzufügen:

- [Durch Dutzende von Power Query-Connectors](connect-power-query.md)
- [Aus einem Common Data Model-Ordner](connect-common-data-model.md)
- [Aus Ihrem eigenen Microsoft Dataverse-Lake](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Fügen Sie Daten aus lokalen Datenquellen hinzu

Das Aufnehmen von Daten aus lokalen Datenquellen in Zielgruppenerkenntnissen wird basierend auf Microsoft Power Platform Dataflows unterstützt. Dataflows können in Customer Insights durch [Bereitstellung der Microsoft Dataverse-Umgebungs-URL](manage-environments.md#create-an-environment-in-an-existing-organization) beim Einrichten der Umgebung aktiviert werden.

Datenquellen, die nach dem Zuordnen einer Dataverse-Umgebung mit Customer Insights erstellt werden, verwenden [Power Platform Dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) standardmäßig. Dataflows unterstützen die lokale Konnektivität mithilfe des Datengateways. Entfernen Sie Datenquellen, die vor einer Dataverse Umgebungszuordnung vorhanden waren, und erstellen Sie sie neu, um [Datengateways lokal zu verwenden](/data-integration/gateway/service-gateway-app.md).

Datengateways einer vorhandenen Power BI- oder Power Apps-Umgebung werden sichtbar und Sie können sie in Customer Insights wiederverwenden. Die Seite mit den Datenquellen enthält Links zu der Microsoft Power Platform Umgebung, in der Sie lokale Datengateways anzeigen und konfigurieren können.

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

Das Laden von Daten kann einige Zeit in Anspruch nehmen. Nach einer erfolgreichen Aktualisierung können die aufgenommenen Daten von der Seite **Entitäten** überprüft werden. Weitere Informationen finden Sie unter [Entitäten](entities.md).

## <a name="refresh-a-data-source"></a>Aktualisieren einer Datenquelle

Datenquellen können nach einem automatischen Zeitplan oder manuell bei Bedarf aufgefrischt werden. 

Gehen Sie zu **Admin** > **System** > [**Planen**](system.md#schedule-tab), um geplante Aktualisierungen aller Ihrer aufgenommenen Datenquellen zu konfigurieren.

Um eine Datenquelle bei Bedarf zu aktualisieren, folgen Sie diesen Schritten:

1. Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.

2. Wählen Sie die vertikalen Auslassungspunkte neben dem Datenquelle, die Sie ändern möchten, und wählen Sie **Aktualisieren** aus dem Dropdown-Menü.

3. Die Datenquelle wird jetzt für eine manuelle Aktualisierung ausgelöst. Durch das Aktualisieren eines Datenquelle werden sowohl das Entitätsschema als auch die Daten für alle im Datenquelle angegebenen Entitäten aktualisiert.

4. Wählen Sie **Auffrischung stoppen**, wenn Sie eine bestehende Auffrischung abbrechen wollen und die Datenquelle in ihren letzten Auffrischungsstatus zurückkehren soll.

## <a name="delete-a-data-source"></a>Löschen einer Datenquelle

1. Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.

2. Wählen Sie die vertikalen Auslassungspunkte neben dem Datenquelle, die Sie entfernen möchten, und wählen Sie **Löschen** aus dem Dropdown-Menü.

3. Bestätigen Sie den Löschvorgang.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
