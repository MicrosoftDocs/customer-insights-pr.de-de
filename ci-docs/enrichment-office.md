---
title: Kundenprofile mit Daten aus Microsoft Office 365 anreichern
description: Verwenden Sie proprietäre Daten von Microsoft Office, um Ihre Kundenprofile mit Engagementdaten anzureichern.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 7192b7680e73a581dd603de174c57b20bec996dd
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954132"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Kundenprofile mit Interaktionsdaten anreichern (Vorschauversion)

Verwenden Sie Daten aus Microsoft Office 365, um Ihre Kundenkontoprofile mit Erkenntnissen über Interaktionserkenntnisse durch Office 365-Apps anzureichern. Die Interaktionsdaten bestehen aus E-Mail- und Besprechungsaktivitäten, die auf Kontoebene aggregiert werden. Beispielsweise die Anzahl der E-Mails von einem Geschäftskonto oder die Anzahl der Besprechungen mit dem Konto. Es werden keine Daten über einzelne Benutzer zur Verfügung gestellt.

## <a name="supported-countries-or-regions"></a>Unterstützte Länder oder Regionen

Wir unterstützen derzeit die folgenden Regionen: Großbritannien, Europa, Nordamerika.

## <a name="prerequisites"></a>Anforderungen

- Eine aktive Office 365 Cloud-Lizenz.
- [Unified customer profile](customer-profiles.md) basierend auf [Geschäftskonten](work-with-business-accounts.md).
- Ihrer Customer Insights-Umgebung muss eine [Microsoft Dataverse-Organisation angefügt](create-environment.md#step-3-connect-to-microsoft-dataverse) sein.
- [Administratorberechtigungen](permissions.md#admin).
- Sie haben die Zustimmung Ihres Office 365 Mandantenadministrators bzw. können diese erhalten, um Office 365 Daten für die Bereitstellung von **Erkenntnisse für die Organisation** in Dynamics 365-Anwendungen bereitzustellen.

## <a name="configure-the-enrichment"></a>Anreicherungskonfiguration

1. Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus.

1. Wählen Sie **Meine Daten anreichern** auf der Kachel **Kundenbindung** aus.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Kachel „Kontobindung“":::

1. Prüfen Sie die Übersicht und wählen Sie dann **Weiter** aus.

1. Geben Sie die E-Mail-Adressen Ihrer Organisation ein, für die Office-Daten aggregiert werden sollen. Es werden nur Daten aus den aufgeführten E-Mail-Adressen für die entsprechende Kommunikation verarbeitet. Eine bewährte Methode besteht darin, E-Mail-Gruppen zu verwenden, z. B. *US-amerikanisches Vertriebsteam*, die in Office 365 einfach verwaltet werden können. Die Anzahl der E-Mail-Adressen in den Gruppen wird aufgelöst und angezeigt. Die Gesamtzahl der E-Mail-Adressen muss mindestens 2 betragen und darf 2.500 nicht überschreiten.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="E-Mail-Adressen für Kontobindung":::

1. Überprüfen Sie und geben Sie Ihre Zustimmung für [Office 365 Mandant-Administrator-Zustimmung](#office-365-tenant-administrator-consent) durch die Auswahl von **Ich stimme zu**.

1. Wählen Sie **Weiter** aus.

1. Wählen Sie das **Kontakt-Dataset** und wählen Sie das Profil oder Segment aus, das Sie anreichern möchten. Wählen Sie **Weiter** aus.

1. Ordnen Sie das Feld für die Kontakt-E-Mail-Adresse zu, und wählen Sie **Weiter** aus.

1. Geben Sie einen **Namen** für die Anreicherung und einen Namen für die **Ausgabeentität** an.

1. Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.

1. Wählen Sie **Schließen** aus, um zur Seite **Anreicherung** zurückzukehren.

### <a name="office-365-tenant-administrator-consent"></a>Zustimmung des Office 365-Mandantenadministrators

Die Zustimmung eines Office 365-Mandantenadministrators ist erforderlich, um die Anreicherung zu aktivieren. Beim Speichern der Anreicherung wird eine E-Mail an den Office 365-Mandantenadministrator gesendet, in der er aufgefordert wird, eine Überprüfung durchzuführen und zuzustimmen, dass Dynamics 365-Anwendungen die Office 365-Daten Ihres Unternehmens verwenden darf, um **Erkenntnisse für die Organisation** bereitzustellen. Der Office 365-Mandantenadministrator kann seine Zustimmung auch direkt über die Office 365-Verwaltungskonsole durch Auswahl von **Erkenntnisse für die Organisation** geben.

## <a name="running-the-enrichment-for-the-first-time"></a>Erstmaliges Ausführen der Anreicherung

Wenn die Anreicherung zum ersten Mal gestartet wird, beginnt der Download der Daten von Office 365, nachdem die Zustimmung des Office 365-Mandantenadministrators erfolgt ist. Dieser Prozess dauert einige Zeit. Der erste Anreicherungsausführung wird mit einer Verzögerung von sechs Stunden geplant. Nach Abschluss der Anreicherung wird auf der Übersichtsseite der Kontobindung die Anzahl der Tage angezeigt, die die Daten abdecken. Führen Sie bei einem großen Datenvolumen die Anreicherung nach einigen Tagen erneut durch. Dadurch wird sichergestellt, dass die Daten für das gesamte Zeitfenster, das ein Jahr beträgt, vollständig sind.

Je nach Größe Ihrer Office-Daten kann es mehrere Stunden dauern, bis eine Anreicherungsausführung abgeschlossen ist.

Wenn Sie eine Anreicherung ausführen, verarbeitet Microsoft die Daten innerhalb der Office 365-Kompatibilitätsgrenze, um aggregierte Erkenntnisse zu erstellen, die Ihrer Customer Insights-Umgebung anschließend hinzugefügt werden. Benutzern von Customer Insights werden keine Daten auf einzelnen Ebenen (z. B. der Text einer E-Mail oder einer Kalendereinladung) zur Verfügung gestellt.

Um den Anreicherungsprozess zu starten, wählen Sie **Ausführen** aus.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Anreicherungsergebnisse

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] Dies ist die *Office* Entität. Die *Office_UserEntity* enthält die Active Directory-IDs für die E-Mail-Adressen, die während der Anreicherungskonfiguration ausgewählt wurden.

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Vorschau der Ergebnisse nach Ausführung des Anreicherungsprozesses.":::

Alle Daten werden bis auf Kontoebene aggregiert. Das System berechnet für jedes Konto eine Bindungsbewertung, die von 0 bis 100 reicht. Die Bindungsbewertung bietet eine zusammengesetzte Messung der Kontobindung in E-Mails und Besprechungen im Vergleich zu Ihren anderen Konten. Die folgende Liste enthält die aggregierten Daten, die die Kontobindungsanreicherung bereitstellt:

| Daten                                                                              | Spaltenname                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Bewertung des Engagements                                                                  |  EngagementScore                         |
| Anzahl der E-Mails an das Konto                                                       |  NoOfEmails_ToAccount                    |
| Anzahl der E-Mails vom Konto                                                     |  NoOfEmails_FromAccount                  |
| Anzahl der vom Konto initiierten Besprechungen                                           |  NoOfMeetings_FromAccount                |
| Anzahl der von Ihrer Organisation initiierten Besprechungen                                 |  NoOfMeetings_ToAccount                  |
| Anzahl der Personen aus Ihrer Organisation in Besprechungen mit dem Konto                  |  NoOfContactsInvolved_Meetings           |
| Anzahl der Personen aus Ihrer Organisation in E-Mail-Unterhaltungen mit dem Konto       |  NoOfContactsInvolved_Emails             |
| Anzahl der Personen aus dem Konto in Besprechungen mit Ihrer Organisation                  |  NoOfAccountContactsInvolved_Meetings    |
| Anzahl der Personen aus dem Konto in E-Mail-Unterhaltungen mit Ihrer Organisation       |  NoOfAccountContactsInvolved_Emails      |
| Startdatum der Bindung (erste E-Mail oder Besprechung in den Daten)                        |  EngagementStartDate                     |
| Tage seit der letzten E-Mail                                                             |  DaysSinceLastEmail                      |
| Tage seit der letzten Besprechung                                                           |  DaysSinceLastMeeting                    |
| Durchschnittliche Dauer der Besprechungen                                                      |  AverageDuration_Of_Meetings             |
| Durchschnittliche Dauer der E-Mail-Antworten vom Konto                                    |  AverageDuration_Of_AccountEmailReplies  |
| Startdatum der Aggregations                                                            |  AggregationStartDate                    |
| Aggregationsebene (Jahr, Monat oder Woche)                                          |  AggregationLevel                        |

## <a name="see-enrichment-data-on-the-customer-card"></a>Siehe Anreicherungsdaten auf der Kundenkarte

Die Kontobindung kann auch auf einzelnen Kundenkarten angezeigt werden. Gehen Sie zu **Kunden** und wählen Sie ein Kundenprofil. Auf der Kundenkarte finden Sie die Bindungsbewertung des Kontos, die Gesamtzahl der E-Mails und die Gesamtzahl der im letzten Jahr aggregierten Besprechungen. Außerdem werden Diagramme zur Verfügung gestellt, die den E-Mail- und Besprechungsverlauf anzeigen.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kundenkarte mit angereicherten Daten.":::

## <a name="next-steps"></a>Nächste Schritte,

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Beispielsweise ein Segment, das alle Kunden enthält, die einen Wert über 60 für *Tage seit der letzten E-Mail* und *Tage seit dem letzten Treffen* aufweisen. Dieses Segment enthält veraltete Konten, die Sie erneut aktivieren können.

[!INCLUDE [footer-include](includes/footer-banner.md)]
