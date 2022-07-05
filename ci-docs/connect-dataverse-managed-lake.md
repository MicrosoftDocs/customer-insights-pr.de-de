---
title: Verbindung zu Daten in einem Microsoft Dataverse verwalteten Data Lake
description: Importieren Sie Daten aus einem verwalteten Microsoft Dataverse-Data Lake.
ms.date: 05/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 9ae0b964d8d39835715b7ddadc712e2338b855af
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080991"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Verbindung zu Daten in einem Microsoft Dataverse verwalteten Data Lake

Microsoft Dataverse Benutzer können sich schnell mit analytischen Einheiten in einem Microsoft Dataverse verwalteten Lake verbinden.

> [!NOTE]
> Sie müssen ein Administrator für die Dataverse-Organisation sein, um fortzufahren und die Liste der im verwalteten Lake verfügbaren Entitäten anzuzeigen.

## <a name="important-considerations"></a>Wichtige Überlegungen

1. In Online-Diensten gespeicherte Daten, wie z.B. Azure Data Lake Storage, können an einem anderen Ort gespeichert werden als dort, wo die Daten verarbeitet oder in Dynamics 365 Customer Insights gespeichert werden. Durch das Importieren von oder Verbinden mit Daten, die in Online-Diensten gespeichert sind, erklären Sie sich damit einverstanden, dass Daten an das Microsoft Trust Center übertragen und dort mit Dynamics 365 Customer Insights gespeichert werden können. [Erfahren Sie mehr im Microsoft Trust Center.](https://www.microsoft.com/trust-center).
2. Nur Dataverse Entitäten mit [Änderungsnachverfolgung](/power-platform/admin/enable-change-tracking-control-data-synchronization) aktiviert sind sichtbar. Diese Entitäten können in den Dataverse-verwalteten Data Lake exportiert und in Customer Insights verwendet werden. Dataverse Tabellen haben standardmäßig die Änderungsnachverfolgung aktiviert. Sie müssen die Änderungsnachverfolgung für benutzerdefinierte Tabellen aktivieren. Um zu prüfen, ob eine Dataverse Tabelle für die Änderungsverfolgung aktiviert ist, gehen Sie zu [Power Apps](https://make.powerapps.com) > **Daten** > **Tabellen**. Finden Sie die Tabelle Ihres Interesses und wählen Sie sie aus. Gehen Sie zu **Einstellungen** > **Erweiterte Optionen** und überprüfen Sie die Einstellung **Änderungsnachverfolgung**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Verbindung zu einem Dataverse verwalteten Lake

1. Wechseln Sie zu **Daten** > **Datenquellen**.

1. Wählen Sie **Datenquelle hinzufügen**.

1. Wählen Sie **Microsoft Dataverse** aus.

1. Geben Sie einen **Namen** und eine optionale **Beschreibung** für die neue Datenquelle ein.

1. Geben Sie die **Serveradresse** für die Dataverse-Organisation an und wählen Sie **Anmelden** aus.

1. Wählen Sie die Tabellen, die Sie als Entitäten in Customer Insights einbinden möchten, aus der verfügbaren Liste aus.

   > [!NOTE]
   > Wenn einige Tabellen bereits ausgewählt sind, liegt dies eventuell daran, dass sie von anderen Dynamics 365-Anwendungen (wie Dynamics 365 Sales Insights oder Customer Service Insights) verwendet werden. Die Auswahl kann nicht mehr geändert werden. Diese Tabellen sind als Entitäten verfügbar, sobald die Datenquelle erstellt wurde.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialogfeld mit einer Liste von Entitäten in der Dataverse-Umgebung.":::

1. Speichern Sie Ihre Auswahl, um mit der Synchronisierung der ausgewählten Tabellen aus Dataverse zu beginnen. Die neu hinzugefügte Verbindung finden Sie auf der Seite **Datenquellen**. Sie wird zur Aktualisierung in die Warteschlange gestellt und zeigt die Entitätsanzahl als 0 an, bis alle ausgewählten Tabellen synchronisiert sind.

Nur eine Datenquelle einer Umgebung kann gleichzeitig denselben Dataverse verwalteten Lake verwenden.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Bearbeiten von einer Dataverse verwalteten Datenquelle

Sie bearbeiten die Entitätsauswahl erst, nachdem Sie die Datenquelle erstellt haben. Zum Beispiel, wenn zusätzliche Entitäten zu Dataverse hinzugefügt wurden, und Sie sie auch importieren möchten.
Um eine Verbindung zu einem anderen Dataverse Data Lake herzustellen, [erstelle Sie eine neue Datenquelle](#connect-to-a-dataverse-managed-lake).

1. Wechseln Sie zu **Daten** > **Datenquellen**.

1. Wählen Sie neben der Datenquelle, die Sie aktualisieren möchten, **Bearbeiten** aus.

1. Wählen Sie zusätzliche Entitäten aus der verfügbaren Liste der Entitäten aus und wählen Sie **Speichern**.
