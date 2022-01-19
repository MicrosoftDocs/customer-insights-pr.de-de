---
title: Verwenden Sie Datenquellen zur Datenerfassung
description: Erfahren Sie, wie Daten aus unterschiedlichen Quellen importiert werden.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 78379c827e132b3b172aa7381f4c5ef2c70b9771
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977828"
---
# <a name="data-sources-overview"></a>Übersicht über Datenquellen

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Die Funktionalität „Zielgruppen-Insights“ in Dynamics 365 Customer Insights verbindet sich mit Daten aus einer breiten Palette von Quellen. Das Herstellen einer Verbindung zu einem Datenquelle wird häufig als Prozess von *Datenerfassung* bezeichnet. Nach der Erfassung der Daten können Sie [vereinheitlichen](data-unification.md) und Aktionen durchführen.

## <a name="add-a-data-source"></a>Datenquelle hinzufügen

Wie Sie je nach gewählter Option eine Datenquelle hinzufügen können, erfahren Sie in den entsprechenden Artikeln.

Die folgenden Datenquellen können hinzugefügt werden:

- [Power Query-Konnektoren](connect-power-query.md)
- [Common Data Model](connect-common-data-model.md)
- [Microsoft Dataverse-Lake](connect-dataverse-managed-lake.md)

> [!NOTE]
> Wenn Sie die Testversion verwenden, enthält der Abschnitt mit den Importmethoden die Option **Customer Insights-Datenbibliothek**. Wählen Sie diese Option aus, um ein Beispiel-DataSet auszuwählen, das für verschiedene Branchen verfügbar ist. Weitere Informationen finden Sie unter [Dynamics 365 Customer Insights-Testversion](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Fügen Sie Daten aus lokalen Datenquellen hinzu

Das Aufnehmen von Daten aus lokalen Datenquellen in Zielgruppenerkenntnissen wird basierend auf Microsoft Power Platform Dataflows unterstützt. Beim Einrichten der Umgebung können Sie Dataflows in Customer Insights durch das [Bereitstellen der Microsoft Dataverse-Umgebungs-URL](create-environment.md) aktivieren.

Datenquellen, die nach dem Verknüpfen einer Dataverse-Umgebung mit Customer Insights erstellt wurden, verwenden standardmäßig [Power Platform-Dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Dataflows unterstützen die lokale Konnektivität mithilfe des Datengateways. Sie können Datenquellen, die vor der Verknüpfung einer Dataverse-Umgebung vorhanden waren, durch [Verwenden von lokalen Datengateways](/data-integration/gateway/service-gateway-app) entfernen und neu erstellen.

Datengateways einer vorhandenen Power BI- oder Power Apps-Umgebung werden sichtbar und Sie können sie in Customer Insights wiederverwenden. Die Seite mit den Datenquellen enthält Links zu der Microsoft Power Platform Umgebung, in der Sie lokale Datengateways anzeigen und konfigurieren können.

## <a name="review-ingested-data"></a>Eingebundene Daten überprüfen

Sie sehen den Namen jeder aufgenommenen Datenquelle, ihren Status und das letzte Mal, dass die Daten für diese Quelle aktualisiert wurden. Sie können die Liste der Datenquellen nach jeder Spalte sortieren.

> [!div class="mx-imgBorder"]
> ![Datenquelle hinzugefügt](media/configure-data-datasource-added.png "Datenquelle hinzugefügt")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

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
