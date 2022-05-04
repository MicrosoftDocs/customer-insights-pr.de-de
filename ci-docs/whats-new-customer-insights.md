---
title: Neue und kommende Funktionen
description: Informationen über neue Funktionen, Verbesserungen und Fehlerbehebungen.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 25c6e2897d836854408871b2c74afa16ecba7435
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647243"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Neuerungen in Dynamics 365 Customer Insights

Wir freuen uns, unsere neuesten Updates bekannt zu geben! In diesem Artikel werden Funktionen für die öffentliche Vorschau, Verbesserungen der allgemeinen Verfügbarkeit und Funktionsupdates zusammengefasst. Um die langfristig geplanten Funktionen zu sehen, werfen Sie einen Blick auf die [Dynamics 365 und Power Platform Freigabe-Pläne](/dynamics365/release-plans/).

Wir führen Updates nach Region durch. So können bestimmte Regionen Merkmale vor anderen sehen. Sofern nicht anders angegeben, müssen Sie keine Maßnahmen ergreifen, und wir aktualisieren die App automatisch ohne Ausfallzeiten.

> [!TIP]
> Zum Senden und Abstimmen zu gewünschten Funktionen und Vorschläge zum Produkt, navigieren Sie zu [Dynamics 365 Anwendungs-Ideen Portal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


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

For more information, see [Aktivieren der Datenfreigabe für Dataverse über Ihre eigene Azure Data Lake Storage (Vorschauversion)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Neue Exportziele: Iterable und Braze

Wir bauen unser Ökosystem an Exportdestinationen mit neuen Verbindungen weiter aus. Sie können jetzt Segmente nach Iterable und Braze exportieren, um deren Aktivierungsdienste zu nutzen.

Weitere Informationen finden Sie unter [Segmente nach Iterable exportieren (Vorschau)](export-iterable.md) und [Segmente nach Braze exportieren (Vorschau)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Verbesserungen am Marketo- und Google Ads-Export

Sich ändernde APIs in verbundenen Diensten führen zu Updates, damit Konnektoren zuverlässig und reibungslos laufen. Wir haben einige Aktualisierungen für die Exporte in Marketo- und Google Ads-Dienste veröffentlicht:

- Google Ads: Die neue Version des Google Ads-Export-Connectors vereinfacht die Authentifizierung und ermöglicht Ihnen jetzt, automatisch neue Google Ads-Zielgruppen zu erstellen. 
- Marketo: Die neue Version des Marketo-Exportkonnektors bietet Unterstützung für die Marketo-ID, sodass Sie Datenduplizierung vermeiden, vorhandene Datensätze aktualisieren und neue Datensätze in Marketo erstellen können. 


## <a name="february-2022-updates"></a>Updates Februar 2022

Die Updates im Februar 2022 beinhalten neue Funktionen, Leistungssteigerungen und Fehlerbehebungen.

### <a name="general-availability-for-prediction-models"></a>Allgemeine Verfügbarkeit für Vorhersage-Modelle

Sofort einsatzbereite Vorhersage-Modelle, einschließlich **Abonnement-Churn**, **Transaktions-Churn** und **Customer Lifetime Value (CLV)** werden als Teil von Customer Insights allgemein verfügbar. 

Weitere Informationen finden Sie unter [Vorhersage-Übersicht](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Neu Datenquelle: Integration mit Azure Synapse Analytics (Vorschau)

Azure Synapse Analytics ist ein Analysedienst für Unternehmen, der Erkenntnisse über Data Warehouses und Big-Data-Systeme hinweg verkürzt.

Organisationen, die bereits Azure Synapse Analytics verwenden, kann diese Daten in Customer Insights aufnehmen. 

Weitere Informationen finden Sie unter [Verbindung zu Azure Synapse Datenquellen (Vorschau)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>LiveRamp-Anreicherung (Vorschauversion)

LiveRamp bietet Identitätsauflösung und Konsolidierung von Kundendaten. Sie können persönliche Kennungen in Ihren Kundendaten dem AbiliTec-Identitätsdiagramm zuordnen und AbiliTec-IDs erhalten. Diese IDs können Sie dann zur besseren Vereinheitlichung Ihrer Kundendaten verwenden.

Weitere Informationen finden Sie unter [Kundenprofile mit Identitätsdaten von LiveRamp (Vorschauversion)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Anreicherung für Datenquellen (Vorschau)

Verwenden Sie Daten aus Quellen wie Microsoft und anderen Partnern, um Ihre Kundendaten vor der Datenvereinheitlichung anzureichern. Datenquellen-Anreicherungen tragen zu einer höheren Datenvollständigkeit und -qualität bei, die dazu beitragen können, bessere Ergebnisse zu erzielen, sobald Sie Ihre Daten vereinheitlicht haben.

Weitere Informationen finden Sie unter [Anreicherungen für Datenquellen (Vorschauversion)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Besitzer der Umgebung ändern

Während mehrere Benutzer Administratorberechtigungen in Customer Insights haben können, ist nur ein Benutzer der Eigentümer einer Umgebung. Eine verbesserte Erfahrung ermöglicht es Ihnen, den Besitzer einer Umgebung zu ändern und den Besitz zu beanspruchen, wenn ein ehemaliger Besitzer die Organisation verlassen hat. 

Weitere Informationen finden Sie unter [Ändern Sie den Besitzer einer Umgebung](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Der Datenvorbereitungsprozess führt den Korruptionsgrund für beschädigte Datensätze auf

Die Datenvorbereitung zeigt jetzt den Grund für die Beschädigung für alle Felder mit beschädigten Daten an. Die Informationen werden zur einfachen Identifizierung auf individueller Datensatzebene bereitgestellt. 

Weitere Informationen finden Sie unter [Korrupte Datenquellen](entities.md#corrupted-data-sources).

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

Weitere Informationen finden Sie unter [Analysieren der Stimmung im Kundenfeedback (Vorschau)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]