---
title: Power BI-Connector
description: Lernen Sie, wie der Dynamics 365 Customer Insights-Connector in Power BI verwendet wird.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e901114703a43b4b4e751e0a93eb4876d7636c00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647160"
---
# <a name="connector-for-power-bi-preview"></a>Connector für Power BI (Vorschau)

Erstellen Sie Visualisierungen für Ihre Daten mit dem Power BI Desktop. Generieren Sie zusätzliche Erkenntnisse und erstellen Sie Berichte mit Ihren einheitlichen Kundendaten.

## <a name="prerequisites"></a>Anforderungen

- Sie haben einheitliche Kundenprofile.
- Die neueste Version von [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) ist auf Ihrem Computer installiert. [Weitere Informationen zu Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurieren des Connector für Power BI

1. Wählen Sie in Power BI Desktop die Option **Datei** > **Daten empfangen** aus.

1. Wählen Sie **Mehr anzeigen** aus und suchen Sie nach **Dynamics 365 Customer Insights**.

1. Wählen Sie **Verbinden** aus.

1. **Melden Sie sich** mit demselben Organisationskonto an, das Sie für Customer Insights verwenden, und wählen Sie **Verbinden** aus.
   > [!NOTE]
   > Das Konto, das Sie in diesem Schritt angeben, wird zum Abrufen von Daten aus Customer Insights verwendet und muss nicht mit dem Konto identisch sein, bei dem Sie in Power BI angemeldet sind. Um das Konto zurückzusetzen, das für den Datenabruf verwendet wird, öffnen Sie Power BI und gehen Sie zu **Datei** > **Optionen** > **Einstellungen** > **Datenquelleneinstellungen**. Wählen Sie in der Liste der Datenquellen **Dynamics 365 Customer Insights-Anmeldung** und dann **Berechtigungen löschen** aus.  

1. Im Dialogfeld **Navigator**. sehen Sie die Liste aller Umgebungen, auf die Sie Zugriff haben. Erweitern Sie eine Umgebung und öffnen Sie einen der Ordner (Entitäten, Kennzahlen, Segmente, Anreicherungen). Öffnen Sie zum Beispiel den Ordner **Entitäten**, um alle Entitäten anzuzeigen, die Sie importieren können.

   ![Power BI Connector-Navigator.](media/power-bi-navigator.png "Power BI Connector-Navigator")

1. Aktivieren Sie die Kontrollkästchen neben den Entitäten, die Sie einschließen möchten, und wählen Sie **Laden** aus. Sie können mehrere Entitäten aus mehreren Umgebungen auswählen.

1. Sie sehen ein Dialogfeld zum Laden, während Ihre Entitäten geladen werden. Sobald alle Ihre ausgewählten Entitäten geladen sind, können Sie die Funktionalitäten von Power BI verwenden, um die Daten zu visualisieren.

## <a name="large-data-sets"></a>Große Datasets

Der Customer Insights-Konnektor für Power BI wurde für Datasets entwickelt, die bis zu 1 Million Kundenprofile enthalten. Das Importieren größerer Datenmengen funktioniert möglicherweise, dauert jedoch lange. Außerdem kann es aufgrund von Power BI-Einschränkungen zu einer Zeitüberschreitung kommen. Weitere Informationen finden Sie unter [Power BI: Empfehlungen für große Datasets](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Arbeiten mit einer Teilmenge von Daten

Erwägen Sie die Arbeit mit einer Teilmenge Ihrer Daten. Sie können z. B. [Segmente](segments.md) erstellen, anstatt alle Kundendatensätze nach Power BI zu exportieren.

## <a name="troubleshooting"></a>Problembehandlung

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Die Customer Insights-Umgebung wird nicht in Power BI angezeigt

Umgebungen, in denen mehr als eine [Beziehung](relationships.md) zwischen zwei identischen Entitäten in Customer Insights definiert ist, sind im Konnektor Power BI nicht verfügbar.

Sie können das duplizierte Beziehungen identifizieren und entfernen.

1. Gehen Sie zu **Daten** > **Beziehungen** in der Umgebung, die Ihnen in Power BI fehlt.
2. Identifizieren Sie duplizierte Beziehungen:
   - Überprüfen Sie, ob zwischen denselben beiden Entitäten mehr als eine Beziehung definiert ist.
   - Überprüfen Sie, ob eine Beziehung zwischen zwei Entitäten erstellt wurde, die beide im Vereinigungsprozess enthalten sind. Zwischen allen am Vereinigungsprozess beteiligten Entitäten ist eine implizite Beziehung definiert.
3. Entfernen Sie alle identifizierten doppelten Beziehungen.

Versuchen Sie nach dem Entfernen des duplizierten Beziehungen, den Power BI-Konnektor wieder zu konfigurieren. Die Umgebung sollte jetzt verfügbar sein.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Fehler in Datumsfeldern beim Laden von Entitäten in Power BI Desktop

Beim Laden von Entitäten, die Felder mit einem Datumsformat wie MM/TT/JJJJ enthalten, können Fehler aufgrund nicht übereinstimmender Gebietsschemaformate auftreten. Diese Fehlanpassung tritt auf, wenn Ihre Power BI Desktop-Datei auf ein anderes Gebietsschema als Englisch (Vereinigte Staaten) festgelegt ist, da die Datumsfelder in Customer Insights im US-Format gespeichert werden.

Die Power BI Desktop-Datei hat eine einzelne Gebietsschemaeinstellung, die beim Abrufen von Daten angewendet wird. Damit diese Datumsfelder richtig interpretiert werden, legen Sie das Gebietsschema der .BPI-Datei auf Englisch (Vereinigte Staaten) fest. [Erfahren Sie, wie Sie das Gebietsschema einer Power BI Desktop-Datei ändern](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop).

[!INCLUDE [footer-include](includes/footer-banner.md)]
