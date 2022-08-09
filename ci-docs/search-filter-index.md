---
title: Verwalten Sie den Such- und Filterindex für Kundenprofile
description: Schnelles Auffinden von Informationen über einheitliche Kundenprofile und Filter für bestimmte Attribute.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187908"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Verwalten Sie den Such- und Filterindex für Kundenprofile

Das Ergebnis der Vereinheitlichung Ihrer Kundendaten ist eine *Kunde* Entität, die eine einheitliche Sicht auf Ihren gesamten Kundenstamm bietet. Um schnell [Informationen über einen bestimmten Kunden oder eine bestimmte Kundengruppe zu finden](customer-profiles.md) für Benutzer, können Adminstratoren die Funktionen **Suchen** und **Filter** auf der Seite **Kunden** konfigurieren.

   :::image type="content" source="media/search-filter.png" alt-text="Suchfilter":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Definieren Sie durchsuchbare Attribute und indizierte Felder

Wenn Sie als Administrator zum ersten Mal durchsuchbare Attribute definieren, müssen Sie zunächst indizierte Felder definieren. Wir empfehlen Ihnen, alle Attribute auszuwählen, nach denen Benutzer Kunden auf der Seite **Kunden** suchen und filtern können. Geben Sie nur Attribute an, die in der Entität *Kunde* vorhanden sind, die Sie während des Datenvereinheitlichungsprozesses angelegt haben.

1. Wechseln Sie zu **Kunden** und wählen Sie **Such- & Filterindex**.

1. Wählen Sie **+Hinzufügen** aus.

1. Wählen Sie die Attribute in der Liste aus, die Sie als indizierte Felder hinzufügen möchten und klicken Sie auf **Anwenden**.

1. Wählen Sie **Hinzufügen** aus, um weitere Attribute hinzuzufügen. Um ein Attribut zu entfernen, wählen Sie das Attribut im Raster aus und wählen Sie **Entfernen**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Seite Index suchen & filtern":::

1. Wählen Sie **Ausführen**, sobald Sie bereit sind, Ihre Einstellungen für Suche und Filter anzuwenden. Nachdem die Änderungen verarbeitet wurden, sehen Sie sie in [Kundenkarten auf der Kundenseite](customer-profiles.md).

## <a name="define-filtering-options-for-a-given-attribute"></a>Definieren von Filteroptionen für ein bestimmtes Attribut

Richten Sie die Felder ein, die auf der Seite **Kunden** zum Durchsuchen und Filtern verwendet werden sollen.

1. Wechseln Sie zu **Kunden** und wählen Sie **Such- & Filterindex**.

1. Wählen Sie ein Attribut und **Filter hinzufügen** aus. Definieren Sie die Anzahl der Ergebnisse und die Reihenfolge, in der sie organisiert werden. Abhängig vom Datentyp des Attributs erscheint einer der folgenden Bereiche.

   - Zeichenfolgentypattribute: Geben Sie die Anzahl der gewünschten Ergebnisse auf dem **Zeichenfolgenfilteroptionen** Bereich und die Bestellrichtlinie an, nach der sie organisiert werden.

   - Numerische Zeichenfolgenattribute: Geben Sie die Intervalle auf dem **Nummernfilteroptionen** Bereich und die Bestellrichtlinie an, nach der sie organisiert werden.

   - Datenattribute: Geben Sie die Intervalle auf dem **Datenfilteroptionen** Bereich und die Bestellrichtlinie an, nach der sie organisiert werden.

1. Klicken Sie auf **OK**. Wiederholen Sie dies für alle Attribute, nach denen Sie filtern möchten.

1. Wählen Sie **Ausführen**, sobald Sie bereit sind, Ihre Einstellungen für Suche und Filter anzuwenden. Nachdem die Änderungen verarbeitet wurden, sehen Sie sie in [Kundenkarten auf der Kundenseite](customer-profiles.md).

## <a name="view-indexed-customer-fields"></a>Indizierte Kundenfelder anzeigen

Die Seite **Such- und Filterindex** zeigt die folgenden Informationen:

- **Name**: Stellt den Namen des Attributs so dar, wie er in der Entität *Kunde* erscheint.
- **Datentyp**: Gibt an, ob der Datentyp eine Zeichenfolge, eine Zahl oder ein Datum ist.
- **In die Suche einbeziehen**: Gibt an, ob dieses Attribut für die Suche nach Kunden auf der Seite **Kunden** über das Feld **Suche** verwendet werden kann.
- **Filter hinzufügen**: Steuerelement, um festzulegen, wie dieses Attribut für die Filterung auf der Seite **Kunden** verwendet werden kann.

## <a name="next-steps"></a>Nächste Schritte,

Überprüfen Sie die [einheitliche Profilseite](customer-profiles.md), um nach Profilen zu suchen oder die indizierten Felder zu verwenden, um eine Teilmenge aller einheitlichen Profile anzuzeigen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
