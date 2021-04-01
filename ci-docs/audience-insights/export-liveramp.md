---
title: LiveRamp Connector
description: Lernen Sie, wie man Daten zu LiveRamp exportiert.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597556"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="f3ab7-103">LiveRamp &reg; Konnektor (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="f3ab7-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="f3ab7-104">Aktivieren Sie Ihre Daten in LiveRamp, um eine Verbindung mit über 500 Plattformen in digitalen, sozialen und TV-Ökosystemen herzustellen.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="f3ab7-105">Arbeiten Sie mit Ihren Daten in LiveRamp, um Werbekampagnen auszurichten, zu Unterdrücken und zu personalisieren.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f3ab7-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f3ab7-106">Prerequisites</span></span>

- <span data-ttu-id="f3ab7-107">Sie benötigen ein LiveRamp-Abonnement, um diesen Connector verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="f3ab7-108">Um ein Abonnement zu erhalten, [kontaktieren Sie LiveRamp ](https://liveramp.com/contact/) direkt.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="f3ab7-109">[Erfahren Sie mehr über LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="f3ab7-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="f3ab7-110">Verbinden Sie mit LiveRamp</span><span class="sxs-lookup"><span data-stu-id="f3ab7-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="f3ab7-111">Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Ziele exportieren**.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f3ab7-112">In der Kachel **LiveRamp** wählen Sie **Einrichten**.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="f3ab7-113">Geben Sie Ihrem Ziel einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f3ab7-114">**Benutzername** und **Passwort** für Ihr LiveRamp Secure FTP (SFTP) Konto bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="f3ab7-115">Diese Anmeldeinformationen können sich von Ihren LiveRamp Onboarding-Anmeldeinformationen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="f3ab7-116">Wählen Sie **Überprüfen**, um die Verbindung zu LiveRamp zu testen.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="f3ab7-117">Geben Sie nach erfolgreicher Überprüfung Ihre Zustimmung für **Datenschutz und Compliance** durch Auswahl des Kontrollkästchens **Genau**.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="f3ab7-118">Wählen Sie **Weiter**, um den LiveRamp-Anschluss einzurichten.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="f3ab7-119">Konfigurieren Sie den Konnektor</span><span class="sxs-lookup"><span data-stu-id="f3ab7-119">Configure the connector</span></span>

1. <span data-ttu-id="f3ab7-120">In dem Feld **Wählen Sie Ihre Schlüsselkennung** wählen Sie **E-Mail**, **Name und Adresse** oder **Telefon**, um die Identitätsauflösung an LiveRamp zu senden.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="f3ab7-121">Ordnen Sie die entsprechenden Attribute Ihrer einheitlichen Kundenentität der ausgewählten Schlüsselkennung zu.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="f3ab7-122">Wählen Sie **Attribute hinzufügen**, um zusätzliche Attribute zuzuordnen, die an LiveRamp gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="f3ab7-123">Wenn Sie mehr Schlüsselkennungsattribute an LiveRamp senden, erhalten Sie wahrscheinlich eine höhere Übereinstimmungsrate.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="f3ab7-124">Wählen Sie die Segmente aus, die Sie in LiveRamp exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="f3ab7-125">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f3ab7-126">![LiveRamp-Connector mit Attributzuordnung](media/export-liveramp-segments.png "LiveRamp-Connector mit Attributzuordnung")</span><span class="sxs-lookup"><span data-stu-id="f3ab7-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f3ab7-127">Exportieren der Daten</span><span class="sxs-lookup"><span data-stu-id="f3ab7-127">Export the data</span></span>

<span data-ttu-id="f3ab7-128">Der Export beginnt in Kürze, wenn alle Voraussetzungen für den Export erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="f3ab7-129">Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="f3ab7-130">Sobald der Export erfolgreich abgeschlossen wurde, können Sie sich bei LiveRamp Onboarding anmelden, um Ihre Daten zu aktivieren und zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f3ab7-131">Datenschutz und Konformität</span><span class="sxs-lookup"><span data-stu-id="f3ab7-131">Data privacy and compliance</span></span>

<span data-ttu-id="f3ab7-132">Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Liveramp aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f3ab7-133">Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass Liveramp alle Datenschutz- oder Sicherheitsverpflichtungen einhält, die Sie haben können.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f3ab7-134">Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f3ab7-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f3ab7-135">Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.</span><span class="sxs-lookup"><span data-stu-id="f3ab7-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]