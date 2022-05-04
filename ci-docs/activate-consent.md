---
title: Einwilligungsregeln für Segmente aktivieren
description: Folgen Sie diesen Schritten, um Zustimmungsdaten zu verknüpfen und Zustimmungsprüfungen in Dynamics 365 Customer Insights zu aktivieren. Ein Administrator kann auch Einwilligungsprüfungen deaktivieren.
ms.date: 11/12/2021
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bfa03f4b7b56b300a74ebd04721cd64b893879f1
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646050"
---
# <a name="activate-consent-rules"></a>Zustimmungsregeln aktivieren

[Das Zustimmungscenter (Vorschau)](consent-management/overview.md) hilft Ihnen, Zustimmungsdaten aus verschiedenen Quellen zu harmonisieren. Verwenden Sie die vereinheitlichte Entität *Zustimmung*, um standardmäßige Zustimmungsüberprüfungen anzuwenden. Nachdem Sie Zustimmungsdaten in das Zustimmungscenter importiert und die Regeln für die Daten konfiguriert haben, wird die Entität *Zustimmung* automatisch mit Dynamics 365 Customer Insights synchronisiert.

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
