---
title: Verwalten Sie unbekannte Profile mit Customer Insights
description: Arbeiten Sie mit unbekannten Kundenprofilen, die in Dynamics 365 Customer Insights erstellt und verwaltet werden.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776820"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Verwalten Sie unbekannte Profile mit Customer Insights

Internetnutzer sind online oft nicht identifiziert oder anonym. Selbst die treuesten Kunden scheinen „unbekannt“ zu sein, wenn sie nicht auf verschiedenen Geräten angemeldet sind. Für viele Marken sind bekannte oder authentifizierte Benutzer trotz wachsender Kundenerwartungen in Bezug auf Personalisierung die Minderheit. Da Cookies von Drittanbietern wahrscheinlich verschwinden werden, ist die Verwaltung von Benutzereinstellungen auf der Grundlage von Erstanbieterdaten von entscheidender Bedeutung, um differenzierte personalisierte Erfahrungen zu erzielen.

Eine einprägsame Personalisierung hängt davon ab, wie gut Sie Ihren Kunden kennen, und Customer Insights hilft Ihnen dabei, indem es alle Ihre Kunden verfolgt.  Sie müssen die Verwendung der zu Beginn des Kundenkontaktverlauf gesammelten Daten nicht einschränken oder einstellen. Mit Customer Insights können Sie Ihre eigenen Daten einbringen, um ein Kundenprofil für unbekannte Benutzer zu erstellen. Dieses Profil können Sie dann trotz fehlender Kontaktdaten für weitere Aktionen nutzen. Importieren Sie First-Party-Daten aus Quellen wie Web-, Mobil- oder CRM-Systemen in Customer Insights, um Kundenprofile kontinuierlich zu bereichern. Wenn Sie mehr Interaktionen vereinheitlichen, [wandeln Sie *Unbekannt*-Kunden in einen *bekannten* Kunden um](unknown-to-known.md).

## <a name="sample-scenario"></a>Beispielszenario

Angenommen, ein Benutzer verwendet sein mobiles Gerät, um auf Ihrer E-Commerce-Website zu surfen. Die Website weist dem Besucher „mobile_guest123“ als eindeutige Kennung zu und Sie beginnen, Verhaltensaktivitäten basierend auf seiner Online-Aktivität zu sammeln. Zum Beispiel, welche Seiten sie besucht haben, wie viel Zeit sie auf diesen Seiten verbracht haben oder auf welche Links sie geklickt haben. Sie kennen ihren Namen oder ihre E-Mail-Adresse nicht, aber diese Daten können Marken helfen, aussagekräftige Erkenntnisse über diesen bestimmten Benutzer zu gewinnen. Im Gegenzug können Sie diese Erkenntnisse beim nächsten Besuch des Benutzers auf der Website nutzen. Fragen Sie Customer Insights nach „mobile_guest123“ ab, um die Segmentliste des Benutzers abzurufen, z. B. „organisch“, „mobile Vorbestellungskunden“, „hochwertige Kunden“ usw., oder rufen Sie das Profil ab, um personalisierte Weberlebnisse zu erstellen. Sie können die Daten auch in ein beliebiges Aktivierungssystem exportieren, um dasselbe zu tun.

## <a name="prerequisites"></a>Anforderungen

- Erstanbieter-Dateneinbindung in Customer Insights
- Jede Entität hat eine eindeutige ID, die als Primärschlüssel festgelegt wird
- Jede Entität mit einem Primärschlüssel zur Personalisierung ist vereinheitlicht
- Das Content-Management-System Ihrer Website kann APIs verwenden (für Web-Personalisierung basierend auf direkter Kommunikation mit Customer Insights)

Die folgende Tabelle zeigt ein vereinfachtes Beispiel, wie hochwertige Webereignisse erfasst werden könnten.

|EventID|EventTimeStamp|UserID|PrimaryKey|EventName|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|abc123|CookieID1|Produktansicht|
|2|09-18-2022 10:05:00|abc123|CookieID1|Produktansicht|
|3|09-18-2022 10:10:00|abc123|CookieID1|Zum Warenkorb hinzufügen|
|4|09-21-2022 09:05:00|abc123|CookieID1|Produktansicht|

## <a name="data-ingestion"></a>Dateneinbindung

Weitere Informationen zu den verfügbaren Optionen für Datenerfassung finden Sie unter [Datenerfassung-Übersicht](data-sources.md).

## <a name="data-unification"></a>Datenvereinigung

Weitere Informationen zum Vereinheitlichen Ihrer Kundenprofile finden Sie unter [Übersicht über die Datenvereinheitlichung](data-unification.md).

## <a name="get-insights"></a>Erkenntnisse gewinnen

[Bereichern](enrichment-hub.md) Ihre Daten, erstellen [Messungen](measures.md), und erstellen [Segmente](segments.md) zur weiteren Aktivierung.

Sie können beispielsweise Segmente von unbekannten Benutzern erstellen, die dieselben Produktseiten aufgerufen, aber nie den Checkout abgeschlossen haben.

## <a name="activation"></a>Aktivierung

Mit Ihren Daten in Customer Insights und Ihren einsatzbereiten Erkenntnissen können Sie Customer Insights zur Personalisierung nutzen:

1. Verwenden Sie die [OData-API](apis.md) zum Abrufen einer Segmentzugehörigkeit oder eines Kundenprofils. Weitere Beispiele finden Sie unter [OData-Abfragebeispiele für Customer Insights-APIs](odata-examples.md).

1. [Exportieren](export-destinations.md) Sie Ihre Daten an Ihre Aktivierungssysteme.

Beispiel: Ein unbekannter Nutzer besucht mehrfach eine Website und besucht Produktseiten für verschiedene Modelle von Lederschuhen. Mit diesen in Customer Insights verfügbaren Daten können Sie den unbekannten Benutzer in das Segment der Personen aufnehmen, die sich für Lederschuhe interessieren. Verwenden Sie dieses Segment, um die Personalisierung Ihrer Website für wiederkehrende Besucher zu informieren. Beim nächsten Besuch erkennt die Seite den unbekannten Nutzer und könnte ihm einen 10%-Gutschein auf Lederschuhe anbieten.

[!INCLUDE [footer-include](includes/footer-banner.md)]
