---
title: Ausführen eines Web SDK-Beispiels
description: Erfahren Sie, wie Sie ein Web SDK-Beispiel personalisieren und ausführen.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606210"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Ausführen des Web SDK-Beispiels für Dynamics 365 Customer Insights Kundenbindungserkenntnisse

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Die Web SDK-Bibliothek der Funktion Kundenbindungserkenntnisse ist eine JavaScript-Bibliothek mit Beispielcode, den Sie auf Ihrer Website verwenden können.

## <a name="prerequisites"></a>Anforderungen

- Installieren Sie [Visual Studio Code](https://code.visualstudio.com/).
- [Installieren Sie die Erweiterung Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) in Visual Studio Code und machen Sie sich mit der Ausführung von Live Server vertraut.
- Sie müssen einen [Kundenbindungs-Erkenntnisarbeitsbereich](create-workspace.md) haben.

## <a name="run-sample"></a>Ausführen des Beispiels

1. [Laden Sie das Web SDK-Beispiel herunter](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Entpacken Sie die komprimierte Datei `ei_websdk_sample.zip`.

1. Öffnen Sie den entpackten Ordner in Visual Studio Code.

1. Rufen Sie das Kundenbindungserkenntnis-Portal für Ihren Arbeitsbereich auf. Wählen Sie **Administrator** > **Arbeitsbereich** und dann **Installationsanleitung**. Folgen Sie der ersten Option und wählen Sie **Code kopieren**, um den JavaScript-Code Ausschnitt zu kopieren.

1. In der `ei_websdk_sample.html` Datei fügen Sie den Codeausschnitt, den Sie gerade kopiert haben, unter diese Zeile ein:

   - <-- FÜGEN SIE DEN JAVASCRIPT-CODEAUSSCHNITT AUS DEM KUNDENBINDUNGSERKENNTNISPORTAL HIER UNTER DIESER LINIE EIN -->

1. Öffnen Sie die Datei `ei_websdk_sample.html` mit Live Server in Visual Studio Code, indem Sie in der Statusleiste **Liveschaltung** auswählen.

1. Beim Öffnen der Seite sollte automatisch ein Ansichtsereignis gesendet werden. Durch Klicken auf eine beliebige Schaltfläche auf der Seite werden Aktionsereignisse gesendet. Die Schaltfläche **Ereignisse nachverfolgen** sendet auch benutzerdefinierte Ereignisse. Durch Auswahl der Schaltfläche **Zu Bing wechseln** wird ein Aktionsereignis gesendet, bevor Sie zur Bing-Website navigieren.

1. Sehen Sie sich den Fluss der Ereignisse an, wenn Sie zu Ihrem Arbeitsbereich navigieren. Dieser Arbeitsbereich ist dem in Schritt 4 eingegebenen Erfassungsschlüssel zugeordnet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
