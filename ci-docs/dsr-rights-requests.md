---
title: Anträge zu den Rechten des Datensubjekts (DSR) gemäß der DSGVO | Microsoft Docs
description: Reagieren Sie auf Anfragen von betroffenen Personen für die Funktionalität Dynamics 365 Customer Insights Zielgruppen-Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350268"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Daten-abhängige Rechteanforderungen unter DSGVO

Die Datenschutz-Grundverordnung (DSGVO) der Europäischen Union ist seit dem 25. Mai 2018 in Kraft. Sie gibt Einzelpersonen erhebliche Rechte in Bezug auf ihre Daten. Bei der DSGVO geht es um den Schutz und die Gewährleistung der Datenschutzrechte von Einzelpersonen. Weitere Informationen zum Einsatz von Microsoft für Sicherheit und Compliance finden Sie im [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Wir haben es uns zur Aufgabe gemacht, unsere Kunden bei der Erfüllung der DSGVO-Anforderungen zu unterstützen. Die Software beinhaltet das Recht, Daten zu löschen und zu exportieren, die persönliche Informationen wie Benutzer-IDs, Telefonnummern und E-Mail-Adressen enthalten. Administratoren können Benutzeranforderungen zum Löschen oder Exportieren persönlicher Daten implementieren.

## <a name="audience-insights"></a>Zielgruppenerkenntnisse

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Reagieren auf DSGVO-Löschanfragen von betroffenen Personen für Dynamics 365 Customer Insights Zielgruppen-Insights-Funktionalitäten

Das "Recht auf Löschung" durch die Entfernung persönlicher Daten aus den Kundendaten eines Unternehmens ist ein wichtiger Schutz in der Datenschutz-Grundverordnung (DSGVO). Durch das Entfernen von persönlichen Daten zählen alle persönlichen Daten und vom System generierte Protokolle, ausgenommen Überwachungsprotokollinformationen.

#### <a name="manage-data-subject-delete-requests"></a>Verwaltung von Löschungsanträgen von Betroffenen

Zielgruppen-Insights bietet die folgenden produktinternen Erfahrungen, um persönliche Daten für einen bestimmten Kunden oder Benutzer zu löschen:

- **Löschanträge für Kundendaten verwalten**: Kundendaten in Customer Insights werden aus Originaldatenquellen außerhalb von Customer Insights aufgenommen. Alle DSGVO-Löschungsanfragen müssen in der ursprünglichen Datenquelle durchgeführt werden.
- **Löschanfragen für Customer Insights-Benutzerdaten verwalten**: Daten für Benutzer werden von Customer Insights erstellt. Alle DSGVO-Löschungsanfragen müssen in Customer Insights durchgeführt werden.

##### <a name="manage-requests-to-delete-customer-data"></a>Verwalten von Löschanforderungen für Kundendaten

Ein Administrator von Customer Insights kann die folgenden Schritte ausführen, um Kundendaten zu entfernen, die in der Datenquelle gelöscht wurden:

1. Melden Sie sich bei Dynamics 365 Customer Insights an.
2. Gehen Sie in Zielgruppen-Insights zu **Daten** > **Datenquellen**
3. Für jede Datenquelle in der Liste, die gelöschte Kundendaten enthält:
   1. Wählen Sie (...) und wählen Sie dann **Aktualisieren**.
   2. Überprüfen Sie den Status der Datenquelle unter **Status**. Ein Häkchen bedeutet, dass die Aktualisierung erfolgreich war. Ein Warndreieck bedeutet, dass etwas schief gelaufen ist. Wenn ein Warndreieck angezeigt wird, wenden Sie sich an D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Umgang mit DSGVO-Löschanträgen für Kundendaten.](audience-insights/media/gdpr-data-sources.png "Behandlung von DSGVO-Löschungsanträgen für Kundendaten")

##### <a name="manage-delete-requests-for-user-data"></a>Verwalten von Löschanfragen für Benutzerdaten

Ein Customer Insights-Administrator kann folgende Schritte durchführen, um Customer Insights-Benutzerdaten zu löschen:

1. Melden Sie sich bei Dynamics 365 Customer Insights an.
2. Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Berechtigungen**.
3. Markieren Sie das Kontrollkästchen für den Benutzer, den Sie löschen möchten.
4. Klicken Sie auf **Entfernen**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Reagieren auf DSGVO-Exportanfragen von Datensubjekten

Als Teil unserer Verpflichtung, Sie auf Ihrem Weg zur Datenschutz-Grundverordnung (DSGVO) zu begleiten, haben wir eine Dokumentation entwickelt, die Ihnen bei der Vorbereitung hilft. Diese Dokumentation beschreibt Schritte, die Sie heute unternehmen können, um die Einhaltung der DSGVO zu unterstützen, wenn Sie Zielgruppen-Insights verwenden.

#### <a name="manage-export-and-view-requests"></a>Verwalten von Export- und Anzeigeanforderungen

Das Recht auf Datenportabilität ermöglicht es den betroffenen Personen, eine Kopie ihrer persönlichen Daten in einem elektronischen Format (ein "strukturiertes, allgemein verwendetes, maschinenlesbares und interoperables Format") anzufordern, das an einen anderen für die Datenverarbeitung Verantwortlichen übermittelt werden kann.

##### <a name="export-customer-data-tenant-admin"></a>Kundendaten exportieren (Mandantenverwaltung)

Ein Mandanten-Administrator kann diese Schritte befolgen, um Daten zu exportieren:

1. Senden Sie eine E-Mail an D365CI@microsoft.com und geben Sie die E-Mail-Adresse des Kunden in der Anfrage an. Das Customer Insights-Team sendet eine E-Mail an die registrierte Admin-E-Mail-Adresse des Mandanten und bittet um eine Bestätigung für den Datenexport.
2. Bestätigen Sie die Meldung zum Export der Daten für den angeforderten Kunden.
3. Erhalten Sie die exportierten Daten über die E-Mail-Adresse des Mandantenverwalters.

##### <a name="export-user-data-tenant-admin"></a>Benutzerdaten exportieren (Mandant Admin)

1. Senden Sie eine E-Mail an D365CI@microsoft.com, wobei Sie die E-Mail-Adresse des Benutzers in der Anfrage angeben. Das Customer Insights-Team sendet eine E-Mail an die registrierte Admin-E-Mail-Adresse des Mandanten und bittet um eine Bestätigung für den Datenexport.
2. Bestätigen Sie die Meldung, um die Daten für den angeforderten Benutzer zu exportieren.
3. Erhalten Sie die exportierten Daten über die E-Mail-Adresse des Mandantenverwalters.

## <a name="consent-management-preview"></a>Zustimmungsverwaltung (Vorschauversion)

Die Zustimmungsverwaltungsfunktion erfasst Benutzerdaten nicht direkt. Sie importiert und verarbeitet nur Zustimmungsdaten, die von Benutzern in anderen Anwendungen bereitgestellt werden.

Um Zustimmungsdaten zu bestimmten Benutzern zu entfernen, entfernen Sie sie aus den Datenquellen, die in die Zustimmungsverwaltungsfunktion aufgenommen wurden. Nach der Aktualisierung der Datenquelle werden die entfernten Daten auch im Zustimmungscenter gelöscht. Anwendungen, die die Einwilligungsentität verwenden, löschen auch Daten, die aus der Quelle nach einer [Aktualisierung](audience-insights/system.md#refresh-processes) entfernt wurden. Wir empfehlen, Datenquellen schnell zu aktualisieren, nachdem Sie auf eine Anfrage einer betroffenen Person, Daten des Benutzers aus allen anderen Prozessen und Anwendungen zu entfernen, reagiert haben.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]