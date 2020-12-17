---
title: Kundenprofile suchen und filtern
description: Schnelles Auffinden von Informationen über einheitliche Kundenprofile und Filter für bestimmte Attribute.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405797"
---
# <a name="customer-profiles-search--filter-index"></a>Kundenprofile: Such- und Filterindex

Das Ergebnis der Vereinheitlichung Ihrer Kundendaten ist eine Kundenprofileinheit, die eine einheitliche Sicht auf Ihren gesamten Kundenstamm bietet. Um schnell [Informationen über einen bestimmten Kunden oder eine bestimmte Kundengruppe zu finden](customer-profiles.md), können Sie die Funktionen **Suchen** und **Filter** auf der Seite **Kunden** konfigurieren. Lesen Sie weiter, um zu erfahren, wie Admins die Attribute auf der Seite **Such- und Filterindex** bearbeiten können, die den Benutzern zum Suchen und Filtern zur Verfügung stehen.

> [!div class="mx-imgBorder"]
> ![Suchfilter](media/search-filter.png "Suchfilter")

## <a name="add-fields-and-specify-attributes"></a>Felder hinzufügen und Attribute angeben

Wenn Sie als Administrator zum ersten Mal durchsuchbare Attribute definieren, müssen Sie zunächst indizierte Felder definieren. Wir empfehlen Ihnen, alle Attribute auszuwählen, nach denen Benutzer Kunden auf der Seite **Kunden** suchen und filtern können. Sie können nur Attribute angeben, die in der Entität Kundenprofil vorhanden sind, die Sie während des Datenvereinheitlichungsprozesses angelegt haben.

1. Öffnen Sie die Seite **Kunden** und wählen Sie **Such- & Filterindex**.

> [!NOTE]
> Wir erstellen eine Standard-Suchindexkonfiguration für die verfügbaren Attribute in der Entität Kunde aus den folgenden semantischen Typen, wie auf der Seite Karte definiert.
> - Person Vorname, Nachname, zweiter Vorname, vollständiger Name
> - Organisationsname
> - E-Mail-Adresse
> - Telefon
> - Informationen zum Standort

2. Wählen Sie **+ Hinzufügen**, um die indizierten Felder anzugeben.

3. Wählen Sie die Attribute in der Liste aus, die Sie als indizierte Felder hinzufügen möchten. Sie können jederzeit weitere Attribute hinzufügen, indem Sie **Hinzufügen** auswählen. Sie können auch alle ausgewählten Attribute entfernen, indem Sie das Symbol **Entfernen** wählen.

## <a name="explore-the-indexed-customer-fields-table"></a>Durchsuchen Sie die Tabelle Indizierte Kundenfelder

Die folgenden Informationen werden in der Tabelle dargestellt.

- **Name**: Stellt den Namen des Attributs so dar, wie er in der Entität Kundenprofil erscheint.
- **Datentyp**: Gibt an, ob der Datentyp eine Zeichenfolge, eine Zahl oder ein Datum ist.
- **In die Suche einbeziehen**: Gibt an, ob dieses Attribut für die Suche nach Kunden auf der Seite **Kunden** über das Feld **Suche** verwendet werden kann.
- **Filter hinzufügen**: Steuerelement, um festzulegen, wie dieses Attribut für die Filterung auf der Seite **Kunden** verwendet werden kann.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Bearbeitung von Filteroptionen für ein bestimmtes Attribut

Das Menü **Filter** auf der Seite **Kunden** kann eine unterschiedliche Anzahl von Attribut-Ebenen enthalten (z. B. verschiedene Altersgruppen, nach denen Kunden gefiltert werden können).

1. Wählen Sie **Filter hinzufügen** für ein bestimmtes Attribut auf der Seite **Such- und Filterindex**. Sie können die Anzahl der Ergebnisse und die Reihenfolge, in der sie organisiert werden, definieren. Abhängig vom Datentyp des Attributs erscheint einer der folgenden Bereiche.

- Zeichenfolgentypattribute: Geben Sie die Anzahl der gewünschten Ergebnisse auf dem **Zeichenfolgenfilteroptionen** Bereich und die Bestellrichtlinie an, nach der sie organisiert werden.

- Numerische Zeichenfolgenattribute: Geben Sie die Intervalle auf dem **Nummernfilteroptionen** Bereich und die Bestellrichtlinie an, nach der sie organisiert werden.

- Datenattribute: Geben Sie die Intervalle auf dem **Datenfilteroptionen** Bereich und die Bestellrichtlinie an, nach der sie organisiert werden.

2. Wählen Sie **Speichern**, um Ihre Änderungen zu übernehmen.

3. Wählen Sie **Ausführen**, sobald Sie bereit sind, Ihre Einstellungen anzuwenden.
