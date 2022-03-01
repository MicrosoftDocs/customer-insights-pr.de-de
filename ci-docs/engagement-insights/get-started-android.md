---
title: Erste Schritte mit Android SDK
description: Erfahren Sie, wie Sie das Android SDK personalisieren und ausführen
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c678c2dafbb77926269b5602bca363c678ec6b3f
ms.sourcegitcommit: ef823f3d7fa28d3a90cfde9409be9465ffa2cf09
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2021
ms.locfileid: "7655341"
---
# <a name="get-started-with-the-android-sdk"></a>Erste Schritte mit dem Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Diese Anleitung führt Sie durch den Prozess der Instrumentalisierung Ihrer Android App mit den Dynamics 365 Customer Insights Kundenbindungserkenntnisse SDK. In fünf Minuten oder früher werden Ereignisse in Ihrem Portal angezeigt.

## <a name="configuration-options"></a>Konfigurationsoptionen
Die folgenden Konfigurationsoptionen können über die bereitgestellte Date an das SDK übergeben werden:

- **Erfassungsschlüssel**: Der Erfassungsschlüssel, der zum Senden von Ereignissen an Ihren Arbeitsbereich verwendet wird.

## <a name="prerequisites"></a>Anforderungen

- Android Studio

- Minimum Android API-Level: 16 (Jelly Bean)

- Ein Erfassungsschlüssel (siehe Anweisungen unten, um ihn zu erhalten)

## <a name="integrate-the-sdk-into-your-application"></a>Integrieren der SDK in Ihre Anwendung
Beginnen Sie den Vorgang, indem Sie einen Arbeitsbereich auswählen, in dem Sie arbeiten möchten, die Android Mobilplattform auswählen und das Android herunterladen.

- Verwenden Sie den Arbeitsbereich-Umschalter im linken Navigationsbereich, um Ihren Arbeitsbereich auszuwählen.

- Wenn Sie keinen bestehenden Arbeitsbereich haben, wählen Sie **Neuer Arbeitsbereich** und befolgen Sie die Schritte zum Erstellen eines [neuen Arbeitsbereichs](create-workspace.md).

- Nachdem Sie einen Arbeitsbereich erstellt haben, gehen Sie zu **Administrator** > **Arbeitsbereich** und wählen Sie **Installationsanleitung**.

## <a name="configure-the-sdk"></a>Konfigurieren des SDK

Nachdem Sie das SDK heruntergeladen haben, können Sie damit in Android Studio arbeiten, um Ereignisse zu aktivieren und zu definieren. Hierzu stehen zwei Möglichkeiten zur Verfügung:
### <a name="option-1-use-jitpack-recommended"></a>Option 1: JitPack verwenden (empfohlen)
1. Fügen Sie das JitPack-Repository zu Ihrem Stamm `build.gradle` hinzu:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Fügen Sie die Abhängigkeit hinzu:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>Option 2: Downloadlink verwenden
1. Laden Sie die [Kundenbindungseinblicke Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) herunter und platzieren Sie die `eiandroidsdk-debug.aar` Datei im `libs` Ordner.

1. Ihre Projektebene `build.gradle` Datei öffnen und die folgenden Ausschnitte hinzufügen:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

## <a name="enable-auto-instrumentation"></a>Automatische Instrumentierung aktivieren

1. Fügen Sie die Berechtigung für das Netzwerk und das Internet in der Datei `AndroidManifest.xml` im Ordner `manifests` hinzu.
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. Richten Sie die Konfiguration des Interaktionserkenntnisse SDK über Ihre `AndroidManifest.xml` Datei ein.

1. Kopieren Sie den XML-Ausschnitt aus der **Installationsanleitung**. `Your-Ingestion-Key` sollte automatisch ausgefüllt werden.

   > [!NOTE]
   > Sie müssen den `${applicationId}` Abschnitt nicht ersetzen. Es wird automatisch ausgefüllt.


   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Aktivieren oder deaktivieren Sie die automatische Erfassung von `View` Ereignissen, indem Sie das `autoCapture` Feld auf `true` oder `false` festlegen. 

   >[!NOTE]
   >`Action`-Ereignisse müssen manuell hinzugefügt werden.

1. (Optional) Andere Konfigurationen umfassen das Festlegen der Endpunkt-Collector-URL. Sie können sie unter den Erfassungsschlüssel-Metadaten in `AndroidManifest.xml` hinzufügen.

   ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
   ```

## <a name="implement-custom-events"></a>Benutzerdefinierten Ereignisse implementieren

Nachdem Sie das SDK initialisiert haben, können Sie mit Ereignissen und ihren Eigenschaften in der `MainActivity`-Umgebung arbeiten.


Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Eigenschaft für alle Ereignisse festlegen (optional)

Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Die folgenden Typen werden für Kontextereigniseigenschaften unterstützt:
- String
- Datum
- Doppelt
- Lang
- Boolesch
- UUID

### <a name="track-an-event"></a>Ereignis nachverfolgen

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

## <a name="set-user-details-for-your-event-optional"></a>Legen Sie Benutzerdetails für Ihr Ereignis fest (optional)

Mit dem SDK können Sie Benutzerinformationen definieren, die mit jedem Ereignis gesendet werden können. Sie können Benutzerinformationen angeben, indem Sie die `setUser(user: User)` API auf der `Analytics` Stufe aufrufen.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Die `User` Datenklasse enthält die folgenden Zeichenfolgen-Eigenschaften:

- **localId**: Die lokale ID des Benutzers.
- **authId**: Die authentifizierte Benutzer-ID.
- **Authentifizierungstyp**: Der Authentifizierungstyp, der zum Abrufen der authentifizierten Benutzer-ID verwendet wird.
- **name**: Der Name des Benutzers.
- **email**: Die E-Mail-Adresse des Benutzers.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
