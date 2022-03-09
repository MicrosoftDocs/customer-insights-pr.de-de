---
title: Anreicherung mit der Anreicherung von Drittanbietern HERE Technologies
description: Allgemeine Informationen über die Drittanbieter-Anreicherung von HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 1b46e8913c6d288b93cdf32e195b5e9387916e70
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230381"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Anreicherung von Kundenprofilen mit HERE Technologies (Vorschau)

HERE Technologies ist ein Unternehmen für Standortplattformen, das ortsbezogene Daten und Dienste anbietet. Mit den Datenanreicherungsdiensten von HERE Technologies können Sie durch Adressnormalisierung, Extraktion von Breiten- und Längengraden und mehr ein genaueres Standortverständnis Ihrer Kunden aufbauen.

## <a name="prerequisites"></a>Anforderungen

Um HERE Technologies Enrichments zu konfigurieren, müssen die folgenden Voraussetzungen erfüllt sein:

- Sie haben ein aktives HERE Technologies Abonnement. Um ein Abonnement zu erhalten, können Sie sich [hier anmelden](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) oder [direkt mit HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) in Verbindung setzen. [Erfahren Sie mehr über HERE Technologies Location Enrichment.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Eine HERE [Verbindung](connections.md) ist verfügbar *oder* Sie haben [Administrator](permissions.md#administrator) Berechtigungen und den HERE Technologien API-Schlüssel.

## <a name="configure-the-enrichment"></a>Anreicherungskonfiguration

1. Gehen Sie zu **Daten** > **Anreicherung**. 

1. Wählen Sie **Meine Daten anreichern** auf der HERE Technologies-Kachel und wählen Sie **Los geht's**.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies-Kachel.](media/HERE-tile.png "HERE Technologies Kachel")

1. Wählen Sie eine [Verbindung](connections.md) aus der Dropdownliste aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist. Wenn Sie ein Administrator sind, können Sie durch Auswahl von **Verbindung hinzufügen** eine Verbindung herstellen. Wählen Sie **HERE Technologien** aus der Dropdwon-Liste aus. 

1. Wählen Sie **Mit HERE Technologies verbinden**, um die Auswahl zu bestätigen.

1.  Wählen Sie **Weiter** und wählen Sie den **Kundendatensatz**, den Sie mit Standortdaten von HERE Technologies anreichern möchten. Sie können die **Kundenentität** auswählen, um alle Ihre Kundenprofile anzureichern, oder eine Segmententität auswählen, um nur Kundenprofile anzureichern, die in diesem Segment enthalten sind.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Screenshot bei Auswahl des Kundendatensatzes.":::

1. Wählen Sie, ob Sie Felder der primären und/oder sekundären Adresse zuordnen wollen. Sie können eine Feldzuordnung für beide Adressen angeben und die Profile für beide Adressen separat anreichern. Zum Beispiel, wenn es eine Privat- und eine Geschäftsadresse gibt. Klicken Sie auf **Weiter**.

1. Definieren Sie, welche Felder aus Ihren einheitlichen Profilen verwendet werden sollen, um nach übereinstimmenden Standortdaten von HERE Technologies zu suchen. Die Felder **Straße 1** und **Postleitzahl** sind für die ausgewählte primäre und/oder sekundäre Adresse erforderlich. Für eine höhere Abgleichsgenauigkeit können weitere Felder hinzugefügt werden.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies Anreicherungs-Konfigurationsseite.](media/enrichment-HERE-configuration.png "HERE Technologies Anreicherungs-Konfigurationsseite")

1. Wählen Sie **Weiter** aus, um die Feldzuordnung abzuschließen.

1. Benennen Sie die Anreicherung. 

1. Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.

## <a name="configure-the-connection-for-here-technologies"></a>Konfigurieren Sie die Verbindung für HERE Technologien 

Sie müssen ein Administrator sein, um Verbindungen zu konfigurieren. Wählen Sie **Verbindung hinzufügen** beim Konfigurieren einer Anreicherung *oder* gehen Sie zu **Administrator** > **Verbindungen** und wählen Sie **Einrichten** auf der Kachel „HERE Technologies“.

1. Geben Sie einen Namen für die Verbindung in das Feld **Anzeigename** ein.

1. Geben Sie einen gültigen API-Schlüssel für HERE Technologies an.

1. Überprüfen Sie und geben Sie Ihre Zustimmung für **Datenschutz und Einhaltung** durch die Auswahl von **Ich stimme zu**.

1. Wählen Sie **Überprüfen**, um die Konfiguration zu validieren.

1. Wählen Sie nach Abschluss der Überprüfung **Speichern** aus.

   > [!div class="mx-imgBorder"]
   > ![Verbindungskonfigurationsseite für HERE Technologies.](media/enrichment-HERE-connection.png "Verbindungskonfigurationsseite für HERE Technologies")

## <a name="enrichment-results"></a>Anreicherungsergebnisse

Wählen Sie **Ausführen** aus der Befehlsleiste aus, um den Anreicherungsprozess zu starten. Sie können das System die Anreicherung auch automatisch als Teil von einer [geplante Aktualisierung](system.md#schedule-tab) ausführen lassen. Die Verarbeitungszeit hängt von der Größe Ihrer Kundendaten und den API-Antwortzeiten von HERE Technologies ab.

Nach Abschluss des Anreicherungsprozesses können Sie die neu angereicherten Kundenprofildaten unter **Meine Anreicherungen** überprüfen. Außerdem finden Sie den Zeitpunkt des letzten Updates und die Anzahl der angereicherten Profile.

Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.

## <a name="next-steps"></a>Nächste Schritte,

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an HERE Technologies aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass HERE Technologies alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights Administrator kann diese Anreicherung jederzeit entfernen, um die Nutzung dieser Funktionalität einzustellen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
