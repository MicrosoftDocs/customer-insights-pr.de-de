---
title: Customer Insights-Daten nach Dynamics 365 Marketing exportieren
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu Dynamics 365 Marketing exportieren.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 195bee789dc043057b47c12c8d93e6d53edb59cd
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976799"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="10d08-103">Segmente in Dynamics 365 Marketing verwenden (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="10d08-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="10d08-104">Verwenden Sie [Segmente](segments.md), um mit Dynamics 365 Marketing Kampagnen zu erstellen und bestimmte Kundengruppen zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="10d08-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="10d08-105">Weitere Informationen finden Sie unter [Segmente ab Dynamics 365 Customer Insights mit Dynamics 365 Marketing verwenden](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="10d08-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="10d08-106">Voraussetzungen für die Verbindung</span><span class="sxs-lookup"><span data-stu-id="10d08-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="10d08-107">Kontaktdatensätze müssen in Dynamics 365 Marketing vorhanden sein, bevor Sie ein Segment von Customer Insights nach Marketing exportieren können.</span><span class="sxs-lookup"><span data-stu-id="10d08-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="10d08-108">Lesen Sie mehr darüber, wie Sie Kontakte in [Dynamics 365 Marketing mit Common Data Services](connect-power-query.md) erfassen können.</span><span class="sxs-lookup"><span data-stu-id="10d08-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="10d08-109">Durch das Exportieren von Segmenten aus Zielgruppenerkenntnissen nach Marketing werden keine neuen Kontaktdatensätze in den Marketinginstanzen erstellt.</span><span class="sxs-lookup"><span data-stu-id="10d08-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="10d08-110">Die Kontaktdatensätze von Marketing müssen in Zielgruppenerkenntnissen aufgenommen und als Datenquelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="10d08-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="10d08-111">Sie müssen auch in die einheitliche Kundenentität aufgenommen werden, um Kunden-IDs Kontakt-IDs zuzuordnen, bevor Segmente exportiert werden können.</span><span class="sxs-lookup"><span data-stu-id="10d08-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="10d08-112">Richten Sie die Verbindung mit Marketing ein</span><span class="sxs-lookup"><span data-stu-id="10d08-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="10d08-113">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="10d08-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="10d08-114">Wählen Sie **Verbindung hinzufügen** und dann **Dynamics 365 Marketing** aus, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="10d08-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="10d08-115">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="10d08-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="10d08-116">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="10d08-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="10d08-117">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="10d08-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="10d08-118">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="10d08-118">Choose who can use this connection.</span></span> <span data-ttu-id="10d08-119">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="10d08-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="10d08-120">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="10d08-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="10d08-121">Geben Sie die Marketing URL Ihrer Organisation im Feld **Server-Adresse** ein.</span><span class="sxs-lookup"><span data-stu-id="10d08-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="10d08-122">In dem Abschnitt **Serveradministratorkonto** wählen Sie **Anmeldung** und ein Dynamics 365 Marketing-Konto.</span><span class="sxs-lookup"><span data-stu-id="10d08-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="10d08-123">Ordnen Sie ein Kunden-ID-Feld der Dynamics 365 Kontakt-ID zu.</span><span class="sxs-lookup"><span data-stu-id="10d08-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="10d08-124">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="10d08-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="10d08-125">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="10d08-125">Configure an export</span></span>

<span data-ttu-id="10d08-126">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="10d08-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="10d08-127">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="10d08-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="10d08-128">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="10d08-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="10d08-129">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="10d08-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="10d08-130">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Dynamics 365 Marketing-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="10d08-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="10d08-131">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="10d08-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="10d08-132">Wählen Sie ein oder mehrere Segmente.</span><span class="sxs-lookup"><span data-stu-id="10d08-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="10d08-133">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="10d08-133">Select **Save**.</span></span>

<span data-ttu-id="10d08-134">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="10d08-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="10d08-135">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="10d08-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="10d08-136">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="10d08-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
