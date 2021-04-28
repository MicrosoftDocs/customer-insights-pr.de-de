---
title: Anreicherung von Firmenprofilen mit der Drittanbieter-Anreicherung Leadspace
description: Allgemeine Informationen über die Drittanbieter-Anreicherung von Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895912"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="92cf4-103">Anreicherung von Firmenprofilen mit Leadspace (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="92cf4-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="92cf4-104">Leadspace ist ein datenwissenschaftliches Unternehmen, das eine B2B-Kundendatenplattform anbietet.</span><span class="sxs-lookup"><span data-stu-id="92cf4-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="92cf4-105">Sie ermöglicht es Kunden mit einheitlichen Kundenprofilen für Unternehmen, ihre Daten anzureichern.</span><span class="sxs-lookup"><span data-stu-id="92cf4-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="92cf4-106">Anreicherungen umfassen zusätzliche Attribute wie Unternehmensgröße, Standort, Branche und mehr.</span><span class="sxs-lookup"><span data-stu-id="92cf4-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="92cf4-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="92cf4-107">Prerequisites</span></span>

<span data-ttu-id="92cf4-108">Um Leadspace zu konfigurieren, müssen die folgenden Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="92cf4-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="92cf4-109">Sie benötigen eine aktive Leadspace-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="92cf4-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="92cf4-110">Sie haben [Einheitliche Kundenprofile](customer-profiles.md) für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="92cf4-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="92cf4-111">Eine Leadspace-Verbindung wurde bereits von einem Administrator konfiguriert oder Sie haben [Administrator](permissions.md#administrator)-Berechtigungen und „dauerhaften Schlüssel“ (bezeichnet als **Leadspace-Token**).</span><span class="sxs-lookup"><span data-stu-id="92cf4-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="92cf4-112">Kontaktieren Sie [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) direkt für Details über ihr Produkt.</span><span class="sxs-lookup"><span data-stu-id="92cf4-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="92cf4-113">Anreicherungskonfiguration</span><span class="sxs-lookup"><span data-stu-id="92cf4-113">Configure the enrichment</span></span>

1. <span data-ttu-id="92cf4-114">Gehen Sie in Zielgruppen-Insights zu **Daten** > **Anreicherung**.</span><span class="sxs-lookup"><span data-stu-id="92cf4-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="92cf4-115">Wählen Sie **Meine Daten anreichern** auf der Leadspace-Kachel und wählen Sie **Los geht's**.</span><span class="sxs-lookup"><span data-stu-id="92cf4-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Screenshot der Leadspace-Kachel.":::

1. <span data-ttu-id="92cf4-117">Wählen Sie eine [Verbindung](connections.md) aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="92cf4-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="92cf4-118">Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="92cf4-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="92cf4-119">Wenn Sie ein Administrator sind, können Sie durch Auswahl von **Verbindung hinzufügen** und **Leadspace** eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="92cf4-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="92cf4-120">Wählen Sie **Mit Leadspace verbinden**, um die Verbindungsauswahl zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="92cf4-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="92cf4-121">Wählen Sie **Weiter** und wählen Sie den **Kundendatensatz**, den Sie mit Unternehmensdaten von Leadspace anreichern möchten.</span><span class="sxs-lookup"><span data-stu-id="92cf4-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="92cf4-122">Sie können die **Kundenentität** auswählen, um alle Ihre Kundenprofile anzureichern, oder eine Segmententität auswählen, um nur Kundenprofile anzureichern, die in diesem Segment enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="92cf4-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Screenshot bei Auswahl des Kundendatensatzes.":::

1. <span data-ttu-id="92cf4-124">Wählen Sie **Weiter** aus, und definieren Sie, welche Felder aus Ihren einheitlichen Profilen verwendet werden sollen, um nach übereinstimmenden Unternehmensdaten von Leadspace zu suchen.</span><span class="sxs-lookup"><span data-stu-id="92cf4-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="92cf4-125">Das Feld **Firmenname** ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="92cf4-125">The **Name of company** field is required.</span></span> <span data-ttu-id="92cf4-126">Für eine höhere Abgleichsgenauigkeit können bis zu zwei weitere Felder, **Firmen-Website** und **Firmenstandort**, hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="92cf4-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace-Feld-Zuordnungsbereich.":::

1. <span data-ttu-id="92cf4-128">Wählen Sie **Weiter** aus, um die Feldzuordnung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="92cf4-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="92cf4-129">Geben Sie einen Namen für die Anreicherung ein und wählen Sie **Anreicherung speichern**, nachdem Sie Ihre Auswahl überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="92cf4-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="92cf4-130">Konfigurieren Sie die Verbindung für Leadspace</span><span class="sxs-lookup"><span data-stu-id="92cf4-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="92cf4-131">Sie müssen ein Administrator sein, um Verbindungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="92cf4-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="92cf4-132">Wählen Sie **Verbindung hinzufügen** beim Konfigurieren einer Anreicherung *oder* gehen Sie zu **Administrator** > **Verbindungen** und wählen Sie **Einrichten** auf der Kachel „Leadspace“.</span><span class="sxs-lookup"><span data-stu-id="92cf4-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="92cf4-133">Wählen Sie **Los geht's** aus</span><span class="sxs-lookup"><span data-stu-id="92cf4-133">Select **Get Started**</span></span> 

1. <span data-ttu-id="92cf4-134">Geben Sie einen Namen für die Verbindung in das Feld **Anzeigename** ein.</span><span class="sxs-lookup"><span data-stu-id="92cf4-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="92cf4-135">Geben Sie ein gültiges Leadspace-Token an.</span><span class="sxs-lookup"><span data-stu-id="92cf4-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="92cf4-136">Prüfen und geben Sie Ihre Zustimmung zum **Datenschutz und Einhaltung von Vorschriften**, indem Sie das Kontrollkästchen **Ich stimme zu** markieren.</span><span class="sxs-lookup"><span data-stu-id="92cf4-136">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="92cf4-137">Wählen Sie **Überprüfen**, um die Konfiguration zu validieren.</span><span class="sxs-lookup"><span data-stu-id="92cf4-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="92cf4-138">Wählen Sie nach Abschluss der Überprüfung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="92cf4-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Verbindungskonfigurationsseite für Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="92cf4-140">Anreicherungsergebnisse</span><span class="sxs-lookup"><span data-stu-id="92cf4-140">Enrichment results</span></span>

<span data-ttu-id="92cf4-141">Nach dem Aktualisieren der Anreicherung können Sie die neu angereicherten Unternehmensdaten unter[Meine Bereicherung](enrichment-hub.md) überprüfen.</span><span class="sxs-lookup"><span data-stu-id="92cf4-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="92cf4-142">Den Zeitpunkt der letzten Aktualisierung und die Anzahl der angereicherten Profile können Sie anzeigen.</span><span class="sxs-lookup"><span data-stu-id="92cf4-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="92cf4-143">Eine Detailansicht jedes angereicherten Profils erhalten Sie unter **Anreicherungen ansehen**.</span><span class="sxs-lookup"><span data-stu-id="92cf4-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="92cf4-144">Weitere Informationen finden Sie unter [Leadspace-APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="92cf4-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="92cf4-145">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="92cf4-145">Next steps</span></span>

<span data-ttu-id="92cf4-146">Bauen Sie auf Ihren angereicherten Kundendaten auf.</span><span class="sxs-lookup"><span data-stu-id="92cf4-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="92cf4-147">Erstellen Sie [Segmente](segments.md), [Maße](measures.md), und selbst [Exportdaten](export-destinations.md), um Ihren Kunden personalisierte Erlebnisse zu bieten.</span><span class="sxs-lookup"><span data-stu-id="92cf4-147">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="92cf4-148">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="92cf4-148">Data privacy and compliance</span></span>

<span data-ttu-id="92cf4-149">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Leadspace aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="92cf4-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="92cf4-150">Microsoft wird diese Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Leadspace alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können.</span><span class="sxs-lookup"><span data-stu-id="92cf4-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="92cf4-151">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="92cf4-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="92cf4-152">Ihr Dynamics 365 Customer Insights-Administrator kann diese Anreicherung jederzeit entfernen, um die Nutzung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="92cf4-152">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
