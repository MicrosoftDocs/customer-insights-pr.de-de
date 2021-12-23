---
title: Neue und kommende Funktionen
description: Informationen über neue Funktionen, Verbesserungen und Fehlerbehebungen.
ms.date: 12/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 346ef93e8471580b782618550ca4eb71b3f3c921
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884261"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Was ist neu an den Funktionalitäten der Zielgruppen-Insights von Dynamics 365 Customer Insights?

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Wir freuen uns, unsere neuesten Updates bekannt zu geben! In diesem Artikel werden Funktionen für die öffentliche Vorschau, Verbesserungen der allgemeinen Verfügbarkeit und Funktionsupdates zusammengefasst. Um die langfristig geplanten Funktionen zu sehen, werfen Sie einen Blick auf die [Dynamics 365 und Power Platform Freigabe-Pläne](/dynamics365/release-plans/).

Wir führen Updates nach Region durch. So können bestimmte Regionen Merkmale vor anderen sehen. Sofern nicht anders angegeben, müssen Sie keine Maßnahmen ergreifen, und wir aktualisieren die App automatisch ohne Ausfallzeiten.

> [!TIP]
> Zum Senden und Abstimmen zu gewünschten Funktionen und Vorschläge zum Produkt, navigieren Sie zu [Dynamics 365 Anwendungs-Ideen Portal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="november-2021-updates"></a>Aktualisierungen im November 2021

Die Updates im November 2021 beinhalten neue Funktionen, Leistungssteigerungen und Fehlerbehebungen.

### <a name="segment-membership-now-available-in-dataverse"></a>Jetzt in Dataverse verfügbare Segment-Mitgliedschaft

Informationen zur Segmentmitgliedschaft für Kundenprofile sind jetzt zusammen mit den Kundenprofilen und Erkenntnissen in Dataverse verfügbar. Dynamics 365-Aktions-Apps und modellgesteuerte Apps können diese Daten verwenden, um nach Segmentmitgliedschaftsdetails für einen bestimmten Kunden zu suchen.

### <a name="activities-support-contact-level-details-for-business-accounts"></a>Aktivitäten unterstützen Details auf Kontaktebene für Geschäftskonten

Sie können jetzt Aktivitäten für Kontakte auf den Aktivitätszeitskalen Ihres Geschäftskontos konfigurieren, anzeigen und filtern, um besser zu verstehen, welche Kontokontakte an bestimmten Aktivitäten teilgenommen haben.

## <a name="october-2021-updates"></a>Oktober 2021 Aktualisierungen

Die Updates im Oktober 2021 beinhalten neue Funktionen, Leistungssteigerungen und Fehlerbehebungen.

### <a name="b-to-b"></a>B2B

Ab Oktober 2021 können Sie in Customer Insights mit Geschäftskonten und den dazugehörigen Kontakten arbeiten. Zuvor war die App hauptsächlich auf einzelne Verbraucher zugeschnitten. Mehrere Funktionsbereiche wurden aktualisiert, um B2B-Szenarien zusätzlich zu einem neuen Umgebungstyp zu unterstützen. Eine Übersicht über unterstützte B2B-Funktionen finden Sie unter [Mit Geschäftskonten in Zielgruppenerkenntnissen arbeiten](work-with-business-accounts.md).

In den folgenden Abschnitten werden einige der Schlüsselbereiche hervorgehoben, die angepasst wurden, um Geschäftskonten und Privatkunden zu unterstützen.

#### <a name="export-segments-based-on-business-accounts"></a>Segmente basierend auf Geschäftskonten exportieren

Alle Segmentexporte in Zielgruppenerkenntnissen sind im Kontext von Geschäftskonten verfügbar. Die meisten Segmentexporte erfordern zusätzliche Konfigurations- und [Kontaktinformationen](segment-builder.md#create-a-new-segment), die in den zugrunde liegenden Segmenten projiziert werden, um für Geschäftskonten gültig zu sein. Weitere Informationen finden Sie unter [Segmente exportieren](export-destinations.md#export-segments).

#### <a name="use-the-linkedin-ads-export-with-business-accounts"></a>LinkedIn Ads-Export mit Geschäftskonten verwenden

Der LinkedIn Ads-Export steht jetzt für das Kontakt- und Unternehmens-Targeting im Kontext von Geschäftskonten zur Verfügung. Wenn Sie das Unternehmens-Targeting als Hauptfokus des LinkedIn-Exports auswählen, können Sie Segmente exportieren, die auf Geschäftskonten basieren, ohne Kontaktinformationen projizieren zu müssen. Weitere Informationen finden Sie in den Dokumentationen zum [LinkedIn Ads-Export](export-linkedin-ads.md) und dem Unterschied zwischen [Kontakt-Targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) und [Unternehmens-Targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting). 

#### <a name="create-measures-based-on-business-accounts-and-their-hierarchy"></a>Kennzahlen basierend auf Geschäftskonten und deren Hierarchie erstellen

Mit dem Kennzahlen-Builder können Sie Kennzahlen rund um Geschäftskonten erstellen und optional die Hierarchieinformationen verwenden. Hierarchieinformationen werden verwendet, um eine Kennzahlberechnung für ein Konto und alle zugehörigen Unterkonten zusammenzufassen. Sie können beispielsweise Kennzahlen wie den Gesamtumsatz für jede Gruppe von Geschäftskonten erstellen, die durch ihre Hierarchie identifiziert werden. Weitere Informationen finden Sie unter [Definieren und Verwalten von Kennzahlen](measures.md).

#### <a name="create-segments-based-on-business-accounts-and-their-hierarchy"></a>Segmente basierend auf Geschäftskonten und deren Hierarchie erstellen

Mit dem Segment-Builder können Sie Segmente von Geschäftkonten erstellen, die optional Kontaktinformationen für jedes Konto in einem Segment enthalten. Wenn Sie eine Kontenhierarchie eingerichtet haben, können Sie Informationen zur Kontenhierarchie bei der Segmenterstellung verwenden. Weitere Informationen finden Sie unter [Eine neues Segment erstellen](segment-builder.md#create-a-new-segment).

#### <a name="retain-your-business-accounts-with-deep-insights-to-their-churn-tendency"></a>Geschäftskonten mit tiefen Einblicken in ihre Abwanderungstendenz beibehalten

Das Vorhersagemodell zur Kundenabwanderung unterstützt jetzt auch Geschäftskonten. Sie können das Abwanderungsrisiko nicht nur für ein Konto bewerten, sondern auch für eine Kombination aus einem Konto und einer Produkt- oder Servicekategorie, die sie bei Ihnen kaufen. Dieser Zusatz hilft Ihnen zu verstehen, ob es wahrscheinlicher ist, dass ein Konto bei Ihnen im Allgemeinen oder nur für eine bestimmte Kategorie von Waren oder Services nicht mehr kauft. Um Sie bei der Verwendung dieses KI-Modells weiter zu unterstützen, werden auch Gründe aufgeführt, warum ein Konto wahrscheinlich abwandert. Weitere Informationen finden Sie unter [Transaktionsabwanderungs-Vorhersage (Vorschau)](predict-transactional-churn.md).

#### <a name="see-contacts-of-a-business-account-in-customer-view"></a>Kontakte eines Geschäftskontos in der Kundenansicht anzeigen

Wenn Geschäftskonten verwandten Konten zugeordnet sind, zeigt die Customer Insights-App diese verknüpften Kontakte als Teil der Kundendetailansicht an. Weitere Informationen finden Sie unter [Kundenprofile](customer-profiles.md).


## <a name="september-2021-updates"></a>Aktualisierungen September 2021

Die Updates im September 2021 beinhalten neue Funktionen, Leistungssteigerungen und Fehlerbehebungen.

### <a name="activities"></a>Aktivitäten

- **Verbesserungen der Aktivitätszeitachse** Wir haben die Filter für die Aktivitätszeitleiste auf Kundenprofilen erweitert. Darüber hinaus können Sie den neuen Filterbereich verwenden, um nach Aktivitätstyp und Datum zu filtern. Datumsangaben können nach verschiedenen Bedingungen gefiltert werden. Weitere Informationen finden Sie unter [Aktivitätszeitachsen in Kundenprofilen anzeigen](activities.md#view-activity-timelines-on-customer-profiles).

### <a name="relationships"></a>Beziehungen

- **Unterstützung von Multi-Hop-Beziehungen** Verwenden Sie Multi-Hop Beziehungen, wenn Sie Aktivitäten konfigurieren und Beziehungen zwischen Entitäten definieren. Multi-Hop Beziehungen verwendet eine Zwischenentität, um zwei Entitäten zu verbinden. Beim Konfigurieren einer Aktivität können Sie eine Multi-Hop-Beziehung verwenden, um Ihre Aktivitätsentität mit einer Zwischenentität und dann mit einer Kundenentität zu verbinden. Sie können Multi-Hop Beziehungen mit Multi-Pfad Beziehungen kombinieren. Weitere Informationen finden Sie im Abschnitt [Multi-Hop Beziehungen](relationships.md#multi-hop-relationship).

- **Unterstützung von Multi-Pfad-Beziehungen** Verwenden Sie Multi-Pfad Beziehungen, wenn Sie Aktivitäten konfigurieren und Beziehungen zwischen Entitäten definieren. Multi-Pfad Beziehungen verbindet eine Quellentität mit mehr als einer Entität. Beim Konfigurieren einer Aktivität können Sie eine Multi-Pfad-Beziehung verwenden, um Ihre Aktivitätsentität mit einer Zwischenentität und dann mit einer Kundenentität zu verbinden. Sie können Multi-Pfad Beziehungen mit Multi-Hop Beziehungen kombinieren. Weitere Informationen finden Sie im Abschnitt [Multi-Pfad Beziehungen](relationships.md#multi-path-relationship).

## <a name="august-2021-updates"></a>Aktualisierungen August 2021

Die Updates im Juli und August 2021 beinhalten eine neue Funktion, Leistungssteigerungen und Fehlerbehebungen.

### <a name="extensibility"></a>Erweiterbarkeit

- **Segmente nach Klaviyo exportieren** Wir haben unsere [Exportziele ausgeweitet, sodass sie jetzt auch Klaviyo umfassen](export-klaviyo.md). Sie können Segmente jetzt exportieren, um Kampagnen zu generieren, E-Mail-Marketing auszuführen und mit spezifischen Kundengruppen mit Klaviyo zu arbeiten. 


## <a name="june-2021-updates"></a>Updates Juni 2021

Die Updates im Juni 2021 enthalten mehrere Funktionen, Leistungsverbesserungen und Fehlerbehebungen.

### <a name="data-ingestion"></a>Dateneinbindung

- **Verbesserte Aktualisierungen des Datenvereinheitlichungsfortschritts** Sie sehen jetzt detailliertere, verbesserte dynamische Statusaktualisierungen in den Schritten zum [Datenvereinheitlichungsprozess](data-unification.md). Mit dieser Funktion können Sie den detaillierten Fortschritt verfolgen, um den Prozessflow zu verstehen und Maßnahmen zu ergreifen, wenn ein Schritt Ihre Aufmerksamkeit erfordert.

### <a name="extensibility"></a>Erweiterbarkeit

- **Exportieren von Segmenten und anderen Daten in die Salesforce Marketing Cloud** Wir haben unsere Exportziele ausgeweitet, sodass sie jetzt die [Salesforce Marketing Cloud](export-salesforce.md) miteinschließen. Sie können jetzt Segmente und andere Datentypen über einen Marken-SFTP-Export in die Salesforce Marketing Cloud exportieren. Der Datenimport kann in Salesforce vollständig automatisiert und zur Erstellung effektiverer Marketingkampagnen verwendet werden.  
 
- **Segmente nach ActiveCampaign exportieren** Wir haben unsere Exportziele ausgeweitet, sodass sie jetzt auch [Aktive Kampagne](export-active-campaign.md) umfassen. Sie können Segmente jetzt exportieren, um Kampagnen zu generieren, E-Mail-Marketing auszuführen und mit spezifischen Kundengruppen in ActiveCampaign arbeiten.
 
- **Segmente nach Sendinblue exportieren** Wir haben unsere Exportziele ausgeweitet, sodass sie jetzt auch [Sendinblue](export-sendinblue.md) umfassen. Sie können Segmente jetzt exportieren, um Kampagnen zu generieren, E-Mail-Marketing auszuführen und mit spezifischen Kundengruppen mit Sendinblue arbeiten.
 
### <a name="ux-updates"></a>UX-Updates 

- **Neue und verbesserte Kundenseite und Profildetailseite** Wir haben die Kundenseite und die Profildetailseiten zur Verbesserung der Benutzererfahrung und Leistung neu gestaltet. Mit diesen Änderungen können Sie Kunden anzeigen, sortieren, suchen und filtern. Filter werden jetzt in der URL dargestellt, um die Suchergebnisse nahtlos mit anderen Benutzern zu teilen. Suchergebnisse können auch als Segment gespeichert werden.    
  Die Detailseite für Kundenprofile gruppiert Daten jetzt in verschiedene Unterabschnitte wie demografische Daten, IDs und andere Profilattribute, um die Lesbarkeit zu verbessern. Andere Abschnitte auf der Profildetailseite sind jetzt interaktiver. Zum Beispiel ermöglicht der Abschnitt „Aktivitäten“ jetzt das Filtern und Sortieren.


## <a name="may-2021-updates"></a>Update Mai 2021

Die Updates im Mai 2021 umfassen verschiedene Funktionen, Leistungsverbesserungen und Fehlerkorrekturen.

### <a name="data-ingestion"></a>Dateneinbindung

- **Anzeigen oder Ändern von Metadaten oder Entitätsdefinitionen beim Anhängen von Daten aus Ihrem Azure Data Lake Storage** – Sie können jetzt Metadaten oder Entitätsdefinitionen in Zielgruppenerkenntnissen anzeigen und bearbeiten, wenn Sie Daten aus einem Common Data Model-Ordner in Ihrem Azure Data Lake Storage anhängen. Diese Funktion bietet Echtzeit-Feedback, Modellprüfung und Fehlerüberprüfung. Sie können sowohl model.json als auch manifest.json nahtlos bearbeiten.

### <a name="extensibility"></a>Erweiterbarkeit

- **Verbesserte Segmentexporte, benutzerdefinierter Zeitplan und Duplizierung** – Sie können jetzt [alle Exporte für ein bestimmtes Segment](export-destinations.md#view-exports-and-export-details) in einer Liste anzeigen. Diese neue Ansicht hilft dabei, die Verwendung eines bestimmten Segments zu verwalten und bestehende Exporte anzupassen oder neue Exporte zu erstellen.    
  Sie können [benutzerdefinierte Aktualisierungszeitpläne](export-destinations.md#schedule-and-run-exports) für einzelne Exporte oder mehrere Exporte gleichzeitig definieren. Bisher wurden alle Exporte bei jeder Systemaktualisierung ausgeführt.    
  Anstatt einen neuen Export von Grund auf neu zu erstellen, können Sie auf der Grundlage eines bestehenden Exports damit beginnen, um Zeit zu sparen.

- **Exportieren von Segmenten nach Microsoft Advertising** – Wir haben unsere Exportziele um Microsoft Advertising erweitert. Erstellen Sie Zielgruppen in Microsoft Advertising mit den Daten Ihres vereinheitlichten Kundenprofils und verwenden Sie diese Zielgruppen für Ihre Advertising-Kampagnen. Weitere Informationen finden Sie unter [Exportieren von Segmenten nach Microsoft Advertising](export-microsoft-advertising.md).

- **Exportieren von Segmenten nach LinkedIn Ads** – Wir haben unsere Exportziele um LinkedIn Ads erweitert und ermöglichen Ihnen dadurch die Nutzung von Contact Targeting sowie Company Targeting über LinkedIn, indem Sie Ihre vereinheitlichten Kundenprofildaten exportieren. Weitere Informationen finden Sie unter [Exportieren von Segmenten nach LinkedIn Ads](export-linkedin-ads.md).


- **Exportieren von Segmenten nach Omnisend** – Wir haben unsere Exportziele um Omnisend erweitert. Verwenden Sie die in Zielgruppenerkenntnissen erstellten Segmente, um Kampagnen zu generieren, E-Mail-Marketing bereitzustellen und spezifische Kundengruppen mit Omnisend zu nutzen. Weitere Informationen finden Sie unter [Exportieren von Segmenten nach Omnisend](export-omnisend.md).

### <a name="predictions"></a>Vorhersagen

- **Eingabedaten-Nutzungsbericht** – Der Eingabedaten-Nutzungsbericht bietet eine konsolidierte Ansicht der Fehler und Warnungen, die Ihre sofort einsatzbereiten Vorhersagen generieren. Er gibt auch Empfehlungen zur Verbesserung der Modellleistung.    
  Der Bericht ist verfügbar, nachdem ein Modell seinen Trainingsprozess abgeschlossen hat. Er wird für jedes Modell separat erstellt, unabhängig davon, ob es erfolgreich abgeschlossen wurde oder nicht.
  Derzeit ist diese Funktion nur für das Abwanderungsmodell für Transaktionen verfügbar. Weitere Informationen finden Sie unter [Eingabedaten-Nutzungsbericht](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Beziehungen

- **Beziehungsvisualisierer** – Die Beziehungsvisualisierungsansicht ermöglicht es Ihnen, alle vorhandenen Beziehungen zwischen Entitäten und ihrer Kardinalität anzuzeigen. Beziehungen sind jetzt in Gruppen organisiert: vom Benutzer erstellte, System- und geerbte Beziehungen. Sie können eine Ansicht auch als Bild exportieren. Weitere Informationen finden Sie unter [Anzeigen von Beziehungen](relationships.md#view-relationships). 

## <a name="april-2021-updates"></a>Update April 2021

Die Updates im April 2021 umfassen verschiedene Funktionen, Leistungsverbesserungen und Fehlerkorrekturen.

### <a name="data-unification"></a>Datenvereinigung
 
- **Verbesserte Zusammenführungserfahrung für die Datenvereinigung**    
  
   Wir haben jetzt eine verbesserte Benutzererfahrung bei der Zusammenführungskonfiguration des Datenvereinigungsprozesses. Die Änderungen umfassen die intuitive Reihenfolge der zusammengeführten Felder und detaillierte Statistiken zu kombinierten und Singleton-Feldern.

- **Entität ordnet alle Quelldatensätze neu an und konfiguriert sie in der Kundenentität**  
      
   Sie können jetzt Entitäten im Datenvereinigungsprozess neu anordnen und aus einem vorhandenen Zusammenführungsplan entfernen. Es bietet Flexibilität, um die Entitäten im Anpassungs-Prozess entsprechend den Geschäftsanforderungen neu zu ordnen. Zusätzlich aktivieren wir die Einbeziehung aller nicht übereinstimmenden Datensätze in die endgültige *Kundenentität*, mit der sie ihre Kundenprofil DataSet-Definition bestimmen können.

### <a name="enrichments"></a>Anreicherungen

 - **Neue Bereicherung: Erweiterte Adressen**    
  
   Wir freuen uns, eine neue Anreicherung einzuführen, um Adressen in Ihren Kundendaten zu verbessern. Adressen in Ihren Daten können unstrukturiert, unvollständig oder falsch sein. Diese Funktion verwendet die Modelle von Microsoft, um Ihre Adressen zu normalisieren und im Common Data Model-Format anzureichern, um eine bessere Genauigkeit und bessere Einblicke zu erzielen.
 
   Weitere Informationen finden Sie unter [Anreicherung von Kundenprofilen mit erweiterten Adressen](enrichment-enhanced-addresses.md).

- **Geführte Konfigurationserfahrung für Anreicherungen**    
  
   Wir haben die Konfigurationserfahrung für Anreicherungen mit einer einfachen, geführten Erfahrung überarbeitet. Sie haben jetzt einen klaren schrittweisen Prozess zum Erstellen und Bearbeiten von Anreicherungen.
 
   Darüber hinaus haben wir die Konfiguration von Verbindungen für Anreicherungen von Drittanbietern getrennt, damit dieselbe Verbindung von mehreren Anreicherungen verwendet werden kann. Nur Administratoren können neue Verbindungen konfigurieren, aber die erstellten Verbindungen stehen sowohl Administratoren als auch Mitwirkenden immer zur Verfügung.    

   Weitere Informationen finden Sie unter [Verbindungs-Überblick](connections.md).

- **Mehrfachanreicherungen des gleichen Typs**    
  
   Wir ermöglichen Benutzern jetzt, mehrere Anreicherungen desselben Anreicherungstyps zu erstellen und zu verwalten. Beispielsweise können Sie jetzt zwei separate Adressanreicherungen erstellen, um zwei verschiedene Kundensegmente anzureichern. Es gelten Beschränkungen für die Anzahl der Anreicherungen desselben Typs, die je nach Anreicherungstyp variieren können.
  
   Weitere Informationen finden Sie unter [Anreicherung für Kundenprofile](enrichment-hub.md).

## <a name="march-2021-updates"></a>Updates März 2021

Die Updates im März 2021 umfassen verschiedene Funktionen, Leistungsverbesserungen und Fehlerkorrekturen.

### <a name="activities"></a>Aktivitäten

- **Aktivitätsassistent und semantische Typen**

   Wir haben unsere Erfahrung mit Aktivitätszuordnungen verbessert und aktualisiert, um die Erstellung von Aktivitätszuordnungen zu steuern und zu vereinfachen. In dieser neuen Umgebung erhalten Benutzer eine geführte Erfahrung, um die einzelnen Schritte des Prozesses abzuschließen. Im Aktivitätszuordnungsschritt kann der Benutzer zusätzlich zur Auswahl aus vielen Aktivitätstypen festlegen, dass Daten semantisch für *Abonnement* und/oder *SalesOrderLine* nach Industriestandardschemata zugeordnet werden sollen, die für den nachgeschalteten Verbrauch verwendet werden können.   

   Weitere Informationen finden Sie unter [Kundenaktivitäten](activities.md).

### <a name="data-ingestion"></a>Dateneinbindung

- **Stellen Sie mit Power Platform-Dataflows und Gateways eine Verbindung zu lokalen Datenquellen her** – Wir freuen uns, die Vorschau von Power Platform-Dataflows und lokalen Verbindungen mit Gateways in Customer Insights mit einer zugeordneten Power Platform- oder Dataverse-Umgebung bekannt zu geben. Alle neuen Datenquellen, die in einer Customer Insights-Umgebung mit einem Dataverse-Umgebungslink erstellt wurden, werden standardmäßig auf Power Platform-Dataflows umgestellt, um lokale Datenkonnektivität und eine Vielzahl von Connectors und Transformationsfunktionen bereitzustellen.

### <a name="extensibility"></a>Erweiterbarkeit

- **Exporte in Verbindungen und Exporten organisiert** – Wir haben den Namen der **Ziele exportieren**-Seite in **Verbindungen** geändert und eine separate Seite für **Exporte** hinzugefügt. Im Rahmen dieses Updates werden vorhandene Exporte in Paare einer Verbindung und einen Export über diese Verbindung umgewandelt. Administratoren haben jetzt mehr Klarheit über ausgehende Daten auf der **Verbindungen**-Seite. Alle Benutzerrollen haben Zugriff auf die **Exporte**-Seite, aber nur Administratoren können festlegen, dass Mitwirkende bestimmte Exporte mit gemeinsam genutzten Verbindungen bearbeiten können.     
  Weitere Informationen finden Sie unter [Verbindungsübersicht](connections.md) und [Exportübersicht](export-destinations.md).

- **Exportieren Sie Segmente in Campaign Monitor** – Wir haben unsere Exportziele um Campaign Monitor erweitert. Sie können jetzt Segmente aus Customer Insights in Campaign Monitor-Listen exportieren und als Basis für Ihre Marketingkampagnen verwenden.    
   Weitere Informationen finden Sie unter [Exportieren nach Campaign Monitor](export-campaign-monitor.md).

- **Exportieren Sie Segmente in Constant Contact** – Wir haben unsere Exportziele um Constant Contact erweitert. Sie können jetzt Segmente aus Customer Insights in Constant Contact-Listen exportieren und als Basis für Ihre Marketingkampagnen verwenden.   
   Weitere Informationen finden Sie unter [Exportieren nach Constant Contact](export-constant-contact.md).

- **Exportieren Sie Segmente in RollWorks** – Wir haben unsere Exportziele um RollWorks erweitert. Sie können jetzt Segmente aus Customer Insights zu RollWorks-Zielgruppen exportieren und sie als Grundlage für Ihre B2B-Werbung verwenden.    
   Weitere Informationen finden Sie unter [Exportieren nach RollWorks](export-rollworks.md).

- **Exportieren Sie Segmente in Snapchat** – Wir haben unsere Exportziele um Snapchat erweitert. Sie können jetzt Segmente aus Customer Insights in Snapchat-Zielgruppen exportieren und als Basis für Ihre Kampagnen verwenden.     
   Weitere Informationen finden Sie unter [Exportieren nach Snapchat](export-snapchat.md).

### <a name="predictions"></a>Vorhersagen

- **Verwenden Sie Produktfilter in prädiktiven Produktempfehlungen** – Wir haben die Möglichkeit hinzugefügt, Produktfilter in unserem Produktempfehlungsmodell zu verwenden. Sie können jetzt ein Vorhersage erstellen, die nur eine Teilmenge Ihrer Produkte verwendet.    
   Weitere Informationen finden Sie unter [Produktfilter konfigurieren](predict-product-recommendation.md#configure-product-filters).

- **Erstellen Sie Segmente aus Modellvorhersagen** – Wir haben eine schnelle Möglichkeit zum Erstellen von Segmenten mit den Ergebnissen eines Vorhersage-Modells hinzugefügt. Auf der Modellergebnisseite können Sie ganz einfach ein neues Segment erstellen, indem Sie die neue **Segment erstellen**-Option auswählen.    
  Weitere Informationen finden Sie unter [Erstellen Sie ein Segment basierend auf einem Vorhersage-Modell](prediction-based-segment.md).

- **Erläuterungen zu Produktempfehlungen** – Wir haben Informationen hinzugefügt, in denen die Schlüsselfaktoren erläutert werden, die das KI-Modell zur Generierung von Produktempfehlungen gelernt hat, und inwieweit diese Faktoren zu den Produktempfehlungen beitragen. Diese Informationen werden dem Modellergebnisbildschirm hinzugefügt.    
   Weitere Informationen finden Sie unter [Überprüfen eines Vorhersagestatus und der Ergebnisse](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>Updates Februar 2021

Die Updates im Februar 2021 enthalten verschiedene Funktionen, Leistungsverbesserungen und Fehlerbehebungen.

#### <a name="extensibility"></a>Erweiterbarkeit

- **Segmente nach AdRoll exportieren**

  Wir haben unsere Exportziele um AdRoll erweitert. Sie können jetzt Segmente aus Customer Insights in AdRoll-Zielgruppen exportieren und als Basis für Ihre Werbung verwenden. Für weitere Informationen, siehe [Konnektor für AdRoll](export-adroll.md).

#### <a name="segments"></a>Segmente
 
- **Ein Segment duplizieren**
  
  Um ein neues Segment basierend auf einem vorhandenen zu erstellen, können Sie jetzt ein Segment duplizieren und das duplizierte Segment bearbeiten, um es weiter zu verfeinern. 

- **Fügen Sie einem Segment zusätzliche Attribute hinzu**

  Sie können jetzt Attribute in Ihre Segmentausgabe aufnehmen, auch wenn diese Attribute nicht Teil des Kundenprofils sind. Fügen Sie beispielsweise Abonnement-IDs in ein Segment ein, obwohl es Teil der Abonnemententität ist, die eine M: 1-Beziehung zur Kundenentität hat. Solange das Attribut zu einer Entität gehört, die sich auf die Kundenentität bezieht, können Sie diese Attribute jetzt einschließen.  

#### <a name="predictions"></a>Vorhersagen

- **Produktempfehlungsvorhersagen erstellen**

  Zu verstehen, was Kunden am Kauf interessiert sind, ist einer der ersten Schritte, die erforderlich sind, um den Geschäftsumsatz zu verbessern und die Kundenbindung durch Personalisierung und Engagement zu stärken. Das Bereitstellen von Empfehlungen für Produkte, die nicht auf die Interessen Ihres Kunden abgestimmt sind, kann zu einem Gefühl der Trennung zwischen dem Kunden und Ihrem Unternehmen führen und letztendlich das potenzielle Umsatz- und Erfahrungspotential für einen Kunden insgesamt begrenzen. 

  Mithilfe Ihrer eigenen Daten können Sie jetzt Vorhersagen darüber erstellen, welche Produkte Ihre Kunden voraussichtlich in Zukunft kaufen werden. Weitere Informationen finden Sie unter [Produktempfehlungsvorhersage](predict-product-recommendation.md).

#### <a name="system-administration"></a>Systemverwaltung

- **Die Kopierumgebung unterstützt mehr Arten von Datenquellen**

  Administratoren können Umgebungskonfigurationen in eine neue Umgebung in derselben Organisation kopieren. Diese Funktion erweitert die Funktionalität „Umgebung kopieren“ auf Fälle, in denen Datenquellen basierend auf einem von Microsoft Dataverse verwalteten Data Lake oder einem Common Data Model-Ordner verwendet werden.

## <a name="january-2021-updates"></a>Updates Januar 2021

Die Updates im Januar 2021 enthalten verschiedene Funktionen, Leistungsverbesserungen und Fehlerbehebungen.

#### <a name="extensibility"></a>Erweiterbarkeit

- **Erweiterte Funktionalität und verbesserte Leistung für den SFTP-Export** Sie können jetzt alle Ausgabeentitäten aus Customer Insights auf einen SFTP-Host exportieren. Bisher war der Export auf Segmenteinheiten beschränkt. Darüber hinaus ermöglicht die Leistung des SFTP-Exports je nach Leistung Ihres SFTP-Hosts mehr Datenvolumen in kürzerer Zeit.    
  Weitere Informationen finden Sie unter [Konnektor für SFTP (Vorschau)](export-sftp.md).  

#### <a name="segments"></a>Segmente

- **Maschinelles Lernen unterstützte vorgeschlagene Segmente, um die Metriken zu verbessern** Es gibt eine neue Möglichkeit, Segmente zu entdecken und zu erstellen. Das System verwendet ein KI-Modell, um Segmente vorzuschlagen, die dazu beitragen können, einen KPI (Kennzahl) zu verbessern, den Sie bereits verfolgen. Wir zeigen das Ausmaß des Einflusses von Attributen, die Sie auf eine Kennzahl oder ein anderes primäres Attribut auswählen. Diese Informationen helfen bei der Suche nach potenziellen Segmenten, die Chancen bieten.    
  Weitere Informationen finden Sie unter [Vorgeschlagene Segmente (Vorschau)](suggested-segments.md).

#### <a name="data-unification"></a>Datenvereinigung

- **Verbessertes Übereinstimmungserlebnis** Im Bereich der Datenvereinigung wurde die Übereinstimmungserfahrung aktualisiert. Hier können Sie die Übereinstimmungsregeln konfigurieren und anzeigen, einschließlich detaillierter Statistiken, um die Funktionsweise der Übereinstimmung weiter zu erläutern. Es gibt Optionen zum Deaktivieren einer Übereinstimmungsregel, sodass diese nicht mehr aktiv ist, während die Konfiguration beibehalten wird, Übereinstimmungsregeln per Drag & Drop verschoben werden und vieles mehr.
  Weitere Informationen finden Sie unter [Entitäten abgleichen](match-entities.md).

- **Die Deduplizierungsausgabe des Übereinstimmungsprozesses ist als Entität verfügbar** Die vom Übereinstimmungsprozess ausgegebenen Deduplizierungsprozesse werden jetzt zur weiteren Analyse in eine separate Entität geschrieben. Diese Entität besteht aus den Feldern, die im Deduplizierungsprozess verwendet werden, und dem Gewinnerdatensatz sowie den entsprechenden alternativen Datensätzen, die mit dem Gewinnerdatensatz zusammengeführt werden.
  Weitere Informationen finden Sie unter [Deduplizierungsausgabe als Entität](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Systemverwaltung

- **Daten nahtlos in Microsoft Dataverse teilen** Sie können jetzt die Ausgabe von Customer Insights in Microsoft Dataverse-Anwendungen mit dem Microsoft Dataverse Managed Data Lake teilen. Sobald Sie eine Dataverse-Umgebung zu Customer Insights zuordnen, erhalten Sie die Option, die Datenfreigabe zu aktivieren.
  Weitere Informationen finden Sie unter [Umgebungen verwalten](manage-environments.md).




[!INCLUDE[footer-include](../includes/footer-banner.md)]