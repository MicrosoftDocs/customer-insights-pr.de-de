---
title: Verwenden Sie Datenquellen zur Datenerfassung
description: Erfahren Sie, wie Daten aus unterschiedlichen Quellen importiert werden.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 1fe8d6e8098831ecc8ff28e571340c56a654de6d
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8739207"
---
# <a name="data-sources-overview"></a>Übersicht über Datenquellen



Dynamics 365 Customer Insights stellt eine Verbindung zu Daten aus einer breiten Palette von Quellen her. Das Herstellen einer Verbindung zu einem Datenquelle wird häufig als Prozess von *Datenerfassung* bezeichnet. Nach der Erfassung der Daten können Sie [vereinheitlichen](data-unification.md) und Aktionen durchführen.

## <a name="add-a-data-source"></a>Datenquelle hinzufügen

Wie Sie je nach gewählter Option eine Datenquelle hinzufügen können, erfahren Sie in den entsprechenden Artikeln.

Die folgenden Datenquellen können hinzugefügt werden:

- [Durch Dutzende von Power Query-Konnektoren](connect-power-query.md)
- [Aus einem Common Data Model-Ordner](connect-common-data-model.md)
- [Aus Ihrem eigenen Microsoft Dataverse-Lake](connect-dataverse-managed-lake.md)
- [Aus einer Azure Synapse Analytics-Datenbank](connect-synapse.md)

## <a name="add-data-from-on-premises-data-sources"></a>Fügen Sie Daten aus lokalen Datenquellen hinzu

Das Einbinden von Daten aus lokalen Datenquellen wird auf der Grundlage von Microsoft Power Platform-Datenflows unterstützt. Beim Einrichten der Umgebung können Sie Dataflows in Customer Insights durch das [Bereitstellen der Microsoft Dataverse-Umgebungs-URL](create-environment.md) aktivieren.

Datenquellen, die nach dem Verknüpfen einer Dataverse-Umgebung mit Customer Insights erstellt wurden, verwenden standardmäßig [Power Platform-Dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Dataflows unterstützen die lokale Konnektivität mithilfe des Datengateways. Sie können Datenquellen, die vor der Verknüpfung einer Dataverse-Umgebung vorhanden waren, durch [Verwenden von lokalen Datengateways](/data-integration/gateway/service-gateway-app) entfernen und neu erstellen.

Datengateways einer vorhandenen Power BI- oder Power Apps-Umgebung werden sichtbar und Sie können sie in Customer Insights wiederverwenden. Die Seite mit den Datenquellen enthält Links zu der Microsoft Power Platform Umgebung, in der Sie lokale Datengateways anzeigen und konfigurieren können.

> [!IMPORTANT]
> Stellen Sie sicher, dass Ihre Gateways auf die neueste Version aktualisiert sind. Sie können ein Update installieren und ein Gateway über eine Eingabeaufforderung, die auf der Gateway-Anzeige angezeigt wird, direkt installieren oder neu konfigurieren oder [die neueste Version herunterladen](https://powerapps.microsoft.com/downloads/). Wenn Sie nicht die neueste Gateway-Version verwenden, schlägt die Datenflussaktualisierung mit Fehlermeldungen wie **Das Schlüsselwort wird nicht unterstützt: Konfigurationseigenschaften. Parametername: Schlüsselwort** fehl.

## <a name="review-ingested-data"></a>Eingebundene Daten überprüfen
Wenn Ihre Umgebung Power Platform Dataflows enthält, enthält die Seite **Datenquellen** drei Abschnitte: 
- **Geteilt**: Datenquellen, die von allen Customer Insights-Administratoren verwaltet werden können. Power BI Dataflows, Ihr eigenes Speicherkonto und das Anhängen an a Dataverse-verwaltete Data Lake sind Beispiele für gemeinsam genutzte Datenquellen.
- **Von mir verwaltet**: Power Platform Dataflows erstellt und können nur von Ihnen verwaltet werden. Andere Customer Insights-Administratoren können diese Datenflows nur anzeigen, aber nicht bearbeiten, aktualisieren oder löschen.
- **Von anderen verwaltet**: Power Platform Dataflows, die von anderen Administratoren erstellt wurden. Sie können sie nur anzeigen. Fürt den Besitzer des Dataflows auf, an den Sie sich für Unterstützung wenden können.
> [!NOTE]
> Alle Entitäten können von anderen Benutzern angezeigt und verwendet werden. Die Benutzerkontextualität gilt nur für die Datenquellen und nicht für die Entitäten, die aus diesen Datenflüssen resultieren.

Wenn keine Power Platform Datenflows verwendet werden, sehen Sie keine Gruppen oder Abschnitte. Die Seite **Datenquellen** enthält nur eine Liste aller Datenquellen.

Sie sehen den Namen jeder aufgenommenen Datenquelle, ihren Status und das letzte Mal, dass die Daten für diese Quelle aktualisiert wurden. Sie können die Liste der Datenquellen nach jeder Spalte sortieren.

> [!div class="mx-imgBorder"]
> ![Datenquelle hinzugefügt](media/configure-data-datasource-added.png "Datenquelle hinzugefügt")

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Das Laden von Daten kann einige Zeit in Anspruch nehmen. Nach einer erfolgreichen Aktualisierung können die aufgenommenen Daten von der Seite **Entitäten** überprüft werden. Weitere Informationen finden Sie unter [Entitäten](entities.md).

## <a name="refresh-a-data-source"></a>Aktualisieren einer Datenquelle

Datenquellen können nach einem automatischen Zeitplan oder manuell bei Bedarf aufgefrischt werden. 

Gehen Sie zu **Admin** > **System** > [**Planen**](system.md#schedule-tab), um geplante Aktualisierungen aller Ihrer aufgenommenen Datenquellen zu konfigurieren.

Um eine Datenquelle bei Bedarf zu aktualisieren, folgen Sie diesen Schritten:

1. Wechseln Sie zu **Daten** > **Datenquellen**.

2. Wählen Sie die vertikalen Auslassungspunkte neben dem Datenquelle, die Sie ändern möchten, und wählen Sie **Aktualisieren** aus dem Dropdown-Menü.

3. Die Datenquelle wird jetzt für eine manuelle Aktualisierung ausgelöst. Durch das Aktualisieren eines Datenquelle werden sowohl das Entitätsschema als auch die Daten für alle im Datenquelle angegebenen Entitäten aktualisiert.

4. Wählen Sie **Auffrischung stoppen**, wenn Sie eine bestehende Auffrischung abbrechen wollen und die Datenquelle in ihren letzten Auffrischungsstatus zurückkehren soll.

## <a name="delete-a-data-source"></a>Löschen einer Datenquelle

1. Wechseln Sie zu **Daten** > **Datenquellen**.

2. Wählen Sie die vertikalen Auslassungspunkte neben dem Datenquelle, die Sie entfernen möchten, und wählen Sie **Löschen** aus dem Dropdown-Menü.

3. Bestätigen Sie den Löschvorgang.


[!INCLUDE [footer-include](includes/footer-banner.md)]
