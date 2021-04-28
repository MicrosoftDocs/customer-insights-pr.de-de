---
title: Anreicherung von mit der Drittanbieter-Anreicherung HERE Technologies
description: Allgemeine Informationen über die Drittanbieter-Anreicherung von HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896050"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="01622-103">Anreicherung von Kundenprofilen mit HERE Technologies (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="01622-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="01622-104">HERE Technologies ist ein Unternehmen für Standortplattformen, das ortsbezogene Daten und Dienste anbietet.</span><span class="sxs-lookup"><span data-stu-id="01622-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="01622-105">Mit den Datenanreicherungsdiensten von HERE Technologies können Sie durch Adressnormalisierung, Extraktion von Breiten- und Längengraden und mehr ein genaueres Standortverständnis Ihrer Kunden aufbauen.</span><span class="sxs-lookup"><span data-stu-id="01622-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="01622-106">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="01622-106">Prerequisites</span></span>

<span data-ttu-id="01622-107">Um HERE Technologies Enrichments zu konfigurieren, müssen die folgenden Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="01622-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="01622-108">Sie haben ein aktives HERE Technologies Abonnement.</span><span class="sxs-lookup"><span data-stu-id="01622-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="01622-109">Um ein Abonnement zu erhalten, können Sie sich [hier anmelden](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) oder [direkt mit HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) in Verbindung setzen.</span><span class="sxs-lookup"><span data-stu-id="01622-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="01622-110">Erfahren Sie mehr über HERE Technologies Location Enrichment.</span><span class="sxs-lookup"><span data-stu-id="01622-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="01622-111">Es gibt eine HERE-[Verbindung](connections.md) *oder* Sie haben [Administrator](permissions.md#administrator)-Berechtigungen und den HERE Technologies-API-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="01622-111">There is a HERE [connection](connections.md) available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="01622-112">Anreicherungskonfiguration</span><span class="sxs-lookup"><span data-stu-id="01622-112">Configure the enrichment</span></span>

1. <span data-ttu-id="01622-113">Gehen Sie zu **Daten** > **Anreicherung**.</span><span class="sxs-lookup"><span data-stu-id="01622-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="01622-114">Wählen Sie **Meine Daten anreichern** auf der HERE Technologies-Kachel und wählen Sie **Los geht's**.</span><span class="sxs-lookup"><span data-stu-id="01622-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="01622-115">![HERE Technologies Kachel](media/HERE-tile.png "HERE Technologies Kachel")</span><span class="sxs-lookup"><span data-stu-id="01622-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="01622-116">Wählen Sie eine [Verbindung](connections.md) aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="01622-116">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="01622-117">Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="01622-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="01622-118">Wenn Sie ein Administrator sind, können Sie durch Auswahl von **Verbindung hinzufügen** eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="01622-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="01622-119">Wählen Sie **HERE Technologies** aus dem Dropdownmenü.</span><span class="sxs-lookup"><span data-stu-id="01622-119">Choose **HERE Technologies** from the drop-down.</span></span> 

1. <span data-ttu-id="01622-120">Wählen Sie **Mit HERE Technologies verbinden**, um die Auswahl zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="01622-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="01622-121">Wählen Sie **Weiter** und wählen Sie den **Kundendatensatz**, den Sie mit Standortdaten von HERE Technologies anreichern möchten.</span><span class="sxs-lookup"><span data-stu-id="01622-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="01622-122">Sie können die **Kundenentität** auswählen, um alle Ihre Kundenprofile anzureichern, oder eine Segmententität auswählen, um nur Kundenprofile anzureichern, die in diesem Segment enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="01622-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Screenshot bei Auswahl des Kundendatensatzes.":::

1. <span data-ttu-id="01622-124">Wählen Sie, ob Sie Felder der primären und/oder sekundären Adresse zuordnen wollen.</span><span class="sxs-lookup"><span data-stu-id="01622-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="01622-125">Sie können eine Feldzuordnung für beide Adressen angeben und die Profile für beide Adressen separat anreichern.</span><span class="sxs-lookup"><span data-stu-id="01622-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="01622-126">Zum Beispiel, wenn es eine Privat- und eine Geschäftsadresse gibt.</span><span class="sxs-lookup"><span data-stu-id="01622-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="01622-127">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="01622-127">Select **Next**.</span></span>

1. <span data-ttu-id="01622-128">Definieren Sie, welche Felder aus Ihren einheitlichen Profilen verwendet werden sollen, um nach übereinstimmenden Standortdaten von HERE Technologies zu suchen.</span><span class="sxs-lookup"><span data-stu-id="01622-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="01622-129">Die Felder **Straße 1** und **Postleitzahl** sind für die ausgewählte primäre und/oder sekundäre Adresse erforderlich.</span><span class="sxs-lookup"><span data-stu-id="01622-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="01622-130">Für eine höhere Abgleichsgenauigkeit können weitere Felder hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="01622-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="01622-131">![HERE Technologies Anreicherungs-Konfigurationsseite](media/enrichment-HERE-configuration.png "HERE Technologies Anreicherungs-Konfigurationsseite")</span><span class="sxs-lookup"><span data-stu-id="01622-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="01622-132">Wählen Sie **Weiter** aus, um die Feldzuordnung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="01622-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="01622-133">Benennen Sie die Anreicherung.</span><span class="sxs-lookup"><span data-stu-id="01622-133">Provide a name for the enrichment.</span></span> 

<span data-ttu-id="01622-134">1. Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="01622-134">1.Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="01622-135">Konfigurieren Sie die Verbindung für HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="01622-135">Configure the connection for HERE technologies</span></span> 

<span data-ttu-id="01622-136">Sie müssen ein Administrator sein, um Verbindungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="01622-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="01622-137">Wählen Sie **Verbindung hinzufügen** beim Konfigurieren einer Anreicherung *oder* gehen Sie zu **Administrator** > **Verbindungen** und wählen Sie **Einrichten** auf der Kachel „HERE Technologies“.</span><span class="sxs-lookup"><span data-stu-id="01622-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="01622-138">Geben Sie einen Namen für die Verbindung in das Feld **Anzeigename** ein.</span><span class="sxs-lookup"><span data-stu-id="01622-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="01622-139">Geben Sie einen gültigen API-Schlüssel für HERE Technologies an.</span><span class="sxs-lookup"><span data-stu-id="01622-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="01622-140">Prüfen und geben Sie Ihre Zustimmung zum **Datenschutz und Einhaltung von Vorschriften**, indem Sie das Kontrollkästchen **Ich stimme zu** markieren.</span><span class="sxs-lookup"><span data-stu-id="01622-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="01622-141">Wählen Sie **Überprüfen**, um die Konfiguration zu validieren.</span><span class="sxs-lookup"><span data-stu-id="01622-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="01622-142">Wählen Sie nach Abschluss der Überprüfung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="01622-142">After completing the verification, select **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="01622-143">![Verbindungskonfigurationsseite für HERE Technologies](media/enrichment-HERE-connection.png "Verbindungskonfigurationsseite für HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="01622-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="01622-144">Anreicherungsergebnisse</span><span class="sxs-lookup"><span data-stu-id="01622-144">Enrichment results</span></span>

<span data-ttu-id="01622-145">Wählen Sie **Ausführen** aus der Befehlsleiste aus, um den Anreicherungsprozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="01622-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="01622-146">Sie können das System die Anreicherung auch automatisch als Teil von einer [geplante Aktualisierung](system.md#schedule-tab) ausführen lassen.</span><span class="sxs-lookup"><span data-stu-id="01622-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="01622-147">Die Verarbeitungszeit hängt von der Größe Ihrer Kundendaten und den API-Antwortzeiten von HERE Technologies ab.</span><span class="sxs-lookup"><span data-stu-id="01622-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="01622-148">Nach Abschluss des Anreicherungsprozesses können Sie die neu angereicherten Kundenprofildaten unter **Meine Anreicherungen** überprüfen.</span><span class="sxs-lookup"><span data-stu-id="01622-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="01622-149">Außerdem finden Sie den Zeitpunkt des letzten Updates und die Anzahl der angereicherten Profile.</span><span class="sxs-lookup"><span data-stu-id="01622-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="01622-150">Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.</span><span class="sxs-lookup"><span data-stu-id="01622-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="01622-151">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="01622-151">Next steps</span></span>

<span data-ttu-id="01622-152">Bauen Sie auf Ihren angereicherten Kundendaten auf.</span><span class="sxs-lookup"><span data-stu-id="01622-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="01622-153">Erstellen Sie [Segmente](segments.md), [Maße](measures.md), und selbst [Exportdaten](export-destinations.md), um Ihren Kunden personalisierte Erlebnisse zu bieten.</span><span class="sxs-lookup"><span data-stu-id="01622-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="01622-154">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="01622-154">Data privacy and compliance</span></span>

<span data-ttu-id="01622-155">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an HERE Technologies aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="01622-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="01622-156">Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass HERE Technologies alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können.</span><span class="sxs-lookup"><span data-stu-id="01622-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="01622-157">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="01622-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="01622-158">Ihr Dynamics 365 Customer Insights-Administrator kann diese Anreicherung jederzeit entfernen, um die Nutzung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="01622-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
