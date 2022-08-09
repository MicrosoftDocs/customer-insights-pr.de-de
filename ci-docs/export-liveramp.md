---
title: Segmente nach LiveRamp exportieren (Vorschauversion)
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu LiveRamp exportieren.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196715"
---
# <a name="export-segments-to-liverampreg-preview"></a>Segmente nach LiveRamp&reg; exportieren (Vorschauversion)

Aktivieren Sie Ihre Daten in LiveRamp, um sich mit über 500 Plattformen in digitalen, sozialen und TVs zu verbinden. Arbeiten Sie mit Ihren Daten in LiveRamp, um Werbekampagnen auszurichten, zu Unterdrücken und zu personalisieren.

## <a name="prerequisites"></a>Anforderungen

- Ein LiveRamp-Abonnement, um diesen Connector verwenden zu können. Um ein Abonnement zu erhalten, [kontaktieren Sie LiveRamp](https://liveramp.com/contact/) direkt. [Erfahren Sie mehr über LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Der LiveRamp-Export verwendet einen SFTP-Export. SFTP-Ziele hinter Firewalls werden derzeit nicht unterstützt.
- Wenn Sie einen SSH-Schlüssel zur Authentifizierung verwenden, stellen Sie sicher, dass Sie [Ihren privaten Schlüssel erstellen](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) als PEM- oder SSH.COM-Format haben. Wenn Sie Putty verwenden, konvertieren Sie Ihren privaten Schlüssel, indem Sie ihn als Open SSH exportieren. Die folgenden privaten Schlüsselformate werden unterstützt:
  - RSA im OpenSSL-PEM‑ und ssh.com-Format
  - DSA im OpenSSL-PEM‑ und ssh.com-Format
  - ECDSA 256/384/521 im OpenSSL-PEM-Format
  - ED25519 und RSA im OpenSSH-Schlüsselformat
- Die Laufzeit eines Exports hängt von Ihrer Systemleistung ab. Wir empfehlen zwei CPU-Kerne und 1 GB Speicher als minimale Konfiguration Ihres Servers.
- Das Exportieren von Entitäten mit bis zu 100 Millionen Kundenprofilen kann 90 Minuten dauern, wenn die empfohlene Mindestkonfiguration von zwei CPU-Kernen und 1 GB Speicher verwendet wird.
- Die tatsächliche Anzahl der Kundenprofile (oder Daten), die Sie nach LiveRamp exportieren können, hängt von Ihrem Vertrag mit LiveRamp ab.

## <a name="set-up-connection-to-liveramp"></a>Verbindung mit LiveRamp einrichten

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **LiveRamp**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wählen Sie aus, ob Sie sich über SSH oder Benutzername/Passwort für Ihre Verbindung authentifizieren möchten, und geben Sie die erforderlichen Details an.

1. Wählen Sie **Überprüfen**, um die Verbindung zu LiveRamp zu testen.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus nach erfolgreicher Überprüfung.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem LiveRamp-Abschnitt aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. In dem Feld **Daten verbinden** wählen Sie **E-Mail**, **Name und Adresse** oder **Telefon**, um die Identitätsauflösung an LiveRamp zu senden.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="LiveRamp-Connector mit Attributzuordnung.":::

1. Ordnen Sie die entsprechenden Attribute aus Ihrer *Kundenentität* für die ausgewählte Schlüsselkennung zu.

1. Wählen Sie **Attribute hinzufügen**, um weitere Attribute zuzuordnen, die an LiveRamp gesendet werden sollen.

   > [!TIP]
   > Wenn Sie mehr Schlüsselkennungsattribute an LiveRamp senden, erhalten Sie wahrscheinlich eine höhere Übereinstimmungsrate.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
