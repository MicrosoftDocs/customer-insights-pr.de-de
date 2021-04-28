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
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896280"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="4c6ce-103">Anreichern von Kundenprofilen mit benutzerdefinierten Daten (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="4c6ce-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="4c6ce-104">Mit dem benutzerdefinierten SFTP-Import (Secure File Transfer Protocol) können Sie Daten importieren, die nicht den Prozess der Datenvereinigung durchlaufen müssen.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="4c6ce-105">Es ist eine flexible, sichere und einfache Möglichkeit, Ihre Daten einzubringen.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="4c6ce-106">Der benutzerdefinierte SFTP-Import kann in Kombination mit dem [SFTP-Export](export-sftp.md) verwendet werden, mit dem Sie die Kundenprofildaten exportieren können, die für die Anreicherung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="4c6ce-107">Die Daten können dann verarbeitet und angereichert werden, und der benutzerdefinierte SFTP-Import kann verwendet werden, um die angereicherten Daten wieder in die Zielgruppen-Insights-Funktionalitäten von Dynamics 365 Customer Insights zu bringen.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4c6ce-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4c6ce-108">Prerequisites</span></span>

<span data-ttu-id="4c6ce-109">Um den benutzerdefinierten SFTP-Import zu konfigurieren, müssen die folgenden Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="4c6ce-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="4c6ce-110">Sie haben den Dateinamen und den Speicherort (Pfad) der Datei, die auf den SFTP-Host importiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="4c6ce-111">Da ist eine *model.json*-Datei, die [das Common Data Model-Schema](/common-data-model/) für die zu importierenden Daten angibt.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="4c6ce-112">Diese Datei muss sich im selben Verzeichnis befinden wie die zu importierende Datei.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="4c6ce-113">Eine SFTP-Verbindung wurde bereits von einem Administrator konfiguriert *oder* Sie haben [Administrator](permissions.md#administrator)-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="4c6ce-114">Sie benötigen die Benutzeranmeldeinformationen, die URL und die Portnummer für den SFTP-Speicherort, von dem Sie Daten importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="4c6ce-115">Konfiguration des Datenimports</span><span class="sxs-lookup"><span data-stu-id="4c6ce-115">Configure the import</span></span>

1. <span data-ttu-id="4c6ce-116">Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="4c6ce-117">Wählen Sie **Meine Daten anreichern** auf der **Benutzerdefinierter SFTP-Import**-Kachel und wählen Sie **Los geht's**.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Benutzerdefinierter SFTP-Import-Kachel":::

1. <span data-ttu-id="4c6ce-119">Wählen Sie eine [Verbindung](connections.md) aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="4c6ce-120">Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="4c6ce-121">Wenn Sie ein Administrator sind, können Sie durch Auswahl von **Verbindung hinzufügen** eine Verbindung herstellen und **Benutzerdefinierter SFTP-Import** aus dem Dropdownmenü auswählen.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="4c6ce-122">Wählen Sie **Verbindung mit dem benutzerdefinierten Import herstellen** aus, um die ausgewählte Verbindung zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="4c6ce-123">Wählen Sie **Weiter** und geben Sie **Dateiname** und **Pfad** der Datendatei ein, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Screenshot bei der Eingabe des Datenorts.":::

1. <span data-ttu-id="4c6ce-125">Wählen Sie **Weiter** und geben Sie einen Namen für die Anreicherung und einen Namen für die Ausgabeentität an.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="4c6ce-126">Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="4c6ce-127">Konfigurieren Sie die Verbindung für den benutzerdefinierten SFTP-Import</span><span class="sxs-lookup"><span data-stu-id="4c6ce-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="4c6ce-128">Sie müssen ein Administrator sein, um Verbindungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="4c6ce-129">Wählen Sie **Verbindung hinzufügen** beim Konfigurieren einer Anreicherung *oder* gehen Sie zu **Administrator** > **Verbindungen** und wählen Sie **Einrichten** auf der Kachel „Benutzerdefinierter Import“.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="4c6ce-130">Geben Sie einen Namen für die Verbindung in das Feld **Anzeigename** ein.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="4c6ce-131">Geben Sie einen gültigen Benutzernamen, ein Kennwort und eine gültige Host-URL für den STFP-Server ein, auf dem sich die zu importierenden Daten befinden.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="4c6ce-132">Prüfen und geben Sie Ihre Zustimmung zum **Datenschutz und Einhaltung von Vorschriften**, indem Sie das Kontrollkästchen **Ich stimme zu** markieren.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="4c6ce-133">Wählen Sie **Überprüfen**, um die Konfiguration zu validieren.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="4c6ce-134">Nach Abschluss der Überprüfung kann die Verbindung durch Klicken auf **Speichern** gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="4c6ce-135">![Verbindungskonfigurationsseite für Experian](media/enrichment-SFTP-connection.png "Verbindungskonfigurationsseite für Experian")</span><span class="sxs-lookup"><span data-stu-id="4c6ce-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="4c6ce-136">Definieren von Feldzuordnungen</span><span class="sxs-lookup"><span data-stu-id="4c6ce-136">Defining field mappings</span></span> 

<span data-ttu-id="4c6ce-137">Das Verzeichnis, das die zu importierende Datei auf dem SFTP-Server enthält, muss auch eine *model.json*-Datei enthalten.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="4c6ce-138">Diese Datei definiert das Schema, das zum Importieren der Daten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="4c6ce-139">Das Schema muss [das Common Data Model](/common-data-model/) verwenden, um die Zuordnung der Felder zu spezifizieren.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="4c6ce-140">Ein einfaches Beispiel für eine model.json-Datei sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="4c6ce-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="4c6ce-141">Anreicherungsergebnisse</span><span class="sxs-lookup"><span data-stu-id="4c6ce-141">Enrichment results</span></span>

<span data-ttu-id="4c6ce-142">Wählen Sie **Ausführen** aus der Befehlsleiste aus, um den Anreicherungsprozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="4c6ce-143">Sie können das System die Anreicherung auch automatisch als Teil von einer [geplante Aktualisierung](system.md#schedule-tab) ausführen lassen.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4c6ce-144">Die Verarbeitungszeit hängt von der Größe der zu importierenden Daten und der Verbindung zum SFTP-Server ab.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="4c6ce-145">Nachdem der Anreicherungsprozess abgeschlossen ist, können Sie Ihre neu importierten benutzerdefinierten Anreicherungsdaten unter **Meine Anreicherungen** überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="4c6ce-146">Außerdem finden Sie den Zeitpunkt des letzten Updates und die Anzahl der angereicherten Profile.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="4c6ce-147">Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4c6ce-148">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4c6ce-148">Next steps</span></span>

<span data-ttu-id="4c6ce-149">Bauen Sie auf Ihren angereicherten Kundendaten auf.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="4c6ce-150">Erstellen Sie [Segmente](segments.md), [Kennzahlen](measures.md) und [Exportieren Sie die Daten](export-destinations.md), um Ihren Kunden personalisierte Erlebnisse zu bieten.</span><span class="sxs-lookup"><span data-stu-id="4c6ce-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
