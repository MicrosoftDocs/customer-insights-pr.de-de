---
title: Anreicherung von Firmenprofilen mit der Drittanbieter-Anreicherung Leadspace
description: Allgemeine Informationen über die Drittanbieter-Anreicherung von Leadspace.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 08a4c56eb1c387015fd9e985a0c9484a13236fcf
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646241"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Anreicherung von Firmenprofilen mit Leadspace (Vorschau)

Leadspace ist ein Data Science-Unternehmen, das eine B2B-Kundendatenplattform bereitstellt. Es ermöglicht Umgebungen mit einheitlichen Kundenprofilen basierend auf Konten, ihre Daten anzureichern. Bereichern von *Kundenprofilen* mit Attributen wie Unternehmensgröße, Standort oder Branche. Bereichern von *Kontaktprofilen* mit Attributen wie Titel, Persona oder E-Mail-Verifizierung.

## <a name="prerequisites"></a>Voraussetzungen

Um Leadspace zu konfigurieren, müssen die folgenden Voraussetzungen erfüllt sein:

- Sie benötigen eine aktive Leadspace-Lizenz.
- Sie haben [Vereinheitlichtes Kund*innenprofil](customer-profiles.md) basierend auf Konten.
- Eine Leadspace-Verbindung wurde bereits von einem Administrator konfiguriert oder Sie haben [Administrator](permissions.md#admin)-Berechtigungen und „dauerhaften Schlüssel“ (bezeichnet als **Leadspace-Token**). Kontaktieren Sie [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) direkt für Details über ihr Produkt.

## <a name="configure-the-enrichment"></a>Anreicherungskonfiguration

1. Gehen Sie zu **Daten** > **Anreicherung**.

1. Wählen Sie **Meine Daten anreichern** auf der Leadspace-Kachel und wählen Sie **Los geht's**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Screenshot der Leadspace-Kachel.":::

1. Wählen Sie eine [Verbindung](connections.md) aus der Dropdownliste aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist. Wenn Sie ein Administrator sind, können Sie durch Auswahl von **Verbindung hinzufügen** und **Leadspace** eine Verbindung herstellen. 

1. Wählen Sie **Mit Leadspace verbinden**, um die Verbindungsauswahl zu bestätigen.

1. Wählen Sie **Weiter** und wählen Sie den **Kundendatensatz**, den Sie mit Unternehmensdaten von Leadspace anreichern möchten. Sie können die **Kundenentität** auswählen, um alle Ihre Kundenprofile anzureichern, oder eine Segmententität auswählen, um nur Kundenprofile anzureichern, die in diesem Segment enthalten sind.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Screenshot bei Auswahl des Kundendatensatzes.":::

1. Wählen Sie **Weiter** aus, und definieren Sie, welche Felder aus Ihren einheitlichen Profilen verwendet werden sollen, um nach übereinstimmenden Unternehmensdaten von Leadspace zu suchen. Das Feld **Firmenname** ist erforderlich. Für eine höhere Abgleichsgenauigkeit können bis zu zwei weitere Felder, **Firmen-Website** und **Firmenstandort**, hinzugefügt werden.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace-Feld-Zuordnungsbereich.":::

1. Wählen Sie **Weiter** aus, um die Feldzuordnung abzuschließen.

1. Aktivieren Sie das Kontrollkästchen, wenn Sie *Kontaktprofile* haben, die Sie bereichern möchten. Customer Insights wird die erforderlichen Felder automatisch zuordnen.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Anreicherung von Leadspace-Kontaktdatensätzen.":::
 
1. Geben Sie einen Namen für die Anreicherung ein und wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.


## <a name="configure-the-connection-for-leadspace"></a>Konfigurieren Sie die Verbindung für Leadspace 

Sie müssen ein Administrator sein, um Verbindungen zu konfigurieren. Wählen Sie **Verbindung hinzufügen** beim Konfigurieren einer Anreicherung *oder* gehen Sie zu **Administrator** > **Verbindungen** und wählen Sie **Einrichten** auf der Kachel „Leadspace“.

1. Wählen Sie **Erste Schritte** aus. 

1. Geben Sie einen Namen für die Verbindung in das Feld **Anzeigename** ein.

1. Geben Sie ein gültiges Leadspace-Token an.

1. Überprüfen Sie und geben Sie Ihre Zustimmung für **Datenschutz und Einhaltung** durch die Auswahl von **Ich stimme zu**.

1. Wählen Sie **Überprüfen**, um die Konfiguration zu validieren.

1. Wählen Sie nach Abschluss der Überprüfung **Speichern** aus.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Verbindungskonfigurationsseite für Leadspace.":::

## <a name="enrichment-results"></a>Anreicherungsergebnisse

Nach dem Aktualisieren der Anreicherung können Sie die neu angereicherten Unternehmensdaten unter[Meine Bereicherung](enrichment-hub.md) überprüfen. Den Zeitpunkt der letzten Aktualisierung und die Anzahl der angereicherten Profile können Sie anzeigen.

Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.

Weitere Informationen finden Sie unter [Leadspace-APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Nächste Schritte,


[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Leadspace aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird diese Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Leadspace alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights Administrator kann diese Anreicherung jederzeit entfernen, um die Nutzung dieser Funktionalität einzustellen.


[!INCLUDE [footer-include](includes/footer-banner.md)]
