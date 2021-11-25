---
title: Zustimmungsregeln für Segmente in Zielgruppenerkenntnissen aktivieren
description: Schritte zum Verknüpfen von Zustimmungsregeln und Aktivieren von Zustimmungsüberprüfungen in Zielgruppenerkenntnissen.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 33ec3a684c2ca47badb4e5461f069d1b2e4a4f3d
ms.sourcegitcommit: 2a0947cffb52eaf885aa2e50c95b3693f7e4c589
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "7753060"
---
# <a name="activate-consent-rules"></a>Zustimmungsregeln aktivieren

[Das Zustimmungscenter (Vorschauversion)](../consent-management/overview.md) hilft Ihnen, Zustimmungsdaten aus verschiedenen Quellen zu harmonisieren. Verwenden Sie die vereinheitlichte Entität *Zustimmung*, um standardmäßige Zustimmungsüberprüfungen anzuwenden. Nachdem Sie Zustimmungsdaten in das Zustimmungscenter importiert und die Regeln für die importierten Zustimmungsdaten konfiguriert haben, wird die Entität *Zustimmung* automatisch mit Zielgruppenerkenntnissen synchronisiert.

## <a name="enable-consent-checks"></a>Zustimmungsüberprüfungen aktivieren

Mit in das Zustimmungscenter (Vorschauversion) importierten Zustimmungsdaten und eingerichteten Regeln können Sie Zustimmungsüberprüfungen in Zielgruppenerkenntnissen aktivieren. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Registerkarte „Zustimmung“ in den Einstellungen von Zielgruppenerkenntnissen mit aktivierten Zustimmungsdaten.":::

1. Gehen Sie in Zielgruppen-Insights zu **Admin** > **System**.

1. Wählen Sie die Registerkarte **Zustimmung (Vorschau)** aus.

1. Stellen Sie im Abschnitt **Zustimmungsüberprüfungen aktivieren** den Umschalter für den Bereich, den Sie aktivieren möchten, auf **Ein**.

1. Aktivieren Sie das Kontrollkästchen **Außerkraftsetzen der Standard-Zustimmungsregeln zulassen**, um die standardmäßigen Zustimmungsüberprüfungen zu entfernen, die für ein bestimmtes Segment erzwungen werden. 

1. Wählen Sie im Dropdown-Menü aus, wo Sie Überschreibungen zulassen möchten.     

1. Wählen Sie im Abschnitt **Zustimmung mit Kundenprofilen verknüpfen** das Attribut aus, das als Kennung verwendet wird, um Zustimmungsdaten mit Kundendaten zu verknüpfen. Es ist wahrscheinlich eine Telefonnummer oder eine E-Mail-Adresse. 

1. Wählen Sie **Speichern** aus, um Ihre Einstellungen anzuwenden.

## <a name="disable-consent-checks"></a>Zustimmungsüberprüfungen deaktivieren

Um die Verwendung von Zustimmungsdaten in Zielgruppenerkenntnissen zu beenden, muss ein Administrator die Systemeinstellungen entsprechend aktualisieren.

1. Gehen Sie in Zielgruppen-Insights zu **Admin** > **System**.

1. Wählen Sie die Registerkarte **Zustimmung (Vorschau)** aus.

1. Stellen Sie im Abschnitt **Zustimmungsüberprüfungen aktivieren** den Umschalter auf **Aus**.
