---
title: Standardzustimmungsregeln für Segmente verwalten
description: Mit der Einwilligungsverwaltungsfunktion können Sie die standardmäßigen Einwilligungsregeln deaktivieren oder ändern, wenn Überschreibungen aktiviert sind.
ms.date: 12/01/2021
ms.service: customer-insights
mms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 28c9ea49b1f3aebd3abd7d4de58fe61e6474158b
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884169"
---
# <a name="disable-or-change-default-consent-rules"></a>Standardzustimmungsregeln deaktivieren oder ändern

Wenn Ihre Organisationen die [Zustimmungsverwaltungsfunktion](../consent-management/overview.md) kombiniert mit Zielgruppenerkenntnissen verwendet, [können Administratoren die Einwilligungsregeln für Segmente erzwingen](activate-consent.md). 

Mit erzwungenen Zustimmungsregeln im Segmentbereich informiert jedes Segment über den Status der Zustimmungsüberprüfung und -regeln. Wenn Überschreibungen zulässig sind, werden die standardmäßigen Zustimmungsregeln für bestimmte Segmente deaktiviert. Jeder Ersteller eines Segments kann einem Segment zusätzlich zu den Standardregeln weitere Zustimmungsregeln hinzufügen. 

## <a name="for-administrators"></a>Für Administratoren

:::image type="content" source="../consent-management/media/consent-rules-segment.png" alt-text="Segmenterstellung mit Optionen für Zustimmungsregeln.":::

**So deaktivieren Sie standardmäßige Zustimmungsregeln**

1. Wählen Sie in der **Zustimmungsregeln**-Benachrichtigung **Details anzeigen** aus. 

1. Stellen Sie den Umschalter **Standard-Zustimmungsregeln** auf **Aus**.

**So fügen Sie weitere Zustimmungsregeln hinzu**

1. Wählen Sie in der **Zustimmungsregeln**-Benachrichtigung **Details anzeigen** aus. 

1. Wählen Sie **Zustimmungsregeln hinzufügen** und dann eine Zustimmungsregel aus der Dropdown-Liste **Datentyp für Zustimmung auswählen** aus.

1. Wählen Sie **Speichern** aus, um die neue Regel auf das Segment anzuwenden.

## <a name="for-contributors"></a>Für Mitwirkende

Zum Erstellen eines Segments ohne erzwungene Zustimmungsregeln müssen Sie mit Ihrem Administrator zusammenarbeiten, um sie in Ihrem Segment zu deaktivieren. Sie können jedoch Ihren eigenen und verwalteten Segmenten Ihre eigenen Zustimmungsregeln hinzufügen.

Dies ist ein dreistufiger Prozess: 
1. [Erstellen Sie das Segment](segments.md) in Zielgruppenerkenntnissen, und speichern Sie es. 

1. Geben Sie den Segmentnamen für Ihren Administrator frei, und bitten Sie ihn, [Überschreibungen für Ihr Segment zu aktivieren](activate-consent.md). 

1. Öffnen Sie Ihre Segmente erneut. Wählen Sie in der Benachrichtigung **Zustimmungsregeln** die Option **Details anzeigen** aus, und fügen Sie die Zustimmungsregeln hinzu, die Sie anwenden möchten. Anschließend müssen Sie Ihr Segment **speichern** und **ausführen**.



[!INCLUDE[footer-include](../includes/footer-banner.md)] 
