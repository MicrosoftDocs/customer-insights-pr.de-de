---
title: Erste Schritte mit der Funktion Kundenbindungserkenntnisse
description: Eine Übersicht der Hilferessourcen für einen schnellen Einstieg.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 644b125f5d140627d357630ded88dd6838d6edb7
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494593"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Erste Schritte mit Dynamics 365 Customer Insights Kundenbindungserkenntnisse (öffentliche Vorschauversion)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

mit der Funktion Kundenbindungserkenntnisse können Sie das Kundenverhalten auf Ihrer Website erfassen und messen. Sie sind in die Funktion Zielgruppenerkenntnisse integriert, sodass Sie neben Kundenprofilberichten auch umfassende Verhaltensanalysen in Echtzeit anzeigen können. Über die Links in diesem Artikel können Sie Ihre Umgebung schnell konfigurieren und einrichten.

## <a name="step-1-review-prerequisites"></a>Schritt 1: Prüfen der Voraussetzungen

Zunächst benötigen Sie ein aktives Microsoft Azure Active Directory (AAD)-Benutzerkonto. Lesen Sie anschließend die folgenden Artikel, bevor Sie einen Arbeitsbereich für Kundenbindungen einrichten.

- Lesen Sie die [Vertragsbedingungen](terms-of-service.md) von Microsoft und stimmen Sie ihnen zu.  
- Lesen Sie den Artikel [Verwalten von Cookies und Benutzereinwilligung](user-consent-storage.md). Bewerten Sie anschließend, ob Sie Ihre Benachrichtigung zur Benutzereinwilligung aktualisieren müssen. Wenn Sie zuvor keine „unwesentlichen“ Cookies hatten, müssen Sie Ihre Website-Richtlinien vermutlich aktualisieren.
- Verwenden Sie das [Glossar](glossary.md) für einen schnelle Einführung in wichtige Begriffe und Konzepte.

## <a name="step-2-explore-engagement-insights"></a>Schritt 2: Erkunden der Funktion Kundenbindungserkenntnisse

Wenn Sie sich zum ersten Mal bei Interaktionserkenntnissen anmelden, können Sie Einstellungen konfigurieren, Richtlinien überprüfen und die Funktion erkunden.

1. Melden Sie sich bei dem [Portal der Funktion Interaktionserkenntnisse](https://home.ci.ai.dynamics.com/app/engagement-insights) mit Ihrem Microsoft AAD-Benutzerkonto (Schule oder Arbeit) an.

1. Wählen Sie Ihre Region aus und aktivieren Sie das Kontrollkästchen, wenn Sie sich für den Erhalt von E-Mail-Updates und Angeboten anmelden möchten.

1. Überprüfen Sie die **Nutzungsbedingungen für Interaktionserkenntnisse (Vorschau)** und die **Datenschutzerklärung**, und wählen Sie dann **Demo erkunden** aus, um diese Einstellungen zu übernehmen.

1. Erkunden Sie das Produkt anhand einer Reihe von Beispieldaten.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Schritt 3: Einrichten eines Arbeitsbereichs und Hinzufügen von Code zu Ihrer Website

In einem Arbeitsbereich können Sie Benutzeraktivitäten in Echtzeit anzeigen und Berichte speichern und verwalten. Fügen Sie Ihrer Website Code hinzu, um mit dem Sammeln von *Ereignissen* zu beginnen, den Aktivitätsdaten, die von Benutzern eingehen.

1. [Erstellen Sie einen Arbeitsbereich](create-workspace.md) und fügen Sie Mitglieder hinzu.

1. [Code zu Ihrer Website hinzufügen](instrument-website.md) oder [mobile App](developer-resources.md#capture-events-from-mobile-apps) um zu sehen, wie Benutzeraktivitäten in Ihrem Arbeitsbereich eintreffen.

1. Zeigen Sie einen [Echtzeitbericht](view-reports.md) an, der aktive Benutzer nach Browser, Gerät, Betriebssystem, Standort und Sprache anzeigt. Sie können auch [benutzerdefinierte Berichte](custom-reports.md) erstellen, um eigene Visualisierungen zu erstellen.
    
## <a name="step-4-export-data-to-other-channels"></a>Schritt 4: Exportieren von Daten in andere Kanäle

Sie können *verfeinerte Ereignisse* (eine virtuelle Ansicht) Ihrer Webanalysedaten erstellen. Filtern Sie die Daten anschließend und exportieren Sie sie nach Azure Data Lake Storage. Sie können die exportierten Daten als Datenquelle aufnehmen. Weitere Informationen finden Sie unter [Erstellen Sie eine Verknüpfung zwischen Zielgruppenerkenntnissen und Kundenbindungserkenntnissen](integrate-audience-insights-engagement-insights.md).

1. [Erstellen Sie verfeinerte Ereignisse](refined-events.md) für den Export.

1. [Exportieren Sie die Daten](export-events.md) nach Data Lake Store.

1. [Erstellen Sie eine Verknüpfung zwischen Zielgruppenerkenntnissen und Interaktionserkenntnissen](integrate-audience-insights-engagement-insights.md), um Daten zwischen den beiden Funktionen auszutauschen.

1. Erfahren Sie, wie Sie [Ereignisdaten mit persönlichen Informationen löschen und exportieren](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Schritt 5: In Verbindung bleiben

Wir schätzen Ihre aktive Teilnahme und berücksichtigen alle relevanten Rückmeldungen bei der Entwicklung zukünftiger Versionen. Teilen Sie Ihr Feedback und melden Sie Probleme über einen dieser Kanäle:
- [Community](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Feedback senden](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Support anfordern](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
