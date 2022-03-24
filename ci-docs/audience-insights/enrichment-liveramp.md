---
title: LiveRamp-Identifizierungsdatenanreicherung
description: Kundenprofile mit LiveRamp Daten anreichern.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ee65cb49447df61dd5c298a84ad21bc119ead558
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373027"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Kundenprofile mit Identitätsdaten von LiveRamp anreichern (Vorschau) 

LiveRamp bietet deterministische Offline-Identitätsauflösung und Konsolidierung von Kundendaten. Sie können persönliche Kennungen in Ihren Kundendaten dem AbiliTec-Identitätsdiagramm zuordnen und AbiliTec-IDs erhalten. Diese IDs können Sie dann zur besseren Vereinheitlichung Ihrer Kundendaten verwenden. 

## <a name="prerequisites"></a>Anforderungen 

Zum Konfigurieren der Anreicherung müssen die folgenden Voraussetzungen erfüllt sein: 

- Sie verfügen über ein aktives LiveRap-Abonnement. Um ein Abonnement zu erhalten, wenden Sie sich an Ihr LiveRamp-Kontoteam oder an [dynamics@liveramp.com](mailto:dynamics@liveramp.com) für mehr Informationen.   

- Ein aktives AbiliTec-Abonnement mit einer Client-ID und einem Geheimnis für den Zugriff auf die API. Weitere Informationen finden Sie unter [AbiliTec API-Entwicklerhub](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Unterstützte Länder/Regionen 

Wir unterstützen derzeit die Anreicherung von Kundenprofilen mit LiveRamp-Daten nur in den USA. 

## <a name="configure-the-enrichment"></a>Anreicherungskonfiguration 

1. Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus. 

1. Wählen Sie **Meine Daten anreichern** auf der Kachel **Identität** aus. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Identitätskachel auf der Anreicherungsübersichtsseite.":::

1. Wählen Sie eine [Verbindung](connections.md) aus der Dropdownliste aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist. Wenn Sie ein Administrator sind, können Sie eine Verbindung herstellen, indem Sie **Verbindung hinzufügen** auswählen. Wählen Sie aus der Dropdown-Liste **LiveRamp** aus. 

1. Wählen Sie **Weiter** und wählen Sie **Dataset anpassen**, wenn sie die Indentitätsdaten von LiveRamp anreichern möchten. Wählen Sie die Entiät *Anpassen*, um alle Ihre Kundenprofile anzureichern, oder wählen Sie eine Entität *Segment*, um nur Kundenprofile anzureichern, die in diesem Segment enthalten sind. 

1. Wählen Sie **Weiter** und definieren Sie, welche Art von Feldern aus Ihren einheitlichen Profilen verwendet werden sollen, um nach übereinstimmenden Identitätsdaten von LiveRamp zu suchen. Mindestens eines der Felder **Name und Adresse**, **Telefon** oder **Email** ist nötig. 

   > [!TIP]
   > Je mehr Schlüsselkennungen und Felder Sie zuordnen, desto höher ist die Wahrscheinlichkeit einer höheren Übereinstimmungsrate 

1. Ordnen Sie die Felder aus Ihrer einheitlichen Entität *Benutzerdefiniert* zu,  die für den Abgleich mit dem AbiliTec-ID-Diagramm von LiveRamp verwendet wird. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Datenzuordnungsoptionen für die LiveRamp-Anreicherung.":::

1. Wählen Sie **Weiter** aus, um die Feldzuordnung abzuschließen. 

1. Geben Sie einen **Namen** für die Anreicherung und einen Namen für die **Ausgabeentität** an. 

1. Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben. 

## <a name="configure-the-connection-for-liveramp"></a>Konfigurieren Sie die Verbindung für LiveRamp 

Sie müssen ein Administrator sein, um [Verbindungen zu konfigurieren](connections.md). **Verbindung hinzufügen** auswählen, wenn die Anreicherung konfiguriert wird oder gehen Sie zu **Administrator** > **Verbindungen** und wählen Sie **Einrichten** auf der Kachel **LiveRamp** aus. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Konfigurationsbereich zum Einrichten der Verbindung zum Dienst LiveRamp AbiliTec. ":::

1. Geben Sie für den **Anzeigename** den Namen der Verbindung ein. 

1. Geben Sie eine gültige LiveRamp-Client-ID und ein Geheimnis an. 

1. Prüfen und geben Sie Ihre Zustimmung zum **Datenschutz und Einhaltung von Vorschriften**, indem Sie das Kontrollkästchen **Ich stimme zu** markieren. 

1. Wählen Sie **Überprüfen**, um die Konfiguration zu validieren. 

1. Um die Verbindun abzuschließen wählen Sie **Speicher** aus. 

## <a name="enrichment-results"></a>Anreicherungsergebnisse 

Wählen Sie Ausführen aus der Befehlsleiste aus, um den Anreicherungsprozess zu starten. Sie können das System die Anreicherung auch automatisch als Teil von einer  [geplante Aktualisierung](system.md#schedule-tab) ausführen lassen. Die Bearbeitungszeit hängt von der Größe Ihrer Kundendaten ab. 

Nachdem der Anreicherungsprozess abgeschlossen ist, können Sie die neu angereicherten Kundenprofildaten unter  **Meine Anreicherungen** prüfen. Außerdem finden Sie den Zeitpunkt des letzten Updates und die Anzahl der angereicherten Profile. 

Eine Detailansicht jedes angereicherten Profils erhalten Sie, indem Sie Daten  **Anreicherungen ansehen** auswählen. 

## <a name="next-steps"></a>Nächste Schritte,

Bauen Sie auf Ihren angereicherten Kundendaten auf. Verwenden Sie die AbiliTec-IDs, um Kundenprofile in einer personenbezogenen Ansicht zu konsolidieren. 
[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität 

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an LiveRamp aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird solche Daten auf Ihre Anweisung übertragen, aber Sie sind dafür verantwortlich, sicherzustellen, dass LiveRamp alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben. Weitere Informationen unter [Microsoft Datenschutzbestimmungen](https://go.microsoft.com/fwlink/?linkid=396732). Ihr Dynamics 365 Customer Insights-Administrator kann diese Anreicherung jederzeit entfernen, um die Nutzung dieser Funktionalität einzustellen. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
