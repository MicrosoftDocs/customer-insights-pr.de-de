---
title: Anreicherung mit der Drittanbieter-Anreicherung Experian
description: Allgemeine Informationen über die Drittanbieter-Anreicherung von Experian.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269559"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="4c277-103">Kundenprofile mit demografischen Daten aus Experian anreichern (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="4c277-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="4c277-104">Experian ist ein weltweit führender Anbieter von Kredit- und Marketingdienstleistungen für Verbraucher- und Geschäftskredite.</span><span class="sxs-lookup"><span data-stu-id="4c277-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="4c277-105">Mit den Datenanreicherungsdiensten von Experian können Sie ein tieferes Verständnis Ihrer Kunden aufbauen, indem Sie Ihre Kundenprofile mit demografischen Daten wie Haushaltsgröße, Einkommen und mehr bereichern.</span><span class="sxs-lookup"><span data-stu-id="4c277-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4c277-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4c277-106">Prerequisites</span></span>

<span data-ttu-id="4c277-107">Für das Konfigurieren von Experian an müssen folgende Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="4c277-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="4c277-108">Sie haben ein aktives Experian-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="4c277-108">You have an active Experian subscription.</span></span> <span data-ttu-id="4c277-109">Um ein Abonnement zu erhalten, [wenden Sie sich direkt an Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="4c277-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="4c277-110">[Weitere Informationen zur Datenanreicherung Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="4c277-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="4c277-111">Sie haben die Benutzer-ID, die Party-ID und die Modellnummer für Ihr SSH-fähiges Secure Transport (ST)-Konto, das Experian für Sie erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="4c277-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="4c277-112">Sie haben [Administrator](permissions.md#administrator) Berechtigungen in Zielgruppen-Insights.</span><span class="sxs-lookup"><span data-stu-id="4c277-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="4c277-113">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="4c277-113">Configuration</span></span>

1. <span data-ttu-id="4c277-114">Wechseln Sie zu **Daten** > **Anreicherung** und wählen Sie die Registerkarte **Entdecken** aus.</span><span class="sxs-lookup"><span data-stu-id="4c277-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="4c277-115">Wählen Sie **Meine Daten anreichern** auf der Experian-Kachel.</span><span class="sxs-lookup"><span data-stu-id="4c277-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4c277-116">![Experian-Kachel](media/experian-tile.png "Experian-Kachel")</span><span class="sxs-lookup"><span data-stu-id="4c277-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="4c277-117">Wählen Sie **Los geht's** und geben Sie die Benutzer-ID, die Partei-ID und die Modellnummer für Ihr Experian Secure Transport-Konto ein.</span><span class="sxs-lookup"><span data-stu-id="4c277-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="4c277-118">Prüfen und geben Sie Ihre Zustimmung zum **Datenschutz und Einhaltung von Vorschriften**, indem Sie das Kontrollkästchen **Ich stimme zu** markieren.</span><span class="sxs-lookup"><span data-stu-id="4c277-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="4c277-119">Bestätigen Sie alle Eingaben durch Auswahl von **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="4c277-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="4c277-120">Ihre Felder zuordnen</span><span class="sxs-lookup"><span data-stu-id="4c277-120">Map your fields</span></span>

1.  <span data-ttu-id="4c277-121">Wählen Sie **Daten hinzufügen** und dann den **Kundendatensatz**, den Sie mit demografischen Daten von Experian anreichern möchten.</span><span class="sxs-lookup"><span data-stu-id="4c277-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="4c277-122">Sie können die **Kundenentität** auswählen, um alle Ihre Kundenprofile anzureichern, oder eine Segmententität auswählen, um nur Kundenprofile anzureichern, die in diesem Segment enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="4c277-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="4c277-123">Wählen Sie Ihre Schlüsselkennungen **Name und Adresse**, **E-Mail**, oder **Telefon** aus, um sie zur Identitätsauflösung an Experian zu senden.</span><span class="sxs-lookup"><span data-stu-id="4c277-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="4c277-124">Weitere an Experian gesendete Schlüsselbezeichnerattribute führen wahrscheinlich zu einer höheren Übereinstimmungsrate.</span><span class="sxs-lookup"><span data-stu-id="4c277-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="4c277-125">Wählen Sie **Weiter** und ordnen Sie die entsprechenden Attribute Ihrer einheitlichen Kundenentität den ausgewählten Schlüsselbezeichnerfeldern zu.</span><span class="sxs-lookup"><span data-stu-id="4c277-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="4c277-126">Wählen Sie **Attribut hinzufügen**, um zusätzliche Attribute zuzuordnen, die Sie an Experian senden möchten.</span><span class="sxs-lookup"><span data-stu-id="4c277-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="4c277-127">Wählen Sie **Speichern** aus, um die Feldzuordnung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4c277-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4c277-128">![Experian-Feldzuordnung](media/experian-field-mapping.png "Experian-Feldzuordnung")</span><span class="sxs-lookup"><span data-stu-id="4c277-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="4c277-129">Anreicherungsergebnisse</span><span class="sxs-lookup"><span data-stu-id="4c277-129">Enrichment results</span></span>

<span data-ttu-id="4c277-130">Wählen Sie **Ausführen** aus der Befehlsleiste aus, um den Anreicherungsprozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="4c277-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="4c277-131">Sie können das System die Anreicherung auch automatisch als Teil von einer [geplante Aktualisierung](system.md#schedule-tab) ausführen lassen.</span><span class="sxs-lookup"><span data-stu-id="4c277-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4c277-132">Die Bearbeitungszeit hängt von der Größe Ihrer Kundendaten und den von Experian für Ihr Konto eingerichteten Anreicherungsprozessen ab.</span><span class="sxs-lookup"><span data-stu-id="4c277-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="4c277-133">Nach Abschluss des Anreicherungsprozesses können Sie die neu angereicherten Kundenprofildaten unter **Meine Anreicherungen** überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4c277-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="4c277-134">Außerdem finden Sie den Zeitpunkt des letzten Updates und die Anzahl der angereicherten Profile.</span><span class="sxs-lookup"><span data-stu-id="4c277-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="4c277-135">Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.</span><span class="sxs-lookup"><span data-stu-id="4c277-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4c277-136">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4c277-136">Next steps</span></span>

<span data-ttu-id="4c277-137">Bauen Sie auf Ihren angereicherten Kundendaten auf.</span><span class="sxs-lookup"><span data-stu-id="4c277-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="4c277-138">Erstellen Sie [Segmente](segments.md), [Maße](measures.md), und selbst [Exportdaten](export-destinations.md), um Ihren Kunden personalisierte Erlebnisse zu bieten.</span><span class="sxs-lookup"><span data-stu-id="4c277-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4c277-139">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="4c277-139">Data privacy and compliance</span></span>

<span data-ttu-id="4c277-140">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Experian aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="4c277-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4c277-141">Microsoft wird diese Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, sicherzustellen, dass Experian alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben.</span><span class="sxs-lookup"><span data-stu-id="4c277-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4c277-142">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4c277-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4c277-143">Ihr Dynamics 365 Customer Insights-Administrator kann diese Anreicherung jederzeit entfernen, um die Nutzung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="4c277-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]