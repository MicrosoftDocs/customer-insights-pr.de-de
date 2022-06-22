---
title: Anreicherung mit der Anreicherung von Drittanbietern HERE Technologies
description: Allgemeine Informationen über die Drittanbieter-Anreicherung von HERE Technologies.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 171ead92427924083a13e2a3d52e7a7da417c801
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953672"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Anreicherung von Kundenprofilen mit HERE Technologies (Vorschau)

HERE Technologies ist ein Unternehmen für Standortplattformen, das ortsbezogene Daten und Dienste anbietet. Die Datenanreicherungsdienste von HERE Technologies verbessern die Genauigkeit der Standortinformationen Ihrer Kunden. Es bietet Adressnormalisierung, Extraktion von Längen- und Breitengraden und mehr.

## <a name="prerequisites"></a>Anforderungen

- Ein aktives Abonnement von HERE Technologies. Um ein Abonnement zu erhalten, [Hier anmelden](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) oder [HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direkt kontaktieren. [Erfahren Sie mehr über HERE Technologies Location Enrichment.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Eine HERE [Verbindung](connections.md) wird von einem Administrator [konfiguriert](#configure-the-connection-for-here-technologies).

## <a name="configure-the-connection-for-here-technologies"></a>Konfigurieren Sie die Verbindung für HERE Technologien

Sie müssen [Administrator](permissions.md#admin) in Customer Insights sein und einen aktiven HERE Technologies API-Schlüssel besitzen.

1. Wählen Sie **Verbindung hinzufügen** beim Konfigurieren einer Anreicherung aus oder gehen Sie zu **Administrator** > **Verbindungen** und wählen Sie **Einrichten** auf der Kachel „HERE Technologies“.

1. Geben Sie einen Namen für die Verbindung und einen gültigen API-Schlüssel von HERE Technologies ein.

1. Überprüfen Sie und geben Sie Ihre Zustimmung für [Datenschutz und Einhaltung](#data-privacy-and-compliance) durch die Auswahl von **Ich stimme zu**.

1. Wählen Sie **Verifizieren**, um die Konfiguration zu bestätigen, und wählen Sie dann **Speichern**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Verbindungskonfigurationsseite für HERE Technologies.":::

### <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an HERE Technologies aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass HERE Technologies alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights Administrator kann diese Anreicherung jederzeit entfernen, um die Nutzung dieser Funktionalität einzustellen.

## <a name="configure-the-enrichment"></a>Anreicherungskonfiguration

1. Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus.

1. Wählen Sie **Meine Daten anreichern** auf der Kachel **Standort** von HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="HERE Technologies-Kachel.":::

1. Prüfen Sie die Übersicht und wählen Sie dann **Weiter** aus.

1. Wählen Sie die Verbindung aus. Wenden Sie sich an einen Administrator, falls keiner verfügbar ist.

1. Wählen Sie **Weiter** aus.

1. Wählen Sie **Kunden Dataset** und wählen Sie das Profil oder Segment aus, das Sie mit Daten von HERE Technolgies anreichern möchten. Die Entität *Kunde* reichert alle Ihre Kundenprofile an, währen ein Segment nur Kundenprofile anreichert, die in diesem Segment enthalten sind.

1. Definieren Sie, welche Art von Feldern aus Ihren einheitlichen Profilen für den Abgleich verwendet werden sollen: die primäre und/oder sekundäre Adresse. Sie können eine Feldzuordnung für beide Adressen angeben und die Profile für beide Adressen separat anreichern. Zum Beispiel für eine Privatadresse und eine Geschäftsadresse. Wählen Sie **Weiter** aus.

1. Ordnen Sie Ihre Felder den Daten von HERE Technologies zu. Die Felder **Straße 1** und **Postleitzahl** sind für die ausgewählte primäre und/oder sekundäre Adresse erforderlich. Fügen Sie für eine höhere Übereinstimmungsgenauigkeit weitere Felder hinzu.

1. Wählen Sie **Weiter** aus, um die Feldzuordnung abzuschließen.

1. Geben Sie einen **Namen** für die Anreicherung und einen Namen für die **Ausgabeentität** an.

1. Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.

1. Wählen Sie **Ausführen**, um den Anreicherungsprozess zu starten oder zu schließen, um zur Seite **Anreicherung** zurückzukehren.

## <a name="enrichment-results"></a>Anreicherungsergebnisse

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Die **Anzahl der Kunden, angereichert nach Feld** stellt Detailinformationen zur Abdeckung jedes angereicherten Felds dar.

## <a name="next-steps"></a>Nächste Schritte,

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
