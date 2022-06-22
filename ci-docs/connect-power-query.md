---
title: Daten über einen Power Query-Konnektor erfassen (enthält Video)
description: Konnektoren für Datenquellen basierend auf Power Query.
ms.date: 05/09/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: b99c3b446e580f455f9678d54d9db414aea9b331
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011656"
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

1. Wählen Sie **Daten transformieren** aus. In diesem Schritt fügen Sie Entitäten zu Ihrer Datenquelle hinzu. Entitäten sind Datasets. Wenn Sie eine Datenbank haben, die mehrere Datensätze enthält, ist jeder Datensatz eine eigene Entität.

1. Im Dialogfeld **Power Query – Abfragen bearbeiten** können Sie die Daten überprüfen und verfeinern. Die Entitäten, die die in Ihrer ausgewählten Datenquelle identifizierten Systeme aufweisen, erscheinen im linken Fensterbereich.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Dialogfeld „Abfragen bearbeiten“":::

1. Sie können Ihre Daten auch transformieren. Wählen Sie eine Entität zum Bearbeiten oder Transformieren aus. Verwenden Sie die Optionen im Power Query-Fenster zum Anwenden von Transformationen. Jede Transformation ist unter **Angewandte Schritte** aufgeführt. Power Query bietet zahlreiche vorgefertigte Transformationsoptionen. Weitere Informationen finden Sie unter [Power Query-Transformationen](/power-query/power-query-what-is-power-query#transformations).

   Wir empfehlen die Verwendung der folgenden Transformationen:

   - Wenn Sie Daten aus einer CSV-Datei erfassen, enthält die erste Zeile häufig Überschriften. Gehen Sie zu **Transformieren** und wählen Sie **Erste Zeile als Kopfzeilen verwnden**.
   - Stellen Sie sicher, dass der Datentyp richtig eingestellt ist. Wählen Sie beispielsweise für Datumsfelder einen Datumstyp aus.

1. Um weitere Entitäten zu Ihrer Datenquelle im Dialog **Abfragen bearbeiten** hinzuzufügen, gehen Sie zur **Startseite** und wählen Sie **Daten abrufen**. Wiederholen Sie die Schritte 6-10, bis Sie alle Entitäten für dieses Datenquelle hinzugefügt haben.

1. Wählen Sie **Save** (Speichern). Die Seite **Datenquellen** öffnet sich und zeigt die neue Datenquelle im Status **Wird aktualisiert** an.

### <a name="available-power-query-data-sources"></a>Verfügbare Power Query-Datenquellen

Eine Liste der Konnektoren, die Sie zum Importieren von Daten in Customer Insights verwenden können, finden Sie in der [Power Query-Konnektor-Referenz](/power-query/connectors/).

Konnektoren mit einem Häkchen in der Spalte **Customer Insights (Dataflows)** sind verfügbar, um neue Datenquellen basierend auf Power Query zu erstellen. Überprüfen Sie die Dokumentation eines bestimmten Konnektors, um mehr über seine Voraussetzungen zu [Abfragebeschränkungen](/power-query/power-query-online-limits) und andere Details zu erfahren.

## <a name="add-data-from-on-premises-data-sources"></a>Fügen Sie Daten aus lokalen Datenquellen hinzu

Das Einbinden von Daten aus lokalen Datenquellen wird auf der Grundlage von Microsoft Power Platform-Datenflows (PPDF) unterstützt. Beim Einrichten der Umgebung können Sie Dataflows in Customer Insights durch das [Bereitstellen der Microsoft Dataverse-Umgebungs-URL](create-environment.md) aktivieren.

Datenquellen, die nach dem Verknüpfen einer Dataverse-Umgebung mit Customer Insights erstellt wurden, verwenden standardmäßig [Power Platform-Dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Dataflows unterstützen die lokale Konnektivität mithilfe des Datengateways. Sie können Datenquellen, die vor der Verknüpfung einer Dataverse-Umgebung vorhanden waren, durch [Verwenden von lokalen Datengateways](/data-integration/gateway/service-gateway-app) entfernen und neu erstellen.

Datengateways einer vorhandenen Power BI- oder Power Apps-Umgebung werden sichtbar und Sie können sie in Customer Insights wiederverwenden. Die Seite mit den Datenquellen enthält Links zu der Microsoft Power Platform Umgebung, in der Sie lokale Datengateways anzeigen und konfigurieren können.

> [!IMPORTANT]
> Stellen Sie sicher, dass Ihre Gateways auf die neueste Version aktualisiert sind. Sie können ein Update installieren und ein Gateway über eine Eingabeaufforderung, die auf der Gateway-Anzeige angezeigt wird, direkt installieren oder neu konfigurieren oder [die neueste Version herunterladen](https://powerapps.microsoft.com/downloads/). Wenn Sie nicht die neueste Gateway-Version verwenden, schlägt die Datenflussaktualisierung mit Fehlermeldungen wie **Das Schlüsselwort wird nicht unterstützt: Konfigurationseigenschaften. Parametername: Schlüsselwort** fehl.

## <a name="edit-power-query-data-sources"></a>Power Query-Datenquellen bearbeiten

> [!NOTE]
> Es ist möglicherweise nicht möglich, Änderungen an Datenquellen vorzunehmen, die derzeit in einem der Prozesse der App verwendet werden (z. B. *Segmentierung*, *Abgleich* oder *Zusammenführung*).
>
> Auf der Seite **Einstellungen** können Sie den Fortschritt jedes aktiven Prozesses verfolgen. Wenn ein Prozess abgeschlossen ist, können Sie zur Seite **Datenquellen** zurückkehren und Ihre Änderungen vornehmen.

1. Wechseln Sie zu **Daten** > **Datenquellen**.

1. Wählen Sie neben der Datenquelle, die Sie aktualisieren möchten, **Bearbeiten** aus.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

1. Übernehmen Sie Ihre Änderungen und Transformationen im Dialogfeld **Power Query – Abfragen bearbeiten** wie in [Erstellen einer neuen Datenquelle](#create-a-new-data-source) beschrieben.

1. Wählen Sie **Speichern** in Power Query, nachdem Sie Ihre Änderungen abgeschlossen haben, um Ihre Änderungen zu speichern.
