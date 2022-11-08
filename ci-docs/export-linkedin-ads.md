---
title: Exportieren von Segmenten nach LinkedIn Ads (Vorschauversion)
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und einen Export nach LinkedIn Ads durchführen.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 06eb915e352ad545f95e96e6108be0f81f43a451
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725307"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Exportieren von Segmenten nach LinkedIn Ads (Vorschauversion)

Exportieren Sie Segmente einheitlicher Kundenprofilen nach LinkedIn Ads, um passende Zielgruppen zu erstellen. Verwenden Sie die passenden Zielgruppen für das Unternehmens- und das Kontakt-Targeting.

## <a name="prerequisites"></a>Anforderungen

- Ein [LinkedIn Campaign Manager-Konto](https://business.linkedin.com/marketing-solutions/ads) und die entsprechenden Administrator-Anmeldeinformationen.
- Eine [LinkedIn Campaign Manager-Konto-ID](https://www.linkedin.com/help/lms/answer/a424270).
- [Konfigurierte Segmente](segments.md) in Customer Insights.
- Die exportierten Segmente benötigen je nach Auswahl mindestens ein bestimmtes Feld [Kontakt-Targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) oder [Unternehmensausrichtung](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) auf Linkedin. Die möglichen Felder sind im Schritt **Datenabgleich** aufgeführt, wenn [der Export konfiguriert wird](#configure-an-export).

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Private Link in Kombination mit Bring Your Own Storage (BYOS) wird nicht unterstützt.
- Bis zu 100.000 Kundenprofile pro Export zu LinkedIn Ads exportieren und die Fertigstellung kann bis zu 10 Stunden dauern.
- Nur Segmente. Ein Segment muss mindestens 300 einzigartige Profile enthalten.

## <a name="set-up-connection-to-linkedin-ads"></a>Einrichten der Verbindung mit LinkedIn Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **LinkedIn Ads**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie Ihre LinkedIn Campaign Manager-Konto-ID an.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie **Verbinden**, um die Verbindung zu initialisieren.

1. Wählen Sie **Mit LinkedIn authentifizieren** aus und geben Sie Ihre Administrator-Anmeldeinformationen für LinkedIn Campaign Manager an.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem LinkedIn Ads-Abschnitt aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. Wählen Sie aus, ob Sie Daten für [Kontakt-Targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) oder [Unternehmens-Targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) auf LinkedIn exportieren möchten.

1. In dem Abschnitt **Datenabgleich** wählen Sie für das Kontakt-Targeting mindestens ein Feld aus, das die E-Mail-Adresse eines Kunden, die Apple-Anzeigen-ID, die Google-Anzeigen-ID, die Google-Benutzer-ID oder zuerst und Nachname darstellt. Wenn Sie Unternehmens-Targeting auswählen, wählen Sie mindestens ein Feld aus, das einen Firmennamen, eine E-Mail-Domäne, eine LinkedIn-Seiten-URL, ein Aktiensymbol oder eine Website darstellt.

1. Wählen Sie zusätzlich die Felder aus, um Ihren Export weiter zu definieren. Wählen Sie **Attribut hinzufügen**, um diese Felder zuzuordnen.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten. Die passenden Zielgruppen in LinkedIn Campaign Manager werden automatisch mit dem Namen der Segmente erstellt, die Sie zum Exportieren ausgewählt haben. Jedes Segment führt zu einer separaten passenden Zielgruppe.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
