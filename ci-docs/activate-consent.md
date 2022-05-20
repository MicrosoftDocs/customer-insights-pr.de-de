---
title: Einwilligungsregeln für Segmente aktivieren
description: Folgen Sie diesen Schritten, um Zustimmungsdaten zu verknüpfen und Zustimmungsprüfungen in Dynamics 365 Customer Insights zu aktivieren. Ein Administrator kann auch Einwilligungsprüfungen deaktivieren.
ms.date: 04/27/2022
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f82e3a4031fee8bcaa88575cbd68b37385a7fffb
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755169"
---
# <a name="activate-consent-rules"></a>Zustimmungsregeln aktivieren

[Das Zustimmungscenter (Vorschau)](consent-management/overview.md) hilft Ihnen, Zustimmungsdaten aus verschiedenen Quellen zu harmonisieren. Verwenden Sie die vereinheitlichte Entität *Zustimmung*, um standardmäßige Zustimmungsüberprüfungen anzuwenden. Nachdem Sie Zustimmungsdaten importiert und die Zuordnungsregeln konfiguriert haben, wird die Entität *Zustimmung* automatisch mit Dynamics 365 Customer Insights synchronisiert.

## <a name="enable-consent-checks"></a>Zustimmungsüberprüfungen aktivieren

Mit in das Zustimmungscenter (Vorschauversion) importierten Zustimmungsdaten und eingerichteten Regeln können Sie Zustimmungsüberprüfungen aktivieren. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Registerkarte Zustimmung in den Customer Insights-Einstellungen mit aktivierten Zustimmungsdaten.":::

1. Gehen Sie in Customer Insights zu **Admin** > **System**.

1. Wählen Sie die Registerkarte **Zustimmung (Vorschau)** aus.

1. Stellen Sie im Abschnitt **Zustimmungsüberprüfungen aktivieren** den Umschalter für alle Bereiche, die Sie aktivieren möchten, auf **Ein**.

1. Aktivieren Sie das Kontrollkästchen **Außerkraftsetzen der Standard-Zustimmungsregeln zulassen**, um die standardmäßigen Zustimmungsüberprüfungen zu entfernen, die für ein bestimmtes Segment erzwungen werden. 

1. Wählen Sie im Dropdown-Menü aus, wo Sie Überschreibungen zulassen möchten.     

1. Wählen Sie im Abschnitt **Zustimmung mit Kundenprofilen verknüpfen** das Attribut aus, das als Kennung verwendet wird, um Zustimmungsdaten mit Kundendaten zu verknüpfen. Es ist wahrscheinlich eine Telefonnummer oder eine E-Mail-Adresse. 

1. Wählen Sie **Speichern** aus, um Ihre Einstellungen anzuwenden.

## <a name="disable-consent-checks"></a>Zustimmungsüberprüfungen deaktivieren

Um die Verwendung von Zustimmungsdaten in Customer Insights zu beenden, muss ein Admin die Systemeinstellungen entsprechend aktualisieren.

1. Gehen Sie in Customer Insights zu **Admin** > **System**.

1. Wählen Sie die Registerkarte **Zustimmung (Vorschau)** aus.

1. Stellen Sie im Abschnitt **Zustimmungsüberprüfungen aktivieren** den Umschalter auf **Aus**.

> [!TIP]
> Weitere Informationen dazu, wie Sie die Verwendung der Zustimmungsverwaltungsfunktion beenden, finden Sie unter [Systemeinstellungen im Zustimmungscenter (Vorschauversion)](consent-management/system-settings.md).
