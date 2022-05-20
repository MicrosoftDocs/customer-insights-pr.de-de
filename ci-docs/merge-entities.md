---
title: Vereinheitlichen von Kunden- oder Kontofeldern
description: Führen Sie Entitäten zusammen, um vereinheitlichte Kundenprofile zu erstellen.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: 78e2528d4a3058f879d83952f72ed88a1da065b6
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740856"
---
# <a name="unify-customer-fields"></a>Vereinheitlichen von Kundenfeldern

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Wählen Sie in diesem Schritt des Vereinigungsprozesses Attribute aus und schließen Sie sie aus, um die Entität des einheitlichen Profils zusammenzuführen. Wenn beispielsweise drei Entitäten über E-Mail-Daten verfügten, möchten Sie möglicherweise alle drei separaten E-Mail-Felder beibehalten oder sie in einem einzigen E-Mail-Feld für das einheitliche Profil zusammenführen. Einige Attribute werden vom System automatisch kombiniert. Sie können stabile und eindeutige Kunden-IDs erstellen und verwandte Profile in einem Cluster gruppieren.

:::image type="content" source="media/m3_unify.png" alt-text="Zusammenführungsseite im Datenvereinigungsprozess mit Tabelle mit zusammengeführten Feldern, die das einheitliche Kundenprofil definieren.":::

## <a name="review-and-update-the-customer-fields"></a>Kundenfelder überprüfen und aktualisieren

1. Überprüfen Sie die Liste der Felder, die vereinheitlicht werden, auf der Registerkarte **Kundenfelder** der Tabelle. Nehmen Sie ggf. Änderungen vor.

   1. Für kombinierte Felder können Sie:
      - [Bearbeiten](#edit-a-merged-field)
      - [Umbenennen](#rename-fields)
      - [Trennen](#separate-merged-fields)
      - [Ausschließen](#exclude-fields)
      - [Nach oben oder nach unten](#change-the-order-of-fields)

   1. Für einzelne Felder können Sie:
      - [Felder kombinieren](#combine-fields-manually)
      - [Eine Gruppe von Feldern kombinieren](#combine-a-group-of-fields)
      - [Umbenennen](#rename-fields)
      - [Ausschließen](#exclude-fields)
      - [Nach oben oder nach unten](#change-the-order-of-fields)

1. Optional [können Sie die Kunden-ID-Konfiguration generieren](#configure-customer-id-generation).

1. Optional [können Sie Profile in Haushalte oder Cluster gruppieren](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Nächster Schritt: Überprüfung der Vereinheitlichung](review-unification.md)

### <a name="edit-a-merged-field"></a>Ein zusammengeführtes Feld bearbeiten

1. Wählen Sie ein zusammengeführtes Feld aus, und klicken Sie dann auf **Bearbeiten**. Der Bereich „Felder kombinieren“ wird angezeigt.

1. Geben Sie mit einer der drei Optionen an, wie die Felder kombiniert oder zusammengeführt werden sollen:
    - **Relevanz**: Identifiziert den Gewinnerwert basierend auf dem für die teilnehmenden Felder angegebenen Relevanzrang. Dies ist die standardmäßige Zusammenführungsoption. Wählen Sie **Nach oben/unten** aus, um die Wichtigkeitseinstufungen festzulegen.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Relevanz-Option im Dialogfeld zum Zusammenführen von Feldern.":::

    - **Am neuesten**: Identifiziert den Gewinnerwert basierend auf der größten Aktualität. Erfordert ein Datum oder ein numerisches Feld für jede teilnehmende Entität im Bereich des Zusammenführens von Feldern, um die Aktualität zu definieren.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Aktualitäts-Option im Dialogfeld zum Zusammenführen von Feldern.":::

    - **Am ältesten**: Identifiziert den Gewinnerwert basierend auf der geringsten Aktualität. Erfordert ein Datum oder ein numerisches Feld für jede teilnehmende Entität im Bereich des Zusammenführens von Feldern, um die Aktualität zu definieren.

1. Sie können weitere Felder hinzufügen, um am Zusammenführungsprozess teilzunehmen.

1. Sie können das zusammengeführte Feld auch umbenennen.

1. Wählen Sie **Fertig** aus, um Ihre Änderungen zu übernehmen.

### <a name="rename-fields"></a>Felder umbenennen

Ändern Sie den Anzeigenamen von zusammengeführten oder separaten Feldern. Der Name der ausgegebenen Entitäten kann nicht geändert werden.

1. Markieren Sie das Feld, und wählen Sie **Umbenennen**.

1. Geben Sie den neuen Anzeigenamen ein.

1. Wählen Sie **Fertig** aus.

### <a name="separate-merged-fields"></a>Separate zusammengeführte Felder

Um zusammengeführte Felder zu trennen, suchen Sie das Attribut in der Tabelle. Getrennte Felder werden als einzelne Datenpunkte im einheitlichen Kundenprofil angezeigt.

1. Wählen Sie das zusammengeführte Feld aus, und wählen Sie **Felder trennen**.

1. Bestätigen Sie die Trennung.

### <a name="exclude-fields"></a>Ausschließen von Feldern

Schließen Sie ein zusammengeführtes oder separates Feld aus dem Unified customer profile aus. Wenn das Feld in anderen Prozessen verwendet wird, z. B. in einem Segment, entfernen Sie es aus diesen Prozessen, bevor Sie es aus dem Kundenprofil ausschließen.

1. Wählen Sie ein Feld aus, und klicken Sie dann auf **Ausschließen**.

1. Bestätigen Sie den Ausschluss.

Um die Liste aller ausgeschlossenen Felder anzuzeigen, wählen Sie **Ausgeschlossene Felder**. Bei Bedarf können Sie das ausgeschlossene Feld erneut hinzufügen.

### <a name="change-the-order-of-fields"></a>Die Reihenfolge von Feldern ändern

Einige Entitäten enthalten mehr Details als andere. Wenn eine Entität die neuesten Daten zu einem Feld enthält, können Sie diese beim Zusammenführen von Werten gegenüber anderen Entitäten priorisieren.

1. Wählen Sie das Feld aus.
  
1. Wählen Sie **Nach oben/nach unten**, um die Reihenfolge festzulegen oder per Drag & Drop an die gewünschte Position zu ziehen.

### <a name="combine-fields-manually"></a>Felder manuell kombinieren

Kombinieren Sie separate Felder, um ein zusammengeführtes Attribut zu erstellen.

1. Wählen Sie **Kombinieren** > **Felder**. Der Bereich „Felder kombinieren“ wird angezeigt.

1. Geben Sie die Richtlinie für das Zusammenführen von Gewinnern in der Dropdown-Liste **Felder kombinieren nach** an.

1. Wählen Sie **Feld hinzufügen**, um mehr Felder zu kombinieren.

1. Einen **Namen** und einen **Name des Ausgabefeldes** bereitstellen.

1. Wählen Sie **Fertig** aus, um Ihre Änderungen zu übernehmen.

### <a name="combine-a-group-of-fields"></a>Eine Gruppe von Feldern kombinieren

Behandeln Sie eine Gruppe von Feldern als eine Einheit. Wenn unsere Datensätze beispielsweise die Felder „Adresse1“, „Adresse2“, „Stadt“, „Bundesland“ und „PLZ“ enthalten, möchten wir die Adresse2 eines anderen Datensatzes nicht zusammenführen, weil wir glauben, dass dies unsere Daten vollständiger machen würde.

1. Wählen Sie **Kombinieren** > **Gruppe von Feldern**.

1. Geben Sie die Richtlinie für das Zusammenführen von Gewinnern in der Dropdown-Liste **Gruppen bewerten nach** an.

1. Wählen Sie **Hinzufügen** aus. Wählen Sie dann aus, ob Sie den Feldern weitere Felder oder Gruppen hinzufügen möchten.

1. Stellen Sie einen **Namen** und einen **Ausgabenamen** für jedes kombinierte Feld bereit.

1. Geben Sie einen **Namen** für die Gruppe von Feldern an.

1. Wählen Sie **Fertig** aus, um Ihre Änderungen zu übernehmen.

## <a name="configure-customer-id-generation"></a>Generierung von Kunden-IDs konfigurieren

Definieren Sie, wie Kunden-ID-Werte, die eindeutigen Kundenprofilkennungen, generiert werden. Der Schritt „Felder vereinheitlichen“ im Datenvereinheitlichungsprozess generiert die eindeutige Kundenprofilkennung. Die Kennung ist die *CustomerId* in der Entität *Customer*, die aus dem Datenvereinheitlichungsprozess resultiert.

Die *CustomerId*  basiert auf einem Hash des ersten Werts der Nicht-Null-Gewinner-Primärschlüssel. Diese Schlüssel stammen von den Entitäten, die bei der Datenvereinheitlichung verwendet werden, und werden von der Abgleichreihenfolge beeinflusst.Die generierte Kunden-ID kann sich also ändern, wenn sich ein Primärschlüsselwert in der primären Entität der Abgleichreihenfolge ändert. Der Primärschlüsselwert repräsentiert möglicherweise nicht immer denselben Kunden.

Durch die Konfiguration einer stabilen Kunden-ID können Sie dieses Verhalten vermeiden.

1. Wählen Sie die Registerkarte **Schlüssel** aus.

1. Bewegen Sie den Mauszeiger auf die Zeile **CustomerId**, und wählen Sie **Konfigurieren**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Steuerung zum Anpassen der ID-Generierung.":::

1. Wählen Sie bis zu fünf Felder aus, die eine eindeutige Kunden-ID enthalten und stabiler sind. Datensätze, die nicht Ihrer Konfiguration entsprechen, verwenden stattdessen eine vom System konfigurierte ID.  

1. Wählen Sie **Fertig** aus.

## <a name="group-profiles-into-households-or-clusters"></a>Profile in Haushalte oder Cluster gruppieren

Sie können Regeln definieren, um verwandte Profile in einem Cluster zu gruppieren. Derzeit sind zwei Arten von Cluster verfügbar – Haushalts- und benutzerdefinierte Cluster. Das System wählt automatisch einen Haushalt mit vordefinierten Regeln aus, wenn die *Kunde* Entität die semantischen Felder *Person.Nachname* und *Standort-Adresse* enthält. Sie können auch einen Cluster mit Ihren eigenen Regeln und Bedingungen erstellen, ähnlich wie bei [Abstimmungsregeln](match-entities.md#define-rules-for-match-pairs).

1. Wählen Sie **Erweitert** > **Cluster erstellen**.

   :::image type="content" source="media/create-cluster.png" alt-text="Steuerelement zum Erstellen eines neuen Clusters.":::

1. Wählen Sie zwischen einem **Haushalt** oder einem **Benutzerdefiniert** Cluster. Wenn die semantischen Felder *Person.Nachname* und *Standort-Adresse* in der *Kunde* Entität vorhanden sind, wird Haushalt automatisch ausgewählt.

1. Geben Sie einen Namen für den Cluster ein und wählen Sie **Fertig**.

1. Wählen Sie die Registerkarte **Cluster**, um den von Ihnen erstellten Cluster zu finden.

1. Geben Sie die Regeln und Bedingungen an, um Ihren Cluster zu definieren.

1. Wählen Sie **Fertig** aus. Der Cluster wird erstellt, wenn der Vereinheitlichungsvorgang abgeschlossen ist. Die Cluster-IDs werden als neue Felder zu der Entität *Customer* hinzugefügt.

> [!div class="nextstepaction"]
> [Nächster Schritt: Überprüfung der Vereinheitlichung](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
