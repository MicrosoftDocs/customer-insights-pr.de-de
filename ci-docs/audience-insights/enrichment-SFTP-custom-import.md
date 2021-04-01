---
title: Anreicherung mit dem benutzerdefinierten SFTP-Import
description: Allgemeine Informationen über das SFTP Custom Import Enrichment.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595854"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Anreichern von Kundenprofilen mit benutzerdefinierten Daten (Vorschau)

Der benutzerdefinierte Import über das Secure File Transfer Protocol(SFTP) ermöglicht es Ihnen, Daten zu importieren, die nicht den Prozess der Datenvereinheitlichung durchlaufen müssen. Es ist eine flexible, sichere und einfache Möglichkeit, Ihre Daten einzubringen. Der benutzerdefinierte SFTP-Import kann in Kombination mit dem [SFTP-Export](export-sftp.md) verwendet werden, mit dem Sie die Kundenprofildaten exportieren können, die für die Anreicherung benötigt werden. Die Daten können dann verarbeitet und angereichert werden, und der benutzerdefinierte SFTP-Import kann verwendet werden, um die angereicherten Daten wieder in die Zielgruppen-Insights-Funktionalitäten von Dynamics 365 Customer Insights zu bringen.

## <a name="prerequisites"></a>Anforderungen

Um den benutzerdefinierten SFTP-Import zu konfigurieren, müssen die folgenden Voraussetzungen erfüllt sein:

- Sie haben Anmeldeinformationen (Benutzername und Kennwort) für den SFTP-Speicherort, von dem die Daten importiert werden sollen.
- Sie haben die URL und die Port-Nummer (normalerweise 22) für den STFP-Host.
- Sie haben den Dateinamen und den Speicherort der zu importierenden Datei auf dem SFTP-Host.
- Es gibt eine *model.json*-Datei, die das Schema für die Daten angibt, die importiert werden sollen. Diese Datei muss sich im selben Verzeichnis befinden wie die zu importierende Datei.
- Sie haben die Berechtigung [Administrator](permissions.md#administrator).

## <a name="configuration"></a>Konfiguration

1. Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus.

1. Wählen Sie auf der Kachel **SFTP-Benutzerdefinierter Import** die Option **Meine Daten anreichern**.

   > [!div class="mx-imgBorder"]
   > ![SFTP-Benutzerdefinierter Import Kachel](media/SFTP_Custom_Import_tile.png "Kachel SFTP-Benutzerdefinierter Import")

1. Wählen Sie **Starten** und geben Sie die Anmeldeinformationen und die Adresse für den SFTP-Server an. Zum Beispiel, sftp://mysftpserver.com:22.

1. Geben Sie den Namen der Datei ein, die die Daten enthält, und den Pfad zur Datei auf dem SFTP-Server, wenn sie sich nicht im Stammordner befindet.

1. Bestätigen Sie alle Eingaben, indem Sie **Verbinden mit benutzerdefiniertem Import** wählen.

   > [!div class="mx-imgBorder"]
   > ![SFTP-Benutzerdefinierter Import Konfigurations-Flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP-Benutzerdefinierter Import Konfigurations-Flyout")

## <a name="defining-field-mappings"></a>Definieren von Feldzuordnungen 

Das Verzeichnis, das die zu importierende Datei auf dem SFTP-Server enthält, muss auch eine *model.json*-Datei enthalten. Diese Datei definiert das Schema, das zum Importieren der Daten verwendet werden soll. Das Schema muss [das Common Data Model](/common-data-model/) verwenden, um die Zuordnung der Felder zu spezifizieren. Ein einfaches Beispiel für eine model.json-Datei sieht wie folgt aus:

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a>Anreicherungsergebnisse

Wählen Sie **Ausführen** aus der Befehlsleiste aus, um den Anreicherungsprozess zu starten. Sie können das System die Anreicherung auch automatisch als Teil von einer [geplante Aktualisierung](system.md#schedule-tab) ausführen lassen. Die Verarbeitungszeit hängt von der Größe der zu importierenden Daten und der Verbindung zum SFTP-Server ab.

Nachdem der Anreicherungsprozess abgeschlossen ist, können Sie Ihre neu importierten benutzerdefinierten Anreicherungsdaten unter **Meine Anreicherungen** überprüfen. Außerdem finden Sie den Zeitpunkt des letzten Updates und die Anzahl der angereicherten Profile.

Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.

## <a name="next-steps"></a>Nächste Schritte

Bauen Sie auf Ihren angereicherten Kundendaten auf. Erstellen Sie [Segmente](segments.md), [Kennzahlen](measures.md) und [Exportieren Sie die Daten](export-destinations.md), um Ihren Kunden personalisierte Erlebnisse zu bieten.




[!INCLUDE[footer-include](../includes/footer-banner.md)]