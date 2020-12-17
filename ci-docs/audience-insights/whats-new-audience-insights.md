---
title: Neue und kommende Funktionen
description: Informationen über neue Funktionen, Verbesserungen und Fehlerbehebungen.
ms.date: 11/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 07b4bee0445f9cd7d53a37cd405af839feb07ae3
ms.sourcegitcommit: 4004eadac7a65e50e0a409cb925958523c2b6348
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/30/2020
ms.locfileid: "4650003"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Was ist neu an den Funktionalitäten der Zielgruppen-Insights von Dynamics 365 Customer Insights?

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Wir freuen uns, unsere neuesten Updates bekannt zu geben! In diesem Artikel werden Funktionen für die öffentliche Vorschau, Verbesserungen der allgemeinen Verfügbarkeit und Funktionsupdates zusammengefasst. Um die langfristig geplanten Funktionen zu sehen, werfen Sie einen Blick auf die [Dynamics 365 und Power Platform Freigabe-Pläne](https://docs.microsoft.com/dynamics365/release-plans/).

Sie können sich auch das folgende Video ansehen, um mehr über die geplanten Funktionalitäten zu erfahren.

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

Wir führen Updates nach Region durch. So können bestimmte Regionen Merkmale vor anderen sehen. Sofern nicht anders angegeben, müssen Sie keine Maßnahmen ergreifen, und wir aktualisieren die App automatisch ohne Ausfallzeiten.

> [!TIP]
> Zum Senden und Abstimmen zu gewünschten Funktionen und Vorschläge zum Produkt, navigieren Sie zu [Dynamics 365  Anwendungs-Ideen Portal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="november-2020-updates"></a>Aktualisierungen im November 2020

Die Updates im November 2020 enthalten mehrere Funktionen, Leistungsverbesserungen und Fehlerkorrekturen.

### <a name="new-and-updated-features-in-november-2020"></a>Neue und aktualisierte Funktionen im November 2020

#### <a name="data-enrichment"></a>Datenanreicherung

- **Nutzen Sie Ihre eigenen Anreicherungsdaten über das Secure File Transfer Protocol (SFTP) für den benutzerdefinierten Import**
  
  Mit SFTP Custom Import können Sie Anreicherungsdaten importieren, die nicht den Prozess der Datenvereinheitlichung durchlaufen müssen. Erfahren Sie mehr über den benutzerdefinierten SFTP-Import.

  Weitere Informationen finden Sie unter [Kundenprofile mit eigenen Daten anreichern (Vorschau)](enrichment-SFTP-custom-import.md).
 
- **Anreichern Sie Ihre Kundendaten mit Standortdaten von HERE Technologies**

  Mit den Datenanreicherungsdiensten von HERE Technologies können Sie durch Adressnormalisierung, Extraktion von Breiten- und Längengraden und mehr ein genaueres Standortverständnis Ihrer Kunden aufbauen. Erfahren Sie mehr über die Anreicherung mit HERE Technologies.

  Weitere Informationen finden Sie unter [Anreicherung von Kundenprofilen mit HERE Technologies](enrichment-here.md).

#### <a name="data-unification"></a>Datenvereinigung

- **Flexibilität zur Aktivierung der Datenprofilierung für ausgewählte Entitäten und Felder aus Ihrem Speicherkonto**

  Sie können angeben, welche Entitäten und Felder aus einem Common Data Model-Ordner in Ihrem Azure Data Lake-Speicherkonto Sie als Teil der Datenerfassung für die Datenprofilierung aktivieren möchten.

  Weitere Informationen finden Sie unter [Verbinden Sie mit einem Common Data Model-Ordner](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Erweiterbarkeit

- **Aktivieren Sie Ihre Segmente über Google Ads**

  Exportieren Sie Segmente aus in Google Ads-Zielgruppenlisten und verwenden Sie diese Listen für Werbung bei Google Search, Google Display Network, YouTube und Gmail. Erfahren Sie mehr über die Aktivierung Ihrer Segmente durch Google Ads.

  Für weitere Informationen, siehe [Konnektor für Google Ads](export-google-ads.md).

- **Aktivieren Sie Ihre Segmente über Marketo**

  Exportieren Sie Segmente zu Marketo-Zielgruppen und verwenden Sie diese Zielgruppen für die Marketingautomatisierung. Erfahren Sie mehr über die Aktivierung Ihrer Segmente durch Marketo. 

  Für weitere Informationen, siehe [Konnektor für Marketo](export-marketo.md).

- **Aktivieren Sie Ihre Segmente über DotDigital**

  Exportieren Sie Segmente zu DotDigital und nutzen Sie diese für Marketingzwecke. Erfahren Sie mehr über das Aktivieren Ihrer Segmente durch DotDigital. 

  Weitere Informationen finden Sie unter [Konnektor für DotDigital](export-dotdigital.md).

#### <a name="predictions"></a>Vorhersagen

- **Transaktionsbedingte Abwanderung vorhersagen**

  Mit der Funktion zur Vorhersage der Transaktionsabwanderung können Sie ohne die Hilfe eines Datenwissenschaftlers vorhersagen, wie wahrscheinlich es ist, dass ein Kunde den Kauf von Produkten oder Dienstleistungen abbricht.  Mit Hilfe des Prediction Score können Sie andere Informationen über Ihre Kunden, wie z. B. den Kundenwert, kombinieren, um Segmente mit hohem Abwanderungsrisiko oder Kunden mit hohem Wert zu erstellen. Verwenden Sie dieses Segment, um Kunden durch Marketingaktivitäten, Kundensupport und andere Szenarien direkt anzusprechen, um das Abwanderungsrisiko zu reduzieren.
 
  Konfigurieren Sie die Definition von Abwanderung als ein für Ihr Unternehmen spezifisches Zeitfenster und definieren Sie, wann Kunden als abgewandert gelten. Ein Lebensmittelgeschäft könnte einen Kunden als abgewandert betrachten, wenn er in den letzten 30 Tagen nichts gekauft hat.
 
  Wenn Sie mit dem Erstellen der Vorhersage fortfahren, geben wir Ihnen eine Anleitung, welche Daten benötigt werden, und ermöglichen Ihnen die Zuordnung von Daten über Ihr Unternehmen zu Feldern, die für die Vorhersage der Abwanderung Ihrer Kunden erforderlich sind. Sie können auch einen Zeitplan festlegen, um das Modell basierend auf neuen Informationen in Ihrem System neu zu trainieren, um sich an veränderte Geschäftsumstände anzupassen.
 
  Weitere Informationen finden Sie unter [Transaktionale Abwanderungsvorhersage (Vorschau)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Systemadministrator

- **Umgebung zurücksetzen**

  Setzt alles in einer Umgebung einer ausgewählten Instanz zurück, um neu zu beginnen.

  Weitere Informationen finden Sie unter [Zurücksetzen einer bestehenden Umgebung](manage-environments.md#reset-an-existing-environment).


- **Verbinden Sie sich mit Ihrem Azure Data Lake-Speicherkonto über einen Service Principal**

  Schreiben Sie Datenausgaben in Ihr Speicherkonto und lesen Sie Daten daraus, indem Sie ein Azure Service Prinzipal verwenden. Bestehende Speicherkonto-Verbindungen können weiterhin den Kontoschlüssel verwenden. Sie bieten auch eine Upgrade-Option, um das Service Prinzipal weiter zu verwenden. Neue Verbindungen basieren auf der Authentifizierungsmethode des Service-Prinzipals für Ihr Speicherkonto.

  Weitere Informationen finden Sie unter [Verbinden Sie mit einem Azure Data Lake Storage Gen2-Konto mit einem Azure-Service-Principal für Zielgruppen-Insights](connect-service-principal.md).

## <a name="october-2020-updates"></a>Oktober 2020 Aktualisierungen

Die Updates im Oktober 2020 enthalten mehrere Funktionen, Leistungsverbesserungen und Fehlerkorrekturen.

### <a name="new-and-updated-features-in-october-2020"></a>Neue und aktualisierte Funktionen im Oktober 2020

#### <a name="extensibility"></a>Erweiterbarkeit

- **Exportieren Sie zu Mailchimp**

Exportieren Sie Segmente zu bestehenden Zielgruppenlisten in Mailchimp, um Ihren Kunden ein personalisiertes E-Mail-Erlebnis zu bieten.

Für weitere Informationen, siehe [Konnektor für Mailchimp](export-mailchimp.md).

#### <a name="data-enrichment"></a>Datenanreicherung

- **Deduplizieren Sie die Quelldatensätze in einer Entität Match**

Geben Sie Deduplizierungsregeln für Entitäten an, die im Abgleichsprozess verwendet werden, um doppelte Datensätze zu identifizieren. Führen Sie diese in einem Datensatz zusammen und verknüpfen Sie alle Quelldatensätze mit diesem zusammengeführten Datensatz. Dieser deduplizierte Datensatz wird dann im Cross-Entity-Matching-Prozess verwendet.

Weitere Informationen finden Sie unter [Definieren der Deduplizierung auf einer übereinstimmenden Entität](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Systemadministrator

- **Orchestration: Neue Aktualisierungsoption in Merge**

Bis heute wurden beim Ausführen des Zusammenführungsprozesses alle nachgelagerten Prozesse ausgeführt, die von der Zusammenführung und nachfolgenden Prozessen abhängen. Sie können jetzt die Ausgabe des Merge-Prozesses (die vereinheitlichte Entität „Kunde“) überprüfen, bevor Sie sie in nachgelagerten Verarbeitungen wie Segmenten oder Kennzahlen verwenden.
Auf der Seite „Zusammenführen“ können Sie nun auswählen, dass nur der Schritt „Zusammenführen“ ausgeführt werden soll und nur dieser Prozess ausgeführt wird. Um auch alle nachgelagerten Prozesse zu aktualisieren, können Sie Zusammenführen und nachgelagerte Prozesse ausführen wählen. 

## <a name="september-2020-updates"></a>Aktualisierungen September 2020

Die Updates im September 2020 enthalten mehrere Funktionen, Leistungsverbesserungen und Fehlerbehebungen.

### <a name="new-and-updated-features-in-september-2020"></a>Neue und aktualisierte Funktionen im September 2020

#### <a name="activities"></a>Aktivitäten

- **Intelligente Vorhersage der Attributsemantik**

Diese neue Funktion sagt die semantischen Typen von Eingabeattributen vorher, die an den Datenvereinigungsprozess weitergegeben werden. Es werden Modelle des maschinellen Lernens verwendet, die die Genauigkeit verbessern und Zeit sparen.

#### <a name="enrichments"></a>Anreicherungen

- **Demografische Anreicherung durch Experian**

Die demografische Anreicherung durch Experian ist jetzt in der Vorschau verfügbar. Experian ist ein weltweit führender Anbieter von Kredit- und Marketingdienstleistungen für Verbraucher- und Geschäftskredite. Mit [den Datenanreicherungsdiensten von Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage) können Sie ein tieferes Verständnis Ihrer Kunden aufbauen, indem Sie Ihre Kundenprofile mit demografischen Daten wie Haushaltsgröße, Einkommen und mehr anreichern.

Um diese Funktion nutzen zu können, müssen Sie über ein aktives Experian-Abonnement verfügen.

Weitere Informationen finden Sie unter [Anreichern der Kundenprofile mit demografischen Daten von Experian](enrichment-experian.md)


#### <a name="system-administration"></a>Systemadministrator

- **Aufgabendetailsbereich**

Im Bereich Aufgabendetails können Sie Details zu den vom System ausgeführten Aufgaben anzeigen. Dies ist eine praktische Möglichkeit, Probleme mit der Konfiguration zu identifizieren und Lösungen zu finden.
Überprüfen Sie die Fehlermeldungen, um festzustellen, wie Sie potenzielle Probleme beheben.
 
- **Verarbeitungsinformationen wurden zusätzlichen Seiten hinzugefügt**

Diese Verbesserung fügt Informationen zum Status Ihrer Entitäten auf den Seiten **Entitäten** und **Kunden** hinzu.
 
Darüber hinaus finden Sie auf beiden Seiten Details zum Fortschritt der Prozesse sowie Details zu den Aufgaben.

- **Verbesserungen an der Systemstatusseite**

Wir haben die Struktur der Statusdetailtabelle auf **System** > **Status** bei der Überprüfung von Datenexporten verbessert.
 
Außerdem sind Fehler in der **Details**-Spalte jetzt detaillierter und nachvollziehbarer. 
 
- **Abbrechen setzt den Auftrag auf den vorherigen Status zurück**

Wenn Sie eine Aufgabe beispielsweise während des Abgleichprozesses abbrechen, wird sie auf ihren letzten Status zurückgesetzt. Wenn der Abgleichvorgang beispielsweise gestern abgeschlossen wurde und Sie ihn heute abbrechen, wird der erfolgreiche Status von gestern wiederhergestellt.


## <a name="august-2020-updates"></a>Aktualisierungen August 2020

Die Updates im August 2020 beinhalten verschiedene Funktionen, Leistungsverbesserungen und Fehlerkorrekturen.

### <a name="new-and-updated-features-in-august-2020"></a>Neue und aktualisierte Funktionen im August 2020

#### <a name="data-unification"></a>Datenvereinigung

- **Verbesserte Erfahrung für die Kartenphase während der Datenvereinigung**

  Durch die Erfahrung mit der Kartenphase im Datenvereinigungsprozess können Sie Entitäten und Attribute auswählen und die Semantik nahtloser definieren.

  Die Änderungen umfassen:
  
  - Es sind weniger Interaktionen erforderlich, um Entitäten und Felder hinzuzufügen
  - Verbesserte Suchfunktionen auf der Kartenseite
  - Visuelle und einfache Identifizierung des vorgeschlagenen Feldtyps

#### <a name="enrichment"></a>Anreicherung

- **Anreicherung der Interessenaffinitäten in weiteren Märkten verfügbar**

  Wir erweitern die Verfügbarkeit der Anreicherung von Interessenaffinitäten über die USA hinaus auf fünf weitere Märkte: Kanada, Australien, Vereinigtes Köngirch, Frankreich und Deutschland. Mit dieser Erweiterung können Sie Ihre Kundendaten mit zusätzlichen Interessen anreichern, die für diese Märkte gelten. Wir reichern auch Ihre Kundenprofile an, die sich in diesen Märkten befinden, indem wir lokale proprietäre Daten von Microsoft Graph verwenden.
  Weitere Informationen finden Sie unter [Anreichern von Kundenprofilen mit Marken- und Interessenaffinitäten](enrichment-microsoft-graph.md).


## <a name="july-2020-updates"></a>Updates Juli 2020

Die Updates im Juli 2020 enthalten verschiedene Funktionen, Leistungsverbesserungen und Fehlerbehebungen.

### <a name="new-and-updated-features-in-july-2020"></a>Neue und aktualisierte Funktionen vom Juli 2020

#### <a name="extensibility"></a>Erweiterbarkeit

- **Power Automate-Auslöser für abgeschlossenen Vereinheitlichungsprozess**

  Wir haben unsere Trigger für Power Automate erweitert , sodass Sie nun eine Benachrichtigung oder Aktion erstellen können, wenn eine Aktualisierung des Vereinheitlichungsprozesses (Zuordnung, Übereinstimmung, Zusammenführung) abgeschlossen ist.    
  Weitere Informationen finden Sie unter [Power Automate-Connector](export-power-automate.md).

#### <a name="enrichment"></a>Anreicherung

- **Anreicherung der Markenaffinität in weiteren Märkten**

  Wir weiten die Verfügbarkeit der Anreicherung der Markenaffinität über die USA hinaus auf fünf weitere Märkte aus: Kanada, Australien, Großbritannien, Frankreich und Deutschland. Mit dieser Erweiterung können Sie Ihre Kundendaten mit lokalen Marken in diesen Märkten anreichern. Wir reichern auch Ihre Kundenprofile an, die sich in diesen Märkten befinden, indem wir lokale proprietäre Daten von Microsoft Graph verwenden.
  Weitere Informationen finden Sie unter [Anreichern von Kundenprofilen mit Marken- und Interessenaffinitäten](enrichment-microsoft-graph.md).

## <a name="june-2020-updates"></a>Updates Juni 2020

Die Updates im Juni 2020 enthalten mehrere Funktionen, Leistungsverbesserungen und Fehlerbehebungen.

### <a name="new-and-updated-features-in-june-2020"></a>Neue und aktualisierte Funktionen vom Juni 2020

#### <a name="enrichment"></a>Anreicherung

- **Anreicherung mit Unternehmensdaten aus Leadspace**
  
  Definieren Sie Felder in einheitlichen Kundenprofilen, mit denen verwandte Unternehmensdaten aus Leadspace abgerufen werden. Nach dem Ausführen des Anreicherungsprozesses werden B2B-Profile mit zusätzlichen Attributen wie Unternehmensgröße, Standort, Branche und mehr angereichert.    
  Diese Zusammenarbeit ermöglicht es Ihnen, die Qualität Ihrer Daten durch zusätzliche Informationen aus Drittanbieterdiensten zu verbessern. Um diese Anreicherung nutzen zu können, benötigen Sie eine Leadspace-Lizenz, um auf die B2B-Unternehmensdaten zugreifen zu können. Das System wird diese Lizenz verwenden, um Ihre Daten kontinuierlich anzureichern.    
  Weitere Informationen finden Sie unter [Anreicherung von Unternehmensprofilen mit Leadspace](enrichment-leadspace.md).

- **Enrichment Hub-Seite**

  Alle verfügbaren Datenanreicherungen von Erst- und Drittanbietern werden am selben Ort konfiguriert. Das Konfigurieren der Datenanreicherung ist eine nahtlose Erfahrung, die von einem gemeinsamen Ort aus verwaltet wird.    
  Weitere Informationen finden Sie unter [Anreicherung für Kundenprofile](enrichment-hub.md).

- **Separate Anreicherung der Marken- und Interessenaffinität**

  Die Marken- und Interessenaffinitäten sind jetzt als zwei unabhängige Anreicherungen verfügbar. Separate Anreicherungen bieten Ihnen die Flexibilität, sie je nach Ihren geschäftlichen Anforderungen oder Bedürfnissen individuell zu konfigurieren und zu verwalten.    
  Weitere Informationen finden Sie unter [Anreichern von Kundenprofilen mit Marken- und Interessenaffinitäten](enrichment-microsoft-graph.md).

#### <a name="extensibility"></a>Erweiterbarkeit

- **Klickbare URLs für einheitliche Aktivitäten im Dynamics 365-Kundenkarten-Add-In**

  Die vereinheitlichten Aktivitäten im Kundenkarten-Add-In zeigen jetzt klickbare URLs an, wenn solche URLs bei der Konfiguration von Aktivitäten definiert wurden.    
  Weitere Informationen finden Sie unter [Kundenkontaktverlauf-Einblicke](customer-card-add-in.md).

- **Marken- und Interessenaffinitäten sind im Dynamics 365-Kundenkarten-Add-In verfügbar**

  Mit einem neuen Steuerelement im Dynamics 365-Kundenkarten-Add-In können Sie Marken- und Interessenanreicherungen für Ihre Kontakte in Kundenbindungs-Apps in Dynamics 365 anzeigen.    
  Weitere Informationen finden Sie unter [Kundenkontaktverlauf-Einblicke](customer-card-add-in.md).

- **Zusätzliche Power Automate-Trigger**

  Wir haben unser Triggerangebot für Power Automate erweitert und die folgenden Trigger hinzugefügt:
  - Erhalten Sie eine Benachrichtigung oder führen Sie eine Aktion aus, wenn eine automatische vollständige Aktualisierung (Datenquellen, Vereinheitlichung, Segmente, Kennzahlen, Exporte) abgeschlossen wird.
  - Definieren Sie einen Schwellenwert für eine Unternehmenskennzahl. Sie können beispielsweise eine Benachrichtigung erstellen, die gesendet wird, wenn der definierte Schwellenwert überschritten wird. Darüber hinaus liefert der Trigger Informationen, mit denen Sie in Power Automate komplexere Workflows erstellen können.    
  Weitere Informationen finden Sie unter [Power Automate-Connector](export-power-automate.md).

- **Exportieren zum Facebook-Anzeigenmanager**
  
  Mit dieser Funktionalität können Sie Segmente in den Facebook Ads Manager exportieren. Segmente werden als benutzerdefinierte Zielgruppen exportiert, um einheitliche Kundenprofile in Facebook-Marketingkampagnen und -Anzeigen zu verwenden. Die benutzerdefinierten Zielgruppen können auch zur Erstellung von Kampagnen auf Instagram über den Facebook-Anzeigenmanager verwendet werden.    
  Weitere Informationen finden Sie unter [Connector für den Facebook-Anzeigenmanager](export-facebook.md).

#### <a name="predictions"></a>Vorhersagen

- **Vorhersage von Abonnementabwanderung**

  Folgen Sie einer geführten Erfahrung, um Abwanderungsprognosen in Abonnementbereichen wie Clouddiensten, Kundenmitgliedschaften und anderen Sektoren zu erstellen. 

  Mit der Funktion zur Vorhersage von Abonnementabwanderungen können Sie die Wahrscheinlichkeit vorhersagen, mit der ein Kunde die Nutzung abonnementbasierter Produkte oder Services einstellt, ohne einen Datenwissenschaftler zu beauftragen. Mit der Vorhersagebewertung können Sie andere Informationen über Ihre Kunden kombinieren, um Segmente mit hohem Abwanderungsrisiko zu erstellen. Mit Hilfe dieses Segments können Sie Kunden im Marketing, im Kundensupport und in anderen Szenarien direkt ansprechen, um das Abwanderungsrisiko für bestimmte Kunden zu reduzieren und so den Umsatz zu steigern und die Kosten zu senken.

  Innerhalb der Erfahrung können Sie die Definition der Abwanderung als zeitbasiertes Fenster konfigurieren, das speziell für Ihr Unternehmen Gültigkeit hat. Beispielsweise möchte ein Video-Streaming-Unternehmen mit einem monatlichen Abonnementprozess einen Kunden 15 Tage nach Ablauf seines Abonnements möglicherweise als abgewandert betrachten.

  Während Sie mit Vorhersage fortfahren, werden wir Ihnen mitteilen, welche Daten benötigt werden, und Ihnen ermöglichen, Daten über Ihr Unternehmen Feldern zuzuordnen, die zur Vorhersage der Abwanderung für Ihre Kunden erforderlich sind. Wenn sich Unternehmensinformationen ändern, können Sie auch einen Zeitplan festlegen, um Ihr System mit neuen Informationen erneut zu trainieren und es an sich ändernde geschäftliche Verhältnisse anzupassen.    
  Weitere Informationen finden Sie unter [Vorhersage von Abonnementabwanderung (Vorschau)](predict-subscription-churn.md).

#### <a name="segments"></a>Segmente

- **Ähnliche Kunden finden**
  
  Finden Sie mithilfe künstlicher Intelligenz ähnliche Kunden in Ihrem Kundenstamm. Ein mit Binärklassifizierung arbeitendes Machine Learning-Modell weist Kunden im erweiterten Segment eine Ähnlichkeitsbewertung zu. Die Bewertung basiert auf der Ähnlichkeit mit Kunden im Quellensegment. Abhängig von der Ähnlichkeitsbewertung werden Kundenprofile zu einem neu erstellten Segment hinzugefügt.

  Dieser Vorgang, der im digitalen Marketing manchmal als Lookalike-Modellierung bezeichnet wir, verwendet ein KI-Modell, um Kunden zu finden, die einem anderen Segment Ihrer Kunden ähneln, indem zusätzliche Attribute berücksichtigt werden. Sie können nicht nur die Attribute auswählen, sondern auch die maximale Anzahl von Kunden angeben, die in diesem neuen Segment enthalten sein sollen. Das KI-Modell berechnet dann Ähnlichkeitsbewertungen für jeden Kunden basierend auf Ihren ausgewählten Attributen und findet Kunden mit der höheren durchschnittlichen Ähnlichkeitsbewertung. Das resultierende Segment umfasst Kunden, die Ähnlichkeit mit dem Kunden in Ihrem ursprünglichen Segment aufweisen.    
  Weitere Informationen finden Sie unter [Ähnliche Kunden](find-similar-customer-segments.md).

- **Segmentüberlappung und Unterscheidungsmerkmale**

  Durch Segmentüberlappung können Sie sehen, wie viele und welche Kunden zwei oder mehr Segmenten gemeinsam haben. Zum Beispiel können Sie sehen, wie sich ein Segment mit Kunden mit hohen Ausgaben mit einem Segment mit Kunden mit hoher Zufriedenheit überlappt, oder ein Segment mit abwandernden Kunden mit einem Segment mit unzufriedenen Kunden. Darüber hinaus können Sie anhand eines zusätzlichen Attributs Ihrer Wahl analysieren, wie sich die Überlappung ändert.

  Unterscheidungsmerkmale der Segmente verdeutlichen, was ein Segment vom Rest Ihrer Kunden oder von einem anderen Segment unterscheidet. Sie müssen lediglich ein Segment identifizieren, woraufhin das System Profilattribute und -kennzahlen identifiziert, die das Segment in Form einer Rangliste von Unterscheidungsmerkmalen von anderen Segmenten unterscheiden – vom stärksten bis zum schwächsten Unterscheidungsmerkmal.    
  Weitere Informationen finden Sie unter [Segmenteinblicke (Vorschau)](segment-insights.md).

- **Segmentlebensdauer**
  
  Definieren Sie einen Zeitplan zum Aktivieren oder Deaktivieren eines Segments.    
  Weitere Informationen finden Sie unter [Verwalten vorhandener Segmente](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Update Mai 2020

Die Updates im Mai 2020 enthalten mehrere Funktionen, Leistungsverbesserungen und Fehlerkorrekturen.

### <a name="new-and-updated-features-in-may-2020"></a>Neue und aktualisierte Funktionen im Mai 2020

#### <a name="data-ingestion"></a>Dateneinbindung

- **Datenerfassung in Echtzeit: Verlaufsansichten**

  Wenn Sie unsere API zum Aufnehmen von Echtzeit-Updates verwenden, können Sie einen aggregierten Verlauf von bis zu 30 Tagen für diese Updates anzeigen. Sie haben Zugriff auf Aggregate aller erfolgreichen oder fehlgeschlagenen API-Aufrufe, einschließlich deren Ergebnis, Quellsystem und anderer nützlicher Metadaten.    
  Weitere Informationen finden Sie unter [Echtzeit-Dateneingabe](real-time-data-ingestion.md).

- **Datenerfassung in Echtzeit: Profilaktualisierungen**

  Mit dieser Erweiterung der Echtzeit-Datenerfassung können Sie innerhalb von Sekunden Änderungen an bestimmten Benutzerprofilfeldern anzeigen.    
  Neben der Echtzeitfunktionalität für Aktivitäten unterstützt das System Aktualisierungen von Profilfeldern mit geringer Latenz. Echtzeitaktualisierungen für Profilfelder haben eine Ablaufzeit und sind daher kein Ersatz für geplante Aktualisierungen.    
  Weitere Informationen finden Sie unter [Echtzeit-Dateneingabe](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Erweiterbarkeit

- **Aktualisierte Zeitleiste und Paginierung im Kundenkarten-Add-In**

  Die Zeitleiste der Kundenkarten-Add-In-Lösung entspricht der Aktivitäts-Zeitleiste. Die Paginierung der Zeitleiste verbesserte sich und zeigte bis zu 50 Aktivitäten gleichzeitig an. Außerdem können zusätzliche Aktivitäten in die Zeitskala geladen werden.    
  Weitere Informationen finden Sie unter [Kundenkontaktverlauf-Einblicke](customer-card-add-in.md).

- **Power Automate Auslöser für Segmentwechsel**

  Auslöser für Power Automate definiert, woraus Sie einen Flow erstellen können. Mit dem neu hinzugefügten Auslöser können Sie einen Schwellenwert für ein Segment definieren. Sie können beispielsweise eine Benachrichtigung erstellen, die gesendet wird, wenn der definierte Schwellenwert überschritten wird.    
  Weitere Informationen finden Sie unter [Power Automate-Connector](export-power-automate.md).

- **Unterstützung für mehrere Mandanten für benutzerdefinierte Modelle**

  Konfigurieren Sie Workflows für benutzerdefinierte Modelle mit einem Webdienst eines anderen Azure Maschinelles Lernen-Mandanten. Sie können sich beim Erstellen eines neuen Workflows für benutzerdefinierte Modelle beim Azure Machine Learning Mandant anmelden. Diese Funktion ist eine Ergänzung zu der vorhandenen Funktion zur Integration in Ihren eigenen benutzerdefinierten Azure Machine Learning Webdienst.    
  Weitere Informationen finden Sie unter [Benutzerdefinierte Machine Learning Modelle](custom-models.md).

#### <a name="segments"></a>Segmente

- **Automatisierung von Entitätspfaden**

  Wenn Sie ein Segment erstellen, müssen Sie den Pfad der Entitäten definieren. Diese Funktion macht einen ersten Schritt zur Automatisierung der Entitätspfaddefinition, damit Sie sich auf die Segmentierungskriterien konzentrieren können, die Sie berücksichtigen.    
  Wenn die Entität, nach der Sie Ihre Kunden segmentieren möchten, in direktem Zusammenhang mit der einheitlichen Kundenentität steht, müssen Sie den Entitätspfad nicht mehr definieren. Wenn es jedoch mehr als einen möglichen Entitätspfad gibt, müssen Sie ihn dennoch manuell definieren.

- **Aktionen für mehrere Segmente**
  
  Benutzer können mehrere Segmente auswählen und mit einem einzigen Klick Aktionen ausführen, z. B. das Aktualisieren der Segmente.    

- **Aktualisieren von Segmenten**

  Benutzer können ein einzelnes Segment aktualisieren oder nur die Segmente auswählen, die sie aktualisieren möchten.    

  
- **Verbesserungen an zusammengesetzten Segmenten**

  Benutzer können Segmente erstellen, bearbeiten und löschen, die auf anderen Segmenten basieren. Zum Beispiel ein Segment, das auf einem anderen Segment aufgebaut ist, das auf einem dritten Segment aufgebaut wurde.    

- **Seite mit Segmentliste**

  Das neue Design der Segmentseite verwendet ein Listenformat, mit dem Sie mehrere Segmente gleichzeitig anzeigen können. Ein Suchfeld wird hinzugefügt, um Segmente schnell zu finden. Benutzer können jetzt Aktionen wie das gleichzeitige Herunterladen oder Löschen auf mehrere Segmente anwenden. Ein neues Trenderlebnis wird eingeführt, um signifikante Änderungen an Segmenten schnell zu erkennen.    
  Weitere Informationen finden Sie unter [Erstellen und Verwalten von Segmenten](segments.md).

#### <a name="system-administration"></a>Systemadministrator

- **Customer Insights verfügbar in Microsoft Dynamics 365 Online Government**

  Mit immer mehr Kanälen für Interaktionen werden Bürgerdaten über unzählige Systeme verteilt, was zu isolierten Daten und einer fragmentierten Ansicht von Informationen über Bürgerinteraktionen führt. Ohne eine vollständige Übersicht über die kanalübergreifenden Interaktionen der einzelnen Bürger ist es für Regierungen unmöglich, in großem Maßstab zu modernisieren. Microsoft ist bestrebt, die Technologiebedürfnisse der Regierung zu unterstützen, um den Erwartungen der Bürger nach konsistenten und reaktionsschnellen Erfahrungen gerecht zu werden.    
  Mit 2020 Release Wave 1, wird Dynamics 365 Customer Insights für die Government Community Cloud (GCC) verfügbar sein, eine Umgebung, die den höheren Compliance-Anforderungen der US-Regierungsbehörden gerecht wird. Agenturen erhalten eine einheitliche Sicht auf die Bürger und verwenden vorgefertigte KI, um Erkenntnisse abzuleiten, die die Interaktion verbessern, Mitarbeiter befähigen und Communities transformieren. Gleichzeitig wird die IT-Komplexität verringert und die Compliance- und Sicherheitsstandards der USA eingehalten. Dynamics 365 Government erfüllt die anspruchsvollen Anforderungen des US-amerikanischen Federal Risk and Authorization Management-Programms (FedRAMP) und ermöglicht es den US-Bundesbehörden, von den Kosteneinsparungen und der strengen Sicherheit der Microsoft Cloud zu profitieren.

## <a name="april-2020-updates"></a>Update April 2020

Die Updates im April 2020 beinhalten verschiedene Funktionen, Leistungsverbesserungen und Fehlerbehebungen.

### <a name="new-and-updated-features-in-april-2020"></a>Neue und aktualisierte Funktionen im April 2020

#### <a name="activities"></a>Aktivitäten

- **Ordnen Sie die Aktivitätsentität dem Standardaktivitätstyp zu**
  
  Die Konfiguration und Speicherung von Aktivitäten basiert derzeit auf einem statischen Entwurf, um sie in einer Zeitleiste anzuzeigen. Die semantische Bedeutung von Aktivitäten, die in KI-Modellen für mehrere Anwendungsfälle geeignet ist, wird derzeit nicht vollständig genutzt. Wir planen, die Aktivitätszeitleiste dynamischer zu gestalten, basierend auf dem Aktivitätstyp und einem besseren semantischen Verständnis der Aktivitäten. Diese Funktion zielt darauf ab, den Aktivitätstyp zu identifizieren, der im Common Data Model für jede aufgenommene Aktivität definiert ist.
  Weitere Informationen finden Sie unter [Kundenaktivitäten](activities.md).

#### <a name="data-ingestion"></a>Dateneinbindung

- **Datenerfassung in Echtzeit: Aktivitäten**
  
  Die Datenerfassung in Echtzeit stellt Daten sofort für den Verbrauch bereit, bis die nachfolgende geplante Aktualisierung diese Daten aus der Datenquelle zieht.    
  Weitere Informationen finden Sie unter [Echtzeit-Dateneingabe](real-time-data-ingestion.md).

- **Verbesserungen bei der Datenaufbereitung**
  
  Erfahren Sie mehr über die in einer Entität aufgenommenen Daten. Mit der Datenzusammenfassung können Sie die Datenqualitätsmerkmale verstehen, die dazu beitragen können, geeignete Maßnahmen zu ergreifen.    
  Weitere Informationen finden Sie unter [Entitätsdaten erkunden](entities.md#exploring-a-specific-entitys-data).

- **Nehmen Sie Analysedaten von Dynamics 365 mit Common Data Service** auf
  
  Common Data Service ist als Möglichkeit zum Erstellen von Datenquellen verfügbar. Bestehende Dynamics 365-Kunden können analytische Entitäten von Common Data Service in Customer Insights aufnehmen. Eine einzige Datenquelle kann gleichzeitig denselben Common Data Service-verwalteten Lake in einer Customer Insights Umgebung nutzen.    
  Weitere Informationen finden Sie unter [Verbindung zu Daten in einem Common Data Service verwalteten Data Lake](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Erweiterbarkeit

- **Exportieren nach LiveRamp**

  Aktivieren Sie Ihre Daten in LiveRamp ®, um eine Verbindung mit über 500 Plattformen in digitalen, sozialen und TV-Ökosystemen herzustellen. Nutzen Sie Ihre Daten in LiveRamp, um Werbekampagnen auszurichten, zu unterdrücken und zu personalisieren.    
  Weitere Informationen finden Sie unter [Live Ramp&reg; Connector](export-liveramp.md).

- **Add-In für Customer Insights-Teams**
  
  Der Bot bietet Suchfunktionen für einheitliche Kundenprofile. Es wird eine Karte mit bis zu 15 Feldern aus dem resultierenden Kundenprofil angezeigt. Mehrere Übereinstimmungen geben eine Liste mit Ergebnissen zurück, in der Sie ein Profil auswählen können.    
  Weitere Informationen finden Sie unter [Teams Bot für Customer Insights](export-teams-bot.md).

#### <a name="measures"></a>Kennzahlen

- **Maßnahmdn-Listenseite**
  
  Zu den Verbesserungen auf der Seite Maßnahmen gehört die Unterstützung von Aktionen für eine einzelne Maßnahme und für mehrere Maßnahmen gleichzeitig. Darüber hinaus finden Sie ein Suchfeld, in dem Sie Maßnahmen schnell finden und verfolgen können.    
  Weitere Informationen finden Sie unter [Erstellen und Verwalten von Segmenten](segments.md).

- **Verbesserungen an zusammengesetzten Maßnahmen**
  
  Benutzer können Maßnahmen erstellen, bearbeiten und löschen, die auf anderen Maßnahmen. Zum Beispiel eine Maßnahmen, die auf einer anderen Maßnahmen aufgebaut ist, die auf einer dritten Maßnahmen aufgebaut wurde.

#### <a name="segments"></a>Segmente

- **Weitere Operator**
  
  Der In-Set-Operator ermöglicht Kunden die Segmentierung nach mehreren möglichen Zeichenfolgenwerten. Bevor dieser Operator hinzugefügt wurde, mussten Sie solche Segmente mit mehreren ODER-Bedingungen erstellen. Mit dem Operator In-Set können Sie dies mit einer einzigen Bedingung tun.    
  Weitere Informationen finden Sie unter [Erstellen und Verwalten von Segmenten](segments.md).

#### <a name="system-administration"></a>Systemadministrator

- **Kopieren Sie die Konfigurationseinstellungen in eine neue Umgebung**
  
  Kopieren Sie Ihre Konfiguration von einer Umgebung in eine andere. Während Sie eine neue Umgebung erstellen, können Sie eine vorhandene Umgebung auswählen, aus der Sie die Konfiguration kopieren möchten. Wir unterstützen derzeit Datenquellen, Datenvereinigung, Beziehungen, zu kopierende Kennzahlen und Segmente. Anmeldeinformationen und tatsächliche Daten von Datenquelle werden nicht kopiert.    
  Weitere Informationen finden Sie unter [Umgebungen verwalten](manage-environments.md).
