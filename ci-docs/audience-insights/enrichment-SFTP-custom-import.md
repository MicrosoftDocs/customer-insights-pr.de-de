---
title: Anreicherung mit dem benutzerdefinierten SFTP-Import
description: Allgemeine Informationen über das SFTP Custom Import Enrichment.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304649"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="08295-103">Anreichern von Kundenprofilen mit benutzerdefinierten Daten (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="08295-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="08295-104">Der benutzerdefinierte Import über das Secure File Transfer Protocol(SFTP) ermöglicht es Ihnen, Daten zu importieren, die nicht den Prozess der Datenvereinheitlichung durchlaufen müssen.</span><span class="sxs-lookup"><span data-stu-id="08295-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="08295-105">Es ist eine flexible, sichere und einfache Möglichkeit, Ihre Daten einzubringen.</span><span class="sxs-lookup"><span data-stu-id="08295-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="08295-106">Der benutzerdefinierte SFTP-Import kann in Kombination mit dem [SFTP-Export](export-sftp.md) verwendet werden, mit dem Sie die Kundenprofildaten exportieren können, die für die Anreicherung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="08295-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="08295-107">Die Daten können dann verarbeitet und angereichert werden, und der benutzerdefinierte SFTP-Import kann verwendet werden, um die angereicherten Daten wieder in die Zielgruppenerkenntnis-Funktion von Dynamics 365 Customer Insights zu bringen.</span><span class="sxs-lookup"><span data-stu-id="08295-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="08295-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="08295-108">Prerequisites</span></span>

<span data-ttu-id="08295-109">Um den benutzerdefinierten SFTP-Import zu konfigurieren, müssen die folgenden Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="08295-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="08295-110">Sie haben den Dateinamen und den Speicherort (Pfad) der zu importierenden Datei auf dem SFTP-Host.</span><span class="sxs-lookup"><span data-stu-id="08295-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="08295-111">Da ist eine *model.json*-Datei, die [das Common Data Model-Schema](/common-data-model/) für die zu importierenden Daten angibt.</span><span class="sxs-lookup"><span data-stu-id="08295-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="08295-112">Diese Datei muss sich im selben Verzeichnis befinden wie die zu importierende Datei.</span><span class="sxs-lookup"><span data-stu-id="08295-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="08295-113">Eine SFTP-Verbindung wurde bereits von einem Administrator konfiguriert *oder* Sie haben [Administrator](permissions.md#administrator)-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="08295-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="08295-114">Sie benötigen die Benutzeranmeldeinformationen, die URL und die Portnummer für den SFTP-Speicherort, von dem Sie Daten importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="08295-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="08295-115">Konfiguration des Datenimports</span><span class="sxs-lookup"><span data-stu-id="08295-115">Configure the import</span></span>

1. <span data-ttu-id="08295-116">Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus.</span><span class="sxs-lookup"><span data-stu-id="08295-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="08295-117">Wählen Sie **Meine Daten anreichern** auf der **Benutzerdefinierter SFTP-Import**-Kachel und wählen Sie **Los geht's**.</span><span class="sxs-lookup"><span data-stu-id="08295-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Benutzerdefinierter SFTP-Import-Kachel":::

1. <span data-ttu-id="08295-119">Wählen Sie eine [Verbindung](connections.md) aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="08295-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="08295-120">Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="08295-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="08295-121">Wenn Sie ein Administrator sind, können Sie eine Verbindung herstellen, indem Sie **Verbindung hinzufügen** und dann **SFTP benutzerdefinierter Import** aus der Dropdown-Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="08295-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="08295-122">Wählen Sie **Verbindung mit dem benutzerdefinierten Import herstellen** aus, um die ausgewählte Verbindung zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="08295-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="08295-123">Wählen Sie **Weiter** und geben Sie einen **Pfad** und einen **Dateinamen** für die Datendatei an, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="08295-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Screenshot bei der Eingabe des Datenorts.":::

1. <span data-ttu-id="08295-125">Wählen Sie **Weiter** und geben Sie einen Namen für die Anreicherung und einen Namen für die Ausgabeentität an.</span><span class="sxs-lookup"><span data-stu-id="08295-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="08295-126">Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="08295-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="08295-127">Konfigurieren Sie die Verbindung für den benutzerdefinierten SFTP-Import</span><span class="sxs-lookup"><span data-stu-id="08295-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="08295-128">Sie müssen ein Administrator sein, um Verbindungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="08295-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="08295-129">Wählen Sie **Verbindung hinzufügen** beim Konfigurieren einer Anreicherung *oder* gehen Sie zu **Administrator** > **Verbindungen** und wählen Sie **Einrichten** auf der Kachel „Benutzerdefinierter Import“.</span><span class="sxs-lookup"><span data-stu-id="08295-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="08295-130">Geben Sie einen Namen für die Verbindung in das Feld **Anzeigename** ein.</span><span class="sxs-lookup"><span data-stu-id="08295-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="08295-131">Geben Sie einen gültigen Benutzernamen, ein Kennwort und eine Host-URL für den SFTP-Server ein, auf dem sich die zu importierenden Daten befinden.</span><span class="sxs-lookup"><span data-stu-id="08295-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="08295-132">Prüfen und geben Sie Ihre Zustimmung zum **Datenschutz und Einhaltung von Vorschriften**, indem Sie das Kontrollkästchen **Ich stimme zu** markieren.</span><span class="sxs-lookup"><span data-stu-id="08295-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="08295-133">Wählen Sie **Überprüfen**, um die Konfiguration zu validieren.</span><span class="sxs-lookup"><span data-stu-id="08295-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="08295-134">Nach Abschluss der Verifizierung kann die Verbindung durch Auswahl von **speichern** gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="08295-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="08295-135">![Experian Verbindungskonfigurationsseite](media/enrichment-SFTP-connection.png "Experian Verbindungskonfigurationsseite")</span><span class="sxs-lookup"><span data-stu-id="08295-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="08295-136">Definieren von Feldzuordnungen</span><span class="sxs-lookup"><span data-stu-id="08295-136">Defining field mappings</span></span> 

<span data-ttu-id="08295-137">Das Verzeichnis, das die zu importierende Datei auf dem SFTP-Server enthält, muss auch eine *model.json*-Datei enthalten.</span><span class="sxs-lookup"><span data-stu-id="08295-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="08295-138">Diese Datei definiert das Schema, das zum Importieren der Daten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="08295-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="08295-139">Das Schema muss verwendet werden, um [Common Data Model](/common-data-model/) zu verwenden, um die Feldzuordnung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="08295-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="08295-140">Ein einfaches Beispiel für eine model.json-Datei sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="08295-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="08295-141">Anreicherungsergebnisse</span><span class="sxs-lookup"><span data-stu-id="08295-141">Enrichment results</span></span>

<span data-ttu-id="08295-142">Wählen Sie **Ausführen** aus der Befehlsleiste aus, um den Anreicherungsprozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="08295-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="08295-143">Sie können das System die Anreicherung auch automatisch als Teil von einer [geplante Aktualisierung](system.md#schedule-tab) ausführen lassen.</span><span class="sxs-lookup"><span data-stu-id="08295-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="08295-144">Die Verarbeitungszeit hängt von der Größe der zu importierenden Daten und der Verbindung zum SFTP-Server ab.</span><span class="sxs-lookup"><span data-stu-id="08295-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="08295-145">Nachdem der Anreicherungsprozess abgeschlossen ist, können Sie Ihre neu importierten benutzerdefinierten Anreicherungsdaten unter **Meine Anreicherungen** überprüfen.</span><span class="sxs-lookup"><span data-stu-id="08295-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="08295-146">Außerdem finden Sie den Zeitpunkt des letzten Updates und die Anzahl der angereicherten Profile.</span><span class="sxs-lookup"><span data-stu-id="08295-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="08295-147">Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.</span><span class="sxs-lookup"><span data-stu-id="08295-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="08295-148">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="08295-148">Next steps</span></span>

<span data-ttu-id="08295-149">Bauen Sie auf Ihren angereicherten Kundendaten auf.</span><span class="sxs-lookup"><span data-stu-id="08295-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="08295-150">Erstellen von [Segmenten](segments.md) und [Maßnahmen](measures.md), und [Exportieren Sie die Daten](export-destinations.md),  um Ihren Kunden personalisierte Erlebnisse zu bieten.</span><span class="sxs-lookup"><span data-stu-id="08295-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
