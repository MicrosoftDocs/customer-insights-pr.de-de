---
title: Customer Insights-Daten nach Dynamics 365 Sales exportieren
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu Dynamics 365 Sales exportieren.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc1a05ba4d21d96aa1a9724d158687bbb86949b6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759590"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="0d45f-103">Segmente in Dynamics 365 Sales verwenden (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="0d45f-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0d45f-104">Verwenden Sie Ihre Kundendaten, um Marketinglisten zu erstellen, Workflows zu verfolgen und Werbeaktionen mit Dynamics 365 Sales zu senden.</span><span class="sxs-lookup"><span data-stu-id="0d45f-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="0d45f-105">Voraussetzungen für die Verbindung</span><span class="sxs-lookup"><span data-stu-id="0d45f-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="0d45f-106">Kontaktdatensätze müssen in Dynamics 365 Sales vorhanden sein, bevor Sie ein Segment von Customer Insights nach Sales exportieren können.</span><span class="sxs-lookup"><span data-stu-id="0d45f-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="0d45f-107">Lesen Sie mehr darüber, wie Sie Kontakte in [Dynamics 365 Sales mit Common Data Services](connect-power-query.md) erfassen können.</span><span class="sxs-lookup"><span data-stu-id="0d45f-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="0d45f-108">Durch das Exportieren von Segmenten aus Zielgruppenerkenntnissen nach Sales werden keine neuen Kontaktdatensätze in den Sales-Instanzen erstellt.</span><span class="sxs-lookup"><span data-stu-id="0d45f-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="0d45f-109">Die Kontaktdatensätze von Sales müssen in Zielgruppenerkenntnissen aufgenommen und als Datenquelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0d45f-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="0d45f-110">Sie müssen auch in die einheitliche Kundenentität aufgenommen werden, um Kunden-IDs Kontakt-IDs zuzuordnen, bevor Segmente exportiert werden können.</span><span class="sxs-lookup"><span data-stu-id="0d45f-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="0d45f-111">Richten Sie die Verbindung mit Sales ein</span><span class="sxs-lookup"><span data-stu-id="0d45f-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="0d45f-112">Gehen Sie zu **Administrator** > **Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="0d45f-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0d45f-113">Wählen Sie **Verbindung hinzufügen** und dann **Dynamics 365 Sales** aus, um die Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0d45f-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="0d45f-114">Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**.</span><span class="sxs-lookup"><span data-stu-id="0d45f-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0d45f-115">Der Name und der Typ der Verbindung beschreiben die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="0d45f-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0d45f-116">Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.</span><span class="sxs-lookup"><span data-stu-id="0d45f-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0d45f-117">Wählen Sie aus, wer diese Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="0d45f-117">Choose who can use this connection.</span></span> <span data-ttu-id="0d45f-118">Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren.</span><span class="sxs-lookup"><span data-stu-id="0d45f-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0d45f-119">Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0d45f-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0d45f-120">Geben Sie die Vertriebs URL Ihrer Organisation im Feld **Server-Adresse** ein.</span><span class="sxs-lookup"><span data-stu-id="0d45f-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="0d45f-121">In dem Abschnitt **Serveradministratorkonto** wählen Sie **Anmeldung** und ein Dynamics 365 Sales Konto.</span><span class="sxs-lookup"><span data-stu-id="0d45f-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="0d45f-122">Ordnen Sie ein Kunden-ID-Feld der Dynamics 365 Kontakt-ID zu.</span><span class="sxs-lookup"><span data-stu-id="0d45f-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="0d45f-123">Wählen Sie zum Abschließen der Verbindung **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="0d45f-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="0d45f-124">Konfigurieren Sie einen Export</span><span class="sxs-lookup"><span data-stu-id="0d45f-124">Configure an export</span></span>

<span data-ttu-id="0d45f-125">Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben.</span><span class="sxs-lookup"><span data-stu-id="0d45f-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0d45f-126">Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0d45f-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0d45f-127">Gehen Sie zu **Daten** > **Exporte**.</span><span class="sxs-lookup"><span data-stu-id="0d45f-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0d45f-128">Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0d45f-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0d45f-129">Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Dynamics 365 Sales-Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="0d45f-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="0d45f-130">Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="0d45f-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0d45f-131">Wählen Sie ein oder mehrere Segmente.</span><span class="sxs-lookup"><span data-stu-id="0d45f-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="0d45f-132">Wählen Sie **Speichern** aus</span><span class="sxs-lookup"><span data-stu-id="0d45f-132">Select **Save**</span></span>

<span data-ttu-id="0d45f-133">Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0d45f-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0d45f-134">Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0d45f-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0d45f-135">Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0d45f-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
