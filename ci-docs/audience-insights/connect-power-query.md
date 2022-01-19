---
title: Daten über einen Power Query-Konnektor erfassen (enthält Video)
description: Connectors für Datenquellen basierend auf Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: aae49be4364676ecc7a307e60eeca13859f1662a
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934977"
---
# <a name="connect-to-a-power-query-data-source"></a>Mit einer Power Query-Datenquelle verbinden

Power Query bietet eine breite Palette von Connectos zum Erfassen von Daten. Die meisten dieser Connectors werden von Dynamics 365 Customer Insights unterstützt. 

Das Hinzufügen von Datenquellen basierend auf Power Query-Konnektoren folgt im Allgemeinen den in diesem Abschnitt beschriebenen Schritten. Abhängig vom verwendeten Connector sind jedoch unterschiedliche Informationen erforderlich. Weitere Informationen finden Sie in der Dokumentation zu einzelnen Konnektoren in der [Power Query-Konnektor-Referenz](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Erstellen Sie eine neue Datenquelle

1. Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.

1. Wählen Sie **Datenquelle hinzufügen**.

1. Wählen Sie **Microsoft Power Query** und dann **Weiter** aus.

1. Geben Sie einen **Namen** für die Datenquelle und wählen Sie **Weiter**, um die Datenquelle zu erstellen.

1. Wählen Sie einen der [verfügbaren Konnektoren](#available-power-query-data-sources) aus. In diesem Beispiel wählen wir den Konnektor **Text/CSV** aus.

1. Geben Sie die erforderlichen Details für den ausgewählten Connector in das Feld **Verbindungseinstellungen** ein und wählen Sie **Weiter**, um eine Vorschau der Daten zu sehen.

1. Wählen Sie **Daten transformieren** aus. In diesem Schritt fügen Sie Entitäten zu Ihrer Datenquelle hinzu. Entitäten sind Datasets. Wenn Sie eine Datenbank haben, die mehrere Datensätze enthält, ist jeder Datensatz eine eigene Entität.

1. Im Dialogfeld **Power Query – Abfragen bearbeiten** können Sie die Daten überprüfen und verfeinern. Die Entitäten, die die in Ihrer ausgewählten Datenquelle identifizierten Systeme aufweisen, erscheinen im linken Fensterbereich.

   > [!div class="mx-imgBorder"]
   > ![Dialogfeld „Abfragen bearbeiten“.](media/data-manager-configure-edit-queries.png "Dialogfeld „Abfragen bearbeiten“")

1. Sie können Ihre Daten auch transformieren. Wählen Sie eine Entität zum Bearbeiten oder Transformieren aus. Verwenden Sie die Optionen im Fenster „Power Query“, um Transformationen anzuwenden. Jede Transformation wird unter **Angewandte Schritte** aufgelistet. Power Query bietet zahlreiche vorgefertigte Transformationsoptionen. Weitere Informationen finden Sie im Artikel [Power Query-Transformationen](/power-query/power-query-what-is-power-query#transformations).

1. Sie können Ihrer Datenquelle weitere Entitäten hinzufügen, indem Sie im Dialog **Abfragen bearbeiten** **Daten holen** wählen.

   Wir empfehlen die Verwendung der folgenden Transformationen:

   - Wenn Sie Daten aus einer CSV-Datei erfassen, enthält die erste Zeile häufig Überschriften. Wechseln Sie zu **Tabelle transformieren** aus und danach **Überschriften als erste Zeile verwenden**.
   - Stellen Sie sicher, dass der Datentyp richtig eingestellt ist.

1. Wählen Sie in der rechten unteren Ecke des Fensters „Power Query“ **Speichern** aus, um die Transformationen zu speichern. Nach dem Speichern finden Sie Ihre Datenquelle auf **Daten** > **Datenquellen**.

1. Auf dieser Seite **Datenquellen** werden Sie feststellen, dass sich das neue Datenquelle im Status **Wird aktualisiert** befindet.

## <a name="available-power-query-data-sources"></a>Verfügbare Power Query-Datenquellen

Eine Liste der Konnektoren, die Sie zum Importieren von Daten in Customer Insights verwenden können, finden Sie in der [Power Query-Konnektor-Referenz](/power-query/connectors/). 

Connectors mit einem Häkchen in der Spalte **Customer Insights (Datenflows)** sind verfügbar, um neue Datenquellen basierend auf Power Query zu erstellen. Lesen Sie die Dokumentation eines bestimmten Connectors, um mehr über seine Voraussetzungen, Einschränkungen und andere Details zu erfahren.

## <a name="edit-power-query-data-sources"></a>Power Query-Datenquellen bearbeiten

> [!NOTE]
> Es ist möglicherweise nicht möglich, Änderungen an Datenquellen vorzunehmen, die derzeit in einem der Prozesse der App verwendet werden (z. B. *Segmentierung*, *Abgleich* oder *Zusammenführung*). 
>
> Auf der Seite **Einstellungen** können Sie den Fortschritt jedes aktiven Prozesses verfolgen. Wenn ein Prozess abgeschlossen ist, können Sie zur Seite **Datenquellen** zurückkehren und Ihre Änderungen vornehmen.

1. Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.

2. Wählen Sie die vertikalen Auslassungspunkte neben dem Datenquelle, die Sie ändern möchten, und wählen Sie **Bearbeiten** aus dem Dropdown-Menü.

   > [!div class="mx-imgBorder"]
   > ![Optionen bearbeiten.](media/edit-option-data-sources.png "Optionen bearbeiten")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Übernehmen Sie Ihre Änderungen und Transformationen in das Dialogfeld **Power Query – Abfragen bearbeiten** wie im Abschnitt [Eine neue Datenquelle erstellen](#create-a-new-data-source) beschrieben ein.

4. Wählen Sie in Power Query nach Abschluss Ihrer Änderungen **Speichern** aus, um Ihre Änderungen zu speichern.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
