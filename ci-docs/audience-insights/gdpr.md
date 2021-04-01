---
title: Anträge zu den Rechten des Datensubjekts (DSR) gemäß der DSGVO | Microsoft Docs
description: Reagieren Sie auf Anfragen von betroffenen Personen für die Funktionalität Dynamics 365 Customer Insights Zielgruppen-Insights.
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9c453c9b416bff0e6362a8ccf7ff534f4efa1e00
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597510"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Daten-abhängige Rechteanforderungen unter DSGVO

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Reagieren auf DSGVO-Löschanfragen von betroffenen Personen für Dynamics 365 Customer Insights Zielgruppen-Insights-Funktionalitäten

Das "Recht auf Löschung" durch die Entfernung persönlicher Daten aus den Kundendaten eines Unternehmens ist ein wichtiger Schutz in der Datenschutz-Grundverordnung (DSGVO). Durch das Entfernen von persönlichen Daten zählen alle persönlichen Daten und vom System generierte Protokolle, ausgenommen Überwachungsprotokollinformationen.

### <a name="manage-data-subject-delete-requests"></a>Verwaltung von Löschungsanträgen von Betroffenen

Zielgruppen-Insights bietet die folgenden produktinternen Erfahrungen, um persönliche Daten für einen bestimmten Kunden oder Benutzer zu löschen:

- **Löschanträge für Kundendaten verwalten**: Kundendaten in Customer Insights werden aus Originaldatenquellen außerhalb von Customer Insights aufgenommen. Alle DSGVO-Löschungsanfragen müssen in der ursprünglichen Datenquelle durchgeführt werden.
- **Löschanfragen für Customer Insights-Benutzerdaten verwalten**: Daten für Benutzer werden von Customer Insights erstellt. Alle DSGVO-Löschungsanfragen müssen in Customer Insights durchgeführt werden.

#### <a name="manage-delete-requests-for-customer-data"></a>Verwalten von Löschanforderungen für Kundendaten

Ein Administrator von Customer Insights kann die folgenden Schritte ausführen, um Kundendaten zu entfernen, die in der Datenquelle gelöscht wurden:

1. Melden Sie sich bei Dynamics 365 Customer Insights an.
2. Gehen Sie in Zielgruppen-Insights zu **Daten** > **Datenquellen**
3. Für jede Datenquelle in der Liste, die gelöschte Kundendaten enthält:
   1. Wählen Sie (...) und wählen Sie dann **Aktualisieren**.
   2. Überprüfen Sie den Status der Datenquelle unter **Status**. Ein Häkchen bedeutet, dass die Aktualisierung erfolgreich war. Ein Warndreieck bedeutet, dass etwas schief gelaufen ist. Wenn ein Warndreieck angezeigt wird, wenden Sie sich an D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Behandlung von DSGVO-Löschanträgen für Kundendaten](media/gdpr-data-sources.png "Behandlung von DSGVO-Löschungsanträgen für Kundendaten")

#### <a name="manage-delete-requests-for-user-data"></a>Verwalten von Löschanfragen für Benutzerdaten

Ein Customer Insights-Administrator kann folgende Schritte durchführen, um Customer Insights-Benutzerdaten zu löschen:

1. Melden Sie sich bei Dynamics 365 Customer Insights an.
2. Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Berechtigungen**.
3. Markieren Sie das Kontrollkästchen für den Benutzer, den Sie löschen möchten.
4. Klicken Sie auf **Entfernen**.

> [!div class="mx-imgBorder"]
> ![Handhabung von DSGVO-Löschanfragen für Benutzerdaten](media/gdpr-permissions.png "Handhabung von DSGVO-Löschanfragen für Benutzerdaten")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Reagieren auf DSGVO-Exportanfragen von Datensubjekten

Als Teil unserer Verpflichtung, Sie auf Ihrem Weg zur Datenschutz-Grundverordnung (DSGVO) zu begleiten, haben wir eine Dokumentation entwickelt, die Ihnen bei der Vorbereitung hilft. Diese Dokumentation beschreibt Schritte, die Sie heute unternehmen können, um die Einhaltung der DSGVO zu unterstützen, wenn Sie Zielgruppen-Insights verwenden.

### <a name="manage-export-and-view-requests"></a>Verwalten von Export- und Anzeigeanforderungen

Das Recht auf Datenportabilität ermöglicht es den betroffenen Personen, eine Kopie ihrer persönlichen Daten in einem elektronischen Format (ein "strukturiertes, allgemein verwendetes, maschinenlesbares und interoperables Format") anzufordern, das an einen anderen für die Datenverarbeitung Verantwortlichen übermittelt werden kann.

#### <a name="export-customer-data-tenant-admin"></a>Kundendaten exportieren (Mandantenverwaltung)

Ein Mandanten-Administrator kann diese Schritte befolgen, um Daten zu exportieren:

1. Senden Sie eine E-Mail an D365CI@microsoft.com und geben Sie die E-Mail-Adresse des Kunden in der Anfrage an. Das Customer Insights-Team sendet eine E-Mail an die registrierte Admin-E-Mail-Adresse des Mandanten und bittet um eine Bestätigung für den Datenexport.
2. Bestätigen Sie die Meldung zum Export der Daten für den angeforderten Kunden.
3. Erhalten Sie die exportierten Daten über die E-Mail-Adresse des Mandantenverwalters.

#### <a name="export-user-data-tenant-admin"></a>Benutzerdaten exportieren (Mandant Admin)

1. Senden Sie eine E-Mail an D365CI@microsoft.com, wobei Sie die E-Mail-Adresse des Benutzers in der Anfrage angeben. Das Customer Insights-Team sendet eine E-Mail an die registrierte Admin-E-Mail-Adresse des Mandanten und bittet um eine Bestätigung für den Datenexport.
2. Bestätigen Sie die Meldung, um die Daten für den angeforderten Benutzer zu exportieren.
3. Erhalten Sie die exportierten Daten über die E-Mail-Adresse des Mandantenverwalters.


[!INCLUDE[footer-include](../includes/footer-banner.md)]