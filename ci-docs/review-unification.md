---
title: Überprüfen der Datenvereinheitlichung
description: Überprüfen Sie die Schritte zur Datenvereinheitlichung, erstellen Sie einheitliche Kundenprofile und überprüfen Sie die Ergebnisse
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 4c709dfb55bf079dd2fe99e41adb4c77c2bece4b
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741656"
---
# <a name="review-data-unification"></a>Überprüfen der Datenvereinheitlichung

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Dieser letzte Schritt im Vereinheitlichungsprozess zeigt eine Zusammenfassung der Schritte im Prozess und bietet die Möglichkeit, Änderungen vorzunehmen, bevor Sie das vereinheitlichte Profil erstellen.

:::image type="content" source="media/m3_review.png" alt-text="Screenshot von „Kundenprofile überprüfen und erstellen“.":::

## <a name="review-the-data-unification-steps"></a>Überprüfen der Schritte zur Datenvereinheitlichung

1. Wählen Sie **Bearbeiten** bei allen Datenvereinheitlichungsschritten, um sie zu überprüfen und Änderungen vorzunehmen.

1. Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **Kundenprofile erstellen**. Die Seite **Vereinheitlichen** wird angezeigt, während das Unified customer profile erstellt wird. Es dauert einige Zeit, bis der Vereinigungsalgorithmus abgeschlossen ist, und Sie können die Konfiguration nicht ändern, bis er abgeschlossen ist.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

Wenn der Vereinheitlichungsprozess abgeschlossen ist, wird die Entität Unified customer profile namens *Kunde* aufgerufen und auf der Seite **Entitäten** im Abschnitt **Profile** aufgeführt. Die erste erfolgreiche Ausführung der Vereinheitlichung erstellt die Entität *Kunde*. Alle nachfolgenden Läufe erweitern diese Entität.

## <a name="review-the-results-of-data-unification"></a>Überprüfen der Ergebnisse der Datenvereinheitlichung

Nach der Vereinigung zeigt die Seite **Daten** > **Vereinheitlichen** die Anzahl der einheitlichen Kundenprofile. Die Ergebnisse jedes Schritts im Vereinigungsprozess werden auf jeder Kachel angezeigt. Zum Beispiel enthält **Quellfelder** die Anzahl der zugeordneten Attribute (Felder) und **Doppelte Datensätze** zeigt die Anzahl der gefundenen doppelten Datensätze.

:::image type="content" source="media/m3_unified.png" alt-text="Screenshot der Seite zur Vereinheitlichung von Daten, nachdem die Daten vereinheitlicht wurden.":::

> [!TIP]
> Die Kachel **Abgleich-Bedingungen** wird nur angezeigt, wenn mehrere Entitäten ausgewählt wurden.

Wir empfehlen Ihnen, die Ergebnisse zu überprüfen, insbesondere die Qualität Ihrer [Abgleich-Bedingungen](data-unification-update.md#manage-match-rules), und sie ggf. zu verfeinern.

Wenn erforderlich, [nehmen Sie Änderungen an den Vereinigungseinstellungen vor](data-unification-update.md) und führen Sie das einheitliche Profil erneut aus.

## <a name="next-step"></a>Nächster Schritt

Konfigurieren Sie [Aktivitäten](activities.md), [Anreicherung](enrichment-hub.md), [Beziehungen](relationships.md) oder [Kennzahlen](measures.md), um mehr Erkenntnisse zu Ihren Kunden zu gewinnen.

[!INCLUDE[footer-include](includes/footer-banner.md)]