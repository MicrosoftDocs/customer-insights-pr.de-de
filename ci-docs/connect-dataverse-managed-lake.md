---
title: Verbindung zu Daten in einem Microsoft Dataverse verwalteten Data Lake
description: Importieren Sie Daten aus einem verwalteten Microsoft Dataverse-Data Lake.
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609794"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Verbindung zu Daten in einem Microsoft Dataverse verwalteten Data Lake

Microsoft Dataverse Benutzer können sich schnell mit analytischen Einheiten in einem Microsoft Dataverse verwalteten Lake verbinden. Nur eine Datenquelle einer Umgebung kann gleichzeitig denselben Dataverse verwalteten Lake verwenden.

> [!NOTE]
> Sie müssen ein Administrator für die Dataverse-Organisation sein, um fortzufahren und die Liste der im verwalteten Lake verfügbaren Entitäten anzuzeigen.

## <a name="prerequisites"></a>Anforderungen

- In Online-Diensten gespeicherte Daten, wie z.B. Azure Data Lake Storage, können an einem anderen Ort gespeichert werden als dort, wo die Daten verarbeitet oder in Dynamics 365 Customer Insights gespeichert werden. Durch das Importieren von oder Verbinden mit Daten, die in Online-Diensten gespeichert sind, erklären Sie sich damit einverstanden, dass Daten an das Microsoft Trust Center übertragen und dort mit Dynamics 365 Customer Insights gespeichert werden können. [Erfahren Sie mehr im Microsoft Trust Center.](https://www.microsoft.com/trust-center).

- Nur Dataverse Entitäten mit [Änderungsnachverfolgung](/power-platform/admin/enable-change-tracking-control-data-synchronization) aktiviert sind sichtbar. Diese Entitäten können in den Dataverse-verwalteten Data Lake exportiert und in Customer Insights verwendet werden. Dataverse Tabellen haben standardmäßig die Änderungsnachverfolgung aktiviert. Sie müssen die Änderungsnachverfolgung für benutzerdefinierte Tabellen aktivieren. Um zu prüfen, ob eine Dataverse Tabelle für die Änderungsverfolgung aktiviert ist, gehen Sie zu [Power Apps](https://make.powerapps.com) > **Daten** > **Tabellen**. Finden Sie die Tabelle Ihres Interesses und wählen Sie sie aus. Gehen Sie zu **Einstellungen** > **Erweiterte Optionen** und überprüfen Sie die Einstellung **Änderungsnachverfolgung**.

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

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Das Laden von Daten kann einige Zeit in Anspruch nehmen. Nach einer erfolgreichen Aktualisierung können die aufgenommenen Daten von der Seite [**Entitäten**](entities.md) überprüft werden.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Bearbeiten von einer Dataverse verwalteten Datenquelle

Sie bearbeiten die Entitätsauswahl erst, nachdem Sie die Datenquelle erstellt haben. Zum Beispiel, wenn zusätzliche Entitäten zu Dataverse hinzugefügt wurden, und Sie sie auch importieren möchten.
Um eine Verbindung zu einem anderen Dataverse Data Lake herzustellen, [erstelle Sie eine neue Datenquelle](#connect-to-a-dataverse-managed-lake).

1. Wechseln Sie zu **Daten** > **Datenquellen**.

1. Wählen Sie neben der Datenquelle, die Sie aktualisieren möchten, **Bearbeiten** aus.

1. Wählen Sie zusätzliche Entitäten aus der verfügbaren Liste der Entitäten aus.

1. Klicken Sie auf **Speichern**, um Ihre Änderungen zu übernehmen und zur Seite **Datenquellen** zurückzukehren.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>Häufige Gründe für Erfassungsfehler oder beschädigte Daten

Die folgenden Prüfungen werden für die erfassten Daten ausgeführt, um beschädigte Datensätze zu erkennen:

- Der Wert eines Felds stimmt nicht mit dem Datentyp seiner Spalte überein.
- Felder enthalten Zeichen, die dazu führen, dass die Spalten nicht dem erwarteten Schema entsprechen. Beispiel: falsch formatierte Anführungszeichen, nicht in Escape-Zeichen gesetzte Anführungszeichen oder Zeilenumbruchzeichen.
- Wenn datetime/date/datetimeoffset-Spalten vorhanden sind, muss deren Format im Modell angegeben werden, wenn es nicht dem Standard-ISO-Format entspricht.

### <a name="schema-or-data-type-mismatch"></a>Schema- oder Datentypkonflikt

Wenn die Daten nicht dem Schema entsprechen, werden die Datensätze als beschädigt eingestuft. Korrigieren Sie entweder die Quelldaten oder das Schema und erfassen Sie die Daten erneut.

### <a name="datetime-fields-in-the-wrong-format"></a>DateTime-Felder im falschen Format

Die DateTime-Felder in der Entität sind nicht im ISO- oder im en-US-Format. Das standardmäßige DateTime-Format in Customer Insights ist das en-US-Format. Alle DateTime-Felder in einer Entität sollten dasselbe Format haben. Customer Insights unterstützt andere Formate, sofern Anmerkungen oder Merkmale auf Quell- oder Entitätsebene in der model- oder manifest.json-Datei vorgenommen werden. Zum Beispiel:

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  In einer manifest.json-Datei kann das DateTime-Format auf Entitätsebene oder auf Attributebene angegeben werden. Verwenden Sie auf der Entitätsebene „exhibitsTraits“ in der Entität in der *.manifest.cdm.json, um das DateTime-Format zu definieren. Verwenden Sie auf Attributebene „appliedTraits“ im Attribut in der Datei entityname.cdm.json.

**Manifest.json auf Entitätsebene**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json auf Attributebene**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
