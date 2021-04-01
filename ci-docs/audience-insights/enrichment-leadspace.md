---
title: Anreicherung von Firmenprofilen mit der Drittanbieter-Anreicherung Leadspace
description: Allgemeine Informationen über die Drittanbieter-Anreicherung von Leadspace.
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597648"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Anreicherung von Firmenprofilen mit Leadspace (Vorschau)

Leadspace ist ein datenwissenschaftliches Unternehmen, das eine B2B-Kundendatenplattform anbietet. Sie ermöglicht es Kunden mit einheitlichen Kundenprofilen für Unternehmen, ihre Daten anzureichern. Die Anreicherung umfasst zusätzliche Attribute wie Unternehmensgröße, Standort, Branche und mehr.

## <a name="prerequisites"></a>Anforderungen

Um Leadspace zu konfigurieren, müssen die folgenden Voraussetzungen erfüllt sein:

- Sie haben eine aktive Leadspace-Lizenz und den „dauerhaften Schlüssel“ (bezeichnet als **Leadspace-Token**). Gehen Sie direkt zu [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) für Details über ihr Produkt.
- Sie haben [Administrator](permissions.md#administrator) Berechtigungen.
- Sie haben [Einheitliche Kundenprofile](customer-profiles.md) für Unternehmen.

## <a name="configuration"></a>Konfiguration

1. Gehen Sie in Zielgruppen-Insights zu **Daten** > **Anreicherung**.

1. Wählen Sie **Meine Daten anreichern** auf der Leadspace-Kachel.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Screenshot der Leadspace-Kachel.":::

1. Wählen Sie **Starten** und geben Sie einen aktiven **Leadspace-Token** (unbefristeter Schlüssel) ein. Prüfen und geben Sie Ihre Zustimmung zum **Datenschutz und Einhaltung von Vorschriften**, indem Sie das Kontrollkästchen **Ich stimme zu** markieren. Bestätigen Sie beide Eingaben, indem Sie **Verbinden mit Leadspace** wählen.

1. Wählen Sie **Daten zuordnen** und dann den Datensatz, den Sie mit Unternehmensdaten von Leadspace anreichern möchten. Sie können die *Kundenentität* auswählen, um alle Ihre Kundenprofile anzureichern, oder eine Segmententität auswählen, um nur Kundenprofile anzureichern, die in diesem Segment enthalten sind.

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Wählen Sie zwischen Kundenprofil und Segmentanreicherung.":::

1. Wählen Sie **Weiter** und legen Sie fest, welche Felder aus Ihren Unified Profiles verwendet werden sollen, um nach passenden Firmendaten von Leadspace zu suchen. Das Feld **Firmenname** ist erforderlich. Für eine höhere Abgleichsgenauigkeit können bis zu zwei weitere Felder, **Firmen-Website** und **Firmenstandort**, hinzugefügt werden.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace-Feld-Zuordnungsbereich.":::
   
1. Wählen Sie **Anwenden**, um die Zuordnung der Felder abzuschließen.

1. Wählen Sie **Ausführen**, um die Firmenprofile anzureichern. Wie lange eine Anreicherung dauert, hängt von der Anzahl der vereinheitlichten Kundenprofile ab.

## <a name="enrichment-results"></a>Anreicherungsergebnisse

Nach dem Aktualisieren der Anreicherung können Sie die neu angereicherten Unternehmensdaten unter[Meine Bereicherung](enrichment-hub.md) überprüfen. Den Zeitpunkt der letzten Aktualisierung und die Anzahl der angereicherten Profile können Sie anzeigen.

Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.

Weitere Informationen finden Sie unter [Leadspace-APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Nächste Schritte

Bauen Sie auf Ihren angereicherten Kundendaten auf. Erstellen Sie [Segmente](segments.md), [Maße](measures.md), und selbst [Exportdaten](export-destinations.md), um Ihren Kunden personalisierte Erlebnisse zu bieten.

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Leadspace aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird diese Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Leadspace alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann diese Anreicherung jederzeit entfernen, um die Nutzung dieser Funktionalität einzustellen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]