---
title: Kundenaktivitäten
description: Definieren Sie Kundenaktivitäten und zeigen Sie diese in der Kundenzeitleiste an.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: dcef8f0547009e1488f1abe91423fa0bf5b061de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267431"
---
# <a name="customer-activities"></a>Kundenaktivitäten

Kombinieren Sie Kundenaktivitäten aus [verschiedenen Datenquellen](data-sources.md) in Dynamics 365 Customer Insights, um eine Kunden-Zeitleiste zu erstellen, die die Aktivitäten in chronologischer Reihenfolge auflistet. Sie können die Zeitleiste in Customer Engagement Apps in Dynamics 365 über [Kundenkarten-Add-In](customer-card-add-in.md)oder in einem Power BI Dashboard integrieren.

## <a name="define-an-activity"></a>Definieren Sie eine Aktivität

Ihre Datenquellen umfassen Entitäten mit Transaktions- und Aktivitätsdaten aus mehreren Datenquellen. Identifizieren Sie diese Einheiten und wählen Sie die Aktivitäten aus, die Sie auf der Zeitachse des Kunden anzeigen möchten. Wählen Sie die Entität, die Ihre Zielaktivität oder -aktivitäten enthält.

1. Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Aktivitäten**.

1. Wählen Sie **Aktivität hinzufügen**.

   > [!NOTE]
   > Eine Entität muss mindestens ein Attribut vom Typ **Datum** haben, um in eine Kundenzeitachse aufgenommen zu werden, und Sie können keine Entitäten ohne **Datum** Felder hinzufügen. Die Kontrolle **Aktivität hinzufügen** ist deaktiviert, wenn keine solche Entität gefunden wird.

1. Legen Sie im Bereich **Aktivität hinzufügen** die Werte für die folgenden Felder fest:

   - **Entität**: Wählen Sie eine Entität, die Transaktions- oder Aktivitätsdaten enthält.
   - **Primärschlüssel**: Wählen Sie das Feld, das einen Datensatz eindeutig identifiziert. Sie sollte keine doppelten Werte, leere Werte oder fehlende Werte enthalten.
   - **Zeitstempel**: Wählen Sie das Feld, das die Startzeit Ihrer Aktivität darstellt.
   - **Ereignis**: Wählen Sie das Feld aus, das das Ereignis für die Aktivität ist.
   - **Internetadresse**: Wählen Sie das Feld, das eine URL darstellt, die zusätzliche Informationen zu dieser Aktivität liefert. Zum Beispiel das Transaktionssystem, aus dem diese Aktivität stammt. Diese URL kann ein beliebiges Feld aus der Datenquelle sein, oder sie kann mit Hilfe einer Power-Query-Transformation als neues Feld konstruiert werden. Diese URL-Daten werden in der Entität Unified Activity gespeichert, die stromabwärts über APIs konsumiert werden kann.
   - **Details**: Wählen Sie optional das Feld, das für zusätzliche Details hinzugefügt wird.
   - **Symbol**: Wählen Sie optional das Symbol, das diese Aktivität repräsentiert.
   - **Aktivitätstyp**: Definieren Sie den Aktivitätstyp-Verweis auf das Common Data Model, der die semantische Definition der Aktivität am besten beschreibt.

1. Konfigurieren Sie im Abschnitt **Beziehung einrichten** die Details, die zum Verbinden Ihrer Aktivitätsdaten mit dem entsprechenden Kunden verwendet werden.

    - **Aktivitätsentitätsfeld**: Wählen Sie das Feld in Ihrer Aktivitätsentität aus, das zum Herstellen einer Beziehung mit einer anderen Entität verwendet werden soll.
    - **Kundenentität**: Wählen Sie die entsprechende Quellkundenentität aus, mit der Ihre Aktivitätsentität in Beziehung steht. Sie können sich nur auf die Quellkundenentitäten beziehen, die im Datenvereinigungsprozess verwendet werden.
    - **Kundenentitätsfeld**: In diesem Feld wird der im Map-Prozess ausgewählte Primärschlüssel der Quellkundenentität angezeigt. Dieses Primärschlüsselfeld in der Quellkundenentität wird verwendet, um eine Beziehung zur Aktivitätsentität herzustellen.
    - **Name**: Wenn bereits eine Beziehung zwischen dieser Aktivitätsentität und der ausgewählten Quellkundenentität besteht, ist der Beziehungsname schreibgeschützt. Wenn keine solche Beziehung besteht, wird eine neue Beziehung mit dem hier angegebenen Namen erstellt.
   
   > [!div class="mx-imgBorder"]
   > ![Definieren der Entitätsbeziehung](media/activities-entities-define.png "Definieren Sie die Entitätsbeziehung")

1. Wählen Sie **Speichern**, um Ihre Änderungen zu übernehmen.

1. Auf der Seite **Aktivitäten** wählen Sie **Ausführen**.

> [!TIP]
> Es gibt [sechs Arten von Status](system.md#status-types) für Aufgaben/Prozesse. Darüber hinaus [hängen die meisten Prozesse von anderen nachfolgenden Prozessen ab](system.md#refresh-policies). Sie können den Status eines Prozesses auswählen, um Details zum Fortschritt des gesamten Auftrags anzuzeigen. Nach der Auswahl von **Siehe Details** für eine der Aufgaben des Auftrags finden Sie zusätzliche Informationen: Verarbeitungszeit, das letzte Verarbeitungsdatum sowie alle mit der Aufgabe verbundenen Fehler und Warnungen.

## <a name="edit-an-activity"></a>Eine Aktivität bearbeiten

1. Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Aktivitäten**.

2. Wählen Sie die Aktivitätsentität aus, die Sie bearbeiten möchten, und wählen Sie **Bearbeiten** aus. Sie können auch die Maus über die Entitätszeile bewegen und das Symbol **Bearbeiten** auswählen.

3. Klicken Sie auf das Symbol **Bearbeiten**.

4. Aktualisieren Sie im Fensterbereich **Aktivität bearbeiten** die Werte und wählen Sie **Speichern**.

5. Auf der Seite **Aktivitäten** wählen Sie **Ausführen**.

## <a name="delete-an-activity"></a>Löschen einer Aktivität

1. Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Aktivitäten**.

2. Wählen Sie die Aktivitätsentität aus, die Sie entfernen möchten, und wählen Sie **Löschen** aus. Sie können auch die Maus über die Entitätszeile bewegen und das Symbol **Löschen** auswählen. Darüber hinaus können Sie mehrere Aktivitätsentitäten auswählen, die gleichzeitig gelöscht werden sollen.
   > [!div class="mx-imgBorder"]
   > ![Bearbeiten oder Löschen der Entitätsbeziehung](media/activities-entities-edit-delete.png "Bearbeiten oder Löschen der Entitätsbeziehung")

3. Wählen Sie das Symbol **Löschen** aus.

4. Bestätigen Sie den Löschvorgang.


[!INCLUDE[footer-include](../includes/footer-banner.md)]