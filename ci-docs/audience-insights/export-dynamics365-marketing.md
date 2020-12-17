---
title: Customer Insights-Daten nach Dynamics 365 Marketing exportieren
description: Erfahren Sie, wie Sie die Verbindung zu Dynamics 365 Marketing konfigurieren.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643772"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="19783-103">Connector für Dynamics 365 Marketing (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="19783-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="19783-104">Verwenden Sie [Segmente](segments.md), um mit Dynamics 365 Marketing Kampagnen zu erstellen und bestimmte Kundengruppen zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="19783-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="19783-105">Weitere Informationen finden Sie unter [Segmente ab Dynamics 365 Customer Insights mit Dynamics 365 Marketing verwenden](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="19783-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="19783-106">Voraussetzung</span><span class="sxs-lookup"><span data-stu-id="19783-106">Prerequisite</span></span>

<span data-ttu-id="19783-107">Kontaktdatensätze [aus Dynamics 365 Marketing übernommen mit Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="19783-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="19783-108">Konfigurieren Sie den Connector für Marketing</span><span class="sxs-lookup"><span data-stu-id="19783-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="19783-109">Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Ziele exportieren**.</span><span class="sxs-lookup"><span data-stu-id="19783-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="19783-110">Unter **Dynamics 365 Marketing**, wählen Sie **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="19783-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="19783-111">Geben Sie Ihrem Exportziel einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="19783-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="19783-112">Geben Sie die Marketing URL Ihrer Organisation im Feld **Server-Adresse** ein.</span><span class="sxs-lookup"><span data-stu-id="19783-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="19783-113">In dem Abschnitt **Serveradministratorkonto** wählen Sie **Anmeldung** und ein Dynamics 365 Marketing-Konto.</span><span class="sxs-lookup"><span data-stu-id="19783-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="19783-114">Ordnen Sie ein Kunden-ID-Feld der Dynamics 365 Kontakt-ID zu.</span><span class="sxs-lookup"><span data-stu-id="19783-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="19783-115">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="19783-115">Select **Next**.</span></span>

1. <span data-ttu-id="19783-116">Wählen Sie ein oder mehrere Segmente.</span><span class="sxs-lookup"><span data-stu-id="19783-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="19783-117">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="19783-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="19783-118">Exportieren der Daten</span><span class="sxs-lookup"><span data-stu-id="19783-118">Export the data</span></span>

<span data-ttu-id="19783-119">Sie könenn [Daten nach Bedarf exportieren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="19783-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="19783-120">Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="19783-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
