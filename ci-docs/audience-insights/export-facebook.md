---
title: Customer Insights-Daten in den Facebook Ads Manager exportieren
description: Erfahren Sie, wie Sie die Verbindung zu einem Facebook Anzeigen-Manager konfigurieren.
ms.date: 06/05/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e2b52fe743563e4bf61d870cbf1718e6c752a67
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596681"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="b5458-103">Konnektor für Facebook Anzeigenmanager (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="b5458-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="b5458-104">Exportieren Sie Segmente einheitlicher Kundenprofile in den Facebook Anzeigenmanager zum Erstellen von Kampagnen auf Facebook und Instagram.</span><span class="sxs-lookup"><span data-stu-id="b5458-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b5458-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b5458-105">Prerequisites</span></span>

- <span data-ttu-id="b5458-106">Sie müssen ein [**Facebook Anzeigenkonto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) haben, das ein [**Facebook Geschäftskonto**](https://business.facebook.com/) enthält.</span><span class="sxs-lookup"><span data-stu-id="b5458-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="b5458-107">Sie müssen ein Administrator auf dem [**Facebook Ad-Konto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) sein.</span><span class="sxs-lookup"><span data-stu-id="b5458-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="b5458-108">Mit Facebook Anzeigenmanager verbinden</span><span class="sxs-lookup"><span data-stu-id="b5458-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="b5458-109">Gehen Sie zu **Administrator** > **Exportziele**.</span><span class="sxs-lookup"><span data-stu-id="b5458-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b5458-110">Unter **Facebook Anzeigenmanager** wählen Sie **Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b5458-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="b5458-111">Geben Sie Ihrem Exportziel einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="b5458-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b5458-112">Wählen Sie **Weitermachen mit Facebook**, um sich bei Ihrem Facebook Anzeigenkonto anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b5458-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="b5458-113">Erlauben Sie die Berechtigung **ads_management** nach der Authentifizierung mit Facebook.</span><span class="sxs-lookup"><span data-stu-id="b5458-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="b5458-114">Wählen Sie das **Facebook Ads Konto**, mit dem Sie arbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="b5458-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="b5458-115">Wählen Sie **vorhandenes benutzerdefiniertes Publikum** aus der Dropdown-Liste au oder erstellen Sie ein **Neues benutzerdefiniertes Publikum**.</span><span class="sxs-lookup"><span data-stu-id="b5458-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="b5458-116">Weitere Informationen finden Sie unter [**Publikum in Facebook Anzeigenmanager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="b5458-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="b5458-117">Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="b5458-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b5458-118">Wählen Sie **Weiter**, um die Konfiguration des Exports zu starten.</span><span class="sxs-lookup"><span data-stu-id="b5458-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="b5458-119">Konfigurieren Sie den Konnektor</span><span class="sxs-lookup"><span data-stu-id="b5458-119">Configure the connector</span></span>

1. <span data-ttu-id="b5458-120">Unter **Wählen Sie Ihr Schlüsselkennungsfeld** wählen Sie **E-Mail**, **Name und Adresse** oder **Telefon** aus und senden es an Facebook Anzeigenmanager.</span><span class="sxs-lookup"><span data-stu-id="b5458-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="b5458-121">Ordnen Sie die entsprechenden Attribute Ihrer einheitlichen Kundenentität der ausgewählten Schlüsselkennung zu.</span><span class="sxs-lookup"><span data-stu-id="b5458-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="b5458-122">[TIPP] Die besten Chancen für eine Übereinstimmung ergeben sich, wenn Sie **E-Mail** als Schlüsselkennung auswählen.</span><span class="sxs-lookup"><span data-stu-id="b5458-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="b5458-123">Das Hinzufügen zusätzlicher Bezeichner kann die Übereinstimmung verbessern.</span><span class="sxs-lookup"><span data-stu-id="b5458-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="b5458-124">Wählen Sie **Attribute hinzufügen**, um zusätzliche Attribute zuzuordnen, die an den Facebook Anzeigenmanager gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b5458-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="b5458-125">Attribute vom Facebook Anzeigenmanager wird den folgenden benutzerfreundlichen Namen zugeordnet: **VN** = **Vorname**, **NN** = **Nachname**, **EI** = **Erste Initiale**, **TELEFON** = **Telefon**, **GEN** = **Geschlecht**, **GEB** = **Geburtsdatum**, **KT** = **Kanton**, **ORT** = **Stadt**, **PLZ** = **Postleitzahl**, **LAND** = **Land/Region**</span><span class="sxs-lookup"><span data-stu-id="b5458-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="b5458-126">Wählen Sie die Segemente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b5458-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="b5458-127">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="b5458-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b5458-128">Exportieren der Daten</span><span class="sxs-lookup"><span data-stu-id="b5458-128">Export the data</span></span>

<span data-ttu-id="b5458-129">Sie könenn [Daten nach Bedarf exportieren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b5458-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b5458-130">Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="b5458-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b5458-131">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b5458-131">Known limitations</span></span>

- <span data-ttu-id="b5458-132">Bis zu 10 Millionen Kundenprofile pro Export zum Facebook-Anzeigenmanager</span><span class="sxs-lookup"><span data-stu-id="b5458-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="b5458-133">Der Export zum Facebook-Anzeigenmanager ist auf Segmente beschränkt</span><span class="sxs-lookup"><span data-stu-id="b5458-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="b5458-134">Das Exportieren von Segmenten mit insgesamt 10 Million Profilen kann bis zu 90 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="b5458-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b5458-135">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="b5458-135">Data privacy and compliance</span></span>

<span data-ttu-id="b5458-136">Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten an Facebook Ads Manager zu übertragen, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie persönlicher Daten.</span><span class="sxs-lookup"><span data-stu-id="b5458-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b5458-137">Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass die Facebook-Anzeigen alle Ihre Datenschutz- oder Sicherheitsverpflichtungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="b5458-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="b5458-138">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b5458-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b5458-139">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="b5458-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]