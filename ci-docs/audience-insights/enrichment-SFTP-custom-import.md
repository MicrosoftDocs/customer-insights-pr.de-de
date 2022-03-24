---
title: Anreicherung mit dem benutzerdefinierten SFTP-Import
description: Allgemeine Informationen über das SFTP Custom Import Enrichment.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 042558af801a1d1fc365939d9aa42c09b98b2679
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376553"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Anreichern von Kundenprofilen mit benutzerdefinierten Daten (Vorschau)

Der benutzerdefinierte Import über das Secure File Transfer Protocol(SFTP) ermöglicht es Ihnen, Daten zu importieren, die nicht den Prozess der Datenvereinheitlichung durchlaufen müssen. Es ist eine flexible, sichere und einfache Möglichkeit, Ihre Daten einzubringen. Der benutzerdefinierte SFTP-Import kann in Kombination mit dem [SFTP-Export](export-sftp.md) verwendet werden, mit dem Sie die Kundenprofildaten exportieren können, die für die Anreicherung benötigt werden. Die Daten können dann verarbeitet und angereichert werden, und der benutzerdefinierte SFTP-Import kann verwendet werden, um die angereicherten Daten wieder in die Zielgruppenerkenntnis-Funktion von Dynamics 365 Customer Insights zu bringen.

## <a name="prerequisites"></a>Anforderungen

Um den benutzerdefinierten SFTP-Import zu konfigurieren, müssen die folgenden Voraussetzungen erfüllt sein:

- Sie haben den Dateinamen und den Speicherort (Pfad) der zu importierenden Datei auf dem SFTP-Host.
- Da ist eine *model.json*-Datei, die [das Common Data Model-Schema](/common-data-model/) für die zu importierenden Daten angibt. Diese Datei muss sich im selben Verzeichnis befinden wie die zu importierende Datei.
- Eine SFTP-Verbindung wurde bereits von einem Administrator konfiguriert *oder* Sie haben [Administrator](permissions.md#admin)-Berechtigungen. Sie benötigen die Benutzeranmeldeinformationen, die URL und die Portnummer für den SFTP-Speicherort, von dem Sie Daten importieren möchten.


## <a name="configure-the-import"></a>Konfiguration des Datenimports

1. Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus.

1. Wählen Sie **Meine Daten anreichern** auf der **Benutzerdefinierter SFTP-Import**-Kachel und wählen Sie **Los geht's**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Benutzerdefinierter SFTP-Import-Kachel":::

1. Wählen Sie eine [Verbindung](connections.md) aus der Dropdownliste aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist. Wenn Sie ein Administrator sind, können Sie eine Verbindung herstellen, indem Sie **Verbindung hinzufügen** und dann **SFTP benutzerdefinierter Import** aus der Dropdown-Liste auswählen.

1. Wählen Sie **Verbindung mit dem benutzerdefinierten Import herstellen** aus, um die ausgewählte Verbindung zu bestätigen.

1.  Wählen Sie **Weiter** und geben Sie einen **Pfad** und einen **Dateinamen** für die Datendatei an, die Sie importieren möchten.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Screenshot bei der Eingabe des Datenorts.":::

1. **Weiter** auswählen und dann Kunden-Dataset wählen. Dies können entweder alle Kundenprofile oder ein Segment sein.

1. Wählen Sie **Weiter** und geben Sie einen Namen für die Anreicherung und einen Namen für die Ausgabeentität an. 

1. Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfigurieren Sie die Verbindung für den benutzerdefinierten SFTP-Import 

Sie müssen ein Administrator sein, um Verbindungen zu konfigurieren. Wählen Sie **Verbindung hinzufügen** beim Konfigurieren einer Anreicherung *oder* gehen Sie zu **Administrator** > **Verbindungen** und wählen Sie **Einrichten** auf der Kachel „Benutzerdefinierter Import“.

1. Geben Sie einen Namen für die Verbindung in das Feld **Anzeigename** ein.

1. Geben Sie einen gültigen Benutzernamen, ein Kennwort und eine Host-URL für den SFTP-Server ein, auf dem sich die zu importierenden Daten befinden.

1. Prüfen und geben Sie Ihre Zustimmung zum **Datenschutz und Einhaltung von Vorschriften**, indem Sie das Kontrollkästchen **Ich stimme zu** markieren.

1. Wählen Sie **Überprüfen**, um die Konfiguration zu validieren.

1. Nach Abschluss der Verifizierung kann die Verbindung durch Auswahl von **speichern** gespeichert werden.

   > [!div class="mx-imgBorder"]
   > ![Experian-Verbindungskonfigurationsseite.](media/enrichment-SFTP-connection.png "Experian Verbindungskonfigurationsseite")


## <a name="defining-field-mappings"></a>Definieren von Feldzuordnungen 

Das Verzeichnis, das die zu importierende Datei auf dem SFTP-Server enthält, muss auch eine *model.json*-Datei enthalten. Diese Datei definiert das Schema, das zum Importieren der Daten verwendet werden soll. Das Schema muss verwendet werden, um [Common Data Model](/common-data-model/) zu verwenden, um die Feldzuordnung anzugeben. Ein einfaches Beispiel für eine model.json-Datei sieht wie folgt aus:

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

## <a name="next-steps"></a>Nächste Schritte,

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
