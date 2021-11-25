---
title: Entitäten und Datasets
description: Zeigen Sie Daten auf der Seite Entitäten an.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 2a207a3dcad4bf192efb6ee1554195f10b19670b
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732079"
---
# <a name="entities-in-audience-insights"></a>Entitäten in Zielgruppen-Insights

Nachdem Sie [Konfiguration Ihrer Datenquellen](data-sources.md), gehen Sie zur Seite **Entitäten**, um die Qualität der aufgenommenen Daten zu bewerten. Entitäten werden als Datasets betrachtet. Mehrere Funktionalitäten von Dynamics 365 Customer Insights sind um diese Entitäten herum aufgebaut. Eine genaue Überprüfung kann Ihnen helfen, die Ausgabe dieser Fähigkeiten zu validieren.

Die Seite **Entitäten** listet Entitäten auf und enthält mehrere Spalten:

- **Name**: Der Name Ihrer Datenentität. Wenn Sie ein Warnsymbol neben einem Entitätsnamen sehen, bedeutet dies, dass die Daten für diese Entität nicht erfolgreich geladen wurden.
- **Quelle**: Zeigt die Datenquelle der Entität an
- **Erstellt von**: Name der Person, die die Entität erstellt hat
- **Erstellt**: Datum und Uhrzeit der Entitätserstellung
- **Aktualisiert**: Name der Person, die die Entität aktualisiert hat
- **Status** : Details zur letzten Aktualisierung der Entität

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Die Daten einer bestimmten Einheit untersuchen

Wählen Sie eine Entität aus, um die verschiedenen Felder und Datensätze innerhalb dieser Entität zu untersuchen.

> [!div class="mx-imgBorder"]
> ![Eine Entität auswählen.](media/data-manager-entities-data.png "Eine Entität auswählen")

- Die Registerkarte **Daten** zeigt eine Tabelle mit Details zu einzelnen Datensätzen der Entität.

> [!div class="mx-imgBorder"]
> ![Feldtabelle.](media/data-manager-entities-fields.PNG "Tabelle Felder")

- Die Registerkarte **Attribute** ist standardmäßig ausgewählt und zeigt eine Tabelle an, in der Details für die ausgewählte Entität wie Feldnamen, Datentypen und Typen überprüft werden. Die Spalte **Typ** zeigt die mit dem Common Data Model verbundenen Typen, die entweder vom System automatisch identifiziert oder von den Benutzern [manuell abgebildet](map-entities.md) werden. Diese Typen sind semantische Typen, die sich von den Datentypen der Attribute unterscheiden können. Das Feld *E-Mail* unten hat zum Beispiel einen Datentyp *Text*, aber sein (semantischer) Common Data Model-Typ könnte *E-Mail* oder *E-Mail-Addresse* sein.

> [!NOTE]
> Beide Tabellen zeigen nur einen Ausschnitt der Daten Ihrer Entität. Um den vollständigen Datensatz anzuzeigen, gehen Sie zur Seite **Datenquellen**, wählen Sie eine Entität, wählen Sie **Bearbeiten** und zeigen Sie dann die Daten dieser Entität mit dem Power Query-Editor an, wie unter [Datenquellen](data-sources.md) erläutert.

Um mehr über die in die Entität aufgenommenen Daten zu erfahren, finden Sie in der Spalte **Zusammenfassung** einige wichtige Merkmale der Daten, wie z. B. Nullen, fehlende Werte, eindeutige Werte, Zählungen und Verteilungen, die auf Ihre Daten anwendbar sind.

Wählen Sie das Diagrammsymbol, um die Zusammenfassung der Daten anzuzeigen.

> [!div class="mx-imgBorder"]
> ![Zusammenfassungssymbol.](media/data-manager-entities-summary.png "Daten-Zusammenfassungstabelle")

## <a name="entity-specific-information"></a>Entitätsspezifische Informationen

Der folgende Abschnitt enthält Informationen zu einigen vom System erstellten Entitäten.

### <a name="corrupted-data-sources"></a>Beschädigte Datenquellen

Felder aus einer erfassten Datenquelle können beschädigte Daten enthalten. Datensätze mit beschädigten Feldern werden in vom System erstellten Entitäten verfügbar gemacht. Wenn Sie über beschädigte Datensätze Bescheid wissen, können Sie erkennen, welche Daten auf dem Quellsystem überprüft und aktualisiert werden müssen. Nach der nächsten Aktualisierung des Datenquelle werden die korrigierten Datensätze in Customer Insights aufgenommen und an Downstream-Prozesse weitergegeben. 

Beispielsweise hat eine Spalte „Geburtstag“ den Datentyp „Datum“. Der Geburtstag eines Kundendatensatzes ist als „01.01.19777“ eingetragen. Das System kennzeichnet diesen Datensatz als beschädigt. Jemand kann jetzt den Geburtstag im Quellsystem auf „1977“ ändern. Nach einer automatisierten Aktualisierung der Datenquellen hat das Feld jetzt ein gültiges Format und der Datensatz wird aus der beschädigten Entität entfernt. 

Gehen Sie zu **Daten** > **Entitäten** und suchen Sie nach den korrumpierten Entitäten im Abschnitt **System**. Benennungsschema beschädigter Entitäten: „DataSourceName_EntityName_corrupt“.

Customer Insights verarbeitet beschädigte Datensätze weiterhin. Sie können jedoch Probleme beim Arbeiten mit den vereinheitlichten Daten verursachen.

Die folgenden Prüfungen werden für die erfassten Daten ausgeführt, um beschädigte Datensätze zu erkennen: 

- Der Wert eines Felds stimmt nicht mit dem Datentyp seiner Spalte überein.
- Felder enthalten Zeichen, die dazu führen, dass die Spalten nicht dem erwarteten Schema entsprechen. Beispiel: falsch formatierte Anführungszeichen, nicht in Escape-Zeichen gesetzte Anführungszeichen oder Zeilenumbruchzeichen.
- Wenn datetime-/date-/datetimeoffset-Spalten vorhanden sind, muss deren Format im Modell festgelegt werden, wenn nicht das Standard-ISO-Format genutzt wird.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
