---
title: Ausführen eines Web SDK-Beispiels
description: Erfahren Sie, wie Sie ein Web SDK-Beispiel personalisieren und ausführen.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036602"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Ausführen des Web SDK-Beispiels für Dynamics 365 Customer Insights Kundenbindungserkenntnisse

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Die Web SDK-Bibliothek der Funktion Kundenbindungserkenntnisse ist eine JavaScript-Bibliothek mit Beispielcode, den Sie auf Ihrer Website verwenden können.

## <a name="prerequisites"></a>Anforderungen

- Installieren Sie [Visual Studio Code](https://code.visualstudio.com/).
- [Installieren Sie die Erweiterung Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) in Visual Studio Code und machen Sie sich mit der Ausführung von Live Server vertraut.
- Sie benötigen den [Erfassungsschlüssel](instrument-website.md).

## <a name="run-sample"></a>Ausführen des Beispiels

1. [Laden Sie das Web SDK-Beispiel herunter](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Entpacken Sie die komprimierte Datei `ei_websdk_sample.zip`.

1. Öffnen Sie den entpackten Ordner in Visual Studio Code.

1. Ersetzen Sie in der Datei `ei_websdk_sample.html` die Zeichenfolge „INGESTION_KEY“ durch Ihren Erfassungsschlüssel vom Portal der Funktion Kundenbindungserkenntnisse und die Zeichenfolge „NAME“ durch den globalen Namen, mit dem das SDK instanziiert werden soll. Stellen Sie sicher, dass Sie alle Vorkommen ersetzen.

1. Öffnen Sie die Datei `ei_websdk_sample.html` mit Live Server in Visual Studio Code, indem Sie in der Statusleiste **Liveschaltung** auswählen.

1. Beim Öffnen der Seite sollte automatisch ein Ansichtsereignis gesendet werden. Durch Klicken auf eine beliebige Schaltfläche auf der Seite werden Aktionsereignisse gesendet. Die Schaltfläche **Ereignisse nachverfolgen** sendet auch benutzerdefinierte Ereignisse. Durch Auswahl der Schaltfläche **Zu Bing wechseln** wird ein Aktionsereignis gesendet, bevor Sie zur Bing-Website navigieren.

1. Sehen Sie sich den Fluss der Ereignisse an, wenn Sie zu Ihrem Arbeitsbereich navigieren. Dieser Arbeitsbereich ist dem in Schritt 4 eingegebenen Erfassungsschlüssel zugeordnet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]