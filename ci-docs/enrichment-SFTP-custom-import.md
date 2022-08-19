---
title: Kundenprofile mit SFTP-Kundenimport anreichern (Vorschauversion)
description: Allgemeine Informationen über das SFTP Custom Import Enrichment.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 831d1d3d3045379bbc5bcdcd4b05b8a147221f31
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237765"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Kundenprofile mit SFTP-Kundenimport anreichern (Vorschauversion)

Der benutzerdefinierte Import über das Secure File Transfer Protocol(SFTP) ermöglicht es Ihnen, Daten zu importieren, die nicht den Prozess der Datenvereinheitlichung durchlaufen müssen. Es ist eine flexible, sichere und einfache Möglichkeit, Ihre Daten einzubringen. Der benutzerdefinierte SFTP-Import kann in Kombination mit dem [SFTP-Export](export-sftp.md) verwendet werden, mit dem Sie die Kundenprofildaten exportieren können, die für die Anreicherung benötigt werden. Die Daten können dann verarbeitet und angereichert werden, und der angepasste SFTP-Import kann verwendet werden, um die angereicherten Daten wieder auf Dynamics 365 Customer Insights zu bringen.

## <a name="prerequisites"></a>Anforderungen

- Dateiname und Speicherort (Pfad) der zu importierenden Datei auf dem SFTP-Host ist bekannt.

- Eine *model.json* Datei, die das Common Data Model-Schema für die zu importierenden Daten angibt, ist verfügbar. Diese Datei muss sich im selben Verzeichnis befinden wie die zu importierende Datei.

- Eine SFTP [Verbindung](connections.md) ist [konfiguriert](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Schemadatei-Beispiel

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfigurieren Sie die Verbindung für den benutzerdefinierten SFTP-Import

Sie müssen [Administrator](permissions.md#admin) in Customer Insights sein und über die Benutzeranmeldeinformationen, die URL und die Portnummer für den SFTP-Speicherort verfügen, von dem Sie Daten importieren möchten.

1. Wählen Sie **Verbindung hinzufügen** beim Konfigurieren einer Anreicherung oder gehen Sie zu **Administrator** > **Verbindungen** und wählen Sie **Einrichten** auf der Kachel Benutzerdefinierter Import.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Benutzerdefinierte Import-Verbindungskonfigurationsseite.":::

1. Geben Sie einen Namen für die Verbindung ein.

1. Geben Sie einen gültigen Benutzernamen, ein Kennwort und eine Host-URL für den SFTP-Server ein, auf dem sich die zu importierenden Daten befinden.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie **Verifizieren**, um die Konfiguration zu bestätigen, und wählen Sie dann **Speichern**.

## <a name="configure-the-import"></a>Konfiguration des Datenimports

1. Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus.

1. Wählen Sie **Meine Daten anreichern** auf der Kachel **SFTP benutzerdefinierter Import** aus.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Benutzerdefinierter SFTP-Import-Kachel":::

1. Prüfen Sie die Übersicht und wählen Sie dann **Weiter** aus.

1. Wählen Sie die Verbindung aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Wählen Sie das **Kunden Dataset** und wählen Sie das Profil oder Segment aus, das Sie anreichern möchten. Die Entität *Kunde* reichert alle Ihre Kundenprofile an, währen ein Segment nur Kundenprofile anreichert, die in diesem Segment enthalten sind.

1. Wählen Sie **Weiter** aus.

1. Geben Sie den **Pfad** und den **Dateiname** der Datendatei ein, die Sie importieren möchten.

1. Wählen Sie **Weiter** aus.

1. Geben Sie einen **Namen** für die Anreicherung und einen Namen für die **Ausgabeentität** an.

1. Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.

1. Wählen Sie **Ausführen**, um den Anreicherungsprozess zu starten oder zu schließen, um zur Seite **Anreicherung** zurückzukehren.

## <a name="view-enrichment-results"></a>Anreicherungsergebnisse anzeigen

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Nächste Schritte,

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
