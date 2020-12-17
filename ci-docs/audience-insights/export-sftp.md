---
title: Customer Insights-Daten zu SFTP-Hosts exportieren
description: Erfahren Sie, wie Sie die Verbindung zu einem SFTP-Host konfigurieren.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643502"
---
# <a name="connector-for-sftp-preview"></a>Connector für SFTP (Vorschau)

Verwenden Sie Ihre Kundendaten in Anwendungen von Drittanbietern, indem Sie sie auf einen Secure File Transfer Protocol(SFTP)-Host exportieren.

## <a name="prerequisites"></a>Anforderungen

- Verfügbarkeit eines SFTP-Hosts und entsprechender Anmeldeinformationen.

## <a name="connect-to-sftp"></a>Verbindung mit SFTP herstellen

1. Gehen Sie zu **Administrator** > **Exportziele**.

1. Wählen Sie **SFTP** und **einrichten** aus.

1. Geben Sie Ihrem Ziel einen erkennbaren Namen im Feld **Anzeigename**.

1. Geben Sie einen **Benutzername**, **Kennwort** und **Hostname** für Ihr SFTP-Konto an. Beispiel: Wenn der Stammordner Ihres SFTP-Servers /root/folder ist und Sie möchten, dass die Daten nach /root/folder/ci_export_destination_folder exportiert werden, sollte der Host sftp://<server_address>/ci_export_destination_folder“ sein.

1. Wählen Sie die **üerprüfen**, um die Verbindung zu testen.

1. Wählen Sie nach erfolgreicher Überprüfung aus, ob Sie Ihre Daten **gezippt** oder **entpackt** exportieren möchten und wählen Sie die **Feldtrennzeichen** für die exportierten Dateien.

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Wählen Sie **Weiter**, um die Konfiguration des Exports zu starten.

## <a name="configure-the-connection"></a>Verbindung konfigurieren

1. Wählen Sie das **Kundenattribut**, das Sie exportieren möchten. Sie können ein oder mehrere Attribute exportieren.

1. Klicken Sie auf **Weiter**.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten.

1. Wählen Sie **Speichern** aus.

## <a name="export-the-data"></a>Exportieren der Daten

Sie könenn [Daten nach Bedarf exportieren](export-destinations.md). Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten über SFTP aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass das Exportziel alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.
