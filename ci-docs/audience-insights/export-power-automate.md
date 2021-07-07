---
title: Power Automate Connector | Microsoft Docs
description: Flows in Microsoft Power Automate aus Dynamics 365 Customer Insights erstellen.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 57be0a204ef920b7a4bb31cf9a5b3a77f96eca0d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305063"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="f49d5-103">Power Automate-Connector (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="f49d5-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="f49d5-104">Lösen Sie bei Änderungen an den Daten automatisch bestimmte Ereignisse aus. Verwalten Sie komplexere Flows direkt in [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="f49d5-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="f49d5-105">Power Automate Auslöser</span><span class="sxs-lookup"><span data-stu-id="f49d5-105">Power Automate triggers</span></span>

<span data-ttu-id="f49d5-106">Verwenden Sie Trigger, um Cloud-Flows zu erstellen und sich wiederholende Aufgaben wie Benachrichtigungen oder erweiterte Aktionen zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="f49d5-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="f49d5-107">Auslösen, wenn die Aktualisierung einer Datenquelle fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="f49d5-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="f49d5-108">Auslösen, wenn eine Datenquellenaktualisierung erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="f49d5-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="f49d5-109">Auslösen, wenn ein Schwellenwert in einem Segment überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="f49d5-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="f49d5-110">Der Auslöser ist auf das Überschreiten des Schwellenwerts beschränkt.</span><span class="sxs-lookup"><span data-stu-id="f49d5-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="f49d5-111">Auslösen, wenn ein Schwellenwert bei einer Geschäftsmaßnahme überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="f49d5-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="f49d5-112">Nur Unternehmenskennzahlen ohne Dimension werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f49d5-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="f49d5-113">Der Auslöser ist auf das Überschreiten des Schwellenwerts beschränkt.</span><span class="sxs-lookup"><span data-stu-id="f49d5-113">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="f49d5-114">Auslöser, wenn eine vollständige Aktualisierung von (Datenquellen, Segmenten, Kennzahlen,...) abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="f49d5-114">Trigger when a full refresh of (data sources, segments, measures, ...) is completed.</span></span>
- <span data-ttu-id="f49d5-115">Wird ausgelöst, wenn eine Aktualisierung des Vereinigungsprozesses (Zuordnung, Übereinstimmung, Zusammenführung) abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="f49d5-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

[<span data-ttu-id="f49d5-116">Konfigurieren Sie Ihre Auslöser in Power Automate</span><span class="sxs-lookup"><span data-stu-id="f49d5-116">Configure your triggers in Power Automate.</span></span>](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a><span data-ttu-id="f49d5-117">Power Automate-Aktionen</span><span class="sxs-lookup"><span data-stu-id="f49d5-117">Power Automate actions</span></span>

<span data-ttu-id="f49d5-118">Der Power Automate-Anschluss bietet andere Aktionen als die verfügbaren Auslöser.</span><span class="sxs-lookup"><span data-stu-id="f49d5-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="f49d5-119">Weitere Informationen finden Sie im [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="f49d5-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="f49d5-120">Power Automate-Workflow erstellen</span><span class="sxs-lookup"><span data-stu-id="f49d5-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="f49d5-121">Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Ziele exportieren**.</span><span class="sxs-lookup"><span data-stu-id="f49d5-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f49d5-122">Auf der **Power Automate**-Kachel wählen Sie **Einrichten**.</span><span class="sxs-lookup"><span data-stu-id="f49d5-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="f49d5-123">Der Customer Insights-Konnektor (Vorschau) in Power Automate wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f49d5-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="f49d5-124">**Anmelden** bei Power Automate.</span><span class="sxs-lookup"><span data-stu-id="f49d5-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="f49d5-125">Wählen Sie einen der verfügbaren Trigger und fügen Sie Ihrem neuen Flow weitere Schritte hinzu.</span><span class="sxs-lookup"><span data-stu-id="f49d5-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="f49d5-126">Weitere Informationen finden Sie unter [Cloud-Flow in Power Automate erstellen](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="f49d5-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="f49d5-127">Beispiele für die Verwendung von Flows:</span><span class="sxs-lookup"><span data-stu-id="f49d5-127">Examples of how to use flows:</span></span> 
- <span data-ttu-id="f49d5-128">Senden Sie eine Nachricht an den Microsoft Teams-Kanal, wenn eine Aktualisierung der Datenquelle fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="f49d5-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="f49d5-129">Senden Sie eine E-Mail an die Dateneigentümer, wenn ein Schwellenwert für ein Segment überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="f49d5-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
