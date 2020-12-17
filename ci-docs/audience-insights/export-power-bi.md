---
title: Power BI-Connector
description: Lernen Sie, wie der Dynamics 365 Customer Insights-Connector in Power BI verwendet wird.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405755"
---
# <a name="connector-for-power-bi-preview"></a>Connector für Power BI (Vorschau)

Erstellen Sie Visualisierungen für Ihre Daten mit dem Power BI Desktop. Generieren Sie zusätzliche Erkenntnisse und erstellen Sie Berichte mit Ihren einheitlichen Kundendaten.

## <a name="prerequisites"></a>Anforderungen

- Sie haben einheitliche Kundenprofile.
- Die neueste Version von [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) ist auf Ihrem Computer installiert. [Weitere Informationen zu Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurieren des Connector für Power BI

1. Wählen Sie in Power BI Desktop die Option **Datei** > **Daten empfangen** aus.

1. Wählen Sie **Mehr anzeigen** aus und suchen Sie nach **Dynamics 365 Customer Insights**.

1. Wählen Sie das Ergebnis und dann **Verbinden** aus.

1. **Melden Sie sich** mit demselben Organisationskonto an, das Sie für Customer Insights verwenden, und wählen Sie **Verbinden** aus.
   > [!NOTE]
   > Das Konto, das Sie in diesem Schritt angeben, wird zum Abrufen von Daten aus Customer Insights verwendet und muss nicht mit dem Konto identisch sein, bei dem Sie in Power BI angemeldet sind. Um das Konto zurückzusetzen, das für den Datenabruf verwendet wird, öffnen Sie Power BI und gehen Sie zu **Datei** > **Optionen** > **Einstellungen** > **Datenquelleneinstellungen**. Wählen Sie in der Liste der Datenquellen **Dynamics 365 Customer Insights-Anmeldung** und dann **Berechtigungen löschen** aus.  

1. Im Dialogfeld **Navigator**. sehen Sie die Liste aller Umgebungen, auf die Sie Zugriff haben. Erweitern Sie eine Umgebung und öffnen Sie einen der Ordner (Entitäten, Kennzahlen, Segmente, Anreicherungen). Öffnen Sie zum Beispiel den Ordner **Entitäten**, um alle Entitäten anzuzeigen, die Sie importieren können.

   ![Power BI Connector-Navigator](media/power-bi-navigator.png "Power BI Connector-Navigator")

1. Aktivieren Sie die Kontrollkästchen neben den Entitäten, die Sie einschließen möchten, und wählen Sie **Laden** aus. Sie können mehrere Entitäten aus mehreren Umgebungen auswählen.

1. Sie sehen ein Dialogfeld zum Laden, während Ihre Entitäten geladen werden. Sobald alle Ihre ausgewählten Entitäten geladen sind, können Sie die Funktionalitäten von Power BI verwenden, um die Daten zu visualisieren.

## <a name="large-data-sets"></a>Große Datasets

Der Customer Insights-Konnektor für Power BI wurde für Datasets entwickelt, die bis zu 1 Million Kundenprofile enthalten. Das Importieren größerer Datenmengen funktioniert möglicherweise, dauert jedoch lange. Außerdem kann es aufgrund von Power BI-Einschränkungen zu einer Zeitüberschreitung kommen. Weitere Informationen finden Sie unter [Power BI: Empfehlungen für große Datasets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Arbeiten mit einer Teilmenge von Daten

Erwägen Sie die Arbeit mit einer Teilmenge Ihrer Daten. Sie können z. B. [Segmente](segments.md) erstellen, anstatt alle Kundendatensätze nach Power BI zu exportieren.
