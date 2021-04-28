---
title: LiveRamp Connector
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu LiveRamp exportieren.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760326"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="d742a-103">Segmente nach LiveRamp&reg; exportieren (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="d742a-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="d742a-104">Aktivieren Sie Ihre Daten in LiveRamp, um sich mit über 500 Plattformen in digitalen, sozialen und TVs zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="d742a-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="d742a-105">Arbeiten Sie mit Ihren Daten in LiveRamp, um Werbekampagnen auszurichten, zu Unterdrücken und zu personalisieren.</span><span class="sxs-lookup"><span data-stu-id="d742a-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="d742a-106">Voraussetzungen für die Verbindung</span><span class="sxs-lookup"><span data-stu-id="d742a-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="d742a-107">Sie benötigen ein LiveRamp-Abonnement, um diesen Connector verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="d742a-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="d742a-108">Um ein Abonnement zu erhalten, [kontaktieren Sie LiveRamp ](https://liveramp.com/contact/) direkt.</span><span class="sxs-lookup"><span data-stu-id="d742a-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="d742a-109">[Erfahren Sie mehr über LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="d742a-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="d742a-110">Verbindung mit LiveRamp einrichten</span><span class="sxs-lookup"><span data-stu-id="d742a-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="d742a-111">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="d742a-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d742a-112">Wählen Sie **Verbindung hinzufügen** und dann **LiveRamp** aus, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d742a-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="d742a-113">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="d742a-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d742a-114">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="d742a-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d742a-115">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="d742a-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d742a-116">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="d742a-116">Choose who can use this connection.</span></span> <span data-ttu-id="d742a-117">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="d742a-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d742a-118">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d742a-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d742a-119">**Benutzername** und **Passwort** für Ihr LiveRamp Secure FTP (SFTP) Konto bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d742a-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="d742a-120">Diese Anmeldeinformationen können sich von Ihren LiveRamp Onboarding-Anmeldeinformationen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="d742a-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="d742a-121">Wählen Sie **Überprüfen**, um die Verbindung zu LiveRamp zu testen.</span><span class="sxs-lookup"><span data-stu-id="d742a-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="d742a-122">Geben Sie nach erfolgreicher Überprüfung Ihre Zustimmung für **Datenschutz und Compliance** durch Auswahl des Kontrollkästchens **Genau**.</span><span class="sxs-lookup"><span data-stu-id="d742a-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="d742a-123">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="d742a-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d742a-124">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="d742a-124">Configure an export</span></span>

<span data-ttu-id="d742a-125">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="d742a-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d742a-126">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d742a-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d742a-127">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="d742a-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d742a-128">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d742a-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d742a-129">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem LiveRamp-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="d742a-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="d742a-130">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="d742a-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d742a-131">In dem Feld **Wählen Sie Ihre Schlüsselkennung** wählen Sie **E-Mail**, **Name und Adresse** oder **Telefon**, um die Identitätsauflösung an LiveRamp zu senden.</span><span class="sxs-lookup"><span data-stu-id="d742a-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d742a-132">![LiveRamp-Connector mit Attributzuordnung](media/export-liveramp-segments.png "LiveRamp-Connector mit Attributzuordnung")</span><span class="sxs-lookup"><span data-stu-id="d742a-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="d742a-133">Ordnen Sie die entsprechenden Attribute Ihrer einheitlichen Kundenentität der ausgewählten Schlüsselkennung zu.</span><span class="sxs-lookup"><span data-stu-id="d742a-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="d742a-134">Wählen Sie **Attribute hinzufügen**, um weitere Attribute zuzuordnen, die an LiveRamp gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d742a-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="d742a-135">Wenn Sie mehr Schlüsselkennungsattribute an LiveRamp senden, erhalten Sie wahrscheinlich eine höhere Übereinstimmungsrate.</span><span class="sxs-lookup"><span data-stu-id="d742a-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="d742a-136">Wählen Sie die Segmente aus, die Sie in LiveRamp exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d742a-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="d742a-137">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="d742a-137">Select **Save**.</span></span>

<span data-ttu-id="d742a-138">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d742a-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d742a-139">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d742a-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d742a-140">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d742a-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d742a-141">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="d742a-141">Data privacy and compliance</span></span>

<span data-ttu-id="d742a-142">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Liveramp aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="d742a-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d742a-143">Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Liveramp alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können.</span><span class="sxs-lookup"><span data-stu-id="d742a-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d742a-144">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d742a-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d742a-145">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="d742a-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
