---
title: Mit einer Power Query-Datenquelle verbinden (enthält Video)
description: Daten über einen Power Query-Konnektor erfassen (enthält Video).
ms.date: 09/29/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4cc7e57dfb0f8d050e91adc441c24e849882f5d8
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609889"
---
# <a name="connect-to-a-power-query-data-source"></a>Verbinden mit einer Power Query-Datenquelle

Power Query bietet eine breite Palette von Konnektoren zum Erfassen von Daten. Die meisten dieser Connectors werden von Dynamics 365 Customer Insights unterstützt.

Das Hinzufügen von Datenquellen basierend auf Power Query-Konnektoren folgt im Allgemeinen den in diesem Abschnitt beschriebenen Schritten. Abhängig vom verwendeten Connector sind jedoch unterschiedliche Informationen erforderlich. Weitere Informationen finden Sie in der Dokumentation zu einzelnen Konnektoren in der [Power Query-Konnektor-Referenz](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Erstellen Sie eine neue Datenquelle

1. Wechseln Sie zu **Daten** > **Datenquellen**.

1. Wählen Sie **Datenquelle hinzufügen**.

1. Wählen Sie **Microsoft Power Query** aus.

1. Geben Sie einen **Namen** und eine optionale **Beschreibung** für die neue Datenquelle ein und wählen Sie **Weiter**.

1. Wählen Sie einen der [verfügbaren Konnektoren](#available-power-query-data-sources) aus. In diesem Beispiel wählen wir den Konnektor **Text/CSV** aus.

1. Geben Sie die erforderlichen Details für den ausgewählten Connector in das Feld **Verbindungseinstellungen** ein und wählen Sie **Weiter**, um eine Vorschau der Daten zu sehen.

1. Wählen Sie **Daten transformieren** aus.

1. Überprüfen und verfeinern Sie Ihre Daten auf der Seite **Power Query – Abfragen bearbeiten**. Die Entitäten, die die in Ihrer ausgewählten Datenquelle identifizierten Systeme aufweisen, erscheinen im linken Fensterbereich.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Dialogfeld „Abfragen bearbeiten“":::

1. Transformieren Sie Ihre Daten. Wählen Sie eine Entität zum Bearbeiten oder Transformieren aus. Verwenden Sie die Optionen im Power Query-Fenster zum Anwenden von Transformationen. Jede Transformation ist unter **Angewandte Schritte** aufgeführt. Power Query bietet zahlreiche [vorgefertigte Transformationsoptionen](/power-query/power-query-what-is-power-query#transformations).

   > [!IMPORTANT]
   > Wir empfehlen die Verwendung der folgenden Transformationen:
   >
   > - Wenn Sie Daten aus einer CSV-Datei erfassen, enthält die erste Zeile häufig Überschriften. Gehen Sie zu **Transformieren** und wählen Sie **Erste Zeile als Kopfzeilen verwnden**.
   > - Stellen Sie sicher, dass der Datentyp richtig eingestellt ist und ihren Daten entspricht. Wählen Sie beispielsweise für Datumsfelder einen Datumstyp aus.

1. Um weitere Entitäten zu Ihrer Datenquelle im Dialog **Abfragen bearbeiten** hinzuzufügen, gehen Sie zur **Startseite** und wählen Sie **Daten abrufen**. Wiederholen Sie die Schritte 5-10, bis Sie alle Entitäten für dieses Datenquelle hinzugefügt haben. Wenn Sie eine Datenbank haben, die mehrere Datensätze enthält, ist jeder Datensatz eine eigene Entität.

1. Wählen Sie **Save** (Speichern). Die Seite **Datenquellen** öffnet sich und zeigt die neue Datenquelle im Status **Wird aktualisiert** an.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Das Laden von Daten kann einige Zeit in Anspruch nehmen. Nach einer erfolgreichen Aktualisierung können die aufgenommenen Daten von der Seite [**Entitäten**](entities.md) überprüft werden.

> [!CAUTION]
>
> - Eine Datenquelle basierend auf Power Query erstellt einen [Dataflow in Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Ändern Sie nicht den Namen eines Datenflusses im Power Platform Admin Center, das in Customer Insights verwendet wird. Das Umbenennen eines Datenflusses verursacht Probleme mit den Verweisen zwischen Customer Insights Datenquelle und dem Dataverse-Datenfluss.
> - Begleitende Auswertungen für Power Query Datenquellen in Customer Insights haben die gleichen [Aktualisierungsgrenzwerte wie Dataflows in PowerBI.com](/power-query/power-query-online-limits#refresh-limits). Wenn eine Datenaktualisierung fehlschlägt, weil sie die Auswertungsgrenze erreicht hat, empfehlen wir Ihnen, den Aktualisierungszeitplan für jeden Datenfluss anzupassen, um sicherzustellen, dass die Datenquellen nicht gleichzeitig verarbeitet werden.

### <a name="available-power-query-data-sources"></a>Verfügbare Power Query-Datenquellen

Eine Liste der Konnektoren, die Sie zum Importieren von Daten in Customer Insights verwenden können, finden Sie in der [Power Query-Konnektor-Referenz](/power-query/connectors/).

Konnektoren mit einem Häkchen in der Spalte **Customer Insights (Dataflows)** sind verfügbar, um neue Datenquellen basierend auf Power Query zu erstellen. Überprüfen Sie die Dokumentation eines bestimmten Konnektors, um mehr über seine Voraussetzungen zu [Abfragebeschränkungen](/power-query/power-query-online-limits) und andere Details zu erfahren.

## <a name="add-data-from-on-premises-data-sources"></a>Fügen Sie Daten aus lokalen Datenquellen hinzu

Das Einbinden von Daten aus lokalen Datenquellen wird auf der Grundlage von Microsoft Power Platform-Datenflows (PPDF) unterstützt. Beim Einrichten der Umgebung können Sie Dataflows in Customer Insights durch das [Bereitstellen der Microsoft Dataverse-Umgebungs-URL](create-environment.md) aktivieren.

Datenquellen, die nach dem Verknüpfen einer Dataverse-Umgebung mit Customer Insights erstellt wurden, verwenden standardmäßig [Power Platform-Dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Dataflows unterstützen die lokale Konnektivität mithilfe des Datengateways. Sie können Datenquellen, die vor der Verknüpfung einer Dataverse-Umgebung vorhanden waren, durch [Verwenden von lokalen Datengateways](/data-integration/gateway/service-gateway-app) entfernen und neu erstellen.

Daten-Gateways von einer bestehenden Power BI oder Power Apps Umgebung sind sichtbar und Sie können sie in Customer Insights wiederverwenden, wenn sich das Datengateway und die Customer Insights-Umgebung in derselben Azure-Region befinden. Die Seite mit den Datenquellen enthält Links zu der Microsoft Power Platform Umgebung, in der Sie lokale Datengateways anzeigen und konfigurieren können.

> [!IMPORTANT]
> Stellen Sie sicher, dass Ihre Gateways auf die neueste Version aktualisiert sind. Sie können ein Update installieren und ein Gateway über eine Eingabeaufforderung, die auf der Gateway-Anzeige angezeigt wird, direkt installieren oder neu konfigurieren oder [die neueste Version herunterladen](https://powerapps.microsoft.com/downloads/). Wenn Sie nicht die neueste Gateway-Version verwenden, schlägt die Datenflussaktualisierung mit Fehlermeldungen wie **Das Schlüsselwort wird nicht unterstützt: Konfigurationseigenschaften. Parametername: Schlüsselwort** fehl.
>
> Fehler mit lokal-Daten-Gateways in Customer Insights werden oft durch Konfigurationsprobleme verursacht. Weitere Informationen zur Problembehandlung bei Datengateways finden Sie unter [Problembehandlung für das lokale Datengateway](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>Power Query-Datenquellen bearbeiten

> [!NOTE]
> Es ist möglicherweise nicht möglich, Änderungen an Datenquellen vorzunehmen, die derzeit in einem der Prozesse der App verwendet werden (z. B. Segmentierung oder Datenvereinheitlichung).
>
> Auf der Seite **Einstellungen** können Sie den Fortschritt jedes aktiven Prozesses verfolgen. Wenn ein Prozess abgeschlossen ist, können Sie zur Seite **Datenquellen** zurückkehren und Ihre Änderungen vornehmen.

1. Wechseln Sie zu **Daten** > **Datenquellen**.

1. Wählen Sie neben der Datenquelle, die Sie aktualisieren möchten, **Bearbeiten** aus.

1. Übernehmen Sie Ihre Änderungen und Transformationen im Dialogfeld **Power Query – Abfragen bearbeiten** wie in [Erstellen einer neuen Datenquelle](#create-a-new-data-source) beschrieben.

1. Klicken Sie auf **Speichern**, um Ihre Änderungen zu übernehmen und zur Seite **Datenquellen** zurückzukehren.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupt-data"></a>Häufige Gründe für Erfassungsfehler oder beschädigte Daten

### <a name="data-type-does-not-match-data"></a>Datentyp stimmt nicht mit Daten überein

Der häufigste Datentypkonflikt tritt auf, wenn ein Datumsfeld nicht auf das richtige Datumsformat eingestellt ist.

Die Daten können an der Quelle repariert und erneut erfasst werden. Oder reparieren Sie die Transformation in Customer Insights. Reparieren Sie die Transformation wie folgt:

1. Wechseln Sie zu **Daten** > **Datenquellen**.

1. Wählen Sie neben der Datenquelle mit dem beschädigten Daten **Bearbeiten** aus.

1. Wählen Sie **Weiter** aus.

1. Wählen Sie jede der Abfragen aus und suchen Sie nach Transformationen, die in „Angewandte Schritte“ angewendet wurden und falsch sind, oder nach Datumsspalten, die nicht mit einem Datumsformat transformiert wurden.

   :::image type="content" source="media/PQ_corruped_date.png" alt-text="Power Query – Bearbeiten zeigt falsches Datumsformat":::

1. Ändern Sie den Datentyp so, dass er den korrekten Daten entspricht.

1. Wählen Sie **Save** (Speichern). Die Datenquelle wurde aktualisiert.

## <a name="troubleshoot-ppdf-power-query-based-data-source-refresh-issues"></a>Problembehandlung Aktualisierungsprobleme PPDF Power Query-basierte Datenquelle

Wenn die Daten veraltet sind oder Sie nach einer Datenquelleaktualisierung eine Fehlermeldung erhalten, führen Sie die folgenden Schritte aus:

1. Navigieren zu [Power Platform](https://make.powerapps.com).

1. Wählen Sie die **Umgebung** für Ihre Customer Insights-Instanz.

1. Gehen Sie zu **Dataflows**.

1. Wählen Sie für den Dataflow, welcher der Datenquelle in Customer Insights entspricht, die vertikalen Auslassungspunkte (&vellip;) und dann **Aktualisierungsverlauf anzeigen**.

1. Wenn der **Status** des Dataflows auf **Erfolg** steht, hat sich eventuell der Besitz an der Power Query-basierten Datenquelle geändert:

   1. Überprüfen Sie den Aktualisierungszeitplan aus dem Aktualisierungsverlauf.
   1. Legen Sie den Zeitplan des neuen Besitzers fest und speichern Sie die Einstellungen.

1. Wenn der **Status** des Dataflows auf **Fehlgeschlagen** steht:

   1. Laden Sie die Aktualisierungsverlaufsdatei herunter.
   1. Gehen Sie die heruntergeladene Datei nach dem Grund für den Fehler durch.
   1. Wenn der Fehler nicht behoben werden kann, wählen Sie **?** aus, um ein Supportticket zu öffnen. Fügen Sie die heruntergeladene Aktualisierungsverlaufsdatei.


[!INCLUDE [footer-include](includes/footer-banner.md)]
