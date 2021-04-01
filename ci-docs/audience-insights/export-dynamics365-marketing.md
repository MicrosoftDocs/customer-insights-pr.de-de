---
title: Customer Insights-Daten nach Dynamics 365 Marketing exportieren
description: Erfahren Sie, wie Sie die Verbindung zu Dynamics 365 Marketing konfigurieren.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597602"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="90b7c-103">Connector für Dynamics 365 Marketing (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="90b7c-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="90b7c-104">Verwenden Sie [Segmente](segments.md), um mit Dynamics 365 Marketing Kampagnen zu erstellen und bestimmte Kundengruppen zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="90b7c-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="90b7c-105">Weitere Informationen finden Sie unter [Segmente ab Dynamics 365 Customer Insights mit Dynamics 365 Marketing verwenden](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="90b7c-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="90b7c-106">Voraussetzung</span><span class="sxs-lookup"><span data-stu-id="90b7c-106">Prerequisite</span></span>

- <span data-ttu-id="90b7c-107">Kontaktdatensätze müssen in Dynamics 365 Marketing vorhanden sein, bevor Sie ein Segment von Customer Insights nach Marketing exportieren können.</span><span class="sxs-lookup"><span data-stu-id="90b7c-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="90b7c-108">Lesen Sie mehr darüber, wie Sie Kontakte in [Dynamics 365 Marketing mit Common Data Services](connect-power-query.md) erfassen können.</span><span class="sxs-lookup"><span data-stu-id="90b7c-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="90b7c-109">Durch das Exportieren von Segmenten aus Zielgruppenerkenntnissen nach Marketing werden keine neuen Kontaktdatensätze in den Marketinginstanzen erstellt.</span><span class="sxs-lookup"><span data-stu-id="90b7c-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="90b7c-110">Die Kontaktdatensätze von Marketing müssen in Zielgruppenerkenntnissen aufgenommen und als Datenquelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="90b7c-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="90b7c-111">Sie müssen auch in die einheitliche Kundenentität aufgenommen werden, um Kunden-IDs Kontakt-IDs zuzuordnen, bevor Segmente exportiert werden können.</span><span class="sxs-lookup"><span data-stu-id="90b7c-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="90b7c-112">Konfigurieren Sie den Connector für Marketing</span><span class="sxs-lookup"><span data-stu-id="90b7c-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="90b7c-113">Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Ziele exportieren**.</span><span class="sxs-lookup"><span data-stu-id="90b7c-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="90b7c-114">Unter **Dynamics 365 Marketing**, wählen Sie **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="90b7c-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="90b7c-115">Geben Sie Ihrem Exportziel einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="90b7c-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="90b7c-116">Geben Sie die Marketing URL Ihrer Organisation im Feld **Server-Adresse** ein.</span><span class="sxs-lookup"><span data-stu-id="90b7c-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="90b7c-117">In dem Abschnitt **Serveradministratorkonto** wählen Sie **Anmeldung** und ein Dynamics 365 Marketing-Konto.</span><span class="sxs-lookup"><span data-stu-id="90b7c-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="90b7c-118">Ordnen Sie ein Kunden-ID-Feld der Dynamics 365 Kontakt-ID zu.</span><span class="sxs-lookup"><span data-stu-id="90b7c-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="90b7c-119">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="90b7c-119">Select **Next**.</span></span>

1. <span data-ttu-id="90b7c-120">Wählen Sie ein oder mehrere Segmente.</span><span class="sxs-lookup"><span data-stu-id="90b7c-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="90b7c-121">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="90b7c-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="90b7c-122">Exportieren der Daten</span><span class="sxs-lookup"><span data-stu-id="90b7c-122">Export the data</span></span>

<span data-ttu-id="90b7c-123">Sie könenn [Daten nach Bedarf exportieren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="90b7c-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="90b7c-124">Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="90b7c-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]