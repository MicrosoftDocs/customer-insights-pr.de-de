---
title: Verbindung mit Tabellen in Microsoft Dataverse herstellen
description: Importieren Sie Daten aus einem verwalteten Microsoft Dataverse-Data Lake.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: ffeccffd0e353cb5490b537552d585c184ad672f9c806e673bd04743214ad068
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033079"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Verbindung zu Daten in einem Microsoft Dataverse verwalteten Data Lake

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

In diesem Artikel erfahren Sie, wie Dataverse-Benutzer schnell eine Verbindung zu ihren analytischen Entitäten in einem verwalteten Dataverse Data Lake herstellen können. Sie müssen ein Administrator in der Dataverse-Organisation sein, um fortzufahren und die Liste der im verwalteten Lake verfügbaren Entitäten anzuzeigen.

## <a name="important-considerations"></a>Wichtige Überlegungen

In Online-Diensten gespeicherte Daten, wie z.B. Azure Data Lake Storage, können an einem anderen Ort gespeichert werden als dort, wo die Daten verarbeitet oder in Dynamics 365 Customer Insights gespeichert werden. Durch das Importieren von oder Verbinden mit Daten, die in Online-Diensten gespeichert sind, erklären Sie sich damit einverstanden, dass Daten an das Microsoft Trust Center übertragen und dort mit Dynamics 365 Customer Insights gespeichert werden können. [Lernen Sie mehr im Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Verbindung zu einem Dataverse verwalteten Lake

1. Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.

2. Wählen Sie **Datenquelle hinzufügen**.

3. Wählen Sie **Verbindung mit verwaltetem Microsoft Dataverse Data Lake** und dann **Weiter** aus.

4. Geben Sie einen **Namen** für das Team ein und wählen Sie **Weiter**. Namensrichtlinien: 
   - Beginnen Sie mit einem Buchstaben.
   - Verwenden Sie nur Buchstaben und Zahlen. Leerzeichen und Sonderzeichen sind nicht zulässig.
   - Verwenden Sie zwischen 3 und 64 Zeichen.

5. Geben Sie die **Serveradresse** für die Dataverse-Organisation an und wählen Sie **Anmelden** aus.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Bildschirm im Datenerfassungsschritt, in dem ein Benutzer die Dataverse-Umgebungs-URL eingeben kann.":::

6. Wählen Sie aus der verfügbaren Liste die Tabellen aus, die Sie als Entitäten in Zielgruppenerkenntnissen erfassen möchten.    

   > [!NOTE]
   > Wenn einige Tabellen bereits ausgewählt sind, liegt dies eventuell daran, dass sie von anderen Dynamics 365-Anwendungen (wie Dynamics 365 Sales Insights oder Customer Service Insights) verwendet werden. Die Auswahl kann nicht mehr geändert werden. Diese Tabellen sind als Entitäten verfügbar, sobald die Datenquelle erstellt wurde.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialogfeld mit einer Liste von Entitäten in der Dataverse-Umgebung.":::

7. Speichern Sie Ihre Auswahl, um mit der Synchronisierung der ausgewählten Tabellen aus Dataverse zu beginnen. Die neu hinzugefügte Verbindung finden Sie auf der Seite **Datenquellen**. Sie wird zur Aktualisierung in die Warteschlange gestellt und zeigt die Entitätsanzahl als 0 an, bis alle ausgewählten Tabellen synchronisiert sind.

Nur eine Datenquelle einer Umgebung kann gleichzeitig denselben Dataverse verwalteten Lake verwenden.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Bearbeiten von einer Dataverse verwalteten Datenquelle

Sie bearbeiten die Entitätsauswahl erst, nachdem Sie die Datenquelle erstellt haben. Zum Beispiel, wenn zusätzliche Entitäten zu Dataverse hinzugefügt wurden, und Sie sie auch importieren möchten.    
Um eine Verbindung zu einem anderen Dataverse Data Lake herzustellen, [erstelle Sie eine neue Datenquelle](#connect-to-a-dataverse-managed-lake).

1. Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.

2. Wählen Sie neben der Datenquelle, die Sie aktualisieren möchten, die Auslassungspunkte aus.

3. Wählen Sie eine Option **Bearbeiten** in der Liste aus.

4. Wählen Sie zusätzliche Entitäten aus der verfügbaren Liste der Entitäten aus und wählen Sie **Speichern**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]