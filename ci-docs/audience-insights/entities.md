---
title: Entitäten und Datasets
description: Zeigen Sie Daten auf der Seite Entitäten an.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e71c69a6207147d8cd65363d51a5fa6bbf896151
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269375"
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
> ![Auswahl einer Entität](media/data-manager-entities-data.png "Wählen Sie eine Entität")

- Die Registerkarte **Daten** ist standardmäßig ausgewählt und zeigt eine Tabelle mit Details zu den einzelnen Datensätzen der Entität.

> [!div class="mx-imgBorder"]
> ![Feldtabelle](media/data-manager-entities-fields.PNG "Tabelle Felder")

- Das Register **Felder** zeigt eine Tabelle zur Überprüfung der Details für die ausgewählte Entität, wie z. B. Feldnamen, Datentypen und -arten. Die Spalte **Typ** zeigt die mit dem Common Data Model verbundenen Typen, die entweder vom System automatisch identifiziert oder von den Benutzern [manuell abgebildet](map-entities.md) werden. Es handelt sich um semantische Typen, die sich von den Datentypen der Attribute unterscheiden können, z. B. hat das Feld *Email* unten einen Datentyp *Text*, aber sein (semantischer) Common Data Model Typ könnte *Email* oder *EmailAddress* sein.

> [!NOTE]
> Beide Tabellen zeigen nur einen Ausschnitt der Daten Ihrer Entität. Um den vollständigen Datensatz anzuzeigen, gehen Sie zur Seite **Datenquellen**, wählen Sie eine Entität, wählen Sie **Bearbeiten** und zeigen Sie dann die Daten dieser Entität mit dem Power Query-Editor an, wie unter [Datenquellen](data-sources.md) erläutert.

Um mehr über die in die Entität aufgenommenen Daten zu erfahren, finden Sie in der Spalte **Zusammenfassung** einige wichtige Merkmale der Daten, wie z. B. Nullen, fehlende Werte, eindeutige Werte, Zählungen und Verteilungen, die auf Ihre Daten anwendbar sind.

Wählen Sie das Diagrammsymbol, um die Zusammenfassung der Daten anzuzeigen.

> [!div class="mx-imgBorder"]
> ![Zusammenfassungssymbol](media/data-manager-entities-summary.png "Daten-Zusammenfassungstabelle")

### <a name="next-step"></a>Nächster Schritt

Siehe [Vereinheitlichung](data-unification.md), um zu erfahren, wie *Karte*, *Abgleich* und *Zusammenführung* der aufgenommenen Daten.


[!INCLUDE[footer-include](../includes/footer-banner.md)]