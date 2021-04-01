---
title: Datenerfassung über einen Power Query Konnektor
description: Connectors für Datenquellen basierend auf Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: b9a1b30e37c3792aa7bdfcfc177da9e8a32c324d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596912"
---
# <a name="connect-to-a-power-query-data-source"></a>Mit einer Power Query-Datenquelle verbinden

Power Query bietet eine breite Palette von Connectos zum Erfassen von Daten. Die meisten dieser Connectors werden von Dynamics 365 Customer Insights unterstützt. Das Hinzufügen von Datenquellen basierend auf Power Query-Connectors erfolgt im Allgemeinen gemäß den im nächsten Abschnitt beschriebenen Schritten. Abhängig vom verwendeten Connector sind jedoch unterschiedliche Informationen erforderlich. Weitere Informationen finden Sie in der Dokumentation zu den einzelnen Connectors im [Power Query-Connectorverweis](/power-query/connectors/).

## <a name="create-a-new-data-source"></a>Erstellen Sie eine neue Datenquelle

1. Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.

1. Wählen Sie **Datenquelle hinzufügen**.

1. Wählen Sie die Methode **Daten importieren** und wählen Sie **Weiter**.

1. Geben Sie einen **Namen** für die Datenquelle und wählen Sie **Weiter**, um die Datenquelle zu erstellen. Namensrichtlinien: 
   - Beginnen Sie mit einem Buchstaben.
   - Verwenden Sie nur Buchstaben und Zahlen. Leerzeichen und Sonderzeichen sind nicht zulässig.
   - Verwenden Sie zwischen 3 und 64 Zeichen.

1. Wählen Sie einen der [verfügbaren Konnektoren](#available-power-query-data-sources) aus. Für dieses Beispiel wählen wir den Connector **Text/CSV**.

1. Geben Sie die erforderlichen Details für den ausgewählten Connector in das Feld **Verbindungseinstellungen** ein und wählen Sie **Weiter**, um eine Vorschau der Daten zu sehen.

1. Wählen Sie **Daten transformieren** aus. In diesem Schritt fügen Sie Entitäten zu Ihrer Datenquelle hinzu. Entitäten sind Datasets. Wenn Sie eine Datenbank haben, die mehrere Datensätze enthält, ist jeder Datensatz eine eigene Entität.

1. Im Dialogfeld **Power Query – Abfragen bearbeiten** können Sie die Daten überprüfen und verfeinern. Die Entitäten, die die in Ihrer ausgewählten Datenquelle identifizierten Systeme aufweisen, erscheinen im linken Fensterbereich.

   > [!div class="mx-imgBorder"]
   > ![Dialogfeld „Abfragen bearbeiten“](media/data-manager-configure-edit-queries.png "Dialogfeld „Abfragen bearbeiten“")

1. Sie können Ihre Daten auch transformieren. Wählen Sie eine Entität zum Bearbeiten oder Transformieren aus. Verwenden Sie die Optionen im Fenster „Power Query“, um Transformationen anzuwenden. Jede Transformation wird unter **Angewandte Schritte** aufgelistet. Power Query bietet zahlreiche vorgefertigte Transformationsoptionen. Weitere Informationen finden Sie im Artikel [Power Query-Transformationen](/power-query/power-query-what-is-power-query#transformations).

1. Sie können Ihrer Datenquelle weitere Entitäten hinzufügen, indem Sie im Dialog **Abfragen bearbeiten** **Daten holen** wählen.

   Diese Transformationen werden dringend empfohlen:

   - Wenn Sie Daten aus einer CSV-Datei erfassen, enthält die erste Zeile häufig Überschriften. Wechseln Sie zu **Tabelle transformieren** aus und danach **Überschriften als erste Zeile verwenden**.
   - Stellen Sie sicher, dass der Datentyp richtig eingestellt ist.

1. Wählen Sie in der rechten unteren Ecke des Fensters „Power Query“ **Speichern** aus, um die Transformationen zu speichern. Nach dem Speichern finden Sie Ihre Datenquelle auf **Daten** > **Datenquellen**.

1. Auf dieser Seite **Datenquellen** werden Sie feststellen, dass sich das neue Datenquelle im Status **Wird aktualisiert** befindet.

## <a name="available-power-query-data-sources"></a>Verfügbare Power Query-Datenquellen

Eine aktuelle Liste derConnectors, die Sie zum Importieren von Daten in Customer Insights auswählen können, finden Sie unter [Power Query-Connectorverweis](/power-query/connectors/). 

Connectors mit einem Häkchen in der Spalte **Customer Insights (Datenflows)** sind verfügbar, um neue Datenquellen basierend auf Power Query zu erstellen. Lesen Sie die Dokumentation eines bestimmten Connectors, um mehr über seine Voraussetzungen, Einschränkungen und andere Details zu erfahren.

## <a name="edit-power-query-data-sources"></a>Power Query-Datenquellen bearbeiten

> [!NOTE]
> Es ist möglicherweise nicht möglich, Änderungen an Datenquellen vorzunehmen, die derzeit in einem der Prozesse der App verwendet werden (z. B. *Segmentierung*, *Abgleich* oder *Zusammenführung*). 
>
> Über die Seite **Einstellungen** können Sie den Fortschritt jedes aktiven Prozesses verfolgen. Wenn ein Prozess abgeschlossen ist, können Sie zur Seite **Datenquellen** zurückkehren und Ihre Änderungen vornehmen.

1. Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.

2. Wählen Sie die vertikalen Auslassungspunkte neben der Datenquelle aus, die Sie ändern möchten, und wählen Sie **Bearbeiten** aus dem Dropdownmenü aus.

   > [!div class="mx-imgBorder"]
   > ![Optionen bearbeiten](media/edit-option-data-sources.png "Optionen bearbeiten")

3. Übernehmen Sie Ihre Änderungen und Transformationen in das Dialogfeld **Power Query – Abfragen bearbeiten** wie im Abschnitt [Eine neue Datenquelle erstellen](#create-a-new-data-source) beschrieben ein.

4. Wählen Sie in Power Query nach Abschluss Ihrer Änderungen **Speichern** aus, um Ihre Änderungen zu speichern.


[!INCLUDE[footer-include](../includes/footer-banner.md)]