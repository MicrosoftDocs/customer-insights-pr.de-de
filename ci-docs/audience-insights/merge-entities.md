---
title: Entitäten bei der Datenvereinheitlichung zusammenführen
description: Führen Sie Entitäten zusammen, um vereinheitlichte Kundenprofile zu erstellen.
ms.date: 09/14/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b038cd3f5b433fedf918d34bbfaf2261e11c5c17
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494318"
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

1.  Sie können zusätzliche Felder hinzufügen, um am Zusammenführungsprozess teilzunehmen.

1.  Sie können das zusammengeführte Feld auch umbenennen.

1. Wählen Sie **Fertig** aus, um Ihre Änderungen zu übernehmen.

1. Klicken Sie auf **Speichern** und **Ausführen**, um die Änderungen zu verarbeiten. 

## <a name="manually-combine-fields"></a>Felder manuell kombinieren

Zusammengeführtes Attribut manuell definieren. 

1. Auf der Seite **Zusammenführen** wählen Sie **Felder kombinieren**.

1. Geben Sie die Richtlinie für das Zusammenführen von Gewinnern in der Dropdown-Liste **Felder kombinieren nach** an.

1. Ein Feld zum Hinzufügen auswählen. Wählen Sie **Felder hinzufügen** aus, um mehr Felder zu kombinieren.

1. Einen **Namen** und einen **Name des Ausgabefeldes** bereitstellen.

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

Die CustomerId in der Kundenentität basiert auf einem Hash des ersten Werts der Gewinner-Primärschlüssel ungleich null. Diese Schlüssel stammen von den Entitäten, die in der Abgleichs- und Zusammenführungsphase verwendet werden und von der Zuordnungsreihenfolge beeinflusst werden.Die generierte CustomerID kann sich also ändern, wenn sich ein Primärschlüsselwert in der primären Entität der Zuordnungsreihenfolge ändert. Folglich repräsentiert der Primärschlüsselwert möglicherweise nicht immer denselben Kunden.

Durch die Konfiguration einer stabilen Kunden-ID können Sie dieses Verhalten vermeiden.

**Eindeutige Kunden-ID konfigurieren**

1. Gehen Sie zu **Vereinheitlichen** > **Zusammenführen**.

1. Wählen Sie auf der Seite **Zusammenführen** die Registerkarte **Schüssel** aus. 

1. Bewegen Sie den Mauszeiger über die Zeile **CustomerId**, und wählen Sie die Option **Konfigurieren**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Steuerung zum Anpassen der ID-Generierung.":::

1. Wählen Sie bis zu fünf Felder aus, die eine eindeutige Kunden-ID enthalten und stabiler sind. Datensätze, die nicht Ihrer Konfiguration entsprechen, verwenden stattdessen eine vom System konfigurierte ID.  

1. Wählen Sie **Fertig**, und führen Sie den Zusammenführungsprozess aus, um Ihre Änderungen zu übernehmen.

## <a name="run-your-merge"></a>Führen Sie Ihre Zusammenführung durch

Unabhängig davon, ob Sie Attribute manuell zusammenführen oder vom System zusammenführen lassen, können Sie Ihre Zusammenführung immer durchführen. Wählen Sie **Ausführen** auf der Seite **Zusammenführen**, um den Prozess zu starten.

> [!div class="mx-imgBorder"]
> ![Datenzusammenführung speichern und ausführen.](media/configure-data-merge-save-run.png "Datenzusammenführung Speichern und Ausführen")

Wählen Sie **nur Zusammenführen ausführen**, wenn Sie nur die Ausgabe in der einheitlichen Kundenentität anzeigen möchten. Nachgelagerte Prozesse werden als [im Aktualisierungsplan definiert](system.md#schedule-tab) aktualisiert.

Wählen Sie **Merge- und Downstream-Prozesse ausführen**, um das System mit Ihren Änderungen zu aktualisieren. Alle Prozesse, einschließlich Anreicherung, Segmente und Maßnahmen, werden automatisch erneut ausgeführt. Nachdem alle nachgelagerten Prozesse abgeschlossen wurden, spiegeln die Kundenprofile alle von Ihnen vorgenommenen Änderungen wider.

Um weitere Änderungen vorzunehmen und den Schritt erneut auszuführen, können Sie eine laufende Zusammenführung abbrechen. Wählen Sie den Text **Wird aktualisiert ...** und **Auftrag abbrechen**  im angezeigten Seitenbereich aus.

> [!TIP]
> Wählen Sie nach dem Ausführen des Zusammenführungsprozesses den Prozessstatus aus, um das Feld **Aufgabendetails** zu öffnen. Dort erhalten Sie einen Überblick über die Bearbeitungszeit, das letzte Bearbeitungsdatum und alle mit der Aufgabe verbundenen Fehler und Warnungen. Wählen Sie **Detail anzeigen** aus, um zu sehen, welche Entitäten am Abgleichsprozess teilgenommen haben, ob die Konfliktlösung erfolgreich war und ob die Updates erfolgreich veröffentlicht wurden.  
> Es gibt [sechs Arten von Status](system.md#status-types) für Aufgaben/Prozesse. Darüber hinaus [hängen die meisten Prozesse von anderen nachfolgenden Prozessen ab](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Drilldownpfad, um über den Link zum Aufgabenstatus zu Prozessdetails zu gelangen.":::

## <a name="next-step"></a>Nächster Schritt

Konfigurieren von [Aktivitäten](activities.md), [Anreicherung](enrichment-hub.md), oder [Beziehungen](relationships.md), um mehr Einblicke über Ihre Kunden zu gewinnen.

Wenn Sie bereits Aktivitäten, Anreicherungen oder Segmente konfiguriert haben, werden diese automatisch verarbeitet, um die neuesten Kundendaten zu verwenden.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
