---
title: Verbindung zu Entitäten im verwalteten Common Data Service Lake
description: Importieren Sie Daten aus einem verwalteten Common Data Service-Data Lake.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596958"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Verbindung zu Daten in einem Common Data Service verwalteten Data Lake

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dieser Artikel enthält Informationen darüber, wie vorhandene Dynamics 365-Kunden schnell eine Verbindung zu ihren Analyseentitäten im verwalteten Common Data Service-Lake herstellen können. Sie müssen ein Administrator in der Common Data Service-Organisation sein, um fortzufahren und die Liste der im verwalteten Lake verfügbaren Entitäten anzuzeigen.

## <a name="important-considerations"></a>Wichtige Überlegungen

In Online-Diensten gespeicherte Daten, wie z.B. Azure Data Lake Storage, können an einem anderen Ort gespeichert werden als dort, wo die Daten verarbeitet oder in Dynamics 365 Customer Insights gespeichert werden. Durch das Importieren von oder Verbinden mit Daten, die in Online-Diensten gespeichert sind, erklären Sie sich damit einverstanden, dass Daten an das Microsoft Trust Center übertragen und dort mit Dynamics 365 Customer Insights gespeichert werden können. [Lernen Sie mehr im Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Verbindung zu einem Common Data Service verwalteten Lake

1. Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.

2. Wählen Sie **Datenquelle hinzufügen**.

3. Wählen Sie **Verbinden mit Common Data Service** und wählen Sie **Weiter**.

4. Geben Sie einen **Namen** für das Team ein und wählen Sie **Weiter**. Namensrichtlinien: 
   - Beginnen Sie mit einem Buchstaben.
   - Verwenden Sie nur Buchstaben und Zahlen. Leerzeichen und Sonderzeichen sind nicht zulässig.
   - Verwenden Sie zwischen 3 und 64 Zeichen.

5. Stellen Sie die **Serveradresse** für Ihre Common Data Service Organisation bereit und wählen Sie **Anmeldung**.

   > [!div class="mx-imgBorder"]
   > ![Dialogfeld zum Eingeben der Common Data Service Serveradresse](media/enter-CDS-org-details.png)

6. Wählen Sie die Entitäten, die Sie aufnehmen wollen, aus der verfügbaren Liste.    

   > [!NOTE]
   > Wenn einige Entitäten bereits ausgewählt sind, können sie von anderen Dynamics 365 Anwendungen verwendet werden (z. B. Dynamics 365 Sales Insights oder Customer Service Insights). Die Auswahl kann nicht mehr geändert werden. Diese Entitäten sind verfügbar, sobald die Datenquelle erstellt wurde.

   > [!div class="mx-imgBorder"]
   > ![Dialogfeld mit einer Liste der Entitäten in der Common Data Service Org](media/select-analytical-entities.png)

7. Speichern Sie Ihre Auswahl, um die Synchronisierung der ausgewählten Objekte mit dem Common Data Service verwalteten Lake zu starten. Die neu hinzugefügte Verbindung finden Sie auf der Seite **Datenquellen**. Es wird zur Aktualisierung in die Warteschlange gestellt und zeigt die Anzahl der Entitäten als 0 an, bis alle Entitäten synchronisiert sind.

Nur eine Datenquelle einer Umgebung kann gleichzeitig denselben Common Data Service verwalteten Lake verwenden.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Bearbeiten von einer Common Data Service verwalteten Datenquelle

Sie bearbeiten die Entitätsauswahl erst, nachdem Sie die Datenquelle erstellt haben. Zum Beispiel, wenn zusätzliche Entitäten zu Common Data Service hinzugefügt wurden, und Sie sie auch importieren möchten.    
Stellen Sie eine Verbindung zu einer anderen Common Data Service her, [Eine neue Datenquelle erstelle](#connect-to-a-common-data-service-managed-lake).

1. Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.

2. Wählen Sie neben der Datenquelle, die Sie aktualisieren möchten, die Auslassungspunkte aus.

3. Wählen Sie eine Option **Bearbeiten** in der Liste aus.

4. Wählen Sie zusätzliche Entitäten aus der verfügbaren Liste der Entitäten aus und wählen Sie **Speichern**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]