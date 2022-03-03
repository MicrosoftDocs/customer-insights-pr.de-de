---
title: Android SDK Beispiel
description: Beispielprojekt, um mehr über die Android SDK zu erfahren
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2ee29a98192bb53bd92241d71c1a76ec2b7bf846
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229917"
---
# <a name="run-the-android-sdk-sample"></a>Ausführen des Android SDK Beispiels

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dieses Beispiel Android Projekt hilft Ihnen zu verstehen, wie das SDK in einer App funktioniert. Sie müssen keinen Code schreiben. Fügen Sie einfach Ihren Erfassungsschlüssel hinzu und Sie können sofort Ereignisse in Ihrem Arbeitsbereich sehen.

## <a name="prerequisites"></a>Anforderungen

- [Android Studio](https://developer.android.com/studio)
- [Aufnahmeschlüssel](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Android SDK Beispiel herunterladen

1. [Laden Sie die Kundenbindungseinblicke Android SDK-Beispiel](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip) herunter.
1. Entpacken Sie die komprimierte Datei `ei-android-sample.zip`.
1. Extrahieren Sie den Ordner in Android Studio.
1. In der `AndroidManifest.xml` Datei ersetzen Sie die Zeichenfolge `"Your-Ingestion-Key"` mit Ihrem Arbeitsbereich-Erfassungsschlüssel aus Kundenbindungseinblicken unter **Administrator** > **Arbeitsplatz** > **Installationsanleitung**. 

   > [!NOTE]
   > Sie müssen den `${applicationId}` Abschnitt nicht ersetzen. Es wird automatisch ausgefüllt.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Um sofort mit dem Beispielprojekt zu beginnen, wählen Sie **Ausführen** aus.
1. Zeigen Sie die Ereignisse in Ihrem Arbeitsbereich an.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
