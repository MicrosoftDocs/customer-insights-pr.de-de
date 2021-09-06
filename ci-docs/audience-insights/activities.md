---
title: Kundenaktivitäten
description: Definieren Sie Kundenaktivitäten und zeigen Sie diese in der Kundenzeitleiste an.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 6ebe899d3e3da43c4108678cd2e4f9a986e18ab35e839044becab4619adb0f14
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033630"
---
# <a name="customer-activities"></a>Kundenaktivitäten

Kombinieren Sie Kundenaktivitäten von [verschiedene Datenquellen](data-sources.md) in Dynamics 365 Customer Insights, um eine Zeitleiste zu erstellen, in der die Aktivitäten chronologisch aufgelistet sind. Fügen Sie die Zeitleiste in Dynamics 365-Apps mit der [Kundenkarten-Add-In](customer-card-add-in.md)-Lösung oder in einem Power BI-Dashboard ein.

## <a name="define-an-activity"></a>Definieren Sie eine Aktivität

Ihre Datenquellen umfassen Entitäten mit Transaktions- und Aktivitätsdaten aus mehreren Datenquellen. Identifizieren Sie diese Einheiten und wählen Sie die Aktivitäten aus, die Sie auf der Zeitachse des Kunden anzeigen möchten. Wählen Sie die Entität, die Ihre Zielaktivität oder -aktivitäten enthält.

> [!NOTE]
> Eine Entität muss mindestens ein Attribut vom Typ **Datum** haben, um in eine Kundenzeitachse aufgenommen zu werden, und Sie können keine Entitäten ohne **Datum** Felder hinzufügen. Die Kontrolle **Aktivität hinzufügen** ist deaktiviert, wenn keine solche Entität gefunden wird.

1. Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Aktivitäten**.

1. WählenSie **Aktivität hinzufügen** aus, um die geführte Erfahrung für den Aktivitäts-Setup-Prozess zu starten.

1. Im Schritt **Aktivitätsdaten** stellen Sie die Werte für die folgenden Felder ein:

   - **Aktivitätsname**: Wählen Sie einen Namen für Ihre Aktivität.
   - **Entität**: Wählen Sie eine Entität aus, die Transaktions- oder Aktivitätsdaten enthält.
   - **Primärschlüssel**: Wählen Sie das Feld, das einen Datensatz eindeutig identifiziert. Sie sollte keine doppelten Werte, leere Werte oder fehlende Werte enthalten.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Richten Sie die Aktivitätsdaten mit Name, Entität und Primärschlüssel ein.":::

1. Wählen Sie **Weiter** aus, um zum nächsten Schritt zu navigieren.

1. Konfigurieren Sie im Schritt **Beziehung** die Details, die zum Verbinden Ihrer Aktivitätsdaten mit dem entsprechenden Kunden verwendet werden. Dieser Schritt visualisiert die Verbindung zwischen Entitäten.  

   - **Erste**: Fremdfeld in Ihrer Aktivitätsentität, das zum Herstellen einer Beziehung mit einer anderen Entität verwendet werden soll.
   - **Zweite**: Entsprechende Quellkundenentität, mit der die Aktivitätsentität zur Beziehung hinzugefügt wird. Sie können sich nur auf Quellkundenentitäten beziehen, die im Datenvereinigungsprozess verwendet werden.
   - **Dritte**: Wenn bereits eine Beziehung zwischen dieser Aktivitätsentität und der ausgewählten Quellkundenentität besteht, ist der Beziehungsname schreibgeschützt. Wenn keine solche Beziehung besteht, wird eine neue Beziehung mit dem Namen erstellt, den Sie in diesem Feld angeben.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definieren der Entitätsbeziehung.":::

1. Wählen Sie **Weiter** aus, um zum nächsten Schritt zu navigieren. 

1. Im Schritt **Vereinheitlichung der Aktivitäten** wählen Sie das Aktivitätsereignis und die Startzeit Ihrer Aktivität. 
   - **Erforderliche Felder**
      - **Ereignisaktivität**: Feld, das das Ereignis für diese Aktivität ist.
      - **Zeitstempel**: Feld, das die Startzeit der Aktivität darstellt.

   - **Optionale Felder**
      - **Zusätzliches Detail**: Feld mit relevanten Informationen für diese Aktivität.
      - **Symbol**: Symbol, das diesen Aktivitätstyp am besten darstellt.
      - **Webadresse**: Feld mit einer URL mit Informationen zu dieser Aktivität. Zum Beispiel das Transaktionssystem, aus dem diese Aktivität stammt. Diese URL kann ein beliebiges Feld aus der Datenquelle sein, oder sie kann mit Hilfe einer Power-Query-Transformation als neues Feld konstruiert werden. Die URL-Daten werden in der *Einheitliche Aktivität*-Entität gespeichert, die mit [APIs](apis.md) im Downstream verbraucht werden kann.
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Geben Sie die Kundenaktivitätsdaten in einer „Einheitliche Aktivität“-Entität an.":::

1. Klicken Sie auf **Weiter**, um zum nächsten Schritt zu wechseln. Sie können **Abschließen und überprüfen** auswählen, um die Aktivität jetzt mit dem Aktivitätstyp **Andere** zu speichern. 

1. Im Schritt **Aktivitätstyp** wählen Sie Schritt für Schritt den Aktivitätstyp und optional aus, ob Sie einige der Aktivitätstypen für die Verwendung in anderen Bereichen von Customer Insights semantisch zuordnen möchten. Zurzeit können *Abonnement* und *SalesOrderLine* Aktivitätstypen semantisch zugeordnet werden, nachdem die Felder für die Zuordnung definiert wurden. Wenn ein Aktivitätstyp für die neue Aktivität nicht relevant ist, können Sie *Andere* oder *Neu erstellen* für einen benutzerdefinierten Aktivitätstyp auswählen.

1. Klicken Sie auf **Weiter**, um zum nächsten Schritt zu wechseln. 

1. Im Schritt **Überprüfen** Schritt überprüfen Sie Ihre Auswahl. Kehren Sie zu einem der vorherigen Schritte zurück und aktualisieren Sie die Informationen bei Bedarf.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Überprüfen Sie die angegebenen Felder für eine Aktivität.":::
   
1. Wählen Sie **Aktivität speichern** aus, um Ihre Änderungen zu übernehmen, und wählen Sie **Fertig** aus, um zu **Daten** > **Aktivitäten** zurückzukehren. Hier sehen Sie, welche Aktivitäten in der Zeitleiste angezeigt werden sollen. 

1. Wählen Sie auf der Seite **Aktivitäten** **Ausführen** aus, um die Aktivität zu verarbeiten. 

> [!TIP]
> Es gibt [sechs Arten von Status](system.md#status-types) für Aufgaben/Prozesse. Darüber hinaus [hängen die meisten Prozesse von anderen nachfolgenden Prozessen ab](system.md#refresh-policies). Sie können den Status eines Prozesses auswählen, um Details zum Fortschritt des gesamten Auftrags anzuzeigen. Nach der Auswahl von **Siehe Details** für eine der Aufgaben des Auftrags finden Sie zusätzliche Informationen: Verarbeitungszeit, das letzte Verarbeitungsdatum sowie alle mit der Aufgabe verbundenen Fehler und Warnungen.


## <a name="manage-existing-activities"></a>Vorhandene Aktivitäten verwalten

Unter **Daten** > **Aktivitäten** können Sie alle Ihre gespeicherten Aktivitäten anzeigen und verwalten. Jede Aktivität wird durch eine Zeile dargestellt, die auch Details zur Quelle, zur Entität und zum Aktivitätstyp enthält.

Die folgenden Aktionen sind verfügbar, wenn Sie eine Aktivität auswählen. 

- **Bearbeiten**: Öffnet das Aktivitätssetup im Überprüfungsschritt. In diesem Schritt können Sie die aktuelle Konfiguration ganz oder teilweise ändern. Wählen Sie nach dem Ändern der Konfiguration **Aktivität speichern** und dann **Ausführen** aus, um die Änderungen zu verarbeiten.

- **Umbenennen**: Öffnet einen Dialog, in dem Sie einen anderen Namen für die ausgewählte Aktivität eingeben können. Wählen Sie **Speichern**, um Ihre Änderungen zu übernehmen.

- **Löschen**: Öffnet ein Dialogfeld, um das Löschen der ausgewählten Aktivität zu bestätigen. Sie können auch mehrere Aktivitäten gleichzeitig löschen, indem Sie die Aktivitäten auswählen und dann das Löschsymbol auswählen. Um den Löschvorgang zu bestätigen, wählen Sie **Löschen**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
