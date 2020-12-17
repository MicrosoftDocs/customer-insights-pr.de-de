---
title: Customer Insights-Daten nach Dynamics 365 Sales exportieren
description: Erfahren Sie, wie Sie die Verbindung zu Dynamics 365 Sales konfigurieren.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643817"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="95c28-103">Connector für Dynamics 365 Sales (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="95c28-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="95c28-104">Verwenden Sie Ihre Kundendaten, um Marketinglisten zu erstellen, Workflows zu verfolgen und Werbeaktionen mit Dynamics 365 Sales zu senden.</span><span class="sxs-lookup"><span data-stu-id="95c28-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="95c28-105">Voraussetzung</span><span class="sxs-lookup"><span data-stu-id="95c28-105">Prerequisite</span></span>

<span data-ttu-id="95c28-106">Kontaktdatensätze [aus Dynamics 365 Sales übernommen mit Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="95c28-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="95c28-107">Konfigurieren Sie den Connector für Vertrieb</span><span class="sxs-lookup"><span data-stu-id="95c28-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="95c28-108">Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Ziele exportieren**.</span><span class="sxs-lookup"><span data-stu-id="95c28-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="95c28-109">Unter **Dynamics 365 Sales**, wählen Sie **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="95c28-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="95c28-110">Geben Sie Ihrem Exportziel einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="95c28-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="95c28-111">Geben Sie die Vertriebs URL Ihrer Organisation im Feld **Server-Adresse** ein.</span><span class="sxs-lookup"><span data-stu-id="95c28-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="95c28-112">In dem Abschnitt **Serveradministratorkonto** wählen Sie **Anmeldung** und ein Dynamics 365 Sales Konto.</span><span class="sxs-lookup"><span data-stu-id="95c28-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="95c28-113">Ordnen Sie ein Kunden-ID-Feld der Dynamics 365 Kontakt-ID zu.</span><span class="sxs-lookup"><span data-stu-id="95c28-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="95c28-114">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="95c28-114">Select **Next**.</span></span>

1. <span data-ttu-id="95c28-115">Wählen Sie ein oder mehrere Segmente.</span><span class="sxs-lookup"><span data-stu-id="95c28-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="95c28-116">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="95c28-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="95c28-117">Exportieren der Daten</span><span class="sxs-lookup"><span data-stu-id="95c28-117">Export the data</span></span>

<span data-ttu-id="95c28-118">Sie könenn [Daten nach Bedarf exportieren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="95c28-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="95c28-119">Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="95c28-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
