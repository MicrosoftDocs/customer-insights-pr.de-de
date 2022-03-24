---
title: Anreichern von Kundenprofilen mit Standortdaten aus Azure Maps
description: Allgemeine Informationen zur Azure Maps-Erstanbieter-Anreicherung.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 2cc44f7b453d2aca328c397b14787c8a02c5e490
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376645"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Anreicherung von Kundenprofilen mit Azure Maps (Vorschau)

Azure Maps bietet standortbezogene Daten und Dienste, um Erfahrungen basierend auf räumlichen Daten mit integrierter Standortintelligenz bereitzustellen. Die Datenanreicherungsdienste von Azure Maps verbessern die Genauigkeit der Standortinformationen Ihrer Kunden. Sie bieten Funktionen wie die Adressnormalisierung und die Extraktion von Breiten- und Längengraden nach Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Anforderungen

Um die Azure Maps-Datenanreicherung zu konfigurieren, müssen die folgenden Voraussetzungen erfüllt sein:

- Sie haben ein aktives Azure Maps-Abonnement. Um ein Abonnement zu erhalten, können Sie [sich registrieren oder eine kostenlose Testversion erhalten](https://azure.microsoft.com/services/azure-maps/).

- Eine Azure Maps-[Verbindung](connections.md) ist verfügbar, *oder* Sie haben [Administratorberechtigungen](permissions.md#admin) und einen aktiven Azure Maps-API-Schlüssel.

## <a name="configure-the-enrichment"></a>Anreicherungskonfiguration

1. Gehen Sie zu **Daten** > **Anreicherung**. 

1. Wählen Sie in der Kachel **Standort** **Meine Daten anreichern**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Maps-Kachel.":::

1. Wählen Sie eine [Verbindung](connections.md) aus der Dropdownliste aus. Wenden Sie sich an einen Administrator, wenn keine Azure Maps-Verbindung verfügbar ist. Wenn Sie ein Administrator sind, können Sie [die Verbindung für Azure Maps konfigurieren](#configure-the-connection-for-azure-maps). 

1. Wählen Sie **Weiter** aus, um die Auswahl zu bestätigen.

1. Wählen Sie das **Kundendataset**, das Sie mit Standortdaten aus Azure Maps anreichern möchten. Sie können die Entität **Kunde** auswählen, um all Ihre vereinheitlichten Kundenprofile anzureichern. Oder wählen Sie eine Segmententität aus, um nur die in diesem Segment enthaltenen Kundenprofile anzureichern.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Screenshot bei Auswahl des Kundendatasets.":::

1. Wählen Sie aus, ob Sie Felder der primären und/oder sekundären Adresse zuordnen möchten. Sie können eine Feldzuordnung für beide Adressen angeben und die Profile für beide Adressen separat anreichern, z. B. für eine Privatadresse und eine Geschäftsadresse. Wählen **Weiter** aus.

1. Definieren Sie, welche Art von Feldern aus Ihren vereinheitlichten Profilen verwendet werden sollen, um nach übereinstimmenden Standortdaten aus Azure Maps zu suchen. Die Felder **Straße 1** und **Postleitzahl** sind für die ausgewählte primäre oder sekundäre Adresse erforderlich. Um eine höhere Übereinstimmungsgenauigkeit zu erzielen, können Sie weitere Felder hinzufügen.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Azure Maps Anreicherungs-Konfigurationsseite.":::

1. Wählen Sie **Weiter** aus, um die Feldzuordnung abzuschließen.

1. Bewerten Sie, ob Sie **Erweiterte Einstellungen** ändern möchten. Diese werden bereitgestellt, um maximale Flexibilität für erweiterte Anwendungsfälle zu bieten, aber die Standardwerte sind in den meisten Fällen ausreichend:
   - **Adresstypen**: Das Standardverhalten ist, dass die Anreicherung die beste Adressübereinstimmung zurückgibt, auch wenn sie unvollständig ist. Um nur vollständige Adressen zu erhalten – zum Beispiel Adressen, die die Hausnummer enthalten – deaktivieren Sie alle Kontrollkästchen außer **Punktadressen**. 
   - **Sprache**: Standardmäßig werden Adressen in der Sprache der Region zurückgegeben, zu der die Adresse bestimmt wurde. Um eine standardisierte Adresssprache anzuwenden, wählen Sie die Sprache aus dem Dropdown-Menü aus. Wählen Sie zum Beispiel **Englisch** aus, wird **Copenhagen, Denmark** anstelle von **København, Danmark** zurückgegeben.

1. Benennen Sie die Anreicherung.

1. Überprüfen Sie die Einstellungen, und wählen Sie dann **Anreicherung speichern** aus.

## <a name="configure-the-connection-for-azure-maps"></a>Konfigurieren der Verbindung für Azure Maps

Sie müssen ein Administrator für Zielgruppenerkenntnisse sein, um Verbindungen zu konfigurieren. Wählen Sie **Verbindung hinzufügen** beim Konfigurieren einer Anreicherung, oder gehen Sie zu **Administrator** > **Verbindungen**, und wählen Sie **Einrichten** auf der Azure Maps-Kachel aus.

1. Geben Sie im Feld **Anzeigename** einen Namen für die Verbindung ein.

1. Geben Sie einen gültigen Azure Maps-API-Schlüssel an.

1. Prüfen und geben Sie Ihre Zustimmung zum **Datenschutz und Einhaltung von Vorschriften**, indem Sie das Kontrollkästchen **Ich stimme zu** markieren.

1. Wählen Sie **Überprüfen**, um die Konfiguration zu validieren.

1. Wählen Sie nach Abschluss der Überprüfung **Speichern** aus.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure Maps Verbindungs-Konfigurationsseite.":::

## <a name="enrichment-results"></a>Anreicherungsergebnisse

Wählen Sie **Ausführen** aus der Befehlsleiste aus, um den Anreicherungsprozess zu starten. Sie können das System die Anreicherung auch automatisch als Teil von einer [geplante Aktualisierung](system.md#schedule-tab) ausführen lassen. Die Bearbeitungszeit hängt von der Größe Ihrer Kundendaten und den API-Antwortzeiten ab.

Nachdem der Anreicherungsprozess abgeschlossen ist, können Sie die neu angereicherten Kundenprofildaten unter **Meine Anreicherungen** anzeigen. Außerdem finden Sie den Zeitpunkt des letzten Updates und die Anzahl der angereicherten Profile.

Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.

## <a name="next-steps"></a>Nächste Schritte,

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten an Azure Maps zu übermitteln, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogene Daten. Microsoft überträgt solche Daten auf Ihre Anweisung, aber Sie sind dafür verantwortlich, dass Azure Maps alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzbestimmungen](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann diese Anreicherung jederzeit entfernen, um die Nutzung dieser Funktionalität einzustellen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
