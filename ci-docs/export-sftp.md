---
title: Daten zu SFTP-Hosts exportieren (Vorschauversion) (enthält Video)
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu einem SFTP-Speicherort exportieren.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207228"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Daten zu SFTP-Hosts exportieren (Vorschauversion)

Verwenden Sie Ihre Kundendaten in Anwendungen von Drittanbietern, indem Sie sie an einen SFTP-Speicherort (Secure File Transfer Protocol) exportieren.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Anforderungen

- Verfügbarkeit eines SFTP-Hosts und entsprechender Anmeldeinformationen.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- SFTP-Ziele hinter Firewalls werden derzeit nicht unterstützt.
- Die Laufzeit eines Exports hängt von Ihrer Systemleistung ab. Wir empfehlen zwei CPU-Kerne und 1 GB Speicher als minimale Konfiguration Ihres Servers.
- Bis zu 100 Millionen Kundenprofile, kann 90 Minuten dauern, wenn die empfohlene Mindestkonfiguration von zwei CPU-Kernen und 1 GB Speicher verwendet wird.
- Wenn Sie einen SSH-Schlüssel zur Authentifizierung verwenden, stellen Sie sicher, dass Sie [Ihren privaten Schlüssel erstellen](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) als PEM- oder SSH.COM-Format haben. Wenn Sie Putty verwenden, konvertieren Sie Ihren privaten Schlüssel, indem Sie ihn als Open SSH exportieren. Die folgenden privaten Schlüsselformate werden unterstützt:
  - RSA im OpenSSL-PEM‑ und ssh.com-Format
  - DSA im OpenSSL-PEM‑ und ssh.com-Format
  - ECDSA 256/384/521 im OpenSSL-PEM-Format
  - ED25519 und RSA im OpenSSH-Schlüsselformat

## <a name="set-up-connection-to-sftp"></a>Verbindungen mit SFTP einrichten

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** aus, und klicken Sie dann auf **SFTP**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wählen Sie aus, ob Sie sich über SSH oder Benutzername/Passwort für Ihre Verbindung authentifizieren möchten, und geben Sie die erforderlichen Details an. Wenn Sie einen SSH-Schlüssel zur Authentifizierung verwenden, stellen Sie sicher, dass Sie [Ihren privaten Schlüssel erstellen](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) als PEM- oder SSH.COM-Format haben. Wenn Sie Putty verwenden, konvertieren Sie Ihren privaten Schlüssel, indem Sie ihn als Open SSH exportieren. Die folgenden privaten Schlüsselformate werden unterstützt:
   - RSA im OpenSSL-PEM‑ und ssh.com-Format
   - DSA im OpenSSL-PEM‑ und ssh.com-Format
   - ECDSA 256/384/521 im OpenSSL-PEM-Format
   - ED25519 und RSA im OpenSSH-Schlüsselformat

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

> [!TIP]
> Der Export von Entitäten, die eine große Datenmenge enthalten, kann bei jedem Export zu mehreren CSV-Dateien im selben Ordner führen. Das Aufteilen von Exporten erfolgt aus Leistungsgründen, um die Zeit zu minimieren, die für den Abschluss eines Exports benötigt wird.

[!INCLUDE [footer-include](includes/footer-banner.md)]
