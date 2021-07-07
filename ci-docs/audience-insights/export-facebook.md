---
title: Customer Insights-Daten in den Facebook Ads Manager exportieren
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zum Facebook Ads Manager exportieren.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e20c7b7fd3989d7621cb7765f38b85c8ab4adfcb
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305109"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="8fe13-103">Segmentliste zum Facebook Ads Manager exportieren (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="8fe13-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="8fe13-104">Exportieren Sie Segmente einheitlicher Kundenprofile in den Facebook Anzeigenmanager zum Erstellen von Kampagnen auf Facebook und Instagram.</span><span class="sxs-lookup"><span data-stu-id="8fe13-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="8fe13-105">Voraussetzungen für die Verbindung</span><span class="sxs-lookup"><span data-stu-id="8fe13-105">Prerequisites for connection</span></span>

- <span data-ttu-id="8fe13-106">Sie benötigen ein [**Facebook Ads Konto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), das ein [**Facebook Business-Konto**](https://business.facebook.com/) enthält.</span><span class="sxs-lookup"><span data-stu-id="8fe13-106">You need to have a [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="8fe13-107">Sie müssen ein Administrator auf dem [**Facebook Ads-Konto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) sein.</span><span class="sxs-lookup"><span data-stu-id="8fe13-107">You need to be an administrator on the [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8fe13-108">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="8fe13-108">Known limitations</span></span>

- <span data-ttu-id="8fe13-109">Bis zu 10 Millionen Kundenprofile pro Export nach Facebook Anzeigenmanager.</span><span class="sxs-lookup"><span data-stu-id="8fe13-109">Up to 10 million customer profiles per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="8fe13-110">Der Export zum Facebook Ads Manager ist auf Segmente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="8fe13-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="8fe13-111">Erstellen oder aktualisieren Sie in Facebook nur benutzerdefinierte Zielgruppen vom Typ *Kundenliste*.</span><span class="sxs-lookup"><span data-stu-id="8fe13-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="8fe13-112">Das Exportieren von Segmenten mit insgesamt 10 Million Profilen kann bis zu 90 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="8fe13-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="8fe13-113">Verbindung herstellen zum Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="8fe13-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="8fe13-114">Bevor Benutzer einen Export erstellen können, muss ein Administrator die Verbindung zum Dienst konfigurieren und den Mitwirkenden die Verwendung der Verbindung ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="8fe13-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="8fe13-115">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="8fe13-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8fe13-116">Wählen Sie **Verbindung hinzufügen** und dann **Facebook Ads Manager** aus, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8fe13-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="8fe13-117">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="8fe13-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8fe13-118">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="8fe13-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8fe13-119">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="8fe13-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8fe13-120">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="8fe13-120">Choose who can use this connection.</span></span> <span data-ttu-id="8fe13-121">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="8fe13-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="8fe13-122">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8fe13-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8fe13-123">Mithilfe von Facebook Ads authentifizieren:</span><span class="sxs-lookup"><span data-stu-id="8fe13-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="8fe13-124">Wählen Sie **Forfahren mit Facebook**, um sich bei Ihrem Facebook Anzeigenkonto anzumelden.</span><span class="sxs-lookup"><span data-stu-id="8fe13-124">Select **Continue with Facebook** to sign in to your Facebook Ads account.</span></span>

   1. <span data-ttu-id="8fe13-125">Erlauben Sie die Berechtigung **ads_management** nach der Authentifizierung mit Facebook.</span><span class="sxs-lookup"><span data-stu-id="8fe13-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="8fe13-126">Wählen Sie das **Facebook Ads Konto**, mit dem Sie arbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="8fe13-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="8fe13-127">Wählen Sie eine **Bestehende benutzerdefinierte Zielgruppe** aus der Dropdown-Liste oder erstellen Sie eine **Neue benutzerdefinierte Zielgruppe**.</span><span class="sxs-lookup"><span data-stu-id="8fe13-127">Select an **Existing custom audience** from the dropdown list or create a **New custom audience**.</span></span> <span data-ttu-id="8fe13-128">Weitere Informationen finden Sie unter [**Publikum in Facebook Anzeigenmanager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="8fe13-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="8fe13-129">Sie können in Facebook nur benutzerdefinierte Zielgruppen des Typs *Kundenliste* mit diesem Export erstellen oder aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8fe13-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="8fe13-130">In einigen Fällen sehen Sie benutzerdefinierte Zielgruppen verschiedener Typen in der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="8fe13-130">In some cases, you see custom audiences of different types in the dropdown list.</span></span> <span data-ttu-id="8fe13-131">Auswahl eines anderen Typs als *Kundenliste* führt zu einem fehlgeschlagenen Export.</span><span class="sxs-lookup"><span data-stu-id="8fe13-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="8fe13-132">Überprüfen Sie **Datenschutz und Konformität** und wählen **Ich stimme zu** aus.</span><span class="sxs-lookup"><span data-stu-id="8fe13-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="8fe13-133">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="8fe13-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="8fe13-134">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="8fe13-134">Configure an export</span></span>

<span data-ttu-id="8fe13-135">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="8fe13-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8fe13-136">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8fe13-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8fe13-137">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="8fe13-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8fe13-138">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8fe13-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="8fe13-139">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Abschnitt **Facebook Ads Manager** aus.</span><span class="sxs-lookup"><span data-stu-id="8fe13-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="8fe13-140">Wenn dieser Abschnittsname nicht angezeigt wird, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="8fe13-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="8fe13-141">Unter **Wählen Sie Ihr Schlüsselkennungsfeld** wählen Sie **E-Mail**, **Name und Adresse** oder **Telefon** aus und senden es an Facebook Anzeigenmanager.</span><span class="sxs-lookup"><span data-stu-id="8fe13-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="8fe13-142">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="8fe13-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="8fe13-143">Ordnen Sie die entsprechenden Attribute Ihrer einheitlichen Kundenentität der ausgewählten Schlüsselkennung zu.</span><span class="sxs-lookup"><span data-stu-id="8fe13-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > [!TIP]
   > <span data-ttu-id="8fe13-144">Die besten Chancen für eine Übereinstimmung ergeben sich, wenn Sie **E-Mail** als Schlüsselkennung auswählen.</span><span class="sxs-lookup"><span data-stu-id="8fe13-144">The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="8fe13-145">Das Hinzufügen zusätzlicher Bezeichner kann die Übereinstimmung verbessern.</span><span class="sxs-lookup"><span data-stu-id="8fe13-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="8fe13-146">Wählen Sie **Attribute hinzufügen**, um weitere Attribute zuzuordnen, die an Facebook Ads Manager gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8fe13-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="8fe13-147">Attribute vom Facebook Ads Manager werden den folgenden benutzerfreundlichen Namen zugeordnet: **FN** = **Vorname**, **LN** = **Nachname**, **FI** = **Anfangsbuchstabe des Vornamens**, **PHONE** = **Telefon**, **GEN** = **Geshclecht**, **DOB** = **Geburtsdatum**, **ST** = **Bundesland**, **CT** = **Stadt**, **ZIP** = **Postleitzahl**, **COUNTRY** = **Land/Region**</span><span class="sxs-lookup"><span data-stu-id="8fe13-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / ZIP Code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="8fe13-148">Wählen Sie die Segemente aus, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="8fe13-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="8fe13-149">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="8fe13-149">Select **Save**.</span></span>

<span data-ttu-id="8fe13-150">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8fe13-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8fe13-151">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8fe13-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="8fe13-152">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8fe13-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8fe13-153">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="8fe13-153">Data privacy and compliance</span></span>

<span data-ttu-id="8fe13-154">Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten an Facebook Ads Manager zu übertragen, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie persönlicher Daten.</span><span class="sxs-lookup"><span data-stu-id="8fe13-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8fe13-155">Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass die Facebook-Anzeigen alle Ihre Datenschutz- oder Sicherheitsverpflichtungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="8fe13-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="8fe13-156">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8fe13-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8fe13-157">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="8fe13-157">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
