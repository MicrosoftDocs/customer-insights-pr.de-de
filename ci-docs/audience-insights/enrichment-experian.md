---
title: Anreicherung mit der Drittanbieter-Anreicherung Experian
description: Allgemeine Informationen über die Drittanbieter-Anreicherung von Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896372"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="0fa8f-103">Kundenprofile mit demografischen Daten aus Experian anreichern (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="0fa8f-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="0fa8f-104">Experian ist ein weltweit führender Anbieter von Kredit- und Marketingdienstleistungen für Verbraucher- und Geschäftskredite.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="0fa8f-105">Mit den Datenanreicherungsdiensten von Experian können Sie ein tieferes Verständnis Ihrer Kunden aufbauen, indem Sie Ihre Kundenprofile mit demografischen Daten wie Haushaltsgröße, Einkommen und mehr bereichern.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0fa8f-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="0fa8f-106">Prerequisites</span></span>

<span data-ttu-id="0fa8f-107">Für das Konfigurieren von Experian an müssen folgende Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="0fa8f-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="0fa8f-108">Sie haben ein aktives Experian-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-108">You have an active Experian subscription.</span></span> <span data-ttu-id="0fa8f-109">Um ein Abonnement zu erhalten, [wenden Sie sich direkt an Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="0fa8f-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="0fa8f-110">[Weitere Informationen zur Datenanreicherung Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="0fa8f-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="0fa8f-111">Eine Experian-Verbindung wurde bereits von einem Administrator konfiguriert *oder* Sie haben [Administrator](permissions.md#administrator)-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="0fa8f-112">Darüber hinaus benötigen Sie die Benutzer-ID, die Party-ID und die Modellnummer für Ihr SSH-fähiges ST-Konto (Secure Transport), das Experian für Sie erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="0fa8f-113">Anreicherungskonfiguration</span><span class="sxs-lookup"><span data-stu-id="0fa8f-113">Configure the enrichment</span></span>

1. <span data-ttu-id="0fa8f-114">Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="0fa8f-115">Wählen Sie **Meine Daten anreichern** auf der Experian-Kachel.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0fa8f-116">![Experian-Kachel](media/experian-tile.png "Experian-Kachel")</span><span class="sxs-lookup"><span data-stu-id="0fa8f-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="0fa8f-117">Wählen Sie eine [Verbindung](connections.md) aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="0fa8f-118">Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="0fa8f-119">Wenn Sie ein Administrator sind, können Sie durch Auswahl von **Verbindung hinzufügen** eine Verbindung herstellen und „Experian“ aus dem Dropdownmenü auswählen.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="0fa8f-120">Wählen Sie **Mit Experian verbinden**, um die Verbindungsauswahl zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="0fa8f-121">Wählen Sie **Weiter** und wählen Sie den **Kundendatensatz**, den Sie mit Demografiedaten von Experian anreichern möchten.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="0fa8f-122">Sie können die **Kundenentität** auswählen, um alle Ihre Kundenprofile anzureichern, oder eine Segmententität auswählen, um nur Kundenprofile anzureichern, die in diesem Segment enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Screenshot bei Auswahl des Kundendatensatzes.":::

1. <span data-ttu-id="0fa8f-124">Wählen Sie **Weiter** aus, und definieren Sie, welche Art von Feldern aus Ihren einheitlichen Profilen verwendet werden soll, um nach übereinstimmenden demografischen Daten von Experian zu suchen.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="0fa8f-125">Mindestens eines der Felder **Name und Adresse**, **Telefon** oder **E-Mail** ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="0fa8f-126">Für eine höhere Übereinstimmungsgenauigkeit können bis zu zwei weitere Felder hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="0fa8f-127">Diese Auswahl wirkt sich auf die Zuordnungsfelder aus, auf die Sie im nächsten Schritt zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="0fa8f-128">Weitere an Experian gesendete Schlüsselbezeichnerattribute führen wahrscheinlich zu einer höheren Übereinstimmungsrate.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="0fa8f-129">Wählen Sie **Weiter** aus, um die Feldzuordnung zu starten.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="0fa8f-130">Definieren Sie, welche Felder aus Ihren einheitlichen Profilen verwendet werden sollen, um nach übereinstimmenden demografischen Daten von Experian zu suchen.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="0fa8f-131">Erforderliche Felder sind gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-131">Required fields are marked.</span></span>

1. <span data-ttu-id="0fa8f-132">Geben Sie einen Namen für die Anreicherung und einen Namen für die Ausgabeentität an.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="0fa8f-133">Wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="0fa8f-134">Konfigurieren Sie die Verbindung für Experian</span><span class="sxs-lookup"><span data-stu-id="0fa8f-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="0fa8f-135">Sie müssen ein Administrator sein, um Verbindungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="0fa8f-136">Wählen Sie **Verbindung hinzufügen** beim Konfigurieren einer Anreicherung *oder* gehen Sie zu **Administrator** > **Verbindungen** und wählen Sie **Einrichten** auf der Kachel „Experian“.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="0fa8f-137">Wählen Sie **Erste Schritte** aus.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="0fa8f-138">Geben Sie einen Namen für die Verbindung in das Feld **Anzeigename** ein.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="0fa8f-139">Geben Sie eine gültige Benutzer-ID, Party-ID und Modellnummer für Ihr Experian Secure Transport-Konto ein.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="0fa8f-140">Prüfen und geben Sie Ihre Zustimmung zum **Datenschutz und Einhaltung von Vorschriften**, indem Sie das Kontrollkästchen **Ich stimme zu** markieren.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="0fa8f-141">Wählen Sie **Überprüfen**, um die Konfiguration zu validieren.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="0fa8f-142">Wählen Sie nach Abschluss der Überprüfung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Verbindungskonfigurationsbereich für Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="0fa8f-144">Anreicherungsergebnisse</span><span class="sxs-lookup"><span data-stu-id="0fa8f-144">Enrichment results</span></span>

<span data-ttu-id="0fa8f-145">Wählen Sie **Ausführen** aus der Befehlsleiste aus, um den Anreicherungsprozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="0fa8f-146">Sie können das System die Anreicherung auch automatisch als Teil von einer [geplante Aktualisierung](system.md#schedule-tab) ausführen lassen.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0fa8f-147">Die Bearbeitungszeit hängt von der Größe Ihrer Kundendaten und den von Experian für Ihr Konto eingerichteten Anreicherungsprozessen ab.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="0fa8f-148">Nach Abschluss des Anreicherungsprozesses können Sie die neu angereicherten Kundenprofildaten unter **Meine Anreicherungen** überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="0fa8f-149">Außerdem finden Sie den Zeitpunkt des letzten Updates und die Anzahl der angereicherten Profile.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="0fa8f-150">Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0fa8f-151">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="0fa8f-151">Next steps</span></span>

<span data-ttu-id="0fa8f-152">Bauen Sie auf Ihren angereicherten Kundendaten auf.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="0fa8f-153">Erstellen Sie [Segmente](segments.md), [Maße](measures.md), und selbst [Exportdaten](export-destinations.md), um Ihren Kunden personalisierte Erlebnisse zu bieten.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0fa8f-154">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="0fa8f-154">Data privacy and compliance</span></span>

<span data-ttu-id="0fa8f-155">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Experian aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0fa8f-156">Microsoft wird diese Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, sicherzustellen, dass Experian alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0fa8f-157">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0fa8f-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0fa8f-158">Ihr Dynamics 365 Customer Insights-Administrator kann diese Anreicherung jederzeit entfernen, um die Nutzung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="0fa8f-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
