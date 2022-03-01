---
title: Erste Schritte mit der Funktion Kundenbindungserkenntnisse
description: Eine Übersicht der Hilferessourcen für einen schnellen Einstieg.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405357"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Erste Schritte mit Dynamics 365 Customer Insights Kundenbindungserkenntnisse (öffentliche Vorschauversion)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

mit der Funktion Kundenbindungserkenntnisse können Sie das Kundenverhalten auf Ihrer Website erfassen und messen. Sie sind in die Funktion Zielgruppenerkenntnisse integriert, sodass Sie neben Kundenprofilberichten auch umfassende Verhaltensanalysen in Echtzeit anzeigen können. Über die Links in diesem Artikel können Sie Ihre Umgebung schnell konfigurieren und einrichten.

## <a name="step-1-review-prerequisites"></a>Schritt 1: Prüfen der Voraussetzungen

Zunächst benötigen Sie ein aktives Microsoft Azure Active Directory-Benutzerkonto. Lesen Sie anschließend die folgenden Artikel, bevor Sie einen Arbeitsbereich für Kundenbindungen einrichten.

- Lesen Sie die [Vertragsbedingungen](terms-of-service.md) von Microsoft und stimmen Sie ihnen zu.  
- Lesen Sie den Artikel [Verwalten von Cookies und Benutzereinwilligung](user-consent-storage.md). Prüfen Sie nach dem Lesen dieses Artikels, ob Sie Ihre Benachrichtigung über die Benutzereinwilligung aktualisieren müssen. Wenn Sie zuvor keine „unwesentlichen“ Cookies hatten, müssen Sie Ihre Website-Richtlinien vermutlich aktualisieren.
- Verwenden Sie das [Glossar](glossary.md) für einen schnelle Einführung in wichtige Begriffe und Konzepte.

## <a name="step-2-explore-engagement-insights"></a>Schritt 2: Erkunden der Funktion Kundenbindungserkenntnisse

Wenn Sie die Funktion Kundenbindungserkenntnisse zum ersten Mal verwenden, können Sie Einstellungen konfigurieren, Richtlinien überprüfen und das Produkt erkunden.

1. Melden Sie sich beim [Portal der Funktion Kundenbindungserkenntnisse](https://pi.dynamics.com) an. Verwenden Sie hierfür Ihr Microsoft Azure Active Directory-Benutzerkonto. (Es kann Ihr Schul- oder Geschäftskonto sein.)

1. Wählen Sie Ihre Region aus und geben Sie über das Kontrollkästchen an, ob Sie den Erhalt von Updates und Angeboten per E-Mail abonnieren möchten.

1. Lesen Sie die **Nutzungsbedingungen für Kundenbindungserkenntnisse (Vorschauversion)** und die **Datenschutzerklärung**. Wählen Sie anschließend **Erkunden der Demo** aus, um sie zu akzeptieren.

1. Erkunden Sie das Produkt anhand einer Reihe von Beispieldaten.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Schritt 3: Einrichten eines Arbeitsbereichs und Hinzufügen von Code zu Ihrer Website

Im Arbeitsbereich können Sie Benutzeraktivitäten in Echtzeit anzeigen und Berichte speichern und verwalten. Fügen Sie Ihrer Website Code hinzu, um mit dem Sammeln von *Ereignissen* zu beginnen, den Aktivitätsdaten, die von Benutzern eingehen.

1. [Erstellen Sie einen Arbeitsbereich](create-workspace.md) und fügen Sie Mitglieder hinzu.

1. [Code zu Ihrer Website hinzufügen](instrument-website.md) oder [mobile App](developer-resources.md#capture-events-from-mobile-apps) um zu sehen, wie Benutzeraktivitäten in Ihrem Arbeitsbereich eintreffen.

1. Zeigen Sie einen [Echtzeitbericht](view-reports.md) an, der aktive Benutzer nach Browser, Gerät, Betriebssystem, Standort und Sprache anzeigt. Sie können auch [benutzerdefinierte Berichte](custom-reports.md) erstellen, um eigene Visualisierungen zu erstellen.
    
## <a name="step-4-export-data-to-other-channels"></a>Schritt 4: Exportieren von Daten in andere Kanäle

Sie können *verfeinerte Ereignisse* (eine virtuelle Ansicht) Ihrer Webanalysedaten erstellen. Filtern Sie die Daten anschließend und exportieren Sie sie nach Azure Data Lake Storage. Sie können die exportierten Daten als Datenquelle aufnehmen. Weitere Informationen finden Sie unter [Erstellen Sie eine Verknüpfung zwischen Zielgruppenerkenntnissen und Kundenbindungserkenntnissen](integrate-audience-insights-engagement-insights.md).

1. [Erstellen Sie verfeinerte Ereignisse](refined-events.md) für den Export.

1. [Exportieren Sie die Daten](export-events.md) nach Data Lake Store.

1. Erfahren Sie, wie Sie [Ereignisdaten mit persönlichen Informationen löschen und exportieren](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Schritt 5: In Verbindung bleiben

Wir bedanken uns für Ihre aktive Teilnahme und planen, das gesamte relevante Feedback bei der Entwicklung zukünftiger Versionen zu berücksichtigen. Teilen Sie Ihr Feedback und melden Sie Probleme über einen dieser Kanäle:
- [Community](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Feedback senden](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Support anfordern](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
