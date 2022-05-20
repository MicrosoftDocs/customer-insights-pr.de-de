---
title: Standardzustimmungsregeln für Segmente verwalten
description: Mit der Einwilligungsverwaltungsfunktion können Sie die standardmäßigen Einwilligungsregeln deaktivieren oder ändern, wenn Überschreibungen aktiviert sind.
ms.date: 12/01/2021
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 764eeca9d99c95a34d9bd4c11d79f8b8e90701e2
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755215"
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
