---
title: Anreicherung mit der Experian Anreicherung von Drittanbietern
description: Allgemeine Informationen zur Experian Anreicherung durch Dritte.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f5aa45316b9e0e99c7ba4389353063e9d3ce06c
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645980"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Anreichern von Kundenprofilen mit demografischen Daten von Experian (Vorschau)

Experian ist ein weltweit führender Anbieter von Kredit‑ und Marketingdienstleistungen für Verbraucher‑ und Geschäftskredite. Mit den Datenanreicherungsdiensten von Experian können Sie ein tieferes Verständnis Ihrer Kunden aufbauen, indem Sie Ihre Kundenprofile mit demografischen Daten wie Haushaltsgröße, Einkommen und mehr bereichern.

## <a name="prerequisites"></a>Anforderungen

Zum Konfigurieren von Experian müssen folgende Voraussetzungen erfüllt sein:

- Sie haben ein aktives Experian Abonnement. Um ein Abonnement zu erhalten [kontaktieren Sie Experian](https://www.experian.com/marketing-services/contact) direkt. [Weitere Informationen zu Experian Datenanreicherung](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Eine Experian Verbindung wurde bereits von einem Administrator konfiguriert *oder* Sie haben [Administrator](permissions.md#admin)-Berechtigungen. Darüber hinaus benötigen Sie die Benutzer-ID, die Partei-ID und die Modellnummer für Ihr SSH-fähiges ST-Konto (Secure Transport), das Experian für Sie erstellt hat.

## <a name="supported-countriesregions"></a>Unterstützte Länder/Regionen

Derzeit unterstützen wir die Anreicherung von Kundenprofilen nur in den USA.

## <a name="configure-the-enrichment"></a>Anreicherungskonfiguration

1. Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus.

1. Wählen Sie **Meine Daten anreichern** auf der Experian Kachel.

   > [!div class="mx-imgBorder"]
   > ![Experian-Kachel.](media/experian-tile.png "Experian tile")
   > 

1. Wählen Sie eine [Verbindung](connections.md) aus der Dropdownliste aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist. Wenn Sie ein Administrator sind, können Sie eine Verbindung herstellen, indem Sie **Verbindung hinzufügen** und dann Experian aus der Dropdown-Liste auswählen. 

1. Wählen Sie **Verbinden mit Experian**, um die Verbindungsauswahl zu bestätigen.

1.  Wählen Sie **Weiter** und wählen **Kunden-Dataset** aus, wenn Sie die demografischen Daten von Experian anreichern möchten. Sie können die **Kundenentität** auswählen, um alle Ihre Kundenprofile anzureichern, oder eine Segmententität auswählen, um nur Kundenprofile anzureichern, die in diesem Segment enthalten sind.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Screenshot bei Auswahl des Kundendatensatzes.":::

1. Wählen Sie **Weiter** und definieren Sie, welche Art von Feldern aus Ihren einheitlichen Profilen verwendet werden sollen, um nach übereinstimmenden demografischen Daten von Experian zu suchen.. Mindestens eines der Felder **Name und Adresse**, **Telefon** oder **E-Mail** ist erforderlich. Für eine höhere Übereinstimmungsgenauigkeit können bis zu zwei weitere Felder hinzugefügt werden. Diese Auswahl wirkt sich auf die Zuordnungsfelder aus, auf die Sie im nächsten Schritt zugreifen können.

    > [!TIP]
    > Weitere Schlüsselkennungsattribute die an Experian gesendet werden, werden wahrscheinlich eine höhere Übereinstimmungsrate ergeben.

1. Wählen Sie **Weiter** aus, um die Feldzuordnung zu starten.

1. Definieren Sie, welche Art von Feldern aus Ihren einheitlichen Profilen verwendet werden sollen, um nach übereinstimmenden demografischen Daten von Experian zu suchen. Erforderliche Felder sind gekennzeichnet.

1. Geben Sie einen Namen für die Anreicherung und einen Namen für die Ausgabeentität an.

1. Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.

## <a name="configure-the-connection-for-experian"></a>Konfigurieren Sie die Verbindung für Experian 

Sie müssen ein Administrator sein, um Verbindungen zu konfigurieren. Wählen Sie **Verbindung hinzufügen** beim Konfigurieren einer Anreicherung *oder* gehe zu **Administrator** > **Verbindung** und wählen Sie **Einrichten** auf der Experian Kachel aus.

1. Wählen Sie **Erste Schritte** aus.

1. Geben Sie einen Namen für die Verbindung in das Feld **Anzeigename** ein.

1. Geben Sie eine gültige Benutzer-ID, Partei-ID und Modellnummer für Ihr Experian Secure Transport-Konto ein.

1. Überprüfen Sie und geben Sie Ihre Zustimmung für **Datenschutz und Einhaltung** durch die Auswahl von **Ich stimme zu**.

1. Wählen Sie **Überprüfen**, um die Konfiguration zu validieren.

1. Wählen Sie nach Abschluss der Überprüfung **Speichern** aus.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian Verbindungskonfigurationsbereich.":::

## <a name="enrichment-results"></a>Anreicherungsergebnisse

Wählen Sie **Ausführen** aus der Befehlsleiste aus, um den Anreicherungsprozess zu starten. Sie können das System die Anreicherung auch automatisch als Teil von einer [geplante Aktualisierung](system.md#schedule-tab) ausführen lassen. Die Bearbeitungszeit hängt von der Größe Ihrer Kundendaten und den Anreicherungsprozessen ab, die für Ihr Konto eingerichtet wurden von Experian.

Nach Abschluss des Anreicherungsprozesses können Sie die neu angereicherten Kundenprofildaten unter **Meine Anreicherungen** überprüfen. Außerdem finden Sie den Zeitpunkt des letzten Updates und die Anzahl der angereicherten Profile.

Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.

## <a name="next-steps"></a>Nächste Schritte,

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten zu übermitteln an Experian, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogene Daten. Microsoft überträgt solche Daten auf Ihre Anweisung, aber Sie sind dafür verantwortlich, dass Experian alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights Administrator kann diese Anreicherung jederzeit entfernen, um die Nutzung dieser Funktionalität einzustellen.


[!INCLUDE [footer-include](includes/footer-banner.md)]
