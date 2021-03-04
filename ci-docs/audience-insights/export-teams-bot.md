---
title: Bot für Microsoft Teams
description: Suchen Sie mit Hilfe eines Bots nach einheitlichen Kundenprofilen in Microsoft Teams.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267951"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="7ebfc-103">Teams Bot für Dynamics 365 Customer Insights (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="7ebfc-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="7ebfc-104">Verbinden Sie mit Microsoft Teams, um einen Bot in Teams-Kanälen nach vereinheitlichten Kundenprofilen suchen zu lassen.</span><span class="sxs-lookup"><span data-stu-id="7ebfc-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7ebfc-105">![Teams Bot zeigt einen Kundendatensatz an](media/teams-bot.png "Teams Bot zeigt einen Kundendatensatz an")</span><span class="sxs-lookup"><span data-stu-id="7ebfc-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7ebfc-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7ebfc-106">Prerequisites</span></span>

<span data-ttu-id="7ebfc-107">Um den Bot einzurichten und zu konfigurieren, müssen folgende Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="7ebfc-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="7ebfc-108">Es gibt mindestens einen [Datenquelle hinzugefügt](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="7ebfc-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="7ebfc-109">Der [Vereinheitlichungsprozess](data-unification.md) ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="7ebfc-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="7ebfc-110">Felder werden dem [Index suchen und filtern](search-filter-index.md) hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7ebfc-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="7ebfc-111">Customer Insights und Teams befinden sich in derselben Organisation.</span><span class="sxs-lookup"><span data-stu-id="7ebfc-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="7ebfc-112">Konfigurieren des Bots</span><span class="sxs-lookup"><span data-stu-id="7ebfc-112">Configure the bot</span></span>

1. <span data-ttu-id="7ebfc-113">Gehen Sie in Zielgruppen-Insights zu **Admin** > **Ziele exportieren**.</span><span class="sxs-lookup"><span data-stu-id="7ebfc-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="7ebfc-114">Auf der Microsoft Teams Kachel wählen Sie **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="7ebfc-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="7ebfc-115">Sie werden zum **Apps** Bereich in Teams weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="7ebfc-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="7ebfc-116">Sie können auch Teams öffnen und **Apps** in der unteren linken Ecke auswählen oder [dirket aus AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) abrufen.</span><span class="sxs-lookup"><span data-stu-id="7ebfc-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="7ebfc-117">Suchen nach **Customer Insights** und App auswählen.</span><span class="sxs-lookup"><span data-stu-id="7ebfc-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="7ebfc-118">Wählen Sie **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7ebfc-118">Select **Add**.</span></span>
1. <span data-ttu-id="7ebfc-119">Nachdem Sie sich bei Customer Insights in Teams angemeldet haben, wird eine Begrüßungsnachricht angezeigt, und Sie können loslegen.</span><span class="sxs-lookup"><span data-stu-id="7ebfc-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="7ebfc-120">Diese Dinge können Sie mit dem Bot tun</span><span class="sxs-lookup"><span data-stu-id="7ebfc-120">Things you can do with the bot</span></span>

<span data-ttu-id="7ebfc-121">Der Bot bietet Suchfunktionen für einheitliche Kundenprofile.</span><span class="sxs-lookup"><span data-stu-id="7ebfc-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="7ebfc-122">Geben Sie **Suche** ein gefolgt von einem Namen, einer E-Mail-Adresse oder einem anderen Feld im einheitlichen Kundenprofil, das dem Such- und Filterindex hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="7ebfc-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="7ebfc-123">Sie erhalten eine Karte mit bis zu 15 Feldern aus dem resultierenden Kundenprofil.</span><span class="sxs-lookup"><span data-stu-id="7ebfc-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="7ebfc-124">Mehrere Übereinstimmungen geben eine Liste mit Ergebnissen zurück, in der Sie ein Profil auswählen können.</span><span class="sxs-lookup"><span data-stu-id="7ebfc-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="7ebfc-125">Sie können den Suchbegriff in doppelte Anführungszeichen setzen, um eine genaue Übereinstimmung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="7ebfc-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="7ebfc-126">Wenn Ihr Unternehmen mehrere Customer Insights-Umgebungen in der gleichen Organisation unterhält, können Sie **switchinstance** eingeben, um zu wählen, mit welcher Umgebung Sie den Bot verbinden wollen.</span><span class="sxs-lookup"><span data-stu-id="7ebfc-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="7ebfc-127">Eingeben von **Hilfe**, um eine Liste der verfügbaren Befehle für den Bot anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7ebfc-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]