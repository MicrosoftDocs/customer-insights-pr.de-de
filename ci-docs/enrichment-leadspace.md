---
title: Unternehmensprofile mit Leadspace anreichern (Vorschauversion)
description: Allgemeine Informationen über die Drittanbieter-Anreicherung von Leadspace.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b58532a541ee22a5e34d0af1a3334ccbd53627b2
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081041"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Unternehmensprofile mit Leadspace anreichern (Vorschauversion)

Leadspace ist ein Data Science-Unternehmen, das eine B2B-Kundendatenplattform bereitstellt. Es ermöglicht Umgebungen mit einheitlichen Kundenprofilen basierend auf Konten, ihre Daten anzureichern. Bereichern von *Kundenprofilen* mit Attributen wie Unternehmensgröße, Standort oder Branche. Bereichern von *Kontaktprofilen* mit Attributen wie Titel, Persona oder E-Mail-Verifizierung.

## <a name="prerequisites"></a>Anforderungen

- Eine aktive Leadspace-Lizenz.
- [Unified customer profiles](customer-profiles.md) basierend auf Konten.
- Eine Leadspace [Verbindung](connections.md) wird von einem Administrator [konfiguriert](#configure-the-connection-for-leadspace). Kontaktieren Sie [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) direkt für Details über ihr Produkt.

## <a name="configure-the-connection-for-leadspace"></a>Konfigurieren Sie die Verbindung für Leadspace

Sie müssen ein [Administrator](permissions.md#admin) in Customer Insights sein und über den unbefristeten Schlüssel verfügen (im Folgenden **Leadspace-Token**).

1. Wählen Sie **Verbindung hinzufügen** beim Konfigurieren einer Anreicherung oder gehen Sie zu **Administrator** > **Verbindungen** und wählen Sie **Einrichten** auf der Kachel Leadspace.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Verbindungskonfigurationsseite für Leadspace.":::

1. Geben Sie einen Namen für die Verbindung und ein gültiges Leadspace-Token ein.

1. Überprüfen Sie und geben Sie Ihre Zustimmung für [Datenschutz und Einhaltung](#data-privacy-and-compliance) durch die Auswahl von **Ich stimme zu**.

1. Wählen Sie **Verifizieren**, um die Konfiguration zu bestätigen, und wählen Sie dann **Speichern**.

### <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Leadspace aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird diese Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Leadspace alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights Administrator kann diese Anreicherung jederzeit entfernen, um die Nutzung dieser Funktionalität einzustellen.

## <a name="configure-the-enrichment"></a>Anreicherungskonfiguration

1. Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus.

1. Wählen Sie **Meine Daten anreichern** auf der Leadspace-Kachel **Unternehmensdaten** aus.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Screenshot der Leadspace-Kachel.":::

1. Prüfen Sie die Übersicht und wählen Sie dann **Weiter** aus.

1. Wählen Sie die Verbindung aus. Wenden Sie sich an einen Administrator, falls keiner verfügbar ist.

1. Wählen Sie **Weiter** aus.

1. Wählen Sie **Kunden Dataset** und wählen Sie das Profil oder Segment aus, das Sie mit Unternehmens-Daten von Leadspace anreichern möchten. Die Entität *Kunde* reichert alle Ihre Kundenprofile an, währen ein Segment nur Kundenprofile anreichert, die in diesem Segment enthalten sind.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Screenshot bei Auswahl des Kundendatensatzes.":::

1. Definieren Sie, welche Art von Feldern aus Ihren einheitlichen Profilen für den Abgleich verwendet werden sollen: die primäre und/oder sekundäre Adresse. Sie können eine Feldzuordnung für beide Adressen angeben und die Profile für beide Adressen separat anreichern. Zum Beispiel für eine Privatadresse und eine Geschäftsadresse. Wählen Sie **Weiter** aus.

1. Ordnen Sie Ihre Firmenfelder den Firmendaten von Leadspace zu. Das Feld **Firmenname** ist erforderlich. Für eine höhere Abgleichsgenauigkeit können bis zu zwei weitere Felder, **Firmen-Website** und **Firmenstandort**, hinzugefügt werden.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace-Feld-Zuordnungsbereich.":::

1. Wählen Sie **Weiter** aus, um die Feldzuordnung abzuschließen.

1. Aktivieren Sie das Kontrollkästchen, wenn Sie *Kontaktprofile* haben, die Sie bereichern möchten. Customer Insights wird die erforderlichen Felder automatisch zuordnen.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Anreicherung von Leadspace-Kontaktdatensätzen.":::

1. Wählen Sie **Weiter** aus.

1. Geben Sie einen **Namen** für die Anreicherung und einen Namen für die **Ausgabeentität** an.

1. Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.

1. Wählen Sie **Ausführen**, um den Anreicherungsprozess zu starten oder zu schließen, um zur Seite **Anreicherung** zurückzukehren.

## <a name="view-enrichment-results"></a>Anreicherungsergebnisse anzeigen

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Weitere Informationen finden Sie unter [Leadspace-APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Nächste Schritte,

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
