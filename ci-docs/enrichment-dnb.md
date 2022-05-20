---
title: Anreicherung von Firmenprofilen mit Dun & Bradstreet
description: Allgemeine Informationen über die Anreicherung von Dun & Bradstreet durch Dritte.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c738c2657d4cda213342629156ddc8104366bd8a
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755399"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Anreicherung von Firmenprofilen mit Dun & Bradstreet (Vorschau)

Dun & Bradstreet bietet kommerzielle Daten, Analysen und Erkenntnisse für Unternehmen. Sie ermöglicht es Kunden mit einheitlichen Kundenprofilen für Unternehmen, ihre Daten anzureichern. Die Anreicherung umfasst Attribute wie DUNS-Nummer, Größe der Firma, Standort, Branche und mehr.

## <a name="prerequisites"></a>Anforderungen

Um eine Dun & Bradstreet-Anreicherung zu konfigurieren, müssen die folgenden Voraussetzungen erfüllt sein:

- Sie haben eine aktive [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) Lizenz.
- Sie haben [Einheitliche Kundenprofile](customer-profiles.md) für Unternehmen.
- Eine Dun & Bradstreet [Verbindung](connections.md) wird von einem Administrator konfiguriert. Sie können sie erstellen, wenn Sie über [Administrator](permissions.md#admin) Berechtigungen und die Anmeldeinformationen von Dun & Bradstreet Connect verfügen.

## <a name="setting-up-your-dun--bradstreet-project"></a>Einrichten Ihres Dun & Bradstreet Projekts

Als lizenzierter Benutzer von Dun & Bradstreet können Sie ein Projekt in [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights) festlegen.


1. Melden Sie sich bei [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights) an. Um Anmeldeinformationen abzurufen, [stellen Sie Ihr Kennwort wieder her](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Laden Sie [unsere csv-Vorlagendatei](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) herunter, die für die Zuordnung der Customer Insights-Felder zu den entsprechenden Dun & Bradstreet-Feldern verwendet wird.

1. Laden Sie die Datei im Schritt **Daten hochladen** bei der Dun & Bradstreet Projekterstellung hoch.

1. Wählen Sie die horizontalen Punkte unter der entsprechenden **Quelle** im neu erstellten Dun & Bradstreet Projekt, um die verfügbaren Optionen zu sehen.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Screenshot der Punkte in einem Dun & Bradstreet Projekt.":::

1. Wählen Sie **S3-Details abrufen**. Speichern Sie diese Informationen an einem sicheren Ort. Sie benötigen sie, um [die Verbindung für die Anreicherung](#configure-a-connection-for-dun--bradstreet) in Customer Insights festzulegen.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Screenshot der Auswahl von S3-Informationen in einem Dun & Bradstreet-Projekt.":::

## <a name="configure-the-enrichment"></a>Anreicherungskonfiguration

1. Gehen Sie zu **Daten** > **Anreicherung**.

1. Wählen Sie **Meine Daten anreichern** auf der Dun & Bradstreet Kachel und wählen Sie **Starten**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Screenshot der Dun & Bradstreet Kachel.":::

1. Wählen Sie eine [Verbindung](connections.md) aus der Dropdownliste aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist. Wenn Sie ein Administrator sind, können Sie eine Verbindung erstellen. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Dun & Bradstreet**.

1. Wählen Sie **Verbinden mit Dun & Bradstreet**, um die Verbindung zu bestätigen.

1. Wählen Sie **Weiter** und wählen Sie das **Kundendataset**, das Sie mit Firmendaten von Dun & Bradstreet anreichern möchten. Sie können die Entität **Kunde** auswählen, um alle Ihre Kundenprofile anzureichern, oder eine Entität aus einem Segment auswählen, um nur die in diesem Segment enthaltenen vereinheitlichten Kundenprofile anzureichern.

1. Wählen Sie **Weiter** und legen Sie fest, welche Felder aus Ihren vereinheitlichten Profilen verwendet werden, um nach passenden Firmendaten von Dun & Bradstreet zu suchen. Entweder **DUNS Nummer** oder **Name der Firma** und **Land** Felder sind erforderlich. Das Feld Land unterstützt [Ländercodes mit zwei oder drei Buchstaben](https://www.iso.org/iso-3166-country-codes.html), den Landesnamen in Englisch, den Landesnamen in der Landessprache und die Telefonvorwahl. Einige allgemein gebräuchliche Ländervarianten sind:

- US: Vereinigte Staaten von Amerika, Vereinigte Staaten, USA, Amerika.
- CA: Kanada.
- GB: Vereinigtes Königreich, UK, Großbritannien, GB, Vereinigtes Königreich von Großbritannien und Nordirland, United Kingdom of Great Britain.
- AU: Australien, Commonwealth von Australien.
- FR: Frankreich, Republik Frankreich.
- DE: Deutschland, Deutsch, Deutschland, Allemagne, Bundesrepublik Deutschland, Bundesrepublik Deutschland.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet Feldzuordnungsfenster.":::

1. Wählen Sie **Weiter** aus, um die Feldzuordnung abzuschließen.

1. Geben Sie einen Namen für die Anreicherung ein und wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.

## <a name="configure-a-connection-for-dun--bradstreet"></a>Konfigurieren Sie eine Verbindung für Dun & Bradstreet

Sie müssen ein Administrator sein, um Verbindungen zu konfigurieren. Wählen Sie **Verbindung hinzufügen** beim Konfigurieren einer Anreicherung *oder* gehen Sie zu **Admin** > **Verbindungen** und wählen Sie **Einrichten** auf der Kachel Dun & Bradstreet.

1. Wählen Sie **Erste Schritte** aus.

1. Geben Sie einen Namen für die Verbindung in das Feld **Anzeigename** ein.

1. Geben Sie gültige Dun & Bradstreet Anmeldeinformationen und Dun & Bradstreet Projektdetails *Region, Ablageordnerpfad und Ablageordnername* an. Sie [erhalten diese Informationen](#setting-up-your-dun--bradstreet-project) vom Dun & Bradstreet Projekt.

1. Überprüfen Sie und geben Sie Ihre Zustimmung für **Datenschutz und Einhaltung** durch die Auswahl von **Ich stimme zu**.

1. Wählen Sie **Überprüfen**, um die Konfiguration zu validieren.

1. Wählen Sie nach Abschluss der Überprüfung **Speichern** aus.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet-Verbindungskonfigurationsseite.":::

## <a name="enrichment-results"></a>Anreicherungsergebnisse

Nach dem Aktualisieren der Anreicherung können Sie die neu angereicherten Unternehmensdaten unter[Meine Bereicherung](enrichment-hub.md) überprüfen. Den Zeitpunkt der letzten Aktualisierung und die Anzahl der angereicherten Profile können Sie anzeigen.

Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.

## <a name="next-steps"></a>Nächste Schritte,

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übermittlung von Daten an Dun & Bradstreet aktivieren, lassen Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights zu, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Dun & Bradstreet alle Ihre Datenschutz- oder Sicherheitsverpflichtungen erfüllt. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights Administrator kann diese Anreicherung jederzeit entfernen, um die Nutzung dieser Funktionalität einzustellen.

[!INCLUDE[footer-include](includes/footer-banner.md)]
