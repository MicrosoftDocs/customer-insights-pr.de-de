---
title: Kundenprofile mit Identitätsdaten von LiveRamp anreichern (Vorschauversion)
description: Kundenprofile mit LiveRamp Daten anreichern.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 49bf558209ca91ab9d8db945862a57adccee1f6b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196347"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Kundenprofile mit Identitätsdaten von LiveRamp anreichern (Vorschauversion)

LiveRamp bietet deterministische Offline-Identitätsauflösung und Konsolidierung von Kundendaten. Sie können persönliche Kennungen in Ihren Kundendaten dem AbiliTec-Identitätsdiagramm zuordnen und AbiliTec-IDs erhalten. Diese IDs können Sie dann zur besseren Vereinheitlichung Ihrer Kundendaten verwenden.

## <a name="supported-countriesregions"></a>Unterstützte Länder/Regionen

Wir unterstützen derzeit die Anreicherung von Kundenprofilen mit LiveRamp-Daten nur in den USA.

## <a name="prerequisites"></a>Anforderungen

- Ein aktives LiveRamp-Abonnement. Um ein Abonnement zu erhalten, wenden Sie sich an Ihr LiveRamp-Kontoteam oder an [dynamics@liveramp.com](mailto:dynamics@liveramp.com) für mehr Informationen.

- Ein aktives AbiliTec-Abonnement mit einer Client-ID und einem Geheimnis für den Zugriff auf die API. Weitere Informationen finden Sie unter [AbiliTec API-Entwicklerhub](https://developers.liveramp.com/abilitec-api/).

- Eine LiveRamp [Verbindung](connections.md) wird von einem Administrator [konfiguriert](#configure-the-connection-for-liveramp).

## <a name="configure-the-connection-for-liveramp"></a>Konfigurieren Sie die Verbindung für LiveRamp

Sie müssen ein [Administrator](permissions.md#admin) in Customer Insights sein und über eine aktive LiveRamp-Client-ID und ein aktives Geheimnis verfügen.

1. **Verbindung hinzufügen** auswählen, wenn die Anreicherung konfiguriert wird oder gehen Sie zu **Administrator** > **Verbindungen** und wählen Sie **Einrichten** auf der Kachel LiveRamp aus.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Konfigurationsbereich zum Einrichten der Verbindung zum Dienst LiveRamp AbiliTec. ":::

1. Geben Sie einen Namen für die Verbindung und eine gültige LiveRamp-Client-ID und ein Geheimnis ein.

1. Überprüfen Sie und geben Sie Ihre Zustimmung für [Datenschutz und Einhaltung](#data-privacy-and-compliance) durch die Auswahl von **Ich stimme zu**.

1. Wählen Sie **Verifizieren**, um die Konfiguration zu bestätigen, und wählen Sie dann **Speichern**.

### <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an LiveRamp aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird solche Daten auf Ihre Anweisung übertragen, aber Sie sind dafür verantwortlich, sicherzustellen, dass LiveRamp alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben. Weitere Informationen unter [Microsoft Datenschutzbestimmungen](https://go.microsoft.com/fwlink/?linkid=396732). Ihr Dynamics 365 Customer Insights-Administrator kann diese Anreicherung jederzeit entfernen, um die Nutzung dieser Funktionalität einzustellen.

## <a name="configure-the-enrichment"></a>Anreicherungskonfiguration

1. Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus.

1. Wählen Sie **Meine Daten anreichern** auf der LiveRamp Kachel **Identität** aus.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Identitätskachel auf der Anreicherungsübersichtsseite.":::

1. Prüfen Sie die Übersicht und wählen Sie dann **Weiter** aus.

1. Wählen Sie die Verbindung aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Wählen Sie **Weiter** aus.

1. Wählen Sie **Kunden Dataset** und wählen Sie das Profil oder Segment aus, das Sie mit Identitäts-Daten von LiveRamp anreichern möchten. Die Entität *Kunde* reichert alle Ihre Kundenprofile an, währen ein Segment nur Kundenprofile anreichert, die in diesem Segment enthalten sind.

1. Definieren Sie, welche Feldtypen in Ihren einheitlichen Profilen verwendet werden sollen, um nach passenden Identitätsdaten von LiveRamp zu suchen. Mindestens eines der Felder **Name und Adresse**, **E-Mail** oder **Telefon** ist nötig. Fügen Sie für eine höhere Übereinstimmungsgenauigkeit andere Felder hinzu. Wählen Sie **Weiter** aus.

1. Ordnen Sie Ihre Felder für die Datenidentifikation von LiveRamp zu.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Datenzuordnungsoptionen für die LiveRamp-Anreicherung.":::

1. Wählen Sie **Weiter** aus, um die Feldzuordnung abzuschließen.

1. Geben Sie einen **Namen** für die Anreicherung und einen Namen für die **Ausgabeentität** an.

1. Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.

1. Wählen Sie **Ausführen**, um den Anreicherungsprozess zu starten oder zu schließen, um zur Seite **Anreicherung** zurückzukehren.

## <a name="view-enrichment-results"></a>Anreicherungsergebnisse anzeigen

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Die **Anzahl der Kunden, angereichert nach Feld** stellt Detailinformationen zur Abdeckung jedes angereicherten Felds dar.

## <a name="next-steps"></a>Nächste Schritte,

Bauen Sie auf Ihren angereicherten Kundendaten auf. Verwenden Sie die AbiliTec-IDs, um Kundenprofile in einer personenbezogenen Ansicht zu konsolidieren.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
