---
title: Anreicherung mit der Experian Anreicherung von Drittanbietern
description: Allgemeine Informationen zur Experian Anreicherung durch Dritte.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309819"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="0d651-103">Anreichern von Kundenprofilen mit demografischen Daten von Experian (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="0d651-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="0d651-104">Experian ist ein weltweit führender Anbieter von Kredit‑ und Marketingdienstleistungen für Verbraucher‑ und Geschäftskredite.</span><span class="sxs-lookup"><span data-stu-id="0d651-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="0d651-105">Mit den Datenanreicherungsdiensten von Experian können Sie ein tieferes Verständnis Ihrer Kunden aufbauen, indem Sie Ihre Kundenprofile mit demografischen Daten wie Haushaltsgröße, Einkommen und mehr bereichern.</span><span class="sxs-lookup"><span data-stu-id="0d651-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0d651-106">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0d651-106">Prerequisites</span></span>

<span data-ttu-id="0d651-107">Zum Konfigurieren von Experian müssen folgende Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="0d651-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="0d651-108">Sie haben ein aktives Experian Abonnement.</span><span class="sxs-lookup"><span data-stu-id="0d651-108">You have an active Experian subscription.</span></span> <span data-ttu-id="0d651-109">Um ein Abonnement zu erhalten [kontaktieren Sie Experian](https://www.experian.com/marketing-services/contact) direkt.</span><span class="sxs-lookup"><span data-stu-id="0d651-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="0d651-110">[Weitere Informationen zu Experian Datenanreicherung](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="0d651-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="0d651-111">Eine Experian Verbindung wurde bereits von einem Administrator konfiguriert *oder* Sie haben [Administrator](permissions.md#administrator)-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="0d651-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="0d651-112">Darüber hinaus benötigen Sie die Benutzer-ID, die Partei-ID und die Modellnummer für Ihr SSH-fähiges ST-Konto (Secure Transport), das Experian für Sie erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="0d651-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="0d651-113">Unterstützte Länder/Regionen</span><span class="sxs-lookup"><span data-stu-id="0d651-113">Supported countries/regions</span></span>

<span data-ttu-id="0d651-114">Derzeit unterstützen wir die Anreicherung von Kundenprofilen nur in den USA.</span><span class="sxs-lookup"><span data-stu-id="0d651-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="0d651-115">Anreicherungskonfiguration</span><span class="sxs-lookup"><span data-stu-id="0d651-115">Configure the enrichment</span></span>

1. <span data-ttu-id="0d651-116">Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus.</span><span class="sxs-lookup"><span data-stu-id="0d651-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="0d651-117">Wählen Sie **Meine Daten anreichern** auf der Experian Kachel.</span><span class="sxs-lookup"><span data-stu-id="0d651-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0d651-118">![Experian Kacheln](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="0d651-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="0d651-119">Wählen Sie eine [Verbindung](connections.md) aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="0d651-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="0d651-120">Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0d651-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="0d651-121">Wenn Sie ein Administrator sind, können Sie eine Verbindung herstellen, indem Sie **Verbindung hinzufügen** und dann Experian aus der Dropdown-Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="0d651-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="0d651-122">Wählen Sie **Verbinden mit Experian**, um die Verbindungsauswahl zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="0d651-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="0d651-123">Wählen Sie **Weiter** und wählen **Kunden-Dataset** aus, wenn Sie die demografischen Daten von Experian anreichern möchten.</span><span class="sxs-lookup"><span data-stu-id="0d651-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="0d651-124">Sie können die **Kundenentität** auswählen, um alle Ihre Kundenprofile anzureichern, oder eine Segmententität auswählen, um nur Kundenprofile anzureichern, die in diesem Segment enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="0d651-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Screenshot bei Auswahl des Kundendatensatzes.":::

1. <span data-ttu-id="0d651-126">Wählen Sie **Weiter** und definieren Sie, welche Art von Feldern aus Ihren einheitlichen Profilen verwendet werden sollen, um nach übereinstimmenden demografischen Daten von Experian zu suchen..</span><span class="sxs-lookup"><span data-stu-id="0d651-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="0d651-127">Mindestens eines der Felder **Name und Adresse**, **Telefon** oder **E-Mail** ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0d651-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="0d651-128">Für eine höhere Übereinstimmungsgenauigkeit können bis zu zwei weitere Felder hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="0d651-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="0d651-129">Diese Auswahl wirkt sich auf die Zuordnungsfelder aus, auf die Sie im nächsten Schritt zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="0d651-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="0d651-130">Weitere Schlüsselkennungsattribute die an Experian gesendet werden, werden wahrscheinlich eine höhere Übereinstimmungsrate ergeben.</span><span class="sxs-lookup"><span data-stu-id="0d651-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="0d651-131">Wählen Sie **Weiter** aus, um die Feldzuordnung zu starten.</span><span class="sxs-lookup"><span data-stu-id="0d651-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="0d651-132">Definieren Sie, welche Art von Feldern aus Ihren einheitlichen Profilen verwendet werden sollen, um nach übereinstimmenden demografischen Daten von Experian zu suchen.</span><span class="sxs-lookup"><span data-stu-id="0d651-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="0d651-133">Erforderliche Felder sind gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="0d651-133">Required fields are marked.</span></span>

1. <span data-ttu-id="0d651-134">Geben Sie einen Namen für die Anreicherung und einen Namen für die Ausgabeentität an.</span><span class="sxs-lookup"><span data-stu-id="0d651-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="0d651-135">Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="0d651-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="0d651-136">Konfigurieren Sie die Verbindung für Experian</span><span class="sxs-lookup"><span data-stu-id="0d651-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="0d651-137">Sie müssen ein Administrator sein, um Verbindungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0d651-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="0d651-138">Wählen Sie **Verbindung hinzufügen** beim Konfigurieren einer Anreicherung *oder* gehe zu **Administrator** > **Verbindung** und wählen Sie **Einrichten** auf der Experian Kachel aus.</span><span class="sxs-lookup"><span data-stu-id="0d651-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="0d651-139">Wählen Sie **Erste Schritte** aus.</span><span class="sxs-lookup"><span data-stu-id="0d651-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="0d651-140">Geben Sie einen Namen für die Verbindung in das Feld **Anzeigename** ein.</span><span class="sxs-lookup"><span data-stu-id="0d651-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="0d651-141">Geben Sie eine gültige Benutzer-ID, Partei-ID und Modellnummer für Ihr Experian Secure Transport-Konto ein.</span><span class="sxs-lookup"><span data-stu-id="0d651-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="0d651-142">Überprüfen Sie und geben Sie Ihre Zustimmung für **Datenschutz und Einhaltung** durch die Auswahl von **Ich stimme zu**.</span><span class="sxs-lookup"><span data-stu-id="0d651-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="0d651-143">Wählen Sie **Überprüfen**, um die Konfiguration zu validieren.</span><span class="sxs-lookup"><span data-stu-id="0d651-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="0d651-144">Wählen Sie nach Abschluss der Überprüfung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="0d651-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian Verbindungskonfigurationsbereich.":::

## <a name="enrichment-results"></a><span data-ttu-id="0d651-146">Anreicherungsergebnisse</span><span class="sxs-lookup"><span data-stu-id="0d651-146">Enrichment results</span></span>

<span data-ttu-id="0d651-147">Wählen Sie **Ausführen** aus der Befehlsleiste aus, um den Anreicherungsprozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="0d651-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="0d651-148">Sie können das System die Anreicherung auch automatisch als Teil von einer [geplante Aktualisierung](system.md#schedule-tab) ausführen lassen.</span><span class="sxs-lookup"><span data-stu-id="0d651-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0d651-149">Die Bearbeitungszeit hängt von der Größe Ihrer Kundendaten und den Anreicherungsprozessen ab, die für Ihr Konto eingerichtet wurden von Experian.</span><span class="sxs-lookup"><span data-stu-id="0d651-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="0d651-150">Nach Abschluss des Anreicherungsprozesses können Sie die neu angereicherten Kundenprofildaten unter **Meine Anreicherungen** überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0d651-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="0d651-151">Außerdem finden Sie den Zeitpunkt des letzten Updates und die Anzahl der angereicherten Profile.</span><span class="sxs-lookup"><span data-stu-id="0d651-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="0d651-152">Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.</span><span class="sxs-lookup"><span data-stu-id="0d651-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0d651-153">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="0d651-153">Next steps</span></span>

<span data-ttu-id="0d651-154">Bauen Sie auf Ihren angereicherten Kundendaten auf.</span><span class="sxs-lookup"><span data-stu-id="0d651-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="0d651-155">Erstellen von [Segmenten](segments.md) und [Maßnahmen](measures.md), und [Exportieren Sie die Daten](export-destinations.md),  um Ihren Kunden personalisierte Erlebnisse zu bieten.</span><span class="sxs-lookup"><span data-stu-id="0d651-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0d651-156">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="0d651-156">Data privacy and compliance</span></span>

<span data-ttu-id="0d651-157">Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten zu übermitteln an Experian, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogene Daten.</span><span class="sxs-lookup"><span data-stu-id="0d651-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0d651-158">Microsoft überträgt solche Daten auf Ihre Anweisung, aber Sie sind dafür verantwortlich, dass Experian alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="0d651-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0d651-159">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0d651-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0d651-160">Ihr Dynamics 365 Customer Insights Administrator kann diese Anreicherung jederzeit entfernen, um die Nutzung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="0d651-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
