---
title: Anreichern von Kundenprofilen mit demografischen Daten von Experian (Vorschauversion)
description: Allgemeine Informationen zur Experian Anreicherung durch Dritte.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: fccb37cde3f05a70009c18b6c52db01a5ede094d
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237995"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Anreichern von Kundenprofilen mit demografischen Daten von Experian (Vorschauversion)

Experian ist ein weltweit führender Anbieter von Kredit‑ und Marketingdienstleistungen für Verbraucher‑ und Geschäftskredite. Mit den Datenanreicherungsdiensten von Experian können Sie ein tieferes Verständnis Ihrer Kunden aufbauen, indem Sie Ihre Kundenprofile mit demografischen Daten wie Haushaltsgröße, Einkommen und mehr bereichern.

## <a name="supported-countriesregions"></a>Unterstützte Länder/Regionen

Derzeit unterstützen wir die Anreicherung von Kundenprofilen nur in den USA.

## <a name="prerequisites"></a>Anforderungen

- Ein aktives Experian Abonnement. Um ein Abonnement zu erhalten [kontaktieren Sie Experian](https://www.experian.com/marketing-services/contact) direkt. [Weitere Informationen zu Experian Datenanreicherung](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Eine Experian [Verbindung](connections.md) wird von einem Administrator [konfiguriert](#configure-the-connection-for-experian).

- Experian Benutzer-ID, die Partei-ID und die Modellnummer für Ihr SSH-fähiges ST-Konto (Secure Transport), das Experian für Sie erstellt hat.

## <a name="configure-the-connection-for-experian"></a>Konfigurieren Sie die Verbindung für Experian

Sie müssen ein [Administrator](permissions.md#admin) in Customer Insights sein und über eine Experian Benutzer-ID, Partei-ID und Modellnummer verfügen.

1. Wählen Sie **Verbindung hinzufügen** beim Konfigurieren einer Anreicherung oder gehen Sie zu **Administrator** > **Verbindungen** und wählen Sie **Einrichten** auf der Experian Kachel aus.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian Verbindungskonfigurationsbereich.":::

1. Geben Sie einen Namen für die Verbindung und eine gültige Benutzer-ID, Partei-ID und Modellnummer für Ihr Experian Secure Transport-Konto ein.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie **Verifizieren**, um die Konfiguration zu bestätigen, und wählen Sie dann **Speichern**.

## <a name="configure-the-enrichment"></a>Anreicherungskonfiguration

1. Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus.

1. Wählen Sie **Meine Daten anreichern** auf der Experian Kachel **Demographie** aus.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian Kachel auf der Anreicherungsübersichtsseite.":::

1. Prüfen Sie die Übersicht und wählen Sie dann **Weiter** aus.

1. Wählen Sie die Verbindung aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Wählen Sie **Weiter** aus.

1. Wählen Sie **Kunden Dataset** und wählen Sie das Profil oder Segment aus, das Sie mit Demografie-Daten von Experian anreichern möchten. Die Entität *Kunde* reichert alle Ihre Kundenprofile an, währen ein Segment nur Kundenprofile anreichert, die in diesem Segment enthalten sind.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Screenshot bei Auswahl des Kundendatensatzes.":::

1. Definieren Sie, welche Feldtypen in Ihren einheitlichen Profilen verwendet werden sollen, um nach passenden Demografiedaten von Experian zu suchen. Mindestens eines der Felder **Name und Adresse**, **Telefon** oder **E-Mail** ist erforderlich. Fügen Sie für eine höhere Übereinstimmungsgenauigkeit andere Felder hinzu. Wählen Sie **Weiter** aus.

1. Ordnen Sie Ihre Felder den Demografie-Daten von Experian zu.

1. Wählen Sie **Weiter** aus, um die Feldzuordnung abzuschließen.

1. Geben Sie einen **Namen** für die Anreicherung und einen Namen für die **Ausgabeentität** an.

1. Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.

1. Wählen Sie **Ausführen**, um den Anreicherungsprozess zu starten oder zu schließen, um zur Seite **Anreicherung** zurückzukehren.

## <a name="view-enrichment-results"></a>Anreicherungsergebnisse anzeigen

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Die **Anzahl der Kunden, angereichert nach Feld** stellt Detailinformationen zur Abdeckung jedes angereicherten Felds dar.

## <a name="next-steps"></a>Nächste Schritte,

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
