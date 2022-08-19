---
title: Kundenprofile mit Standortdaten von Azure Maps anreichern (Vorschauversion)
description: Allgemeine Informationen zur Azure Maps-Erstanbieter-Anreicherung.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f14b4fc20a9a1d8842f42f9e0e656b3d8dcddcf4
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2022
ms.locfileid: "9238041"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>Kundenprofile mit Standortdaten von Azure Maps anreichern (Vorschauversion)

Azure Maps stellt standortzentrierte Daten und Dienste bereit, um Erfahrungen basierend auf Geodaten mit integrierter Standortintelligenz zu bieten. Die Datenanreicherungsdienste von Azure Maps verbessern die Genauigkeit der Standortinformationen Ihrer Kunden. Sie bieten Funktionen wie die Adressnormalisierung und die Extraktion von Breiten- und Längengraden nach Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Anforderungen

- Sie müssen ein aktives Azure Abonnement haben. Für ein Abonnement [melden Sie sich an oder fordern Sie eine kostenlose Testversion an](https://azure.microsoft.com/services/azure-maps/).

- Eine Azure Maps [Verbindung](connections.md) wird von einem Administrator [konfiguriert](#configure-the-connection-for-azure-maps).

## <a name="configure-the-connection-for-azure-maps"></a>Konfigurieren der Verbindung für Azure Maps

Sie müssen [Administrator](permissions.md#admin) in Customer Insights sein und einen aktiven Azure Maps API-Schlüssel besitzen.

1. Wählen Sie **Verbindung hinzufügen** beim Konfigurieren einer Anreicherung, oder gehen Sie zu **Administrator** > **Verbindungen**, und wählen Sie **Einrichten** auf der Azure Maps-Kachel aus.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure Maps Verbindungs-Konfigurationsseite.":::

1. Geben Sie einen Namen für die Verbindung und einen gültigen Azure Maps API-Schlüssel ein.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie **Verifizieren**, um die Konfiguration zu bestätigen, und wählen Sie dann **Speichern**.

## <a name="configure-the-enrichment"></a>Anreicherungskonfiguration

1. Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus.

1. Wählen Sie **Meine Daten anreichern** auf der Kachel **Standort** aus der Microsoft Azure Maps-Kachel aus.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Maps-Kachel.":::

1. Prüfen Sie die Übersicht und wählen Sie dann **Weiter** aus.

1. Wählen Sie die Verbindung aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Wählen Sie **Weiter** aus.

1. Wählen Sie **Kunden Dataset** und wählen Sie das Profil oder Segment aus, das Sie mit Daten von Microsoft anreichern möchten. Die Entität *Kunde* reichert alle Ihre Kundenprofile an, währen ein Segment nur Kundenprofile anreichert, die in diesem Segment enthalten sind.

1. Definieren Sie, welche Art von Feldern aus Ihren einheitlichen Profilen für den Abgleich verwendet werden sollen: die primäre und/oder sekundäre Adresse. Sie können eine Feldzuordnung für beide Adressen angeben und die Profile für beide Adressen separat anreichern. Zum Beispiel für eine Privatadresse und eine Geschäftsadresse. Wählen Sie **Weiter** aus.

1. Ordnen Sie Ihre Felder für die Standortdaten Azure Maps zu. Die Felder **Straße 1** und **Postleitzahl** sind für die ausgewählte primäre und/oder sekundäre Adresse erforderlich. Fügen Sie für eine höhere Übereinstimmungsgenauigkeit weitere Felder hinzu.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Azure Maps-Attributzuordnung.":::

1. Wählen Sie **Weiter** aus, um die Feldzuordnung abzuschließen.

1. **Erweiterte Einstellungen** bewerten, die maximale Flexibilität für erweiterte Anwendungsfälle bieten. Die folgenden Standardwerte müssen jedoch normalerweise nicht geändert werden.

   - **Art der Adressen**: Die beste Adressübereinstimmung wird zurückgegeben, auch wenn sie unvollständig ist. Um nur vollständige Adressen zu erhalten&mdash; zum Beispiel Adressen, die die Hausnummer enthalten&mdash; deaktivieren Sie alle Kontrollkästchen außer **Punktadressen**.
   - **Sprache**: Adressen werden in der Sprache basierend auf der Adressregion zurückgegeben. Um eine standardisierte Adresssprache anzuwenden, wählen Sie die Sprache aus dem Dropdown-Menü aus. Wenn Sie beispielsweise **Englisch** auswählen, wird **Kopenhagen, Dänemark** statt **København, Danmark** zurückgegeben.
   - **Maximale Anzahl von Ergebnissen**: Anzahl der Ergebnisse pro Adresse.

1. Wählen Sie **Weiter** aus.

1. Geben Sie einen **Namen** für die Anreicherung und einen Namen für die **Ausgabeentität** an.

1. Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.

1. Wählen Sie **Ausführen**, um den Anreicherungsprozess zu starten oder zu schließen, um zur Seite **Anreicherung** zurückzukehren.

## <a name="view-enrichment-results"></a>Anreicherungsergebnisse anzeigen

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Die **Anzahl der Kunden, angereichert nach Feld** stellt Detailinformationen zur Abdeckung jedes angereicherten Felds dar.

## <a name="next-steps"></a>Nächste Schritte,

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
