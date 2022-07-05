---
title: Entitäten in Customer Insights
description: Zeigen Sie Daten auf der Seite Entitäten an.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 4abb7704710ac269a4f3c9463fe905fa6eec3234
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081509"
---
# <a name="entities-in-customer-insights"></a>Entitäten in Customer Insights

Nachdem Sie [Konfiguration Ihrer Datenquellen](data-sources.md), gehen Sie zur Seite **Entitäten**, um die Qualität der aufgenommenen Daten zu bewerten. Entitäten werden als Datasets betrachtet. Mehrere Funktionalitäten von Dynamics 365 Customer Insights sind um diese Entitäten herum aufgebaut. Eine genaue Überprüfung kann Ihnen helfen, die Ausgabe dieser Fähigkeiten zu validieren.

Die Seite **Entitäten** listet Entitäten auf und enthält die folgenden Spalten:

- **Name**: Der Name der Datenentität. Wenn Sie ein Warnsymbol neben einem Entitätsnamen sehen, bedeutet dies, dass die Daten für diese Entität nicht erfolgreich geladen wurden.
- **Quelle**: Datenquellentyp, der die Entität erfasst hat.
- **Aktualisiert**: Zeitpunkt der letzten Aktualisierung der Entität.
- **Status**: Details zur letzten Aktualisierung der Entität.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Die Daten einer bestimmten Einheit untersuchen

1. Gehen Sie zu **Daten** > **Entitäten**.
1. Wählen Sie auf der Seite **Entitäten** eine Entität aus, um die Detailseite zu öffnen.  
1. Untersuchen Sie die verschiedenen Felder und Datensätze, die für diese Entität enthalten sind.

- Die Registerkarte **Attribute** ist standardmäßig ausgewählt und zeigt eine Tabelle an, in der Details für die ausgewählte Entität wie Feldnamen, Datentypen und Typen überprüft werden. Die Spalte **Typ** zeigt die mit dem Common Data Model verbundenen Typen, die entweder vom System automatisch identifiziert oder von den Benutzern [manuell abgebildet](map-entities.md) werden. Diese Typen sind semantische Typen, die sich von den Datentypen der Attribute unterscheiden können. Das Feld *E-Mail* unten hat zum Beispiel einen Datentyp *Text*, aber sein (semantischer) Common Data Model-Typ könnte *E-Mail* oder *E-Mail-Addresse* sein.

> [!div class="mx-imgBorder"]
> ![Feldtabelle.](media/data-manager-entities-fields.PNG "Tabelle Felder")

> [!NOTE]
> Diese Seite zeigt nur ein Beispiel der Daten Ihrer Entität. Um den vollständigen Datensatz anzuzeigen, gehen Sie zur Seite **Datenquellen**, wählen Sie eine Entität, wählen Sie **Bearbeiten** und zeigen Sie dann die Daten dieser Entität mit dem Power Query-Editor an, wie unter [Datenquellen](data-sources.md) erläutert.

Um mehr über die in die Entität aufgenommenen Daten zu erfahren, finden Sie in der Spalte **Zusammenfassung** einige wichtige Merkmale der Daten, wie z. B. Nullen, fehlende Werte, eindeutige Werte, Zählungen und Verteilungen, die auf Ihre Daten anwendbar sind. Wählen Sie das Diagrammsymbol, um die Zusammenfassung der Daten anzuzeigen.

> [!div class="mx-imgBorder"]
> ![Zusammenfassungssymbol.](media/data-manager-entities-summary.png "Daten-Zusammenfassungstabelle")

- Die Registerkarte **Daten** zeigt eine Tabelle mit Details zu einzelnen Datensätzen der Entität. Die aufgeführten Details hängen vom Datentyp der Entität ab.

> [!div class="mx-imgBorder"]
> ![Eine Entität auswählen.](media/data-manager-entities-data.png "Eine Entität auswählen")

- Die Registerkarte **Berichte** (für einige Entitäten verfügbar) ermöglicht Ihnen die Visualisierung Ihrer Daten und enthält die folgenden Spalten:

  - **Berichtsname**: Name des Berichts.
  - **Erstellt von**: Name der Person, die die Entität erstellt hat.
  - **Erstellt**: Datum und Uhrzeit der Entitätserstellung.
  - **Bearbeitet von**: Name der Person, die die Entität geändert hat.
  - **Bearbeitet**: Datum und Uhrzeit der Entitätänderung. 

## <a name="entity-specific-information"></a>Entitätsspezifische Informationen

Der folgende Abschnitt enthält Informationen zu einigen vom System erstellten Entitäten.

### <a name="corrupted-data-sources"></a>Beschädigte Datenquellen

Felder aus einer erfassten Datenquelle können beschädigte Daten enthalten. Datensätze mit beschädigten Feldern werden in vom System erstellten Entitäten verfügbar gemacht. Wenn Sie über beschädigte Datensätze Bescheid wissen, können Sie erkennen, welche Daten auf dem Quellsystem überprüft und aktualisiert werden müssen. Nach der nächsten Aktualisierung des Datenquelle werden die korrigierten Datensätze in Customer Insights aufgenommen und an Downstream-Prozesse weitergegeben. 

Beispielsweise hat eine Spalte „Geburtstag“ den Datentyp „Datum“. Der Geburtstag eines Kundendatensatzes ist als „01.01.19777“ eingetragen. Das System kennzeichnet diesen Datensatz als beschädigt. Jemand kann jetzt den Geburtstag im Quellsystem auf „1977“ ändern. Nach einer automatisierten Aktualisierung der Datenquellen hat das Feld jetzt ein gültiges Format und der Datensatz wird aus der beschädigten Entität entfernt. 

Gehen Sie zu **Daten** > **Entitäten** und suchen Sie nach den korrumpierten Entitäten im Abschnitt **System**. Benennungsschema beschädigter Entitäten: „DataSourceName_EntityName_corrupt“. Wählen Sie eine beschädigte Entität aus, um alle beschädigten Felder und den Grund auf individueller Datensatzebene zu identifizieren.
> [!div class="mx-imgBorder"]
> ![Beschädigungsgrund.](media/corruption-reason.png "Beschädigungsgrund")

Customer Insights verarbeitet beschädigte Datensätze weiterhin. Sie können jedoch Probleme beim Arbeiten mit den vereinheitlichten Daten verursachen.

Die folgenden Prüfungen werden für die erfassten Daten ausgeführt, um beschädigte Datensätze zu erkennen: 

- Der Wert eines Felds stimmt nicht mit dem Datentyp seiner Spalte überein.
- Felder enthalten Zeichen, die dazu führen, dass die Spalten nicht dem erwarteten Schema entsprechen. Beispiel: falsch formatierte Anführungszeichen, nicht in Escape-Zeichen gesetzte Anführungszeichen oder Zeilenumbruchzeichen.
- Wenn datetime/date/datetimeoffset-Spalten vorhanden sind, muss deren Format im Modell angegeben werden, wenn es nicht dem Standard-ISO-Format entspricht.


[!INCLUDE [footer-include](includes/footer-banner.md)]
