---
title: Ausführen des iOS SDK Beispiels
description: Beispielprojekt, um mehr über die iOS SDK zu erfahren
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 053e626d06d3e17b39b448987410058e45e8ae0385f3ecdef40314cb46ae4bf4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036827"
---
# <a name="run-the-ios-sdk-sample"></a>Ausführen des iOS SDK Beispiels

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dieses Beispiel iOS Projekt hilft Ihnen zu verstehen, wie das SDK in einer App funktioniert. Sie müssen keinen Code schreiben. Fügen Sie einfach Ihren Erfassungsschlüssel hinzu und Sie können sofort Ereignisse in Ihrem Arbeitsbereich sehen.

## <a name="prerequisites"></a>Anforderungen

- [XCodeversion 9+](https://developer.apple.com/xcode/downloads/)
- [Aufnahmeschlüssel](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>iOS SDK Beispiel herunterladen

1. [Laden Sie die Kundenbindungseinblicke iOS SDK-Beispiel herunter](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Entpacken Sie die komprimierte Datei `ei-ios-sample.zip`.
1. Öffnen Sie das Beispiel-App-Projekt in Xcode.
1. In der `EIConfig.plist` Datei ersetzen Sie die Zeichenfolge `“YOUR-INGESTION-KEY”` im Feld `ingestionKey` mit Ihrem Arbeitsbereich-Erfassungsschlüssel aus Kundenbindungseinblicken unter **Administrator** > **Arbeitsplatz** > **Installationsanleitung**.
1. Um sofort mit dem Beispielprojekt zu beginnen, wählen Sie **Ausführen** aus.
1. Zeigen Sie die Ereignisse in Ihrem Arbeitsbereich an.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
