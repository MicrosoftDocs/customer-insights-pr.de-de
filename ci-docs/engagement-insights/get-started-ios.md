---
title: Erste Schritte mit iOS SDK
description: Erfahren Sie, wie Sie das iOS SDK personalisieren und ausführen
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: f05929435eeee9cf3f891ab18842c5861e39d5ba
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494229"
---
# <a name="get-started-with-the-ios-sdk"></a>Erste Schritte mit der iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Diese Anleitung führt Sie durch den Prozess der Instrumentalisierung Ihrer iOS Anwendung mit einer Dynamics 365 Customer Insights Kundenbindungserkenntnisse SDK. In fünf Minuten oder früher werden Ereignisse in Ihrem Portal angezeigt.

## <a name="configuration-options"></a>Konfigurationsoptionen

Die folgenden Konfigurationsoptionen können über die bereitgestellte `EIConfig.plist` Date an das SDK übergeben werden:

- **Erfassungsschlüssel**: Der Erfassungsschlüssel, der zum Senden von Ereignissen an Ihr Projekt verwendet wird.
- **AutocollectAction**: Ein boolescher Wert zum Aktivieren oder Deaktivieren der automatischen Instrumentierung des Aktionsereignisses.
- **AutocollectAction**: Ein boolescher Wert zum Aktivieren oder Deaktivieren der automatischen Instrumentierung des Ansichtsereignisses.
- **endpointUrl**: Die Endpunkt URL, an die die Ereignisse geleitet werden.

## <a name="prerequisites"></a>Anforderungen

- XCodeversion 9+
- iOS Version 8.2+
- Ein Aufnahmeschlüssel (siehe Anweisungen unten, um ihn zu erhalten)

## <a name="integrate-the-sdk-into-your-application"></a>Integrieren der SDK in Ihre Anwendung

Beginnen Sie den Vorgang, indem Sie einen Arbeitsbereich auswählen, in dem Sie arbeiten möchten, die iOS-Mobilplattform auswählen und das SDK herunterladen.

- Verwenden Sie den Arbeitsbereich-Umschalter im linken Navigationsbereich, um Ihren Arbeitsbereich auszuwählen.

- Wenn Sie keinen bestehenden Arbeitsbereich haben, wählen Sie **Neuer Arbeitsbereich** und befolgen Sie die Schritte zum Erstellen eines [neuen Arbeitsbereichs](create-workspace.md).

- Nachdem Sie einen Arbeitsbereich erstellt haben, gehen Sie zu **Administrator** > **Arbeitsplatz** und wählen **Installationsanleitung**.

## <a name="configure-the-sdk"></a>Konfigurieren des SDK

Nachdem Sie das SDK heruntergeladen haben, können Sie damit in Xcode arbeiten, um Ereignisse zu aktivieren und zu definieren. Hierzu stehen zwei Möglichkeiten zur Verfügung

### <a name="option-1-using-cocoapods-recommended"></a>Option 1: Verwenden von CocoaPods (empfohlen)
CocoaPods ist ein Abhängigkeitsmanager für Swift- und Objective-C-Cocoa-Projekte. Dadurch wird die Integration des Interaktionserkenntnisse SDK für iOS einfacher. CocoaPods ermöglicht Ihnen außerdem ein Upgrade auf die neueste Version des Interaktionserkenntnisse SDK. So verwenden Sie CocoaPods, um das Interaktionserkenntnisse SDK in Ihr Xcode-Projekt zu integrieren. 

1. Installieren Sie CocoaPods. 

1. Erstellen Sie eine neue Datei namens Podfile im Stammverzeichnis Ihres Projekts, und fügen Sie die folgenden Anweisungen hinzu.Ersetzen Sie YOUR_TARGET_PROJECT_NAME durch den Namen Ihres Xcode-Projekts. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
Die obige Pod-Konfiguration enthält sowohl die Debug- als auch die Releaseversionen des SDK. Wählen Sie diejenige aus, die für Ihr Projekt am besten geeignet ist.

1. Installieren Sie den Pod, indem Sie den folgenden Befehl ausführen: `pod install --repo-update `

### <a name="option-2-using-download-link"></a>Option 2: Downloadlink verwenden

1. Laden Sie die [Kundenbindungseinblicke iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) herunter und platzieren Sie die `EIObjC.xcframework` Datei im `Frameworks` Ordner.

1. Wenn ein `Frameworks` Ordner nicht vorhanden ist, erstellen Sie einen im Projektordner.

## <a name="enable-auto-instrumentation"></a>Automatische Instrumentierung aktivieren
 
Sie können die automatische Instrumentierung ganz einfach ohne Codierung aktivieren. Wenn das Projekt ausgeführt wird, verfolgt es automatisch die `view` und `action` Ereignisse mit dem konfigurierten Erfassungsschlüssel. 

1. Aktualisieren und fügen Sie die bereitgestellte `EIConfig.plist` Datei in Ihrem Projektverzeichnisordner für die folgenden Felder ein:
    - Erfassungsschlüssel = `"Your-Ingestion-Key"`
    - autocollectView = JA
    - autocollectAction = JA

2. Dann füge die `EIConfig.plist` Datei in Ihr Projekt in Xcode hinzu. 



Um die automatische Instrumentierung zu deaktivieren, aktualisieren Sie die folgenden Felder in der bereitgestellten `EIConfig.plist` Datei in Ihrem Projektverzeichnisordner. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Benutzerdefinierten Ereignisse implementieren

1. Öffnen Sie Ihr Projekt in Xcode und navigieren Sie zu den Einstellungen **Allgemein**. 
1. Ergänzen Sie die `EIObjC.xcframework` zum Projekt im Abschnitt Frameworks, Bibliotheken und eingebettete Inhalte.

1. die Framework-Kopfzeilendatei in AppDelegate.m mit dem folgenden Ausschnitt importieren:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Initialisieren Sie Kundenbindungseinblicke SDK aus der Anwendung: didFinishLaunchingWithOptions.
1. Kopieren Sie den XML-Ausschnitt aus der **Installationsanleitung**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Ereignis nachverfolgen:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Legen Sie Benutzerdetails für Ihre Veranstaltung fest

Mit dem SDK können Sie Benutzerinformationen definieren, die mit jedem Ereignis gesendet werden können. Sie können Benutzerinformationen angeben, indem Sie die `setUser:(nonnull EIUser *)user` API auf dem SDK aufrufen.

Angeben von Benutzerdetails auf der `Analytics` Ebene bedeutet, dass alle Telemetriedaten über diese Informationen verfügen. Wenn Sie jedoch auf Ereignisebene angeben, indem Sie die `setUser:(nonnull EIUser *)user` API für das EIEvent-Objekt aufrufen, enthält nur dieses spezifische Ereignis die Informationen.

Die `EIUser` Datenklasse enthält die folgenden NSString-Eigenschaften:

- **localId**: Die lokale ID des Benutzers.
- **authId**: Die authentifizierte Benutzer-ID.
- **authType**: Der Authentifizierungstyp, mit dem die authentifizierte Benutzer-ID abgerufen wird.
- **name**: Der Name des Benutzers.
- **email**: Die E-Mail-Adresse des Benutzers.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
