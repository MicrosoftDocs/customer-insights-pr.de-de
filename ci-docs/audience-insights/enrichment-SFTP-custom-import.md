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
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="88f0e-103">Anreichern von Kundenprofilen mit benutzerdefinierten Daten (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="88f0e-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="88f0e-104">Der benutzerdefinierte Import über das Secure File Transfer Protocol(SFTP) ermöglicht es Ihnen, Daten zu importieren, die nicht den Prozess der Datenvereinheitlichung durchlaufen müssen.</span><span class="sxs-lookup"><span data-stu-id="88f0e-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="88f0e-105">Es ist eine flexible, sichere und einfache Möglichkeit, Ihre Daten einzubringen.</span><span class="sxs-lookup"><span data-stu-id="88f0e-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="88f0e-106">Der benutzerdefinierte SFTP-Import kann in Kombination mit dem [SFTP-Export](export-sftp.md) verwendet werden, mit dem Sie die Kundenprofildaten exportieren können, die für die Anreicherung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="88f0e-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="88f0e-107">Die Daten können dann verarbeitet und angereichert werden, und der benutzerdefinierte SFTP-Import kann verwendet werden, um die angereicherten Daten wieder in die Zielgruppen-Insights-Funktionalitäten von Dynamics 365 Customer Insights zu bringen.</span><span class="sxs-lookup"><span data-stu-id="88f0e-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="88f0e-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="88f0e-108">Prerequisites</span></span>

<span data-ttu-id="88f0e-109">Um den benutzerdefinierten SFTP-Import zu konfigurieren, müssen die folgenden Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="88f0e-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="88f0e-110">Sie haben Anmeldeinformationen (Benutzername und Kennwort) für den SFTP-Speicherort, von dem die Daten importiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="88f0e-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="88f0e-111">Sie haben die URL und die Port-Nummer (normalerweise 22) für den STFP-Host.</span><span class="sxs-lookup"><span data-stu-id="88f0e-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="88f0e-112">Sie haben den Dateinamen und den Speicherort der zu importierenden Datei auf dem SFTP-Host.</span><span class="sxs-lookup"><span data-stu-id="88f0e-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="88f0e-113">Es gibt eine *model.json*-Datei, die das Schema für die Daten angibt, die importiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="88f0e-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="88f0e-114">Diese Datei muss sich im selben Verzeichnis befinden wie die zu importierende Datei.</span><span class="sxs-lookup"><span data-stu-id="88f0e-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="88f0e-115">Sie haben die Berechtigung [Administrator](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="88f0e-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="88f0e-116">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="88f0e-116">Configuration</span></span>

1. <span data-ttu-id="88f0e-117">Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus.</span><span class="sxs-lookup"><span data-stu-id="88f0e-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="88f0e-118">Wählen Sie auf der Kachel **SFTP-Benutzerdefinierter Import** die Option **Meine Daten anreichern**.</span><span class="sxs-lookup"><span data-stu-id="88f0e-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="88f0e-119">![SFTP-Benutzerdefinierter Import Kachel](media/SFTP_Custom_Import_tile.png "Kachel SFTP-Benutzerdefinierter Import")</span><span class="sxs-lookup"><span data-stu-id="88f0e-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="88f0e-120">Wählen Sie **Starten** und geben Sie die Anmeldeinformationen und die Adresse für den SFTP-Server an.</span><span class="sxs-lookup"><span data-stu-id="88f0e-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="88f0e-121">Zum Beispiel, sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="88f0e-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="88f0e-122">Geben Sie den Namen der Datei ein, die die Daten enthält, und den Pfad zur Datei auf dem SFTP-Server, wenn sie sich nicht im Stammordner befindet.</span><span class="sxs-lookup"><span data-stu-id="88f0e-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="88f0e-123">Bestätigen Sie alle Eingaben, indem Sie **Verbinden mit benutzerdefiniertem Import** wählen.</span><span class="sxs-lookup"><span data-stu-id="88f0e-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="88f0e-124">![SFTP-Benutzerdefinierter Import Konfigurations-Flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP-Benutzerdefinierter Import Konfigurations-Flyout")</span><span class="sxs-lookup"><span data-stu-id="88f0e-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="88f0e-125">Definieren von Feldzuordnungen</span><span class="sxs-lookup"><span data-stu-id="88f0e-125">Defining field mappings</span></span> 

<span data-ttu-id="88f0e-126">Das Verzeichnis, das die zu importierende Datei auf dem SFTP-Server enthält, muss auch eine *model.json*-Datei enthalten.</span><span class="sxs-lookup"><span data-stu-id="88f0e-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="88f0e-127">Diese Datei definiert das Schema, das zum Importieren der Daten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="88f0e-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="88f0e-128">Das Schema muss [das Common Data Model](/common-data-model/) verwenden, um die Zuordnung der Felder zu spezifizieren.</span><span class="sxs-lookup"><span data-stu-id="88f0e-128">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="88f0e-129">Ein einfaches Beispiel für eine model.json-Datei sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="88f0e-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="88f0e-130">Anreicherungsergebnisse</span><span class="sxs-lookup"><span data-stu-id="88f0e-130">Enrichment results</span></span>

<span data-ttu-id="88f0e-131">Wählen Sie **Ausführen** aus der Befehlsleiste aus, um den Anreicherungsprozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="88f0e-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="88f0e-132">Sie können das System die Anreicherung auch automatisch als Teil von einer [geplante Aktualisierung](system.md#schedule-tab) ausführen lassen.</span><span class="sxs-lookup"><span data-stu-id="88f0e-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="88f0e-133">Die Verarbeitungszeit hängt von der Größe der zu importierenden Daten und der Verbindung zum SFTP-Server ab.</span><span class="sxs-lookup"><span data-stu-id="88f0e-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="88f0e-134">Nachdem der Anreicherungsprozess abgeschlossen ist, können Sie Ihre neu importierten benutzerdefinierten Anreicherungsdaten unter **Meine Anreicherungen** überprüfen.</span><span class="sxs-lookup"><span data-stu-id="88f0e-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="88f0e-135">Außerdem finden Sie den Zeitpunkt des letzten Updates und die Anzahl der angereicherten Profile.</span><span class="sxs-lookup"><span data-stu-id="88f0e-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="88f0e-136">Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.</span><span class="sxs-lookup"><span data-stu-id="88f0e-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="88f0e-137">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="88f0e-137">Next steps</span></span>

<span data-ttu-id="88f0e-138">Bauen Sie auf Ihren angereicherten Kundendaten auf.</span><span class="sxs-lookup"><span data-stu-id="88f0e-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="88f0e-139">Erstellen Sie [Segmente](segments.md), [Kennzahlen](measures.md) und [Exportieren Sie die Daten](export-destinations.md), um Ihren Kunden personalisierte Erlebnisse zu bieten.</span><span class="sxs-lookup"><span data-stu-id="88f0e-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]