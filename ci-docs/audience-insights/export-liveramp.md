---
title: LiveRamp Connector
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu LiveRamp exportieren.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: f9a0a88fb58897e4d279c181f4cdb4f6c852da60
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618934"
---
# <a name="export-segments-to-liverampreg-preview"></a>Segmente nach LiveRamp&reg; exportieren (Vorschau)

Aktivieren Sie Ihre Daten in LiveRamp, um sich mit über 500 Plattformen in digitalen, sozialen und TVs zu verbinden. Arbeiten Sie mit Ihren Daten in LiveRamp, um Werbekampagnen auszurichten, zu Unterdrücken und zu personalisieren.

## <a name="prerequisites-for-a-connection"></a>Voraussetzungen für die Verbindung

- Sie benötigen ein LiveRamp-Abonnement, um diesen Connector verwenden zu können.
- Um ein Abonnement zu erhalten, [kontaktieren Sie LiveRamp](https://liveramp.com/contact/) direkt. [Erfahren Sie mehr über LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Verbindung mit LiveRamp einrichten

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und dann **LiveRamp** aus, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Benutzername** und **Passwort** für Ihr LiveRamp Secure FTP (SFTP) Konto bereitstellen.
Diese Anmeldeinformationen können sich von Ihren LiveRamp Onboarding-Anmeldeinformationen unterscheiden.

1. Wählen Sie **Überprüfen**, um die Verbindung zu LiveRamp zu testen.

1. Geben Sie nach erfolgreicher Überprüfung Ihre Zustimmung für **Datenschutz und Compliance** durch Auswahl des Kontrollkästchens **Genau**.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem LiveRamp-Abschnitt aus. Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. In dem Feld **Wählen Sie Ihre Schlüsselkennung** wählen Sie **E-Mail**, **Name und Adresse** oder **Telefon**, um die Identitätsauflösung an LiveRamp zu senden.
   > [!div class="mx-imgBorder"]
   > ![LiveRamp-Connector mit Attributzuordnung.](media/export-liveramp-segments.png "LiveRamp-Connector mit Attributzuordnung")

1. Ordnen Sie die entsprechenden Attribute aus Ihrer *Kundenentität* für die ausgewählte Schlüsselkennung zu.

1. Wählen Sie **Attribute hinzufügen**, um weitere Attribute zuzuordnen, die an LiveRamp gesendet werden sollen.

   > [!TIP]
   > Wenn Sie mehr Schlüsselkennungsattribute an LiveRamp senden, erhalten Sie wahrscheinlich eine höhere Übereinstimmungsrate.

1. Wählen Sie die Segmente aus, die Sie in LiveRamp exportieren möchten.

1. Wählen Sie **Speichern** aus.

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt. Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Liveramp aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Liveramp alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
