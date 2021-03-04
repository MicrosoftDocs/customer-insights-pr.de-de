---
title: Customer Insights-Daten nach Dynamics 365 Sales exportieren
description: Erfahren Sie, wie Sie die Verbindung zu Dynamics 365 Sales konfigurieren.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269007"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="2654e-103">Connector für Dynamics 365 Sales (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="2654e-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="2654e-104">Verwenden Sie Ihre Kundendaten, um Marketinglisten zu erstellen, Workflows zu verfolgen und Werbeaktionen mit Dynamics 365 Sales zu senden.</span><span class="sxs-lookup"><span data-stu-id="2654e-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="2654e-105">Voraussetzung</span><span class="sxs-lookup"><span data-stu-id="2654e-105">Prerequisite</span></span>

1. <span data-ttu-id="2654e-106">Kontaktdatensätze müssen in Dynamics 365 Sales vorhanden sein, bevor Sie ein Segment von Customer Insights nach Sales exportieren können.</span><span class="sxs-lookup"><span data-stu-id="2654e-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="2654e-107">Lesen Sie mehr darüber, wie Sie Kontakte in [Dynamics 365 Sales mit Common Data Services](connect-power-query.md) erfassen können.</span><span class="sxs-lookup"><span data-stu-id="2654e-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="2654e-108">Durch das Exportieren von Segmenten aus Zielgruppenerkenntnissen nach Sales werden keine neuen Kontaktdatensätze in den Sales-Instanzen erstellt.</span><span class="sxs-lookup"><span data-stu-id="2654e-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="2654e-109">Die Kontaktdatensätze von Sales müssen in Zielgruppenerkenntnissen aufgenommen und als Datenquelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2654e-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="2654e-110">Sie müssen auch in die einheitliche Kundenentität aufgenommen werden, um Kunden-IDs Kontakt-IDs zuzuordnen, bevor Segmente exportiert werden können.</span><span class="sxs-lookup"><span data-stu-id="2654e-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="2654e-111">Konfigurieren Sie den Connector für Vertrieb</span><span class="sxs-lookup"><span data-stu-id="2654e-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="2654e-112">Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Ziele exportieren**.</span><span class="sxs-lookup"><span data-stu-id="2654e-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="2654e-113">Unter **Dynamics 365 Sales**, wählen Sie **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="2654e-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="2654e-114">Geben Sie Ihrem Exportziel einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="2654e-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="2654e-115">Geben Sie die Vertriebs URL Ihrer Organisation im Feld **Server-Adresse** ein.</span><span class="sxs-lookup"><span data-stu-id="2654e-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="2654e-116">In dem Abschnitt **Serveradministratorkonto** wählen Sie **Anmeldung** und ein Dynamics 365 Sales Konto.</span><span class="sxs-lookup"><span data-stu-id="2654e-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="2654e-117">Ordnen Sie ein Kunden-ID-Feld der Dynamics 365 Kontakt-ID zu.</span><span class="sxs-lookup"><span data-stu-id="2654e-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="2654e-118">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2654e-118">Select **Next**.</span></span>

1. <span data-ttu-id="2654e-119">Wählen Sie ein oder mehrere Segmente.</span><span class="sxs-lookup"><span data-stu-id="2654e-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="2654e-120">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="2654e-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="2654e-121">Exportieren der Daten</span><span class="sxs-lookup"><span data-stu-id="2654e-121">Export the data</span></span>

<span data-ttu-id="2654e-122">Sie könenn [Daten nach Bedarf exportieren](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="2654e-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="2654e-123">Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="2654e-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]