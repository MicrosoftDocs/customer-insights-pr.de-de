---
title: Anreicherung von Firmenprofilen mit der Drittanbieter-Anreicherung Leadspace
description: Allgemeine Informationen über die Drittanbieter-Anreicherung von Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895912"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Anreicherung von Firmenprofilen mit Leadspace (Vorschau)

Leadspace ist ein datenwissenschaftliches Unternehmen, das eine B2B-Kundendatenplattform anbietet. Sie ermöglicht es Kunden mit einheitlichen Kundenprofilen für Unternehmen, ihre Daten anzureichern. Anreicherungen umfassen zusätzliche Attribute wie Unternehmensgröße, Standort, Branche und mehr.

## <a name="prerequisites"></a>Anforderungen

Um Leadspace zu konfigurieren, müssen die folgenden Voraussetzungen erfüllt sein:

- Sie benötigen eine aktive Leadspace-Lizenz.
- Sie haben [Einheitliche Kundenprofile](customer-profiles.md) für Unternehmen.
- Eine Leadspace-Verbindung wurde bereits von einem Administrator konfiguriert oder Sie haben [Administrator](permissions.md#administrator)-Berechtigungen und „dauerhaften Schlüssel“ (bezeichnet als **Leadspace-Token**). Kontaktieren Sie [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) direkt für Details über ihr Produkt.

## <a name="configure-the-enrichment"></a>Anreicherungskonfiguration

1. Gehen Sie in Zielgruppen-Insights zu **Daten** > **Anreicherung**.

1. Wählen Sie **Meine Daten anreichern** auf der Leadspace-Kachel und wählen Sie **Los geht's**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Screenshot der Leadspace-Kachel.":::

1. Wählen Sie eine [Verbindung](connections.md) aus der Dropdownliste aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist. Wenn Sie ein Administrator sind, können Sie durch Auswahl von **Verbindung hinzufügen** und **Leadspace** eine Verbindung herstellen. 

1. Wählen Sie **Mit Leadspace verbinden**, um die Verbindungsauswahl zu bestätigen.

1. Wählen Sie **Weiter** und wählen Sie den **Kundendatensatz**, den Sie mit Unternehmensdaten von Leadspace anreichern möchten. Sie können die **Kundenentität** auswählen, um alle Ihre Kundenprofile anzureichern, oder eine Segmententität auswählen, um nur Kundenprofile anzureichern, die in diesem Segment enthalten sind.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Screenshot bei Auswahl des Kundendatensatzes.":::

1. Wählen Sie **Weiter** aus, und definieren Sie, welche Felder aus Ihren einheitlichen Profilen verwendet werden sollen, um nach übereinstimmenden Unternehmensdaten von Leadspace zu suchen. Das Feld **Firmenname** ist erforderlich. Für eine höhere Abgleichsgenauigkeit können bis zu zwei weitere Felder, **Firmen-Website** und **Firmenstandort**, hinzugefügt werden.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace-Feld-Zuordnungsbereich.":::

1. Wählen Sie **Weiter** aus, um die Feldzuordnung abzuschließen.

1. Geben Sie einen Namen für die Anreicherung ein und wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.


## <a name="configure-the-connection-for-leadspace"></a>Konfigurieren Sie die Verbindung für Leadspace 

Sie müssen ein Administrator sein, um Verbindungen zu konfigurieren. Wählen Sie **Verbindung hinzufügen** beim Konfigurieren einer Anreicherung *oder* gehen Sie zu **Administrator** > **Verbindungen** und wählen Sie **Einrichten** auf der Kachel „Leadspace“.

1. Wählen Sie **Los geht's** aus 

1. Geben Sie einen Namen für die Verbindung in das Feld **Anzeigename** ein.

1. Geben Sie ein gültiges Leadspace-Token an.

1. Prüfen und geben Sie Ihre Zustimmung zum **Datenschutz und Einhaltung von Vorschriften**, indem Sie das Kontrollkästchen **Ich stimme zu** markieren.

1. Wählen Sie **Überprüfen**, um die Konfiguration zu validieren.

1. Wählen Sie nach Abschluss der Überprüfung **Speichern** aus.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Verbindungskonfigurationsseite für Leadspace.":::

## <a name="enrichment-results"></a>Anreicherungsergebnisse

Nach dem Aktualisieren der Anreicherung können Sie die neu angereicherten Unternehmensdaten unter[Meine Bereicherung](enrichment-hub.md) überprüfen. Den Zeitpunkt der letzten Aktualisierung und die Anzahl der angereicherten Profile können Sie anzeigen.

Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.

Weitere Informationen finden Sie unter [Leadspace-APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Nächste Schritte

Bauen Sie auf Ihren angereicherten Kundendaten auf. Erstellen Sie [Segmente](segments.md), [Maße](measures.md), und selbst [Exportdaten](export-destinations.md), um Ihren Kunden personalisierte Erlebnisse zu bieten.

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Leadspace aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird diese Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Leadspace alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann diese Anreicherung jederzeit entfernen, um die Nutzung dieser Funktionalität einzustellen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
