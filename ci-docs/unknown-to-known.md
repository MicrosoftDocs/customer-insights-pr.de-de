---
title: Personalisieren Sie Ihre Erfahrungen mit Daten über bekannte und unbekannte Benutzer
description: Integrieren Sie die Informationen über zuvor unbekannte Benutzer, wenn Sie ihre Identität kennen.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8e3477750d82f965dc2d62174fb35554d9447b7b
ms.sourcegitcommit: 52eca81c36e93d553140f5a37cf6013aaa42623a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2022
ms.locfileid: "9224294"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Personalisieren Sie Ihre Erfahrungen mit Daten über bekannte und unbekannte Benutzer

Die Verwaltung von Kundendaten ist keine neue Herausforderung, aber es wird immer schwieriger, wenn Benutzer durch die verschiedenen digitalen Kanäle navigieren, die Marken anbieten. Ein Benutzer, der in einem Kanal bekannt (authentifiziert) ist, wird in einem anderen unbekannt (nicht authentifiziert), wenn er nicht angemeldet ist. Das Problem besteht häufig darin, dass nicht authentifizierte (unbekannte) Benutzer keine gemeinsame ID haben. Es kann verwendet werden, um aussagekräftige Profilattribute zuzuordnen und einheitliche Kundenprofile zu generieren. Customer Insights hilft bei der Lösung dieses Problems, indem Daten aus Tracking-Methoden auf Ihren Quellsystemen aufgenommen werden. Die Konsolidierung unbekannter und bekannter Profile bietet Unternehmen einen vollständigen Überblick über aktuelle Profile und ihre historischen Transaktionen, Verhaltensweisen und demografischen Daten. Es geht sogar noch einen Schritt weiter, indem es eine Identitätsauflösung bereitstellt, mit der Sie die Kundenaktivitäten über mehrere Kanäle vereinheitlichen können, einschließlich Ihrer Website, Einkäufe im Geschäft, Treueprogramme usw.

## <a name="sample-scenario"></a>Beispielszenario

Denken wir an eine Kaffeekette, die über eine breite Kundenbasis verfügt, die Kaffee und Lebensmittel in Geschäften kauft und Produkte online bestellt. Häufig werden Online-Besucher beim Durchsuchen der Produkte nicht authentifiziert, was sie zu „unbekannten Benutzern“ macht. Für die Kaffeekette ist es schwierig, personalisierte Angebote und Erfahrungen zu liefern, wenn die Benutzer unbekannt sind. Andererseits können sich Kunden in ihr Konto einloggen und „bekannte Benutzer“ des Unternehmens werden, indem sie einem Treuesystem beitreten, was wiederum personalisiertere Erfahrungen ermöglicht. Customer Insights kann der Kaffeekette dabei helfen, Erkenntnisse über bekannte und bisher unbekannte Benutzer zu gewinnen.

Mit Customer Insights kann das Unternehmen Kundenprofile mit Aktivitätsdaten aus nicht authentifizierten (unbekannten) Sitzungen kombinieren, nachdem sich ein Benutzer angemeldet hat und bekannt geworden ist. Die Kaffeekette kann Daten aus anderen Datenquellen mithilfe integrierter Konnektoren in Customer Insights einbringen, um Identitäten für Kunden aus verschiedenen Kanälen zusammenzuführen.

## <a name="prerequisites"></a>Anforderungen

- Webdaten werden gesammelt und umfassen „Besucher-IDs“ für alle Besucher.
- Webdaten enthalten „authentifizierte Benutzer-IDs“ für eingeloggte Besucher. Diese IDs sind mit dem Kundenbindungssystem verknüpft.
- Hochwertige Ereignisdaten wie „Produktansicht“ und „Kasse“ werden definiert und zusammen mit dem Zeitstempel des Ereignisses und einer Ereignis-ID in die Quelldaten aufgenommen.

Die folgende Tabelle zeigt ein vereinfachtes Beispiel, wie hochwertige Webereignisse erfasst werden könnten.

|EventID|EventTimeStamp|UserID|LoyaltyID|EventName|
|--|--|--|--|--|
|1|23.07.2022 10:00:00|abc123|--|Produktansicht|
|2|23.07.2022 10:05:00|abc123|707|Treue-Anmelden|
|3|23.07.2022 10:10:00|abc123|707|Auschecken|
|4|23.07.2022 10:20:00|xyz789|--|Produktansicht|

## <a name="data-ingestion"></a>Dateneinbindung

Daten über Kunden können als Ereignisdaten von Ihrer Website stammen und in Ihren eigenen internen oder externen Datenanalysediensten gespeichert werden. Die Webdaten enthalten bekannte und unbekannte Benutzer, wenn die Website über einen Authentifizierungsfluss verfügt, der in einen Authentifizierungsdienst integriert ist. Beispielsweise ein eCommerce-System, bei dem Benutzer ihre vollständigen Daten angeben müssen, um eine Kauftransaktion abzuschließen. Oder ein Treuesystem, das eine Authentifizierung erfordert, um einen gültigen Empfänger der Prämienrabatte zu bestätigen.

Die Ereignisdaten in unserem obigen Beispiel enthalten die unterschiedlichen Profil-IDs der bekannten und unbekannten Benutzer. Bei Ereignis 1 und 4 sind die Benutzer unbekannt, während sich bei Ereignis 2 und 3 der Benutzer mit der ID abc123 bei einem Treueprogramm anmeldet.

:::image type="content" source="media/website-data-source.png" alt-text="Datenquellen einschließlich der Contoso-Website":::

Weitere Informationen zu den verfügbaren Optionen für Datenerfassung finden Sie unter [Datenerfassung-Übersicht](data-sources.md).

## <a name="data-unification"></a>Datenvereinigung

Das Konvergieren unbekannter Identitäten mit bekannten Identitäten trägt dazu bei, die Personalisierung basierend auf dem Benutzerverhalten zu ermöglichen, unabhängig von ihrem Profilstatus (bekannt oder unbekannt). Personalisierte Inhalte für alle Benutzer helfen Kunden, schnell zu den relevantesten Produkten oder Dienstleistungen zu gelangen, an denen sie gerade interessiert sind.

Da einige der Benutzer in unseren Daten bekannt sind, können wir Customer Insights verwenden, um diese Daten mit dem Profil des Benutzers zu kombinieren. Weitere Informationen zum Vereinheitlichen Ihrer Kundenprofile finden Sie unter [Übersicht über die Datenvereinheitlichung](data-unification.md).

1. Wählen Sie die Quellfelder aus der Webdatenentität aus. Verwenden Sie die in Ihren Webdaten gespeicherten Profildaten und wählen Sie die Felder aus, die IDs mit demografischen Daten darstellen.

   :::image type="content" source="media/website-source-fields.png" alt-text="Quellfelder für Webdatenquellen":::

1. Regeln zum Zusammenführen doppelter Datensätze hinzufügen Wählen Sie für Webdaten die am häufigsten ausgefüllten Daten aus.

1. Abgleichsregeln und -bedingungen festlegen Die Webprofil-Ereignisdaten in diesem Beispiel werden anhand von IDs mit den Profilen aus anderen Datenquellen abgeglichen, die Kundeninformationen enthalten. Richten Sie genaue Übereinstimmungsregeln für IDs als separate Regeln mit jeder der anderen Profilentitäten ein, die einen entsprechenden Primärschlüssel oder eine ID-Übereinstimmung aufweisen. In dem Beispiel werden Webereignis-Profildaten als letzte übereinstimmende Entität verwendet, sodass zuerst andere Profildaten kombiniert werden.
   1. Nicht prüfen von **Alle Datensätze einschließen** erstellt vereinheitlichte Profile für bekannte Benutzer und schließt ihre entsprechenden unbekannten Benutzer-IDs ein. Dies ist hilfreich in Szenarien, in denen Sie daran interessiert sind, die vergangenen Verhaltensaktivitäten bekannter Benutzer anzuzeigen, als diese noch unbekannt waren.
   1. Überprüfung von **Alle Datensätze einschließen** erstellt separate Profildatensätze für unbekannte Benutzer. Unbekannte Benutzer erhalten eine eindeutige Kunden-ID. Wenn in Zukunft ein bekanntes Profil in den Profildaten von Web-Ereignissen verknüpft wird, kann die Reise des neu bekannten Benutzers auch auf der Grundlage früherer unbekannter Verhaltensdaten angezeigt und zur Personalisierung verwendet werden.

:::image type="content" source="media/website-match-rule.png" alt-text="Übereinstimmungsregel für die Entität Website Datenquelle.":::

## <a name="get-insights"></a>Erkenntnisse gewinnen

Wenn Kundenprofile für unbekannte und bekannte Benutzer erstellt werden, können die hochwertigen Webereignisdaten als [Aktivitäten](activities.md) verwendet werden. Diese Aktivitäten können verwendet werden, um mehr Einblicke zu gewinnen. Beispielsweise haben Kunden, die vor sechs Monaten eine Website besucht haben (als sie noch unbekannt waren) oder Kunden, die keine Treue-ID haben, nie einen Checkout abgeschlossen.

:::image type="content" source="media/website-known-unknown.png" alt-text="Screenshot der Seite „Kunden“ mit bekannten und unbekannten Kunden":::

[Bereichern](enrichment-hub.md) Ihre Daten, erstellen [Messungen](measures.md), und erstellen [Segmente](segments.md) zur weiteren Aktivierung.

Sie können beispielsweise Segmente bekannter Benutzer erstellen, die sich einige Produkte angesehen, aber nie die Kaufabwicklung abgeschlossen haben.

Weitere Informationen finden Sie unter [Segmente-Übersicht](segments.md).

## <a name="activate-insights"></a>Insights aktivieren

Es gibt mehrere Möglichkeiten, Ihre Daten zu exportieren und auf der Grundlage der zugrunde liegenden Erkenntnisse Maßnahmen zu ergreifen.

Weitere Informationen finden Sie in [Überblick zu Exporte](export-destinations.md).
