---
title: Neuerungen in Dynamics 365 Customer Insights
description: Informationen über neue Funktionen, Verbesserungen und Fehlerbehebungen.
ms.date: 08/31/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 2a386d65a5e285d471e9cafc45f247e7b4ae23bb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609591"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Neuerungen in Dynamics 365 Customer Insights

Wir freuen uns, unsere neuesten Updates bekannt zu geben! In diesem Artikel werden Funktionen für die öffentliche Vorschau, Verbesserungen der allgemeinen Verfügbarkeit und Funktionsupdates zusammengefasst. Um die langfristig geplanten Funktionen zu sehen, werfen Sie einen Blick auf die [Dynamics 365 und Power Platform Freigabe-Pläne](/dynamics365/release-plans/).

Wir führen Updates nach Region durch. So können bestimmte Regionen Merkmale vor anderen sehen. Sofern nicht anders angegeben, müssen Sie keine Maßnahmen ergreifen, und wir aktualisieren die App automatisch ohne Ausfallzeiten.

> [!TIP]
> Zum Senden und Abstimmen zu gewünschten Funktionen und Vorschläge zum Produkt, navigieren Sie zu [Dynamics 365 Anwendungs-Ideen Portal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="august-2022-updates"></a>Aktualisierungen August 2022

Die Updates im August 2022 beinhalten neue Funktionen, Leistungssteigerungen und Fehlerbehebungen.

### <a name="contact-unification-in-b-to-b-environments"></a>Kontaktvereinheitlichung in B-to-B-Umgebungen

B-to-B-Umgebungen in Customer Insights unterstützen jetzt eine verbesserte Datenvereinheitlichung.

Sie können jetzt neben Konten auch Kontakte vereinheitlichen, um einen vollständigen Überblick über Ihre Geschäftskontakte zu erhalten. Einheitliche Kontakte sind mit einheitlichen Konten verknüpft und werden nun auf den Kundenkarten aufgeführt. 

Weitere Informationen finden Sie unter [Einheitliches Kontaktprofil erstellen](data-unification-contacts.md).

### <a name="create-and-export-of-segments-based-on-unified-contacts"></a>Erstellen und exportieren Sie Segmente basierend auf einheitlichen Kontakten

Dank der neuen Kontaktvereinheitlichung können Sie Kontaktsegmente anhand von Kriterien aus Kontakten, Konten oder beiden erstellen. Diese Segmente können zur Aktivierung in anderen Diensten exportiert werden.

Weitere Informationen finden Sie in [Überblick zu Exporte](export-destinations.md).

### <a name="deployment-regions-aligned-with-microsoft-dataverse"></a>Einsatzregionen ausgerichtet mit Microsoft Dataverse bereitstellen

Beim Erstellen einer neuen Customer Insights-Umgebung können Sie die Region auswählen, in der der Service bereitgestellt und gehostet werden soll. Wir haben die Regionsauswahl aktualisiert, um sie mit Microsoft Dataverse und der Power Platform auszurichten.

Sie können jetzt ganz einfach dieselbe Region wie Ihre vorhandene Microsoft Dataverse Umgebung oder Ihr Azure Data Lake Storage Konto auswählen (falls Sie diese Option wählen), vorbehaltlich der Verfügbarkeit von Customer Insights in dieser Region.

Weitere Informationen finden Sie unter [Erstellen Sie eine neue Umgebung](create-environment.md) und [Produktverfügbarkeit nach Region](https://dynamics.microsoft.com/availability-reports/).

## <a name="july-2022-updates"></a>Updates Juli 2022

Die Updates im Juli 2022 beinhalten neue Funktionen, Leistungssteigerungen und Fehlerbehebungen.

### <a name="export-to-moengage"></a>Exportieren nach MoEngage

Exportieren Sie Segmente einheitlicher Kundenprofile in MoEngage und verwenden Sie sie für E-Mail-Marketing in MoEngage.

Weitere Informationen finden Sie unter [Exportieren von Segmenten nach MoEngage](export-moengage.md).

### <a name="ssh-support-for-sftp-based-exports"></a>SSH-Unterstützung für SFTP-basierte Exporte

Wählen Sie aus, ob Sie sich über SSH oder Benutzername/Passwort für Verbindungen zu SFTP-Exportzielen authentifizieren möchten.

Weitere Informationen finden Sie unter [Exportieren von Daten an SFTP-Hosts](export-sftp.md).

### <a name="personalize-experiences-with-data-about-known-and-unknown-users"></a>Personalisieren Sie Erfahrungen mit Daten über bekannte und unbekannte Benutzer

Die Verwaltung von Kundendaten ist keine neue Herausforderung, aber es wird immer schwieriger, wenn Benutzer durch die verschiedenen digitalen Kanäle navigieren, die Marken anbieten. Ein Benutzer, der in einem Kanal bekannt (authentifiziert) ist, wird in einem anderen unbekannt (nicht authentifiziert), wenn er nicht angemeldet ist. Das Problem besteht häufig darin, dass nicht authentifizierte (unbekannte) Benutzer keine gemeinsame ID haben. Es kann verwendet werden, um aussagekräftige Profilattribute zuzuordnen und einheitliche Kundenprofile zu generieren. Customer Insights hilft bei der Lösung dieses Problems, indem Daten aus Tracking-Methoden auf Ihren Quellsystemen aufgenommen werden.

Weitere Informationen finden Sie unter [Personalisieren Sie Ihre Erfahrungen mit Daten über bekannte und unbekannte Benutzer](unknown-to-known.md).

## <a name="june-2022-updates"></a>Updates Juni 2022

Die Updates im Juni 2022 beinhalten neue Funktionen, Leistungssteigerungen und Fehlerbehebungen.

### <a name="updated-user-experience-for-data-sources-and-data-ingestion"></a>Aktualisierte Benutzererfahrung für Datenquellen und Datenaufnahme

Der Import von Daten aus einer Vielzahl von Datenquellen ist die Grundlage für die Konsolidierung Ihrer Kundendaten in Dynamics 365 Customer Insights. Wir haben die Benutzererfahrung für den Import und die Verbindung von Datenquellen überarbeitet. Dieses Update soll es Ihnen erleichtern, Daten in Customer Insights aufzunehmen.

Weitere Informationen finden Sie unter [Übersicht über Datenquellen](data-sources.md).

### <a name="export-to-inmobi"></a>Exportieren nach InMobi

InMobi hilft Marken, Verbraucher zu verstehen, zu identifizieren, anzusprechen und zu gewinnen. Sie können Segmente und andere Daten über Azure Blob Storage-Konten in den InMobi-Dienst exportieren.

Weitere Informationen finden Sie unter [Segmente nach InMobi exportieren (Vorschauversion)](export-inmobi.md)

### <a name="lockbox-support-in-customer-insights"></a>Lockbox-Unterstützung in Customer Insights

Kunden-Lockbox bietet eine Schnittstelle zum Überprüfen und Genehmigen (oder Ablehnen) von Datenzugriffsanfragen. Diese Anfragen treten auf, wenn Datenzugriff auf Kundendaten erforderlich ist, um einen Supportfall zu lösen.

Weitere Informationen unter [Sicherer Zugriff auf Kunddaten mit Kunden-Lockbox (Vorschauversion)](security-overview.md#securely-access-customer-data-with-customer-lockbox-preview).

### <a name="connect-to-your-data-using-azure-private-link"></a>Stellen Sie über Azure Private Link eine Verbindung zu Ihren Daten her

Mit Azure Private Link können Sie uns Customer Insights mit Ihrem Azure Data Lake Storage Konto über ein privates Endpunkt in Ihrem virtuellen Netzwerk verbinden. Für Daten in einem Speicherkonto, das nicht dem öffentlichen Internet ausgesetzt ist, ermöglicht Private Link die Verbindung mit diesem eingeschränkten Netzwerk.

Weitere Informationen finden Sie unter [Private Link in Customer Insights verwenden](security-overview.md#set-up-an-azure-private-link).

## <a name="may-2022-updates"></a>Update Mai 2022

Die Updates im Mai 2022 beinhalten neue Funktionen, Leistungssteigerungen und Fehlerbehebungen.

### <a name="updated-data-unification-experience"></a>Aktualisierte Erfahrung mit der Datenvereinheitlichung

 Mit der Datenvereinheitlichung können Sie ehemals unterschiedliche Datenquellen in einem einzigen Master-DataSet vereinen, das eine einheitliche Ansicht dieser Daten bietet. Daten können in einer einzelnen Entität oder mehreren Entitäten vereinheitlicht werden. Wählen Sie zuerst [Entitäten und Quellfelder aus](map-entities.md), [entfernen Sie doppelte Datensätze](remove-duplicates.md), legen Sie Regeln fest für [passenden Bedingungen](match-entities.md), und definieren Sie, welche [Felder in die einheitlichen Kundenprofile aufgenommen werden sollen](merge-entities.md).

Weitere Informationen finden Sie unter [Datenvereinheitlichung-Übersicht](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>Aktualisierte Homepage in Customer Insights

Die **Homepage** zeigt Anleitungen für den Konfigurationsprozess für Schlüsselfunktionen und bietet einen Überblick über Segmente, Kennzahlen und Anreicherungsdaten. Wir haben die Erfahrung aktualisiert, um relevantere Informationen auf einen Blick bereitzustellen.

Weitere Informationen finden Sie unter [Customer Insights erkunden](home.md).

### <a name="track-usage-of-a-segment"></a>Verfolgen Sie die Nutzung eines Segments

Sie können nun [die Nutzung eines Segments in Apps nachverfolgen](segments.md#track-usage-of-a-segment), die auf derselben Dataverse Organisation basieren, die mit Customer Insights verbunden ist. Für [Customer Insights-Segmente, die in Kundenkontaktverläufe von Dynamics 365 Marketing verwendet werden](/dynamics365/marketing/real-time-marketing-ci-profile) informiert Sie das System über die Nutzung dieses Segments.

### <a name="export-to-criteo"></a>Nach Criteo exportieren

Criteo ist eine Online-Plattform, die Benutzern hilft, digitale Werbung zu verwalten. Exportieren Sie Segmente von Unified Customer Profiles, um Kampagnen zu erstellen, E-Mail-Marketing zu betreiben und bestimmte Kundengruppen mit Criteo zu nutzen.

Weitere Informationen finden Sie unter [Segmente nach Criteo exportieren (Vorschauversion)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Verfeinerte Dokumentationsstruktur für die Umgebungserstellung

Wir haben die Hilfedokumente zur Erstellung und Verwaltung von Umgebungen in Customer Insights erneut durchgesehen. Die Artikel sind jetzt im Inhaltsverzeichnis unter dem Knoten Umgebungen gruppiert. Die neu strukturierten Artikel bieten mehr Anleitungen für die verschiedenen Möglichkeiten zum Einrichten von Umgebungen und haben eine klarere Struktur. Wenn Sie uns Feedback geben möchten, teilen Sie uns dies über die Steuerelemente am Ende der Hilfeartikel mit.

Weitere Informationen finden Sie unter [So geht es. Eine neue Umgebung erstellen](create-environment.md).

## <a name="april-2022-updates"></a>Update April 2022

Die Updates im April 2022 beinhalten neue Funktionen, Leistungssteigerungen und Fehlerbehebungen.

### <a name="dun--bradstreet-enrichment-preview"></a>Ergänzung um Dun&Bradstreet-Daten (Vorschauversion)

Dun & Bradstreet bietet kommerzielle Daten, Analysen und Erkenntnisse für Unternehmen. Sie ermöglicht es Kunden mit einheitlichen Kundenprofilen für Unternehmen, ihre Daten anzureichern. Die Anreicherung umfasst Attribute wie DUNS-Nummer, Größe der Firma, Standort, Branche und mehr.

Weitere Informationen finden Sie unter [Anreicherung von Firmenprofilen mit Dun & Bradstreet (Vorschauversion)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Definieren des Kennzahlentyps beim Erstellen einer neuen Kennzahl

Sie können jetzt zwischen Kennzahlen für einzelne Profile und Kennzahlen für Ihr gesamtes Unternehmen unterscheiden. Während Geschäftskennzahlen auf der Startseite von Customer Insights angezeigt werden, werden Kundenkennzahlen in den detaillierten Kundenansichten angezeigt.

Weitere Informationen finden Sie unter [Kennzahlen-Builder verwenden, um Kennzahlen von Grund auf neu zu erstellen](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Konsolidierung der Customer Insights-Dokumentation

Wir haben unsere Dokumentationsartikel überarbeitet und die Erwähnungen von Kundenbindungs- und Zielgruppenerkenntnisse-Funktionen entfernt. In Zukunft beziehen wir uns konsequent auf den Produktnamen Customer Insights, wenn wir über die Kernfunktionen der Anwendung schreiben. Diese Änderung führt auch zu einer erheblichen Umstrukturierung des Inhaltsverzeichnisses, der URL-Struktur und der Dateipfade im zugrunde liegenden Dokumentationsrepository. Alle Ihre Lesezeichen oder vorhandenen Links funktionieren weiterhin und leiten zu den aktualisierten URLs weiter.

Wenn Sie uns mitteilen möchten, wie Sie diese Änderung wahrnehmen oder ob etwas nicht wie erwartet funktioniert, teilen Sie uns dies mit, [indem Sie Feedback für diese Seite senden](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

## <a name="march-2022-updates"></a>Updates März 2022

Die Updates im März 2022 beinhalten neue Funktionen, Leistungssteigerungen und Fehlerbehebungen.

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec-Anreicherung (Vorschauversion)

LiveRamp bietet Identitätsauflösung und Konsolidierung von Kundendaten. Sie können persönliche Kennungen in Ihren Kundendaten dem AbiliTec-Identitätsdiagramm zuordnen und AbiliTec-IDs erhalten. Diese IDs können Sie dann zur besseren Vereinheitlichung Ihrer Kundendaten verwenden.

Weitere Informationen finden Sie unter [Kundenprofile mit Identitätsdaten von LiveRamp (Vorschauversion)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Organisieren Sie Segmente und Kennzahlen mit Tags und Filtern

Wenn Ihre Organisation viele Segmente oder Kennzahlen verwaltet, kann es manchmal schwierig sein, die richtige zu finden. Mit dieser neuen Funktion können Sie Listen mithilfe von Tags und Spalten organisieren. Es hilft, Daten schnell und einfach zu finden und die Ansichten anzupassen.

Weitere Informationen finden Sie unter [Mit Tags und Spalten arbeiten](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Datenfreigabe aktivieren mit Dataverse bei Verwendung Ihres eigenen Speicherkontos

Wenn Ihre Umgebung Azure Data Lake Storage verwendet, um Customer Insights-Daten zu speichern , benötigt der Datenaustausch mit Microsoft Dataverse eine zusätzliche Konfiguration.
Früher konnten Sie die Datenfreigabe nur mit Dataverse aktivieren, wenn Ihre Daten in unserem Managed Data Lake gespeichert wurden.

For more information, see [Aktivieren der Datenfreigabe für Dataverse über Ihre eigene Azure Data Lake Storage (Vorschauversion)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Neue Exportziele: Iterable und Braze

Wir bauen unser Ökosystem an Exportdestinationen mit neuen Verbindungen weiter aus. Sie können jetzt Segmente nach Iterable und Braze exportieren, um deren Aktivierungsdienste zu nutzen.

Weitere Informationen finden Sie unter [Segmente nach Iterable exportieren (Vorschauversion)](export-iterable.md) und [Segmente nach Braze exportieren (Vorschauversion)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Verbesserungen am Marketo- und Google Ads-Export

Sich ändernde APIs in verbundenen Diensten führen zu Updates, damit Konnektoren zuverlässig und reibungslos laufen. Wir haben einige Aktualisierungen für die Exporte in Marketo- und Google Ads-Dienste veröffentlicht:

- Google Ads: Die neue Version des Google Ads-Export-Connectors vereinfacht die Authentifizierung und ermöglicht Ihnen jetzt, automatisch neue Google Ads-Zielgruppen zu erstellen. 
- Marketo: Die neue Version des Marketo-Exportkonnektors bietet Unterstützung für die Marketo-ID, sodass Sie Datenduplizierung vermeiden, vorhandene Datensätze aktualisieren und neue Datensätze in Marketo erstellen können. 

## <a name="february-2022-updates"></a>Updates Februar 2022

Die Updates im Februar 2022 beinhalten neue Funktionen, Leistungssteigerungen und Fehlerbehebungen.

### <a name="general-availability-for-prediction-models"></a>Allgemeine Verfügbarkeit für Vorhersage-Modelle

Sofort einsatzbereite Vorhersage-Modelle, einschließlich **Abonnement-Churn**, **Transaktions-Churn** und **Customer Lifetime Value (CLV)** werden als Teil von Customer Insights allgemein verfügbar. 

Weitere Informationen finden Sie unter [Vorhersage-Übersicht](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Neu Datenquelle: Integration mit Azure Synapse Analytics (Vorschauversion)

Azure Synapse Analytics ist ein Analysedienst für Unternehmen, der Erkenntnisse über Data Warehouses und Big-Data-Systeme hinweg verkürzt.

Organisationen, die bereits Azure Synapse Analytics verwenden, kann diese Daten in Customer Insights aufnehmen. 

Weitere Informationen finden Sie unter [Verbindung zu Azure Synapse Datenquellen (Vorschauversion)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>LiveRamp-Anreicherung (Vorschauversion)

LiveRamp bietet Identitätsauflösung und Konsolidierung von Kundendaten. Sie können persönliche Kennungen in Ihren Kundendaten dem AbiliTec-Identitätsdiagramm zuordnen und AbiliTec-IDs erhalten. Diese IDs können Sie dann zur besseren Vereinheitlichung Ihrer Kundendaten verwenden.

Weitere Informationen finden Sie unter [Kundenprofile mit Identitätsdaten von LiveRamp (Vorschauversion)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Anreicherung für Datenquellen (Vorschauversion)

Verwenden Sie Daten aus Quellen wie Microsoft und anderen Partnern, um Ihre Kundendaten vor der Datenvereinheitlichung anzureichern. Datenquellen-Anreicherungen tragen zu einer höheren Datenvollständigkeit und -qualität bei, die dazu beitragen können, bessere Ergebnisse zu erzielen, sobald Sie Ihre Daten vereinheitlicht haben.

Weitere Informationen finden Sie unter [Anreicherungen für Datenquellen (Vorschauversion)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Besitzer der Umgebung ändern

Während mehrere Benutzer Administratorberechtigungen in Customer Insights haben können, ist nur ein Benutzer der Eigentümer einer Umgebung. Eine verbesserte Erfahrung ermöglicht es Ihnen, den Besitzer einer Umgebung zu ändern und den Besitz zu beanspruchen, wenn ein ehemaliger Besitzer die Organisation verlassen hat. 

Weitere Informationen finden Sie unter [Ändern Sie den Besitzer einer Umgebung](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Der Datenvorbereitungsprozess führt den Korruptionsgrund für beschädigte Datensätze auf

Die Datenvorbereitung zeigt jetzt den Grund für die Beschädigung für alle Felder mit beschädigten Daten an. Die Informationen werden zur einfachen Identifizierung auf individueller Datensatzebene bereitgestellt.

Weitere Informationen finden Sie unter [Korrupte Datenquellen](data-sources.md#corrupt-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Ende der Vorschau für Berichtsfunktionen in der Funktion für Bindungserkenntnisse

Die Vorschauversion von Dynamics 365 Customer Insights Interaktionserkenntnisse endete am 15. Februar 2022.  
Diese Änderung bedeutet, dass die Testversion von Customer Insights nicht mehr die Möglichkeit bietet, Trichter oder andere Berichtsfunktionen zu erstellen.

Wir laden Sie ein, die vielen anderen Funktionen von [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/), der Microsoft Kundendatenplattform (CDP), zu erkunden und zu bewerten.    
 
Für eine Übergangszeit haben bestehende Vorschauteilnehmer weiterhin Zugriff auf einige Vorschaufunktionen:

- Code abrufen, um eine Website oder mobile App zu instrumentieren 
- Ereignisse und Ereigniseigenschaften anzeigen 
- Einheitliche Profile mit erfassten und verfeinerten Ereignissen verbessern, um vom vollen Wert ihrer Kundendaten zu profitieren
  
Während der Übergangszeit werden erfasste Ereignisse weiterhin an den verbundenen Data Lake gestreamt. Sobald diese Funktion deaktiviert ist, wird der Datenaustausch gestoppt und es werden keine neuen Ereignisse mehr an den verbundenen Speicher gesendet.
Wenden Sie sich direkt an Ihr Microsoft-Kontoteam, wenn Sie Fragen zum Ende der Funktionsvorschau haben. Ihr Kontoteam wird Sie über bevorstehende Markteinführungen auf dem Laufenden halten. 

## <a name="january-2022-updates"></a>Updates Januar 2022

Die Updates im Januar 2022 beinhalten neue Funktionen, Leistungssteigerungen und Fehlerbehebungen.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Stimmungsanalyse Ihres Kundenfeedbacks

Customer Insights bietet eine neue KI-gestützte Funktion, um die Kundenstimmung zu synthetisieren und bestimmte Geschäftsaspekte als Möglichkeiten für gezielte Verbesserungen zu identifizieren. Durch die Analyse des schriftlichen Feedbacks Ihrer Kunden können Sie zu geringen Kosten genaue Erkenntnisse gewinnen. Stimmungsanalyse auf Basis von NLP-Modellen (Natural Language Processing), die zwei abgeleitete Erkenntnisse für jede Kunden-ID generieren. Eine Stimmungsbewertung (von –5 bis 5) und eine Liste anwendbarer Geschäftsaspekte. 

Weitere Informationen finden Sie unter [Analysieren der Stimmung im Kundenfeedback (Vorschauversion)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]