---
title: Customer Insights-Daten zu SFTP-Hosts exportieren
description: Erfahren Sie, wie Sie die Verbindung zu einem SFTP-Host konfigurieren.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598384"
---
# <a name="connector-for-sftp-preview"></a>Connector für SFTP (Vorschau)

Verwenden Sie Ihre Kundendaten in Anwendungen von Drittanbietern, indem Sie sie auf einen Secure File Transfer Protocol(SFTP)-Host exportieren.

## <a name="prerequisites"></a>Anforderungen

- Verfügbarkeit eines SFTP-Hosts und entsprechender Anmeldeinformationen.

## <a name="connect-to-sftp"></a>Mit SFTP verbinden

1. Gehen Sie zu **Administrator** > **Exportziele**.

1. Wählen Sie **SFTP** und **einrichten** aus.

1. Geben Sie Ihrem Ziel einen erkennbaren Namen im Feld **Anzeigename**.

1. Geben Sie **Benutzername**, **Kennwort** und **Hostname** und **Exportordner** für Ihr SFTP-Konto an.

1. Wählen Sie die **üerprüfen**, um die Verbindung zu testen.

1. Wählen Sie nach erfolgreicher Überprüfung aus, ob Sie Ihre Daten als **Gzipped** oder **Entpackt** exportieren möchten, und wählen Sie die **Feldtrennzeichen** für die exportierten Dateien aus.

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Wählen Sie **Weiter**, um die Konfiguration des Exports zu starten.

## <a name="configure-the-export"></a>Export konfigurieren

1. Wählen Sie die Entitäten für die zu exportierenden Beispielsegmente.

   > [!NOTE]
   > Jede ausgewählte Entität besteht beim Export aus bis zu fünf Ausgabedateien. 

1. Wählen Sie **Speichern** aus.

## <a name="export-the-data"></a>Exportieren der Daten

Sie könenn [Daten nach Bedarf exportieren](export-destinations.md). Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Die Laufzeit eines Exports hängt von Ihrer Systemleistung ab. Wir empfehlen zwei CPU-Kerne und 1 GB Speicher als minimale Konfiguration Ihres Servers. 
- Das Exportieren von Entitäten mit bis zu 100 Millionen Kundenprofilen kann 90 Minuten dauern, wenn die empfohlene Mindestkonfiguration von zwei CPU-Kernen und 1 GB Speicher verwendet wird. 

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten über SFTP aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass das Exportziel alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]