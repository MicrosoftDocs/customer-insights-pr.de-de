---
title: Kundenaktivitäten
description: Definieren Sie Kundenaktivitäten, und zeigen Sie diese in einer Zeitskala auf Kundenprofilen an.
ms.date: 07/22/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsight
ms.openlocfilehash: cc21b0eeb368156437e60d851c2d144f3974c066
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188138"
---
# <a name="customer-activities"></a>Kundenaktivitäten

Kundenaktivitäten sind Aktionen oder Ereignisse, die von Kunden durchgeführt werden. Zum Beispiel Transaktionen, Support-Anrufdauer, Website-Bewertungen, Käufe oder Rückgaben. Diese Aktivitäten sind in einer oder mehreren Datenquellen enthalten. Konsolidieren Sie mit Customers Insights Ihre Kundenaktivitäten aus diesen [Datenquellen](data-sources.md) und verknüpfen Sie sie mit Kundenprofilen. Diese Aktivitäten werden chronologisch in einer Zeitleiste auf dem Kundenprofil angezeigt. Schließen Sie die Zeitskala in Dynamics 365-Apps mit der Lösung [Kundenkarten-Add-In](customer-card-add-in.md).

## <a name="define-an-activity"></a>Definieren Sie eine Aktivität

Eine Entität muss mindestens ein Attribut vom Typ **Datum** haben, um in eine Kundenzeitachse aufgenommen zu werden. Die Kontrolle **Aktivität hinzufügen** ist deaktiviert, wenn keine solche Entität gefunden wird.

1. Gehen Sie zu **Daten** > **Aktivitäten**.

1. Wählen Sie **Aktivität hinzufügen** aus, um das geführte Erlebnis zu starten.

1. Geben Sie im Schritt **Aktivitätsdaten** die folgenden Informationen ein:

   - **Aktivitätsname**: Name für Ihre Aktivität.
   - **Aktivitätsentität**: Entität, die Transaktions- oder Aktivitätsdaten enthält.
   - **Primärschlüssel** – Das Feld, mit dem ein Datensatz eindeutig identifiziert wird. Sie sollte keine doppelten Werte, leere Werte oder fehlende Werte enthalten.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Richten Sie die Aktivitätsdaten mit Name, Entität und Primärschlüssel ein.":::

1. Wählen Sie **Weiter** aus.

1. Wählen Sie im Schritt **Beziehung** die Option **Beziehung hinzufügen** aus, um Ihre Aktivitätsdaten mit dem entsprechenden Kundendatensätzen zu verwenden. Dieser Schritt visualisiert die Verbindung zwischen Entitäten.  

   - **Fremdschlüssel aus Entität**: Feld in Ihrer Aktivitätsentität, das zum Herstellen einer Beziehung mit einer anderen Entität verwendet werden soll.
   - **Zu Entitätsname**: Entsprechende Quellkundenentität, mit der die Aktivitätsentität zur Beziehung hinzugefügt wird. Sie können sich nur auf Quellkundenentitäten beziehen, die im Datenvereinigungsprozess verwendet werden.
   - **Beziehungsname**: Name, der die Beziehung zwischen Entitäten identifiziert. Wenn bereits eine Beziehung zwischen dieser Aktivitätsentität und der ausgewählten Quellkundenentität besteht, ist der Beziehungsname schreibgeschützt.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definieren der Entitätsbeziehung.":::

   > [!TIP]
   > In B2B-Umgebungen können Sie zwischen Kontoentitäten und anderen Entitäten wählen. Wenn Sie eine Kontoentität auswählen, wird der Beziehungspfad automatisch festgelegt. Für andere Entitäten müssen Sie den Beziehungspfad über eine oder mehrere Zwischenentitäten definieren, bis Sie eine Kontoentität erreichen.

1. Wählen Sie **Anwenden** aus, um die Beziehung zu erstellen.

1. Wählen Sie **Weiter** aus.

1. Im Schritt **Vereinheitlichung der Aktivitäten** wählen Sie das Aktivitätsereignis und die Startzeit Ihrer Aktivität.
   - **Erforderliche Felder**
      - **Ereignisaktivität**: Feld, das das Ereignis für diese Aktivität ist.
      - **Zeitstempel**: Feld, das die Startzeit der Aktivität darstellt.

   - **Optionale Felder**
      - **Zusätzliches Detail**: Feld mit relevanten Informationen für diese Aktivität.
      - **Symbol**: Symbol, das diesen Aktivitätstyp am besten darstellt.
      - **Webadresse**: Feld mit einer URL mit Informationen zu dieser Aktivität. Zum Beispiel das Transaktionssystem, aus dem diese Aktivität stammt. Bei dieser URL kann es sich um ein beliebiges Feld aus der Datenquelle handeln, oder es kann mithilfe einer Power Query-Transformation als neues Feld erstellt werden. Die URL-Daten werden in der *Einheitliche Aktivität*-Entität gespeichert, die mit [APIs](apis.md) im Downstream verbraucht werden kann.

   - **In der Zeitachse anzeigen**
      - Wählen Sie aus, ob diese Aktivität in der Zeitskalaansicht Ihren Kundenprofilen angezeigt werden soll. Wählen Sie **Ja** aus, um die Aktivität in der Zeitskala anzuzeigen, oder **Nein**, um sie zu verbergen.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Geben Sie die Kundenaktivitätsdaten in einer „Einheitliche Aktivität“-Entität an.":::

1. Wählen Sie **Weiter** aus, um einen Aktivitätstypen auszuwählen, oder klicken Sie auf **Abschließen und überprüfen**, um die Aktivität jetzt mit dem Aktivitätstyp **Andere** zu speichern.

1. Im Schritt **Aktivitätstyp** wählen Sie Schritt für Schritt den Aktivitätstyp und optional aus, ob Sie einige der Aktivitätstypen für die Verwendung in anderen Bereichen von Customer Insights semantisch zuordnen möchten. Momentan unterstützen Sie Aktivitätstypen *Feedback*, *Treue*, *SalesOrder*, *SalesOrderLine* und *Abonnement* die Semantik, nachdem der Zuordnung der Felder zugestimmt wurde. Wenn ein Aktivitätstyp für die neue Aktivität nicht relevant ist, können Sie *Andere* oder *Neu erstellen* für einen benutzerdefinierten Aktivitätstyp auswählen.

1. Wählen Sie **Weiter** aus.

1. Im Schritt **Überprüfen** Schritt überprüfen Sie Ihre Auswahl. Kehren Sie zu einem der vorherigen Schritte zurück und aktualisieren Sie die Informationen bei Bedarf.

1. Wählen Sie **Aktivität speichern** aus, um Ihre Änderungen zu übernehmen, und wählen Sie **Fertig** aus, um zu **Daten** > **Aktivitäten** zurückzukehren. Die erstellte Aktivität wird angezeigt.

1. Nachdem Sie alle Ihre Aktivitäten erstellt haben, wählen Sie **Ausführen** aus, um sie zu verarbeiten.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Vorhandene Aktivitäten verwalten

Gehen Sie zu **Daten** > **Aktivitäten**, um Ihre gespeicherten Aktivitäten, ihre Quellentität, den Aktivitätstyp und ob sie in der Kundenchronik enthalten sind, anzuzeigen. Sie können die Liste der Aktivitäten nach einer beliebigen Spalte sortieren oder das Suchfeld verwenden, um die Aktivität zu finden, die Sie verwalten möchten.

Wählen Sie eine Aktivität aus, um verfügbare Aktionen anzuzeigen.

- **Bearbeiten** Sie die Aktivität, um seine Konfiguration zu ändern. Die Konfiguration öffnet sich auf dem Überprüfungsschritt. Wählen Sie nach dem Ändern der Konfiguration **Aktivität speichern** und dann **Ausführen** aus, um die Änderungen zu verarbeiten.
- **Umbenennen** der Aktivität. Wählen Sie **Speichern**, um Ihre Änderungen zu übernehmen.
- **Löschen** der Aktivität. Wählen Sie die Aktivitäten aus, und klicken Sie dann auf **Löschen**, um mehr als eine Aktivität zeitgleich zu löschen. Bestätigen Sie den Löschvorgang.

## <a name="view-activity-timelines-on-customer-profiles"></a>Aktivitätszeitachsen in Kundenprofilen anzeigen

1. Wenn Sie **In Aktivitätszeitleiste anzeigen** in der Aktivitätskonfiguration ausgewählt haben für **Kunden** und ein Kundenprofil und die Kundenaktivitäten im Bereich **Aktivitätszeitleiste** anzuzeigen.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Zeigen Sie konfigurierte Aktivitäten in Kundenprofilen an.":::

1. Zum Filtern von Aktivitäten in der Aktivitätszeitleiste:

   - Wählen Sie eines oder mehrere der Aktivitätssymbole aus, um Ihre Ergebnisse so zu verfeinern, dass nur die ausgewählten Typen berücksichtigt werden.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtern Sie Aktivitäten nach Typ mithilfe der Symbole.":::

   - Wählen Sie **Filter** aus, um ein Filterfenster zu öffnen, um Ihre Zeitachsenfilter zu konfigurieren. Nach *ActivityType* und/oder *Date* filtern. Wählen Sie **Übernehmen** aus.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Verwenden Sie das Filterbedienfeld, um Filterbedingungen zu konfigurieren.":::

1. Um Filter zu entfernen, wählen Sie aus **Filter löschen** oder **Filter** und deaktivieren Sie das Kontrollkästchen Filter.

> [!NOTE]
> Aktivitätsfilter werden entfernt, wenn Sie ein Kundenprofil verlassen. Sie müssen sie jedes Mal anwenden, wenn Sie ein Kundenprofil öffnen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
