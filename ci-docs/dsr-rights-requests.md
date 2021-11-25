---
title: Anträge zu den Rechten des Datensubjekts (DSR) gemäß der DSGVO | Microsoft Docs
description: Reagieren Sie auf Anfragen von betroffenen Personen für die Funktionalität Dynamics 365 Customer Insights Zielgruppen-Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c116f7ce208c0288851a4b2230e27784ba3a5337
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732679"
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


## <a name="engagement-insights-preview"></a>Interaktionserkenntnisse (Vorschauversion)

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Löschen und Exportieren von Ereignisdaten mit Endbenutzerinformationen

In den folgenden Abschnitten wird beschrieben, wie Sie Ereignisdaten löschen und exportieren, die möglicherweise persönliche Daten enthalten.

So löschen oder exportieren Sie Daten:

1. Markieren Sie Ereigniseigenschaften, die Daten mit persönlichen Informationen enthalten.
2. Löschen oder exportieren Sie Daten, die bestimmten Werten zugeordnet sind (z. B. eine angegebene Benutzer-ID).

#### <a name="tag-and-update-event-properties"></a>Markieren und Aktualisieren von Ereigniseigenschaften

Persönliche Daten werden auf Ereigniseigenschaftsebene markiert. Markieren Sie zunächst die Eigenschaften, die zum Löschen oder Exportieren in Betracht gezogen werden.

Gehen Sie folgendermaßen vor, um eine Ereigniseigenschaft mit persönlichen Informationen zu markieren:

1. Öffnen Sie den Arbeitsbereich mit dem Ereignis.

1. Wechseln Sie zu **Daten** > **Ereignisse**, um die Liste der Ereignisse im ausgewählten Arbeitsbereich anzuzeigen.
  
1. Wählen Sie das Ereignis aus, das Sie markieren möchten.

1. Wählen Sie **Eigenschaften bearbeiten** aus, um den Bereich zu öffnen, in dem alle Eigenschaften des ausgewählten Ereignisses aufgelistet sind.
     
1. Wählen Sie zuerst **...** und dann **Bearbeiten** aus, um den Dialog **Eigenschaft aktualisieren** anzuzeigen.

   ![Ereignis bearbeiten.](engagement-insights/media/edit-event.png "Ereignis bearbeiten")

1. Wählen Sie im Fenster **Eigenschaft aktualisieren** oben rechts **...** aus und wählen Sie dann das Feld **Enthält EUII** aus. Wählen Sie **Aktualisieren** aus, um Ihre Änderungen zu speichern.

   ![Speichern Sie Ihre Änderungen.](engagement-insights/media/update-property.png "Speichern Sie Ihre Änderungen")

   > [!NOTE]
   > Jedes Mal, wenn sich das Ereignisschema ändert oder Sie ein neues Ereignis erstellen, wird empfohlen, die zugehörigen Ereigniseigenschaften zu bewerten und sie gegebenenfalls als persönliche Daten zu markieren.

#### <a name="delete-or-export-tagged-event-data"></a>Löschen oder Exportieren von markierten Ereignisdaten

Wenn alle Ereigniseigenschaften wie im vorherigen Schritt beschrieben entsprechend markiert wurden, kann ein Umgebungsadministrator eine Löschanforderung für die markierten Ereignisdaten ausgeben.

Verwalten von Lösch- oder Exportanforderungen für EUII-Daten

1. Wechseln Sie zu **Administrator** > **Umgebung** > **Einstellungen**.

1. Wählen Sie im Bereich **Endbenutzerinformationen (EUII) verwalten** die Option **EUII verwalten** aus.

##### <a name="deletion"></a>Löschen

Zum Löschen können Sie eine Liste der durch Kommas getrennten Benutzer-IDs in das Feld **Endbenutzerinformationen (EUII) löschen** eingeben. Diese IDs werden dann mit allen markierten Ereigniseigenschaften aller Projekte in der aktuellen Umgebung über eine exakte Zeichenfolgenübereinstimmung verglichen. 

Wenn ein Eigenschaftswert mit einer der angegebenen IDs übereinstimmt, wird das zugehörige Ereignis dauerhaft gelöscht. Aufgrund der Unumkehrbarkeit dieser Aktion müssen Sie den Löschvorgang nach der Auswahl von **Löschen** bestätigen.

##### <a name="export"></a>Export

Der Exportvorgang ist identisch mit dem Löschvorgang, wenn es darum geht, Ereigniseigenschaftswerte im Bereich **Endbenutzerinformationen (EUII) exportieren** zu definieren. Zusätzlich müssen Sie eine **Azure-Blobspeicher-URL** angeben, um das Exportziel festzulegen. Die Azure-Blob-URL muss eine [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview) enthalten.

Nach der Auswahl von **Exportieren** werden alle Ereignisse des aktuellen Teams, die übereinstimmende markierte Eigenschaften enthalten, im CSV-Format an das Exportziel exportiert.

### <a name="good-practices"></a>Bewährte Methoden

* Vermeiden Sie das Senden von Ereignissen, die persönliche Daten enthalten.
* Wenn Sie Ereignisse mit EUII-Daten senden müssen, begrenzen Sie die Anzahl der Ereignisse und Ereigniseigenschaften, die EUII-Daten enthalten. Beschränken Sie sich im Idealfall auf ein solches Ereignis.
* Stellen Sie sicher, dass möglichst wenige Personen Zugriff auf die gesendeten persönlichen Daten haben.
* Stellen Sie bei Ereignissen mit persönlichen Daten sicher, dass Sie eine Eigenschaft so festlegen, dass ein eindeutiger Bezeichner ausgegeben wird, der problemlos mit einem bestimmten Benutzer verknüpft werden kann (z. B. eine Benutzer-ID). Dies erleichtert das Isolieren von Daten und das Exportieren oder Löschen der richtigen Daten.
* Markieren Sie nur eine Eigenschaft pro Ereignis als Eigenschaft mit persönlichen Daten. Idealerweise ist dies eine, die nur einen eindeutigen Bezeichner enthält.
* Markieren Sie keine Eigenschaften, die ausführliche Werte enthalten (z. B. einen vollständigen Anforderungstext). Die Funktion Kundenbindungserkenntnisse verwendet eine genaue Zeichenfolgenübereinstimmung, wenn entschieden wird, welche Ereignisse gelöscht oder exportiert werden sollen.

[!INCLUDE[footer-include](includes/footer-banner.md)]