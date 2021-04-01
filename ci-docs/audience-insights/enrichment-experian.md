---
title: Anreicherung mit der Drittanbieter-Anreicherung Experian
description: Allgemeine Informationen über die Drittanbieter-Anreicherung von Experian.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4d4723e8f793ee857c4f5204a42be8338c71d4c3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597786"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Kundenprofile mit demografischen Daten aus Experian anreichern (Vorschau)

Experian ist ein weltweit führender Anbieter von Kredit- und Marketingdienstleistungen für Verbraucher- und Geschäftskredite. Mit den Datenanreicherungsdiensten von Experian können Sie ein tieferes Verständnis Ihrer Kunden aufbauen, indem Sie Ihre Kundenprofile mit demografischen Daten wie Haushaltsgröße, Einkommen und mehr bereichern.

## <a name="prerequisites"></a>Voraussetzungen

Für das Konfigurieren von Experian an müssen folgende Voraussetzungen erfüllt sein:

- Sie haben ein aktives Experian-Abonnement. Um ein Abonnement zu erhalten, [wenden Sie sich direkt an Experian](https://www.experian.com/marketing-services/contact). [Weitere Informationen zur Datenanreicherung Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Sie haben die Benutzer-ID, die Party-ID und die Modellnummer für Ihr SSH-fähiges Secure Transport (ST)-Konto, das Experian für Sie erstellt hat.
- Sie haben [Administrator](permissions.md#administrator) Berechtigungen in Zielgruppen-Insights.

## <a name="configuration"></a>Konfiguration

1. Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus.

1. Wählen Sie **Meine Daten anreichern** auf der Experian-Kachel.

   > [!div class="mx-imgBorder"]
   > ![Experian-Kachel](media/experian-tile.png "Experian-Kachel")

1. Wählen Sie **Los geht's** und geben Sie die Benutzer-ID, die Partei-ID und die Modellnummer für Ihr Experian Secure Transport-Konto ein. Prüfen und geben Sie Ihre Zustimmung zum **Datenschutz und Einhaltung von Vorschriften**, indem Sie das Kontrollkästchen **Ich stimme zu** markieren. Bestätigen Sie alle Eingaben durch Auswahl von **Anwenden**.

## <a name="map-your-fields"></a>Ihre Felder zuordnen

1.  Wählen Sie **Daten hinzufügen** und dann den **Kundendatensatz**, den Sie mit demografischen Daten von Experian anreichern möchten. Sie können die **Kundenentität** auswählen, um alle Ihre Kundenprofile anzureichern, oder eine Segmententität auswählen, um nur Kundenprofile anzureichern, die in diesem Segment enthalten sind.

1. Wählen Sie Ihre Schlüsselkennungen **Name und Adresse**, **E-Mail**, oder **Telefon** aus, um sie zur Identitätsauflösung an Experian zu senden.

   > [!TIP]
   > Weitere an Experian gesendete Schlüsselbezeichnerattribute führen wahrscheinlich zu einer höheren Übereinstimmungsrate.

1. Wählen Sie **Weiter** und ordnen Sie die entsprechenden Attribute Ihrer einheitlichen Kundenentität den ausgewählten Schlüsselbezeichnerfeldern zu.

1. Wählen Sie **Attribut hinzufügen**, um zusätzliche Attribute zuzuordnen, die Sie an Experian senden möchten.

1.  Wählen Sie **Speichern** aus, um die Feldzuordnung abzuschließen.

    > [!div class="mx-imgBorder"]
    > ![Experian-Feldzuordnung](media/experian-field-mapping.png "Experian-Feldzuordnung")

## <a name="enrichment-results"></a>Anreicherungsergebnisse

Wählen Sie **Ausführen** aus der Befehlsleiste aus, um den Anreicherungsprozess zu starten. Sie können das System die Anreicherung auch automatisch als Teil von einer [geplante Aktualisierung](system.md#schedule-tab) ausführen lassen. Die Bearbeitungszeit hängt von der Größe Ihrer Kundendaten und den von Experian für Ihr Konto eingerichteten Anreicherungsprozessen ab.

Nach Abschluss des Anreicherungsprozesses können Sie die neu angereicherten Kundenprofildaten unter **Meine Anreicherungen** überprüfen. Außerdem finden Sie den Zeitpunkt des letzten Updates und die Anzahl der angereicherten Profile.

Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.

## <a name="next-steps"></a>Nächste Schritte

Bauen Sie auf Ihren angereicherten Kundendaten auf. Erstellen Sie [Segmente](segments.md), [Maße](measures.md), und selbst [Exportdaten](export-destinations.md), um Ihren Kunden personalisierte Erlebnisse zu bieten.

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Experian aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird diese Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, sicherzustellen, dass Experian alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann diese Anreicherung jederzeit entfernen, um die Nutzung dieser Funktionalität einzustellen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]