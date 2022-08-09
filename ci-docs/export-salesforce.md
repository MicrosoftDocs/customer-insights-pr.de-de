---
title: Exportieren von Daten in die Salesforce Marketing Cloud (Vorschauversion)
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und in die Salesforce Marketing Cloud exportieren.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197037"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Exportieren von Daten in die Salesforce Marketing Cloud (Vorschauversion)

Verwenden Sie Ihre Kundendaten in Salesforce Marketing Cloud, indem Sie sie über einen SFTP-Speicherort (Secure File Transfer Protocol) exportieren.

## <a name="prerequisites"></a>Anforderungen

- Ein [SFTP-Host für Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) und entsprechende Admin-Anmeldeinformationen.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Verbindung zur Salesforce Marketing Cloud einrichten

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Salesforce Marketing Cloud**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie **Benutzername**, **Kennwort** und **Hostname** und **Exportordner** für Ihr SFTP-Konto an.

1. Wählen Sie die **üerprüfen**, um die Verbindung zu testen.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem SFTP-Abschnitt aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. Wählen Sie, ob Sie Ihre Daten **Gzipped** oder **Entpackt** exportieren möchten, und das **Feldtrennzeichen** für die exportierten Dateien.

1. Wählen Sie die Entitäten für die zu exportierenden Beispielsegmente.

   > [!NOTE]
   > Jede ausgewählte Entität wird beim Export in bis maximal fünf Ausgabedateien aufgeteilt.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importieren Sie Customer Insights-Daten vom SFTP Standort in die Salesforce Marketing Cloud

1. Erstellen der [Datenerweiterungen in der Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5), um die Customer Insights-Datendatei vom SFTP-Speicherort zu importieren.

2. [Importieren Sie die Daten vom SFTP-Speicherort](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) in die Salesforce Marketing Cloud-Datenerweiterung.

3. Richten Sie die Automatisierung ein, um die Daten in die Data Extensions zu importieren. Mehr erfahren über [Dateiablageautomatisierungen und geplante Automatisierungen](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definieren einer [Dateiablageautomatisierung](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) oder einer [geplante Automatisierung](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Hier ist ein Beispiel für [eine Automatisierung mit SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
