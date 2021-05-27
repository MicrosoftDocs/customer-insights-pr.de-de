---
title: Entitäten und Datasets
description: Zeigen Sie Daten auf der Seite Entitäten an.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049393"
---
# <a name="entities-in-audience-insights"></a>Entitäten in Zielgruppen-Insights

Nachdem Sie [Konfiguration Ihrer Datenquellen](data-sources.md), gehen Sie zur Seite **Entitäten**, um die Qualität der aufgenommenen Daten zu bewerten. Entitäten werden als Datasets betrachtet. Mehrere Funktionalitäten von Dynamics 365 Customer Insights sind um diese Entitäten herum aufgebaut. Eine genaue Überprüfung kann Ihnen helfen, die Ausgabe dieser Fähigkeiten zu validieren.

Die Seite **Entitäten** listet Entitäten auf und enthält mehrere Spalten:

- **Name**: Der Name Ihrer Datenentität. Wenn Sie ein Warnsymbol neben einem Entitätsnamen sehen, bedeutet dies, dass die Daten für diese Entität nicht erfolgreich geladen wurden.
- **Quelle**: Zeigt die Datenquelle der Entität an
- **Erstellt von**: Name der Person, die die Entität erstellt hat
- **Erstellt**: Datum und Uhrzeit der Entitätserstellung
- **Aktualisiert von**: Name der Person, die die Entität aktualisiert hat
- **Zuletzt aktualisiert**: Datum und Uhrzeit der letzten Aktualisierung der Entität
- **Letzte Aktualisierung**: Datum und Uhrzeit der letzten Datenaktualisierung

## <a name="exploring-a-specific-entitys-data"></a>Erforschung der Daten einer bestimmten Einheit

Wählen Sie eine Entität aus, um die verschiedenen Felder und Datensätze innerhalb dieser Entität zu untersuchen.

> [!div class="mx-imgBorder"]
> ![Eine Entität auswählen](media/data-manager-entities-data.png "Wählen Sie eine Entität")

- Die Registerkarte **Daten** zeigt eine Tabelle mit Details zu einzelnen Datensätzen der Entität.

> [!div class="mx-imgBorder"]
> ![Feldtabelle](media/data-manager-entities-fields.PNG "Tabelle Felder")

- Die Registerkarte **Attribute** ist standardmäßig ausgewählt und zeigt eine Tabelle an, in der Details für die ausgewählte Entität wie Feldnamen, Datentypen und Typen überprüft werden. Die Spalte **Typ** zeigt die mit dem Common Data Model verbundenen Typen, die entweder vom System automatisch identifiziert oder von den Benutzern [manuell abgebildet](map-entities.md) werden. Es handelt sich um semantische Typen, die sich von den Datentypen der Attribute unterscheiden können, z. B. hat das Feld *Email* unten einen Datentyp *Text*, aber sein (semantischer) Common Data Model Typ könnte *Email* oder *EmailAddress* sein.

> [!NOTE]
> Beide Tabellen zeigen nur einen Ausschnitt der Daten Ihrer Entität. Um den vollständigen Datensatz anzuzeigen, gehen Sie zur Seite **Datenquellen**, wählen Sie eine Entität, wählen Sie **Bearbeiten** und zeigen Sie dann die Daten dieser Entität mit dem Power Query-Editor an, wie unter [Datenquellen](data-sources.md) erläutert.

Um mehr über die in die Entität aufgenommenen Daten zu erfahren, finden Sie in der Spalte **Zusammenfassung** einige wichtige Merkmale der Daten, wie z. B. Nullen, fehlende Werte, eindeutige Werte, Zählungen und Verteilungen, die auf Ihre Daten anwendbar sind.

Wählen Sie das Diagrammsymbol, um die Zusammenfassung der Daten anzuzeigen.

> [!div class="mx-imgBorder"]
> ![Zusammenfassungssymbol](media/data-manager-entities-summary.png "Daten-Zusammenfassungstabelle")

### <a name="next-step"></a>Nächster Schritt

Siehe [Vereinheitlichung](data-unification.md), um zu erfahren, wie *Karte*, *Abgleich* und *Zusammenführung* der aufgenommenen Daten.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
