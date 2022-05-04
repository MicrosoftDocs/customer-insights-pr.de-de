---
title: Entitäten bei der Datenvereinheitlichung zusammenführen
description: Führen Sie Entitäten zusammen, um vereinheitlichte Kundenprofile zu erstellen.
ms.date: 01/28/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 978a7c9bc440398fa39e9fa1d366d74e5c7aaea0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647380"
---
# <a name="merge-entities"></a>Entitäten zusammenführen

Die Zusammenführungsphase ist die letzte Phase des Datenvereinheitlichungsprozesses. Sein Zweck ist es, widersprüchliche Daten abzugleichen. Beispiele für widersprüchliche Daten könnten ein Kundenname sein, der in zwei Ihrer Datensätze gefunden wurde, der jedoch in jedem etwas anders angezeigt wird („Grant Marshall“ gegenüber "Grant Marshal"), oder eine Telefonnummer, die sich im Format (617-803-091X im Vergleich zu 617803091X unterscheidet). Die Zusammenführung dieser widersprüchlichen Datenpunkte erfolgt auf einer attributweisen Basis.

:::image type="content" source="media/merge-fields-page.png" alt-text="Zusammenführungsseite im Datenvereinigungsprozess mit Tabelle mit zusammengeführten Feldern, die das einheitliche Kundenprofil definieren.":::

Nach Abschluss der [Match-Phase](match-entities.md) starten Sie die Zusammenführungsphase durch Auswahl der Kachel **zusammenführen** auf der Seite **Vereinheitlichen**.

## <a name="review-system-recommendations"></a>Systemempfehlungen überprüfen

Unter **Daten** > **Vereinheitlichen** > **Zusammenführen** wählen Sie Attribute aus und schließen sie aus, um sie in Ihrer einheitlichen Kundenprofilentität zusammenzuführen. Das einheitliche Kundenprofil ist das Ergebnis des Datenvereinigungsprozesses. Einige Attribute werden vom System automatisch zusammengeführt.

Um die Attribute anzuzeigen, die in einem Ihrer automatisch zusammengeführten Attribute enthalten sind, wählen Sie dieses zusammengeführte Attribut in der Registerkarte **Kundenfelder** der Tabelle aus. Die beiden Attribute, aus denen das zusammengeführte Attribut besteht, werden in zwei neuen Zeilen unterhalb des zusammengeführten Attributs angezeigt.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Trennen, umbenennen, ausschließen und bearbeiten Sie zusammengeführte Felder

Sie können ändern, wie das System zusammengeführte Attribute verarbeitet, um das einheitliche Kundenprofil zu generieren. Wählen Sie **mehr anzeigen** und wählen Sie, was Sie ändern möchten.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Optionen im Dropdown-Menü mehr anzeigen, um zusammengeführte Attribute zu verwalten.":::

Weitere Informationen finden Sie in den folgenden Abschnitten.

## <a name="separate-merged-fields"></a>Separate zusammengeführte Felder

Um zusammengeführte Felder zu trennen, suchen Sie das Attribut in der Tabelle. Getrennte Felder werden als einzelne Datenpunkte im einheitlichen Kundenprofil angezeigt. 

1. Wählen Sie das zusammengeführte Feld aus.
  
1. Wählen Sie **mehr anzeigen** und wählen Sie **separate Felder** aus.
 
1. Bestätigen Sie die Trennung.

1. Klicken Sie auf **Speichern** und **Ausführen**, um die Änderungen zu verarbeiten.

## <a name="rename-merged-fields"></a>Zusammengeführte Felder umbenennen

Ändern Sie den Anzeigename der zusammengeführten Attribute. Der Name der ausgegebenen Entitäten kann nicht geändert werden.

1. Wählen Sie das zusammengeführte Feld aus.
  
1. Wählen Sie **mehr anzeigen** und wählen Sie **umbenennen** aus.

1. Bestätigen Sie den geänderten Anzeigenamen. 

1. Klicken Sie auf **Speichern** und **Ausführen**, um die Änderungen zu verarbeiten.

## <a name="exclude-merged-fields"></a>Zusammengeführte Felder ausschließen

Schließen Sie ein Attribut aus dem einheitlichen Kundenprofil aus. Wenn das Feld in anderen Prozessen verwendet wird, z. B. in einem Segment, entfernen Sie es aus diesen Prozessen, bevor Sie es aus dem Kundenprofil ausschließen. 

1. Wählen Sie ein zusammengeführtes Feld aus.
  
1. Wählen Sie **mehr anzeigen** und wählen Sie **ausschließen** aus.

1. Bestätigen Sie den Ausschluss.

1. Klicken Sie auf **Speichern** und **Ausführen**, um die Änderungen zu verarbeiten. 

Auf der Seite **Zusammenführen** wählen Sie **Ausgeschlossene Felder**, um die Liste aller ausgeschlossenen Felder anzuzeigen. In diesem Bereich können Sie ausgeschlossene Felder wieder hinzufügen.

## <a name="edit-a-merged-field"></a>Ein zusammengeführtes Feld bearbeiten

1.  Wählen Sie ein zusammengeführtes Feld aus.

1.  Wählen Sie **mehr anzeigen** und wählen Sie **bearbeiten** aus.

1.  Geben Sie mit einer der drei Optionen an, wie die Felder kombiniert oder zusammengeführt werden sollen:
    - **Relevanz**: Identifiziert den Gewinnerwert basierend auf dem für die teilnehmenden Felder angegebenen Relevanzrang. Dies ist die standardmäßige Zusammenführungsoption. Wählen Sie **Nach oben/unten** aus, um die Wichtigkeitseinstufungen festzulegen.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Relevanz-Option im Dialogfeld zum Zusammenführen von Feldern."::: 
    - **Am neuesten**: Identifiziert den Gewinnerwert basierend auf der größten Aktualität. Erfordert ein Datum oder ein numerisches Feld für jede teilnehmende Entität im Bereich des Zusammenführens von Feldern, um die Aktualität zu definieren.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Aktualitäts-Option im Dialogfeld zum Zusammenführen von Feldern.":::
    - **Am ältesten**: Identifiziert den Gewinnerwert basierend auf der geringsten Aktualität. Erfordert ein Datum oder ein numerisches Feld für jede teilnehmende Entität im Bereich des Zusammenführens von Feldern, um die Aktualität zu definieren.

1.  Sie können weitere Felder hinzufügen, um am Zusammenführungsprozess teilzunehmen.

1.  Sie können das zusammengeführte Feld auch umbenennen.

1. Wählen Sie **Fertig** aus, um Ihre Änderungen zu übernehmen.

1. Klicken Sie auf **Speichern** und **Ausführen**, um die Änderungen zu verarbeiten. 

## <a name="combine-fields-manually"></a>Felder manuell kombinieren

Zusammengeführtes Attribut manuell definieren.

1. Auf der **Zusammenführen**-Seite wählen Sie **Kombinieren**.

1. Wählen Sie die Option **Felder**.

1. Geben Sie die Richtlinie für das Zusammenführen von Gewinnern in der Dropdown-Liste **Felder kombinieren nach** an.

1. Ein Feld zum Hinzufügen auswählen. Wählen Sie **Felder hinzufügen** aus, um mehr Felder zu kombinieren.

1. Einen **Namen** und einen **Name des Ausgabefeldes** bereitstellen.

1. Wählen Sie **Fertig** aus, um Ihre Änderungen zu übernehmen.

1. Klicken Sie auf **Speichern** und **Ausführen**, um die Änderungen zu verarbeiten. 

## <a name="combine-a-group-of-fields"></a>Eine Gruppe von Feldern kombinieren

Behandeln Sie eine Gruppe von Feldern als eine Einheit. Zum Beispiel, wenn unsere Datensätze die Felder Adresse1, Adresse2, Stadt, Bundesland und Postleitzahl enthalten. Wir sollten wahrscheinlich nicht die Adresse2 eines anderen Datensatzes zusammenführen, weil wir glauben, dass unsere Daten dadurch vollständiger würden

1. Auf der **Zusammenführen**-Seite wählen Sie **Kombinieren**.

1. Wählen Sie die Option **Guppe von Feldern**.

1. Geben Sie die Richtlinie für das Zusammenführen von Gewinnern in der Dropdown-Liste **Gruppen bewerten nach** an.

1. Wählen Sie **Hinzufügen** aus. Wählen Sie dann aus, ob Sie den Feldern weitere Felder oder zusätzliche Gruppen hinzufügen möchten.

1. Stellen Sie einen **Namen** und einen **Ausgabenamen** für jedes kombinierte Feld bereit.

1. Geben Sie einen **Namen** für die Gruppe von Feldern an. 

1. Wählen Sie **Fertig** aus, um Ihre Änderungen zu übernehmen.

1. Klicken Sie auf **Speichern** und **Ausführen**, um die Änderungen zu verarbeiten.

## <a name="change-the-order-of-fields"></a>Die Reihenfolge von Feldern ändern

Einige Entitäten enthalten mehr Details als andere. Wenn eine Entität die neuesten Daten zu einem Feld enthält, können Sie diese beim Zusammenführen von Werten gegenüber anderen Entitäten priorisieren.

1. Wählen Sie das zusammengeführte Feld aus.
  
1. Wählen Sie **mehr anzeigen** und wählen Sie **bearbeiten** aus.

1. In dem Bereich **Felder kombinieren** wählen Sie **nach oben/unten bewegen**, um die Reihenfolge festzulegen oder ziehen Sie sie an die gewünschte Position.

1. Die Änderung bestätigen.

1. Klicken Sie auf **Speichern** und **Ausführen**, um die Änderungen zu verarbeiten.

## <a name="configure-customer-id-generation"></a>Generierung von Kunden-IDs konfigurieren 

Nachdem Sie das Zusammenführen von Feldern konfiguriert haben, können Sie definieren, wie CustomerId-Werte, die eindeutigen Kundenprofil-IDs, generiert werden. Der Zusammenführungsschritt im Datenvereinheitlichungsprozess generiert die eindeutige Kundenprofilkennung. Die Kennung ist die CustomerId in der Entität *Kunde*, die aus dem Datenvereinheitlichungsprozess resultiert. 

Die CustomerId in der Kundenentität basiert auf einem Hash des ersten Werts der Gewinner-Primärschlüssel ungleich null. Diese Schlüssel stammen von den Entitäten, die in der Abgleichs- und Zusammenführungsphase verwendet werden und von der Zuordnungsreihenfolge beeinflusst werden.Die generierte CustomerID kann sich also ändern, wenn sich ein Primärschlüsselwert in der primären Entität der Zuordnungsreihenfolge ändert. Daher repräsentiert der Primärschlüsselwert möglicherweise nicht immer denselben Kunden.

Durch die Konfiguration einer stabilen Kunden-ID können Sie dieses Verhalten vermeiden.

**Eindeutige Kunden-ID konfigurieren**

1. Gehen Sie zu **Vereinheitlichen** > **Zusammenführen**.

1. Wählen Sie die Registerkarte **Schlüssel** aus. 

1. Bewegen Sie den Mauszeiger über die Zeile **CustomerId**, und wählen Sie die Option **Konfigurieren**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Steuerung zum Anpassen der ID-Generierung.":::

1. Wählen Sie bis zu fünf Felder aus, die eine eindeutige Kunden-ID enthalten und stabiler sind. Datensätze, die nicht Ihrer Konfiguration entsprechen, verwenden stattdessen eine vom System konfigurierte ID.  

1. Wählen Sie **Fertig**, und führen Sie den Zusammenführungsprozess aus, um Ihre Änderungen zu übernehmen.

## <a name="group-profiles-into-households-or-clusters"></a>Profile in Haushalte oder Cluster gruppieren

Als Teil des Konfigurationsprozesses der Kundenprofilgenerierung können Sie Regeln definieren, um verwandte Profile in einem Cluster zu gruppieren. Derzeit sind zwei Arten von Cluster verfügbar – Haushalts- und benutzerdefinierte Cluster. Das System wählt automatisch einen Haushalt mit vordefinierten Regeln aus, wenn die *Kunde* Entität die semantischen Felder *Person.Nachname* und *Standort-Adresse* enthält. Sie können auch einen Cluster mit Ihren eigenen Regeln und Bedingungen erstellen, ähnlich wie bei [Abstimmungsregeln](match-entities.md#define-rules-for-match-pairs).

**Definieren Sie einen Haushalt oder ein Cluster**

1. Gehen Sie zu **Vereinheitlichen** > **Zusammenführen**.

1. Auf der **Zusammenführen** Registerkarte, wählen Sie **Erweitert** > **Cluster erstellen**.

   :::image type="content" source="media/create-cluster.png" alt-text="Steuerelement zum Erstellen eines neuen Clusters.":::

1. Wählen Sie zwischen einem **Haushalt** oder einem **Benutzerdefiniert** Cluster. Wenn die semantischen Felder *Person.Nachname* und *Standort-Adresse* in der *Kunde* Entität vorhanden sind, wird Haushalt automatisch ausgewählt.

1. Geben Sie einen Namen für den Cluster ein und wählen Sie **Fertig**.

1. Wählen Sie die Registerkarte **Cluster**, um den von Ihnen erstellten Cluster zu finden.

1. Geben Sie die Regeln und Bedingungen an, um Ihren Cluster zu definieren.

1. Wählen Sie **Ausführen**, um den Zusammenführungsprozess auszuführen und den Cluster zu erstellen.

Nach dem Ausführen des Zusammenführungsprozesses werden die Cluster-IDs als neue Felder zu der Entität *Kunde* hinzugefügt.

## <a name="run-your-merge"></a>Führen Sie Ihre Zusammenführung durch

Unabhängig davon, ob Sie Attribute manuell zusammenführen oder vom System zusammenführen lassen, können Sie Ihre Zusammenführung immer durchführen. Wählen Sie **Ausführen** auf der Seite **Zusammenführen**, um den Prozess zu starten.

> [!div class="mx-imgBorder"]
> ![Datenzusammenführung speichern und ausführen.](media/configure-data-merge-save-run.png "Datenzusammenführung Speichern und Ausführen")

Wählen Sie **nur Zusammenführen ausführen**, wenn Sie nur die Ausgabe in der einheitlichen Kundenentität anzeigen möchten. Nachgelagerte Prozesse werden als [im Aktualisierungsplan definiert](system.md#schedule-tab) aktualisiert.

Wählen Sie **Merge- und Downstream-Prozesse ausführen**, um das System mit Ihren Änderungen zu aktualisieren. Alle Prozesse, einschließlich Anreicherung, Segmente und Maßnahmen, werden automatisch erneut ausgeführt. Nachdem alle nachgelagerten Prozesse abgeschlossen wurden, spiegeln die Kundenprofile alle von Ihnen vorgenommenen Änderungen wider.

Um weitere Änderungen vorzunehmen und den Schritt erneut auszuführen, können Sie eine laufende Zusammenführung abbrechen. Wählen Sie den Text **Wird aktualisiert ...** und **Auftrag abbrechen**  im angezeigten Seitenbereich aus.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

:::image type="content" source="media/process-detail-path.png" alt-text="Drilldownpfad, um über den Link zum Aufgabenstatus zu Prozessdetails zu gelangen.":::

## <a name="next-step"></a>Nächster Schritt

Konfigurieren von [Aktivitäten](activities.md), [Anreicherung](enrichment-hub.md), oder [Beziehungen](relationships.md), um mehr Einblicke über Ihre Kunden zu gewinnen.

Wenn Sie bereits Aktivitäten, Anreicherungen oder Segmente konfiguriert haben, werden diese automatisch verarbeitet, um die neuesten Kundendaten zu verwenden.

[!INCLUDE [footer-include](includes/footer-banner.md)]
