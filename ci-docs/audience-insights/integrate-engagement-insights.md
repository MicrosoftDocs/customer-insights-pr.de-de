---
title: Integrieren Sie Webdaten aus Erkenntnissen zur Kundenbindung in Zielgruppenerkenntnisse
description: Bringen Sie Webinformationen über Kunden von Erkenntnissen zur Kundenbindung zu Zielgruppenerkenntnissen.
ms.date: 06/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 76a53a897e90152707a7c1255ed5ed93a5f3b5a0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305017"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Integrieren Sie Webdaten aus Erkenntnissen zur Kundenbindung in Zielgruppenerkenntnisse

Kunden erledigen ihre täglichen Transaktionen häufig online über Websites. Die Funktion Kundenbindungseinblicke (Vorschau) in Dynamics 365 Customer Insights ist eine praktische Lösung, um Webdaten als Quelle zu integrieren. Zusätzlich zu Transaktions-, Demografie- oder Verhaltensdaten können wir Aktivitäten im Web in einheitlichen Kundenprofilen anzeigen. Wir können diese Profile verwenden, um zusätzliche Erkenntnisse wie Segmente, Kennzahlen oder Vorhersagen für die Zielgruppen-Aktivierung zu gewinnen.

In diesem Artikel werden die Schritte beschrieben, mit denen Sie die Webaktivitätsdaten Ihrer Kunden aus Interaktionserkenntnissen in Ihre vorhandene Zielgruppenerkenntnisse-Umgebung übertragen können.

In diesem Beispiel nehmen wir eine Umgebung an, die einheitliche Kundenprofile enthält. Die Profile wurden mit Quellen aus Umfragen, Einzelhandelsverkäufen und einem Ticketingsystem vereinheitlicht. Es zeigt auch die damit verbundenen Aktivitäten der Kunden. 

Wir möchten jetzt wissen, ob ein Kunde unsere Web-Eigenschaften besucht und deren Aktivitäten versteht. Zu den Aktivitäten gehören beispielsweise besuchte Websites oder angesehene Produktseiten über einen in einer E-Mail erhaltenen Link.

## <a name="prerequisites"></a>Anforderungen

Um Daten aus Interaktionserkenntnissen zu integrieren, müssen einige Voraussetzungen erfüllt sein: 

- Integrieren Sie das Interaktionserkenntnisse-SDK in Ihre Website. Weitere Informationen finden Sie unter [Entwicklerressourcenübersicht](../engagement-insights/developer-resources.md).
- Das Exportieren von Webereignissen aus Kundenbindungserkenntnissen erfordert Zugriff auf ein Azure Data Lake Storage Konto, das verwendet wird, um die Webereignisdaten in Zielgruppenerkenntnissen aufzunehmen. Weitere Informationen finden Sie unter [Ereignisse exportieren](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Konfigurieren Sie verfeinerte Ereignisse in Interaktionserkenntnisse

Nachdem ein Administrator eine Website mit dem Kundenbindungserkenntnissen SDK instrumentiert hat, werden *Basisereignisse* erfasst, wenn ein Benutzer eine Webseite anzeigt oder irgendwo klickt. Basisereignisse enthalten in der Regel zahlreiche Details. Abhängig von Ihrem Anwendungsfall benötigen Sie nur eine Teilmenge der Daten in einem Basisereignis. Mit Interaktionserkenntnissen können Sie *verfeinerte Ereignisse* erstellen, die nur die Eigenschaften eines von Ihnen ausgewählten Basisereignisses enthalten.     

Weitere Informationen finden Sie unter [Erstellen und Verwenden von verfeinerten Ereignissen](../engagement-insights/refined-events.md).

Überlegungen beim Erstellen verfeinerter Ereignisse: 

- Geben Sie einen aussagekräftigen Namen für das verfeinerte Ereignis an. Er wird als Aktivitätsname in Zielgruppeneinblicken verwendet.
- Wählen Sie mindestens die folgenden Eigenschaften aus, um eine Aktivität in Zielgruppenerkenntnisse zu erstellen: 
    - Signal.Action.Name – zeigt die Aktivitätsdetails an.
    - Signal.User.ID – wird verwendet, um die Kunden-ID zuzuordnen.
    - Signal.View.Uri – wird als Webadresse als Grundlage für Segmente oder Kennzahlen verwendet.
    - Signal.Export.ID – wird als Primärschlüssel für Ereignisse verwendet.
    - Signal.Zeitstempel - bestimmt Datums- und Uhrzeit für die Aktivität.

Wählen Sie die Filter aus, um sich auf die Ereignisse und Seiten zu konzentrieren, die für Ihren Anwendungsfall wichtig sind. In diesem Beispiel verwenden wir den Aktionsnamen „E-Mail-Werbung“.

## <a name="export-the-refined-web-events"></a>Exportieren Sie die verfeinerten Webereignisse 

Nachdem Sie das verfeinerte Ereignis definiert haben, müssen Sie den Export der Ereignisdaten nach Azure Data Lake Storage konfigurieren, die als Datenquelle für die Aufnahme in Zielgruppenerkenntnissen festgelegt werden kann. Exporte erfolgen ständig, wenn die Ereignisse aus der Web-Eigenschaft fließen.

Weitere Informationen finden Sie unter [Ereignisse exportieren](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Nehmen Sie Ereignisdaten in Zielgruppenerkenntnisse auf

Nachdem Sie das verfeinerte Ereignis definiert und seinen Export konfiguriert haben, fahren wir mit der Aufnahme der Daten in Zielgruppenerkenntnisse fort. Sie müssen eine neue Datenquelle basierend auf einem Common Data Model-Ordner erstellen. Geben Sie die Details für das Speicherkonto ein, in das Sie die Ereignisse exportieren. In dem Datei *default.cdm.json* wählen Sie das verfeinerte Ereignis aus, das aufgenommen werden soll, und erstellen Sie die Entität in Zielgruppenerkenntnisse.

Weitere Informationen finden Sie unter [Stellen Sie mit einem Azure Data Lake-Konto eine Verbindung zu einem Common Data Model-Ordner her](connect-common-data-model.md).


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Verknüpfen Sie verfeinerte Ereignisdaten als Aktivität eines Kundenprofils

Nach Abschluss der Entitätsaufnahme können Sie die Aktivität für das Kundenprofil konfigurieren.

Weitere Informationen finden Sie unter [Kundenaktivitäten](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Aktivitätsseite mit erweitertem Aktivitätsbereich „Bearbeiten“ und ausgefüllten Feldern.":::

Konfigurieren Sie die neue Aktivität mit der folgenden Zuordnung: 

- **Primärschlüssel**: Signal.Export.ID, eine eindeutige ID, die für jeden Ereignisdatensatz in Interaktionserkenntnisse verfügbar ist. Diese Eigenschaft wird automatisch generiert.

- **Zeitstempel**: Signal.Timestamp in der Ereigniseigenschaft.

- **Ereignis**: Signal.Name des Ereignisnamens, den Sie nachverfolgen möchten.

- **Webadresse**: Signal.View.Uri bezieht sich auf den URI der Seite, die das Ereignis erstellt hat.

- **Details**: Signal.Action.Name, um die Informationen darzustellen, die dem Ereignis zugeordnet werden sollen. Die ausgewählte Eigenschaft in diesem Fall zeigt an, dass das Ereignis für die E-Mail-Werbung bestimmt ist.

- **Aktivitätstyp**: In diesem Beispiel wählen wir den bestehenden Aktivitätstyp WebLog. Diese Auswahl ist eine nützliche Filteroption, um Vorhersage-Modelle auszuführen oder Segmente basierend auf diesem Aktivitätstyp zu erstellen.

- **Beziehung aufbauen**: Diese wichtige Einstellung bindet die Aktivität an vorhandene Kundenprofile. **Signal.User.ID** ist die Kennung, die im zu erfassenden SDK konfiguriert ist und sich auf die Benutzer-ID in anderen Datenquellen bezieht, die in Zielgruppenerkenntnisse konfiguriert sind. In diesem Beispiel konfigurieren wir die Beziehung zwischen Signal.User.ID und RetailCustomers:CustomerRetailId, dem Primärschlüssel, der im Zuordnungsschritt des Datenvereinigungsprozesses identifiziert wurde.

Nach der Verarbeitung der Aktivitäten können Sie Kundendatensätze überprüfen und eine Kundenkarte öffnen, um Aktivitäten aus Interaktionserkenntnissen in der Zeitleiste anzuzeigen. 

> [!TIP]
> Um eine Kunden-ID mit einer Aktivität zu Einsichten zu finden, gehen Sie zu **Entitäten** und zeigen eine Vorschau der Daten für die UnifiedActivity-Entität an. ActivityTypeDisplay = WebLog enthält die im obigen Beispiel konfigurierte Aktivität für Engagement Insights. Kopieren Sie die Kunden-ID für einen dieser Datensätze und für diese ID auf die **Kunden**-Seite.

## <a name="next-steps"></a>Nächste Schritte

Sie können jetzt [Segmente](segments.md), [Kennzahlen](measures.md) und [Vorhersagen](predictions.md) erstellen, um eine sinnvolle Verbindung zu Ihren Kunden herzustellen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
