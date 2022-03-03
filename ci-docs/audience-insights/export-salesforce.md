---
title: Exportieren Sie Customer Insights-Daten in die Salesforce Marketing Cloud
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und in die Salesforce Marketing Cloud exportieren.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 17a608a64433cdc395e0b503a42b6290db5c39ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230203"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Exportieren von Segmenten und anderen Daten in die Salesforce Marketing Cloud (Vorschau)

Verwenden Sie Ihre Kundendaten in Salesforce Marketing Cloud, indem Sie sie über einen SFTP-Speicherort (Secure File Transfer Protocol) exportieren.

## <a name="prerequisites-for-connection"></a>Voraussetzungen für die Verbindung

- Verfügbarkeit eines SFTP-Hosts und entsprechender Admin-Zugangsdaten. [So richten Sie SFTP-Standorte für Salesforce Marketing Cloud ein](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Verbindung zur Salesforce Marketing Cloud einrichten

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Salesforce Marketing Cloud**, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie **Benutzername**, **Kennwort** und **Hostname** und **Exportordner** für Ihr SFTP-Konto an.

1. Wählen Sie die **üerprüfen**, um die Verbindung zu testen.

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem SFTP-Abschnitt aus. Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. Wählen Sie, ob Sie Ihre Daten **Gzipped** oder **Entpackt** exportieren möchten, und das **Feldtrennzeichen** für die exportierten Dateien.

1. Wählen Sie die Entitäten für die zu exportierenden Beispielsegmente.

   > [!NOTE]
   > Jede ausgewählte Entität wird beim Export in bis zu fünf Ausgabedateien aufgeteilt. 

1. Wählen Sie **Speichern** aus.

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt. Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importieren Sie Customer Insights-Daten vom SFTP Standort in die Salesforce Marketing Cloud

1. Erstellen der [Datenerweiterungen in der Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5), um die Customer Insights-Datendatei vom SFTP-Speicherort zu importieren.

2. [Importieren Sie die Daten vom SFTP-Speicherort](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) in die Salesforce Marketing Cloud-Datenerweiterung. 

3. Richten Sie die Automatisierung ein, um die Daten in die Data Extensions zu importieren. Mehr erfahren über [Dateiablageautomatisierungen und geplante Automatisierungen](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definieren einer [Dateiablageautomatisierung](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) oder einer [geplante Automatisierung](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Hier ist ein Beispiel für [eine Automatisierung mit SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten über SFTP aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass das Exportziel alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
