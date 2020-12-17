---
title: Power Automate Connector | Microsoft Docs
description: Erstellen Sie in Microsoft Power Automate aus Dynamics 365 Customer Insights Flows.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405750"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="9319f-103">Power Automate-Connector (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="9319f-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="9319f-104">Lösen Sie bei Änderungen an den Daten automatisch bestimmte Ereignisse aus. Verwalten Sie komplexere Flows direkt in [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="9319f-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="9319f-105">Power Automate Auslöser</span><span class="sxs-lookup"><span data-stu-id="9319f-105">Power Automate triggers</span></span>

<span data-ttu-id="9319f-106">Sie können eine Vielzahl von Triggern verwenden, mit denen Sie Flows erstellen können, um sich wiederholende Aufgaben zu automatisieren, z. B. Benachrichtigungen oder fortgeschrittenere Aktionen.</span><span class="sxs-lookup"><span data-stu-id="9319f-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="9319f-107">Auslösen, wenn die Aktualisierung einer Datenquelle fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="9319f-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="9319f-108">Auslösen, wenn eine Datenquellenaktualisierung erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="9319f-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="9319f-109">Auslösen, wenn ein Schwellenwert in einem Segment überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="9319f-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="9319f-110">Der Auslöser ist auf das Überschreiten des Schwellenwerts beschränkt.</span><span class="sxs-lookup"><span data-stu-id="9319f-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="9319f-111">Auslösen, wenn ein Schwellenwert bei einer Geschäftsmaßnahme überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="9319f-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="9319f-112">Der Auslöser ist auf das Überschreiten des Schwellenwerts beschränkt.</span><span class="sxs-lookup"><span data-stu-id="9319f-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="9319f-113">Auslöser, wenn eine vollständige Aktualisierung von (Datenquellen, Segmenten, Kennzahlen,...) abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="9319f-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="9319f-114">Wird ausgelöst, wenn eine Aktualisierung des Vereinigungsprozesses (Zuordnung, Übereinstimmung, Zusammenführung) abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="9319f-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="9319f-115">[Konfigurieren Sie Ihre Auslöser in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="9319f-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="9319f-116">Power Automate-Aktionen</span><span class="sxs-lookup"><span data-stu-id="9319f-116">Power Automate actions</span></span>
<span data-ttu-id="9319f-117">Der Power Automate-Anschluss bietet andere Aktionen als die verfügbaren Auslöser.</span><span class="sxs-lookup"><span data-stu-id="9319f-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="9319f-118">Weitere Informationen finden Sie im [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="9319f-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="9319f-119">Erstellen Sie einen Power Automate-Fluss in Zielgruppen-Insights</span><span class="sxs-lookup"><span data-stu-id="9319f-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="9319f-120">Gehen Sie in Zielgruppen-Insights zu **Admin** > **System**.</span><span class="sxs-lookup"><span data-stu-id="9319f-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="9319f-121">Wählen Sie auf der Seite **System** die Registerkarte **Status**.</span><span class="sxs-lookup"><span data-stu-id="9319f-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="9319f-122">Wählen Sie im Abschnitt **Datenquellen** die Option **Flows** und in der Dropdownliste die Option **Einen Flow erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="9319f-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9319f-123">![Power Automate-Conntector zeigt "Flow erstellen Aktion"](media/power-automate-connector-create-flow.png "Power Automate Connector, der die Aktion "Flow erstellen" anzeigt")</span><span class="sxs-lookup"><span data-stu-id="9319f-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="9319f-124">Wählen Sie in Power Automate einen der verfügbaren Trigger aus, um Ihren bevorzugten Flow zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9319f-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="9319f-125">Wenn Sie Ihren ersten Flow erstellen, müssen Sie sich zuerst mit dem Power Automate Konnektor authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="9319f-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
