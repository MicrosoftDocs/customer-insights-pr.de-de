---
title: Customer Insights-Daten zu SFTP-Hosts exportieren
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu einem SFTP-Speicherort exportieren.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 000b44dc8e5cc419132bd17e359fbdd5879caf1b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124318"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>Exportieren von Segmenten und anderen Daten nach SFTP (Vorschau)

Verwenden Sie Ihre Kundendaten in Anwendungen von Drittanbietern, indem Sie sie an einen SFTP-Speicherort (Secure File Transfer Protocol) exportieren.

## <a name="prerequisites-for-connection"></a>Voraussetzungen für die Verbindung

- Verfügbarkeit eines SFTP-Hosts und entsprechender Anmeldeinformationen.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Die Laufzeit eines Exports hängt von Ihrer Systemleistung ab. Wir empfehlen zwei CPU-Kerne und 1 GB Speicher als minimale Konfiguration Ihres Servers. 
- Das Exportieren von Entitäten mit bis zu 100 Millionen Kundenprofilen kann 90 Minuten dauern, wenn die empfohlene Mindestkonfiguration von zwei CPU-Kernen und 1 GB Speicher verwendet wird. 

## <a name="set-up-connection-to-sftp"></a>Verbindungen mit SFTP einrichten

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und dann **SFTP** aus, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie **Benutzername**, **Kennwort** und **Hostname** und **Exportordner** für Ihr SFTP-Konto an.

1. Wählen Sie die **üerprüfen**, um die Verbindung zu testen.

1. Wählen Sie, ob Sie Ihre Daten **Gzipped** oder **Entpackt** exportieren möchten, und das **Feldtrennzeichen** für die exportierten Dateien.

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem SFTP-Abschnitt aus. Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. Wählen Sie die Entitäten für die zu exportierenden Beispielsegmente.

   > [!NOTE]
   > Jede ausgewählte Entität wird beim Export in bis zu fünf Ausgabedateien aufgeteilt. 

1. Wählen Sie **Speichern** aus.

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt. Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten über SFTP aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass das Exportziel alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).
Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
