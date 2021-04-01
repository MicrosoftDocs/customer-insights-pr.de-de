---
title: LiveRamp Connector
description: Lernen Sie, wie man Daten zu LiveRamp exportiert.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597556"
---
# <a name="liverampreg-connector-preview"></a>LiveRamp &reg; Konnektor (Vorschau)

Aktivieren Sie Ihre Daten in LiveRamp, um eine Verbindung mit über 500 Plattformen in digitalen, sozialen und TV-Ökosystemen herzustellen. Arbeiten Sie mit Ihren Daten in LiveRamp, um Werbekampagnen auszurichten, zu Unterdrücken und zu personalisieren.

## <a name="prerequisites"></a>Voraussetzungen

- Sie benötigen ein LiveRamp-Abonnement, um diesen Connector verwenden zu können.
- Um ein Abonnement zu erhalten, [kontaktieren Sie LiveRamp ](https://liveramp.com/contact/) direkt. [Erfahren Sie mehr über LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Verbinden Sie mit LiveRamp

1. Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Ziele exportieren**.

1. In der Kachel **LiveRamp** wählen Sie **Einrichten**.

1. Geben Sie Ihrem Ziel einen erkennbaren Namen im Feld **Anzeigename**.

1. **Benutzername** und **Passwort** für Ihr LiveRamp Secure FTP (SFTP) Konto bereitstellen.
Diese Anmeldeinformationen können sich von Ihren LiveRamp Onboarding-Anmeldeinformationen unterscheiden.

1. Wählen Sie **Überprüfen**, um die Verbindung zu LiveRamp zu testen.

1. Geben Sie nach erfolgreicher Überprüfung Ihre Zustimmung für **Datenschutz und Compliance** durch Auswahl des Kontrollkästchens **Genau**.

1. Wählen Sie **Weiter**, um den LiveRamp-Anschluss einzurichten.

## <a name="configure-the-connector"></a>Konfigurieren Sie den Konnektor

1. In dem Feld **Wählen Sie Ihre Schlüsselkennung** wählen Sie **E-Mail**, **Name und Adresse** oder **Telefon**, um die Identitätsauflösung an LiveRamp zu senden.

1. Ordnen Sie die entsprechenden Attribute Ihrer einheitlichen Kundenentität der ausgewählten Schlüsselkennung zu.

1. Wählen Sie **Attribute hinzufügen**, um zusätzliche Attribute zuzuordnen, die an LiveRamp gesendet werden sollen.

   > [!TIP]
   > Wenn Sie mehr Schlüsselkennungsattribute an LiveRamp senden, erhalten Sie wahrscheinlich eine höhere Übereinstimmungsrate.

1. Wählen Sie die Segmente aus, die Sie in LiveRamp exportieren möchten.

1. Wählen Sie **Speichern** aus.

> [!div class="mx-imgBorder"]
> ![LiveRamp-Connector mit Attributzuordnung](media/export-liveramp-segments.png "LiveRamp-Connector mit Attributzuordnung")

## <a name="export-the-data"></a>Exportieren der Daten

Der Export beginnt in Kürze, wenn alle Voraussetzungen für den Export erfüllt sind. Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.
Sobald der Export erfolgreich abgeschlossen wurde, können Sie sich bei LiveRamp Onboarding anmelden, um Ihre Daten zu aktivieren und zu verteilen.

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Liveramp aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Liveramp alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]