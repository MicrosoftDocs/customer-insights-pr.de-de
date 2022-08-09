---
title: Power BI-Connector (Vorschauversion)
description: Lernen Sie, wie der Dynamics 365 Customer Insights-Connector in Power BI verwendet wird.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196669"
---
# <a name="power-bi-connector-preview"></a>Power BI-Connector (Vorschauversion)

Erstellen Sie Visualisierungen für Ihre Daten mit Microsoft Power BI Desktop. Generieren Sie zusätzliche Erkenntnisse und erstellen Sie Berichte mit Ihren einheitlichen Kundendaten.

## <a name="prerequisites"></a>Anforderungen

- Vereinheitlichtes Kundenprofil
- Die neueste Version von [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) ist auf Ihrem Computer installiert. [Weitere Informationen zu Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurieren des Connector für Power BI

1. Wählen Sie in Power BI Desktop die Option **Datei** > **Daten empfangen** aus.

1. Wählen Sie **Mehr anzeigen** aus und suchen Sie nach **Dynamics 365 Customer Insights**.

1. Wählen Sie **Verbinden** aus.

1. **Melden Sie sich** mit demselben Organisationskonto an, das Sie für Customer Insights verwenden, und wählen Sie **Verbinden** aus.
   > [!NOTE]
   > Das Konto, das Sie in diesem Schritt angeben, wird zum Abrufen von Daten aus Customer Insights verwendet und muss nicht mit dem Konto identisch sein, bei dem Sie in Power BI angemeldet sind. Um das Konto zurückzusetzen, das für den Datenabruf verwendet wird, öffnen Sie Power BI und gehen Sie zu **Datei** > **Optionen** > **Einstellungen** > **Datenquelleneinstellungen**. Wählen Sie in der Liste der Datenquellen **Dynamics 365 Customer Insights-Anmeldung** und dann **Berechtigungen löschen** aus.  

1. Zeigen Sie im Dialogfeld **Navigator** die Liste aller Umgebungen an, auf die Sie Zugriff haben. Erweitern Sie eine Umgebung und öffnen Sie einen der Ordner (Entitäten, Kennzahlen, Segmente, Anreicherungen). Öffnen Sie zum Beispiel den Ordner **Entitäten**, um alle Entitäten anzuzeigen, die Sie importieren können.

   :::image type="content" source="media/power-bi-navigator.png" alt-text="Power BI Connector-Navigator.":::

1. Aktivieren Sie die Kontrollkästchen neben den Entitäten, die Sie einschließen möchten, und wählen Sie **Laden** aus. Sie können mehrere Entitäten aus mehreren Umgebungen auswählen.

   Sie sehen ein Dialogfeld zum Laden, während Ihre Entitäten geladen werden. Sobald alle Ihre ausgewählten Entitäten geladen sind, können Sie die Funktionalitäten von Power BI verwenden, um die Daten zu visualisieren.

## <a name="large-data-sets"></a>Große Datasets

Der Customer Insights-Konnektor für Power BI wurde für Datasets entwickelt, die bis zu 1 Million Kundenprofile enthalten. Das Importieren größerer Datensätze funktioniert möglicherweise, dauert jedoch lange und kann Zeitüberschreitungen durch Power BI Einschränkungen haben. Weitere Informationen finden Sie unter [Power BI: Empfehlungen für große Datasets](/power-bi/admin/service-premium-what-is#large-datasets).

### <a name="work-with-a-subset-of-data"></a>Arbeiten mit einer Teilmenge von Daten

Erwägen Sie die Arbeit mit einer Teilmenge Ihrer Daten. Sie können z. B. [Segmente](segments.md) erstellen, anstatt alle Kundendatensätze nach Power BI zu exportieren.

## <a name="troubleshooting"></a>Problembehandlung

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Die Customer Insights-Umgebung wird nicht in Power BI angezeigt

Umgebungen, in denen mehr als eine [Beziehung](relationships.md) zwischen zwei identischen Entitäten in Customer Insights definiert ist, sind im Konnektor Power BI nicht verfügbar.

Identifizieren und entfernen Sie duplizierte Beziehungen.

1. Gehen Sie zu **Daten** > **Beziehungen** in der Umgebung, die Ihnen in Power BI fehlt.
1. Identifizieren Sie duplizierte Beziehungen:
   - Überprüfen Sie, ob zwischen denselben beiden Entitäten mehr als eine Beziehung definiert ist.
   - Überprüfen Sie, ob eine Beziehung zwischen zwei Entitäten erstellt wurde, die beide im Vereinigungsprozess enthalten sind. Zwischen allen am Vereinigungsprozess beteiligten Entitäten ist eine implizite Beziehung definiert.
1. Entfernen Sie alle identifizierten doppelten Beziehungen.

Versuchen Sie nach dem Entfernen des duplizierten Beziehungen, den Power BI-Konnektor wieder zu konfigurieren.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Fehler in Datumsfeldern beim Laden von Entitäten in Power BI Desktop

Beim Laden von Entitäten, die Felder mit einem Datumsformat wie MM/TT/JJJJ enthalten, können Fehler aufgrund nicht übereinstimmender Gebietsschemaformate auftreten. Diese Fehlanpassung tritt auf, wenn Ihre Power BI Desktop-Datei auf ein anderes Gebietsschema als Englisch (Vereinigte Staaten) festgelegt ist, da die Datumsfelder in Customer Insights im US-Format gespeichert werden.

Die Power BI Desktop-Datei hat eine einzelne Gebietsschemaeinstellung, die beim Abrufen von Daten angewendet wird. Um die Datenfehler zu reparieren, [setzen Sie das Gebietsschema der .BPI-Datei](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) auf Englisch (Vereinigte Staaten).

[!INCLUDE [footer-include](includes/footer-banner.md)]
