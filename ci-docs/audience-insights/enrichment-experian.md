---
title: Anreicherung mit der Drittanbieter-Anreicherung Experian
description: Allgemeine Informationen über die Drittanbieter-Anreicherung von Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896372"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Kundenprofile mit demografischen Daten aus Experian anreichern (Vorschau)

Experian ist ein weltweit führender Anbieter von Kredit- und Marketingdienstleistungen für Verbraucher- und Geschäftskredite. Mit den Datenanreicherungsdiensten von Experian können Sie ein tieferes Verständnis Ihrer Kunden aufbauen, indem Sie Ihre Kundenprofile mit demografischen Daten wie Haushaltsgröße, Einkommen und mehr bereichern.

## <a name="prerequisites"></a>Voraussetzungen

Für das Konfigurieren von Experian an müssen folgende Voraussetzungen erfüllt sein:

- Sie haben ein aktives Experian-Abonnement. Um ein Abonnement zu erhalten, [wenden Sie sich direkt an Experian](https://www.experian.com/marketing-services/contact). [Weitere Informationen zur Datenanreicherung Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Eine Experian-Verbindung wurde bereits von einem Administrator konfiguriert *oder* Sie haben [Administrator](permissions.md#administrator)-Berechtigungen. Darüber hinaus benötigen Sie die Benutzer-ID, die Party-ID und die Modellnummer für Ihr SSH-fähiges ST-Konto (Secure Transport), das Experian für Sie erstellt hat.

## <a name="configure-the-enrichment"></a>Anreicherungskonfiguration

1. Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus.

1. Wählen Sie **Meine Daten anreichern** auf der Experian-Kachel.

   > [!div class="mx-imgBorder"]
   > ![Experian-Kachel](media/experian-tile.png "Experian-Kachel")
   > 

1. Wählen Sie eine [Verbindung](connections.md) aus der Dropdownliste aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist. Wenn Sie ein Administrator sind, können Sie durch Auswahl von **Verbindung hinzufügen** eine Verbindung herstellen und „Experian“ aus dem Dropdownmenü auswählen. 

1. Wählen Sie **Mit Experian verbinden**, um die Verbindungsauswahl zu bestätigen.

1.  Wählen Sie **Weiter** und wählen Sie den **Kundendatensatz**, den Sie mit Demografiedaten von Experian anreichern möchten. Sie können die **Kundenentität** auswählen, um alle Ihre Kundenprofile anzureichern, oder eine Segmententität auswählen, um nur Kundenprofile anzureichern, die in diesem Segment enthalten sind.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Screenshot bei Auswahl des Kundendatensatzes.":::

1. Wählen Sie **Weiter** aus, und definieren Sie, welche Art von Feldern aus Ihren einheitlichen Profilen verwendet werden soll, um nach übereinstimmenden demografischen Daten von Experian zu suchen. Mindestens eines der Felder **Name und Adresse**, **Telefon** oder **E-Mail** ist erforderlich. Für eine höhere Übereinstimmungsgenauigkeit können bis zu zwei weitere Felder hinzugefügt werden. Diese Auswahl wirkt sich auf die Zuordnungsfelder aus, auf die Sie im nächsten Schritt zugreifen können.

    > [!TIP]
    > Weitere an Experian gesendete Schlüsselbezeichnerattribute führen wahrscheinlich zu einer höheren Übereinstimmungsrate.

1. Wählen Sie **Weiter** aus, um die Feldzuordnung zu starten.

1. Definieren Sie, welche Felder aus Ihren einheitlichen Profilen verwendet werden sollen, um nach übereinstimmenden demografischen Daten von Experian zu suchen. Erforderliche Felder sind gekennzeichnet.

1. Geben Sie einen Namen für die Anreicherung und einen Namen für die Ausgabeentität an.

1. Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.

## <a name="configure-the-connection-for-experian"></a>Konfigurieren Sie die Verbindung für Experian 

Sie müssen ein Administrator sein, um Verbindungen zu konfigurieren. Wählen Sie **Verbindung hinzufügen** beim Konfigurieren einer Anreicherung *oder* gehen Sie zu **Administrator** > **Verbindungen** und wählen Sie **Einrichten** auf der Kachel „Experian“.

1. Wählen Sie **Erste Schritte** aus.

1. Geben Sie einen Namen für die Verbindung in das Feld **Anzeigename** ein.

1. Geben Sie eine gültige Benutzer-ID, Party-ID und Modellnummer für Ihr Experian Secure Transport-Konto ein.

1. Prüfen und geben Sie Ihre Zustimmung zum **Datenschutz und Einhaltung von Vorschriften**, indem Sie das Kontrollkästchen **Ich stimme zu** markieren.

1. Wählen Sie **Überprüfen**, um die Konfiguration zu validieren.

1. Wählen Sie nach Abschluss der Überprüfung **Speichern** aus.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Verbindungskonfigurationsbereich für Experian.":::

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
