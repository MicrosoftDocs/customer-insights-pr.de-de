---
title: Standardzustimmungsregeln für Segmente verwalten
description: Mit der Einwilligungsverwaltungsfunktion können Sie die standardmäßigen Einwilligungsregeln deaktivieren oder ändern, wenn Überschreibungen aktiviert sind.
ms.date: 12/01/2021
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 43f03ea97765e112a8ea2a7da97cc548c8c84dfc
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646100"
---
# <a name="disable-or-change-default-consent-rules"></a>Standardzustimmungsregeln deaktivieren oder ändern

Wenn Ihr Unternehmen die Funktionalität [Zustimmungsverwaltung](consent-management/overview.md) mit Dynamics 365 Customer Insights verwendet, [können Admins Zustimmungsregeln](activate-consent.md) für Segmente durchsetzen. 

Mit erzwungenen Zustimmungsregeln im Segmentbereich informiert jedes Segment über den Status der Zustimmungsüberprüfung und -regeln. Wenn Überschreibungen zulässig sind, werden die standardmäßigen Zustimmungsregeln für bestimmte Segmente deaktiviert. Jeder Ersteller eines Segments kann einem Segment zusätzlich zu den Standardregeln weitere Zustimmungsregeln hinzufügen. 

## <a name="for-administrators"></a>Für Administratoren

:::image type="content" source="consent-management/media/consent-rules-segment.png" alt-text="Segmenterstellung mit Optionen für Zustimmungsregeln.":::

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
1. [Erstellen Sie das Segment](segments.md) in Customer Insights und speichern Sie es. 

1. Geben Sie den Segmentnamen für Ihren Administrator frei, und bitten Sie ihn, [Überschreibungen für Ihr Segment zu aktivieren](activate-consent.md). 

1. Öffnen Sie Ihre Segmente erneut. Wählen Sie in der Benachrichtigung **Zustimmungsregeln** die Option **Details anzeigen** aus, und fügen Sie die Zustimmungsregeln hinzu, die Sie anwenden möchten. Anschließend müssen Sie Ihr Segment **speichern** und **ausführen**.



[!INCLUDE [footer-include](includes/footer-banner.md)] 
