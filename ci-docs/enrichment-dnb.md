---
title: Anreicherung von Firmenprofilen mit Dun & Bradstreet (Vorschauversion)
description: Allgemeine Informationen über die Anreicherung von Dun & Bradstreet durch Dritte.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: e89b64774dcb519a071dd3d403473807a50e7f33
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237903"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Anreicherung von Firmenprofilen mit Dun & Bradstreet (Vorschauversion)

Dun & Bradstreet bietet kommerzielle Daten, Analysen und Erkenntnisse für Unternehmen. Sie ermöglicht es Kunden mit einheitlichen Kundenprofilen für Unternehmen, ihre Daten anzureichern. Die Anreicherung umfasst Attribute wie DUNS-Nummer, Größe der Firma, Standort, Branche und mehr.

## <a name="prerequisites"></a>Anforderungen

- Eine aktive [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) Lizenz.
- [Unified customer profiles](customer-profiles.md) für Unternehmen.
- Ein Dun & Bradstreet [Projekt](#set-up-your-dun--bradstreet-project) ist eingerichtet.
- Eine Dun & Bradstreet [Verbindung](connections.md) wird von einem Administrator [konfiguriert](#configure-a-connection-for-dun--bradstreet).

## <a name="set-up-your-dun--bradstreet-project"></a>Einrichten Ihres Dun & Bradstreet Projekts

Als lizenzierter Benutzer von Dun & Bradstreet können Sie ein Projekt in [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights) festlegen.

1. Melden Sie sich bei [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights) an. Um Anmeldeinformationen abzurufen, [stellen Sie Ihr Kennwort wieder her](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Laden Sie [unsere csv-Vorlagendatei](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) herunter, die für die Zuordnung der Customer Insights-Felder zu den entsprechenden Dun & Bradstreet-Feldern verwendet wird.

1. Laden Sie die Datei im Schritt **Daten hochladen** bei der Dun & Bradstreet Projekterstellung hoch.

1. Wählen Sie die horizontalen Punkte unter der entsprechenden **Quelle** im neu erstellten Dun & Bradstreet Projekt, um die verfügbaren Optionen zu sehen.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Screenshot der Punkte in einem Dun & Bradstreet Projekt.":::

1. Wählen Sie **S3-Details abrufen**. Speichern Sie diese Informationen an einem sicheren Ort. Sie benötigen sie, um [die Verbindung für die Anreicherung](#configure-a-connection-for-dun--bradstreet) in Customer Insights festzulegen.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Screenshot der Auswahl von S3-Informationen in einem Dun & Bradstreet-Projekt.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Konfigurieren Sie eine Verbindung für Dun & Bradstreet

Sie können sie erstellen, wenn Sie über [Administrator](permissions.md#admin) Berechtigungen in Customer Insights und die Anmeldeinformationen von Dun & Bradstreet Connect verfügen.

1. Wählen Sie **Verbindung hinzufügen** beim Konfigurieren einer Anreicherung aus oder gehen Sie zu **Admin** > **Verbindungen** und wählen Sie **Einrichten** auf der Kachel Dun & Bradstreet.

1. Geben Sie einen Namen für die Verbindung ein.

1. Geben Sie gültige Dun & Bradstreet Anmeldeinformationen und Dun & Bradstreet Projektdetails *Region, Ablageordnerpfad und Ablageordnername* an. Sie [erhalten diese Informationen](#set-up-your-dun--bradstreet-project) vom Dun & Bradstreet Projekt.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie **Verifizieren**, um die Konfiguration zu bestätigen, und wählen Sie dann **Speichern**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet-Verbindungskonfigurationsseite.":::

## <a name="supported-countries-or-regions"></a>Unterstützte Länder oder Regionen

Wir unterstützen derzeit die folgenden Länder-/Regionsoptionen: Kanada (Englisch) oder Vereinigte Staaten (Englisch).

## <a name="configure-the-enrichment"></a>Anreicherungskonfiguration

1. Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus.

1. Wählen Sie **Meine Daten anreichern** auf der Dun & Bradstreet-Kachel **Unternehmensdaten** aus.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Screenshot der Dun & Bradstreet Kachel.":::

1. Prüfen Sie die Übersicht und wählen Sie dann **Weiter** aus.

1. Verbindung auswählen und bestätigen. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Wählen Sie **Weiter** aus.

1. Wählen Sie **Kunden Dataset** und wählen Sie das Profil oder Segment aus, das Sie mit Unternehmens-Daten von Dun & Bradstreet anreichern möchten. Die Entität *Kunde* reichert alle Ihre Kundenprofile an, währen ein Segment nur Kundenprofile anreichert, die in diesem Segment enthalten sind.

1. Definieren Sie, welche Feldtypen in Ihren einheitlichen Profilen verwendet werden sollen, um nach passenden Firmendaten von Dun & Bradstreet zu suchen. Mindestens eines der Felder **Name und Adresse**, **Telefon** oder **E-Mail** ist erforderlich.

1. Klicken Sie auf **Weiter**.

1. Ordnen Sie Ihre Firmenfelder den Firmendaten von Dun & Bradstreet zu. Entweder **DUNS Nummer** oder **Name der Firma** und **Land** Felder sind erforderlich.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet Feldzuordnungsfenster.":::

1. Wählen Sie **Weiter** aus, um die Feldzuordnung abzuschließen.

1. Geben Sie einen **Namen** für die Anreicherung und einen Namen für die **Ausgabeentität** an.

1. Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.

1. Wählen Sie **Ausführen**, um den Anreicherungsprozess zu starten oder zu schließen, um zur Seite **Anreicherung** zurückzukehren.

## <a name="view-enrichment-results"></a>Anreicherungsergebnisse anzeigen

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Nächste Schritte,

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
