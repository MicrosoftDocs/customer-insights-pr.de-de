---
title: Entitäten in Customer Insights
description: Zeigen Sie Daten auf der Seite Entitäten an.
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610097"
---
# <a name="entities-in-customer-insights"></a>Entitäten in Customer Insights

Nachdem Sie [Konfiguration Ihrer Datenquellen](data-sources.md), gehen Sie zur Seite **Entitäten**, um die Qualität der aufgenommenen Daten zu bewerten. Entitäten werden als Datasets betrachtet. Mehrere Funktionalitäten von Dynamics 365 Customer Insights sind um diese Entitäten herum aufgebaut. Eine genaue Überprüfung kann Ihnen helfen, die Ausgabe dieser Fähigkeiten zu validieren.

Während Sie in Customer Insights arbeiten und Ihre Daten anreichern oder Segmente, Kennzahlen und Aktivitäten erstellen, werden die aus diesen Aktionen erstellten Entitäten im **Entitäten** Seite angezeigt.

## <a name="view-a-list-of-entities"></a>Eine Liste mit Entitäten anzeigen

Gehe zu **Daten** > **Entitäten**, um eine Liste der Entitäten anzuzeigen. Die folgenden Informationen sind für jedes Entität verfügbar.

- **Name**: Name der Datenentität. Wenn Sie ein Warnsymbol neben einem Entitätsnamen sehen, bedeutet dies, dass die Daten für diese Entität nicht erfolgreich geladen wurden.
- **Quelle**: Datenquellentyp, der die Entität erfasst hat.
- **Aktualisiert**: Zeitpunkt der letzten Aktualisierung der Entität.
- **Status**: Details zur letzten Aktualisierung der Entität.

## <a name="explore-a-specific-entitys-data"></a>Die Daten einer bestimmten Einheit untersuchen

1. Gehen Sie zu **Daten** > **Entitäten**.
1. Wählen Sie eine Entität aus, um die Seite Details zu öffnen.  
1. Untersuchen Sie die verschiedenen Felder und Datensätze, die für diese Entität enthalten sind.

- Die Registerkarte **Attribute** ist standardmäßig ausgewählt und zeigt Details für die ausgewählte Entität wie Feldnamen, Datentypen und Typen überprüft werden. Die Spalte **Typ** zeigt die mit dem Common Data Model verbundenen Typen, die entweder vom System automatisch identifiziert oder von den Benutzern [manuell abgebildet](map-entities.md) werden. Diese Typen sind semantische Typen, die sich von den Datentypen der Attribute unterscheiden können. Das Feld *Email* unten hat zum Beispiel einen Datentyp *String*, aber sein (semantischer) Common Data Model-Typ könnte *E-Mail*, *EmailAddress* oder *Identity.Service.Email* sein.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Feldtabelle.":::

   > [!NOTE]
   > Diese Seite zeigt nur ein Beispiel der Daten Ihrer Entität. Um den vollständigen Datensatz anzuzeigen, gehen Sie zur Seite **Datenquellen**, wählen Sie eine Entität, wählen Sie **Bearbeiten** und zeigen Sie dann die Daten dieser Entität mit dem Power Query-Editor an, wie unter [Datenquellen](data-sources.md) erläutert.

   Um mehr über die in die Entität aufgenommenen Daten zu erfahren, finden Sie in der Spalte **Zusammenfassung** einige wichtige Merkmale der Daten, wie z. B. Nullen, fehlende Werte, eindeutige Werte, Zählungen und Verteilungen, die auf Ihre Daten anwendbar sind. Wählen Sie das Diagrammsymbol, um die Zusammenfassung der Daten anzuzeigen.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Daten-Zusammenfassungstabelle":::

- Die Registerkarte **Daten** zeigt Details zu einzelnen Datensätzen der Entität. Die aufgeführten Details hängen vom Datentyp der Entität ab.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Eine Entität auswählen.":::

- Die Registerkarte **Berichte** (für einige Entitäten verfügbar) ermöglicht Ihnen die Visualisierung Ihrer Daten und enthält die folgenden Spalten:

  - **Berichtsname**: Name des Berichts.
  - **Erstellt von**: Name der Person, die die Entität erstellt hat.
  - **Erstellt**: Datum und Uhrzeit der Entitätserstellung.
  - **Bearbeitet von**: Name der Person, die die Entität geändert hat.
  - **Bearbeitet**: Datum und Uhrzeit der Entitätänderung.

[!INCLUDE [footer-include](includes/footer-banner.md)]
