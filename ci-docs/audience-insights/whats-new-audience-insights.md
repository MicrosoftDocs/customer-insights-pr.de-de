---
title: Neue und kommende Funktionen
description: Informationen über neue Funktionen, Verbesserungen und Fehlerbehebungen.
ms.date: 05/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: c66b37d6e4d6ed830238566fbc09934832892b34
ms.sourcegitcommit: 3f9981df97fa7b1f432a446d3f11936ea4cfbde5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "5988919"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Was ist neu an den Funktionalitäten der Zielgruppen-Insights von Dynamics 365 Customer Insights?

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Wir freuen uns, unsere neuesten Updates bekannt zu geben! In diesem Artikel werden Funktionen für die öffentliche Vorschau, Verbesserungen der allgemeinen Verfügbarkeit und Funktionsupdates zusammengefasst. Um die langfristig geplanten Funktionen zu sehen, werfen Sie einen Blick auf die [Dynamics 365 und Power Platform Freigabe-Pläne](/dynamics365/release-plans/).

Wir führen Updates nach Region durch. So können bestimmte Regionen Merkmale vor anderen sehen. Sofern nicht anders angegeben, müssen Sie keine Maßnahmen ergreifen, und wir aktualisieren die App automatisch ohne Ausfallzeiten.

> [!TIP]
> Zum Senden und Abstimmen zu gewünschten Funktionen und Vorschläge zum Produkt, navigieren Sie zu [Dynamics 365  Anwendungs-Ideen Portal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

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

- **Exportieren Sie Segmente in RollWorks** – Wir haben unsere Exportziele um RollWorks erweitert. Sie können jetzt Segmente aus Customer Insights in RollWorks-Zielgruppen exportieren und als Basis für Ihre B2B-Kampagnen verwenden.    
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

  Administratoren können Umgebungskonfigurationen in eine neue Umgebung in derselben Organisation kopieren. Diese Funktion erweitert die Kopierumgebungsfunktionalität für Fälle, in denen Datenquellen auf Common Data Service Data Lake basierenoder ein Common Data Model-Ordner verwendet wird.

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