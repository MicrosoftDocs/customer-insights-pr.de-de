---
title: Zustimmung des Kunden verwenden
description: Respektieren Sie die Einwilligungspräferenzen Ihrer Kunden in Customer Insights, indem Sie Einwilligungsdaten importieren.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 77b09b6eb0a916e724542d503d96d19c5581aca1
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2022
ms.locfileid: "8947498"
---
# <a name="use-customer-consent"></a>Zustimmung des Kunden verwenden

Datenschutz- und Datenschutzbestimmungen geben Einzelpersonen das Recht zu regeln, wie eine Organisation ihre personenbezogenen Daten verwendet. Beispiele für solche Vorschriften sind die Datenschutz-Grundverordnung in der Europäischen Union oder der California Consumer Privacy Act in den Vereinigten Staaten. Diese Bestimmungen ermöglichen es Personen, sich gegen die Erhebung, Verarbeitung oder Weitergabe ihrer personenbezogenen Daten durch Dritte zu entscheiden.  

Kunden können ihre Einwilligung für bestimmte Kontaktformen widerrufen oder verweigern. Sie können auch verlangen, dass Sie sich gegen die Erhebung, Speicherung, Verwendung oder den Verkauf ihrer personenbezogenen Daten entscheiden. Es ist wichtig, dass Ihr Unternehmen die Einwilligungs- und Datenschutzpräferenzen aller Kunden respektiert.  

Dynamics 365 Customer Insights hilft Ihnen dabei, die Wünsche Ihrer Kunden zu erfüllen, indem Sie ihre Präferenzen als Teil der einheitlichen Kundenprofile importieren und speichern.

Sofern Einwilligungsdaten getrennt von Ihren Kundenprofilen gespeichert werden, [fügen Sie Ihre Zustimmungsdaten als neues Datenquelle hinzu](#import-and-unify-consent-data). Das Datenquelle, das die Einwilligungsdaten enthält, wird dem Datenvereinheitlichungsprozess hinzugefügt. Die erfolgreiche Zusammenführung von Einwilligungsdaten und Kundenprofilen führt dann zu einheitlichen Kundenprofilen, die die Einwilligungsinformationen enthalten. Für Kundenprofile, die bereits Einwilligungsinformationen enthalten, gehen Sie direkt zum Abschnitt [Zustimmungsdaten verwenden](#use-consent-data).

## <a name="prerequisites"></a>Anforderungen

Die folgenden Informationen müssen in Ihren Quelldaten verfügbar sein, um Einwilligungsdaten mit anderen Kundenprofilen zu vereinheitlichen:

- Alternativschlüssel, um die Einwilligungsinformationen Benutzerprofilen in Customer Insights zuzuordnen. Beispielsweise eine Telefonnummer oder eine E-Mail-Adresse.
- Zustimmungswert, um den Status der Zustimmung des Kunden zu bestimmen.

Ziehen Sie Erwähung, die folgenden *optionalen* Informationen hinzuzufügen:

- Primärschlüssel zum Aktualisieren des Zustimmungsstatus, wenn ein Kunde eine Änderung anfordert.
- Art der Einwilligung, wenn es mehr als eine Möglichkeit gibt, Kundeninformationen zu verarbeiten.
- Datum der Einwilligung oder jede andere Art von Daten, die für Ihre Einwilligungsszenarien relevant sind.

Beispieltabelle einer einfachen Einwilligungsdatenbank mit mehreren Einwilligungsoptionen:

|Einwilligungs-ID (Primärschlüssel)   |E‑Mail (Alternativschlüssel)  |Einwilligungsoption  |Einwilligungswert  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Newsletter       |  False       |
|2    |  holly@contoso.com       |  Produktupdates       |  true       |
|3    |  frank@contoso.com       |  Newsletter       | true        |
|4    |  frank@contoso.com       |  Produktupdates       |  False       |

## <a name="import-and-unify-consent-data"></a>Einwilligungsdaten importieren und vereinheitlichen

Sie können Zustimmungsdaten auf die gleiche Weise importieren, wie Sie andere Datenquellen in Customer Insights aufnehmen. Weitere Informationen zu unterstützten Datenquellen und deren Import finden Sie unter [Übersicht Datenquellen](data-sources.md).

Weitere Informationen zum Vereinheitlichen Ihrer Datenquellen finden Sie unter [Übersicht über die Datenvereinheitlichung](data-unification.md).

## <a name="use-consent-data"></a>Zustimmungsdaten verwenden

Sobald Ihre Zustimmungsdaten Teil Ihrer einheitlichen Kundenprofile sind, können Sie sie in Customer Insights verwenden. Erstellen Sie beispielsweise ein Segment mit einer Regel, um sicherzustellen, dass Sie die Privatsphäre- und Datenschutzpräferenzen Ihrer Kunden respektieren. Regeln, die Einwilligungspräferenzen unterstützen, werden verwendet, um Benutzer basierend auf Profilattributen aus einem Segment auszuschließen. Hinzufügen einer Regel zu einem Segment, die Kundenprofile ausschließt, die keine Zustimmung zur Kontaktaufnahme gegeben haben.

Unter Bezugnahme auf die Beispieltabelle oben könnte ein Segment diese Regel enthalten: `Consent option=Newsletter & Consent value=True`. Diese Konfiguration führt zu einem Segment, das Kontaktpräferenzen berücksichtigt, um einen Newsletter zu senden.

Weitere Informationen zum Erstellen von Segmenten finden Sie unter [Segmente erstellen](segment-builder.md).

Sobald das Segment erstellt ist, können Sie eine der vielen [Exportoptionen](export-destinations.md) verwenden, um das Segment in anderen Anwendungen verwenden.

## <a name="ensure-updated-consent-status"></a>Stellen Sie sicher, dass der Einwilligungsstatus aktualisiert ist

Es ist wichtig, den Zustimmungsstatus für Ihre Kunden auf dem neuesten Stand zu halten. Die geplante Aktualisierung in Customer Insights importiert immer den neuesten Stand Ihrer Datenquellen. Diese Informationen werden dann durch Datenvereinheitlichung verarbeitet und führen zu aktualisierten Kundenprofilen. Diese aktualisierten Profile werden dann zum Aktualisieren von Segmenten verwendet, um sicherzustellen, dass Sie mit den aktuellsten Informationen arbeiten.

Stellen Sie mit anderen Worten sicher, dass die Quelldaten, die in Customer Insights importiert werden, immer die neuesten Informationen enthalten.

Weitere Informationen finden Sie unter [Segmente manuell aktualisieren](segments.md#refresh-segments) oder [konfigurieren Sie eine geplante Aktualisierung](system.md#schedule-tab).
