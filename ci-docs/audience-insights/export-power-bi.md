---
title: Power BI-Connector
description: Lernen Sie, wie der Dynamics 365 Customer Insights-Connector in Power BI verwendet wird.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405755"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="4ade3-103">Connector für Power BI (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="4ade3-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="4ade3-104">Erstellen Sie Visualisierungen für Ihre Daten mit dem Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="4ade3-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="4ade3-105">Generieren Sie zusätzliche Erkenntnisse und erstellen Sie Berichte mit Ihren einheitlichen Kundendaten.</span><span class="sxs-lookup"><span data-stu-id="4ade3-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4ade3-106">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4ade3-106">Prerequisites</span></span>

- <span data-ttu-id="4ade3-107">Sie haben einheitliche Kundenprofile.</span><span class="sxs-lookup"><span data-stu-id="4ade3-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="4ade3-108">Die neueste Version von [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) ist auf Ihrem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="4ade3-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="4ade3-109">[Weitere Informationen zu Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="4ade3-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="4ade3-110">Konfigurieren des Connector für Power BI</span><span class="sxs-lookup"><span data-stu-id="4ade3-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="4ade3-111">Wählen Sie in Power BI Desktop die Option **Datei** > **Daten empfangen** aus.</span><span class="sxs-lookup"><span data-stu-id="4ade3-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="4ade3-112">Wählen Sie **Mehr anzeigen** aus und suchen Sie nach **Dynamics 365 Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="4ade3-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="4ade3-113">Wählen Sie das Ergebnis und dann **Verbinden** aus.</span><span class="sxs-lookup"><span data-stu-id="4ade3-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="4ade3-114">**Melden Sie sich** mit demselben Organisationskonto an, das Sie für Customer Insights verwenden, und wählen Sie **Verbinden** aus.</span><span class="sxs-lookup"><span data-stu-id="4ade3-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="4ade3-115">Das Konto, das Sie in diesem Schritt angeben, wird zum Abrufen von Daten aus Customer Insights verwendet und muss nicht mit dem Konto identisch sein, bei dem Sie in Power BI angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="4ade3-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="4ade3-116">Um das Konto zurückzusetzen, das für den Datenabruf verwendet wird, öffnen Sie Power BI und gehen Sie zu **Datei** > **Optionen** > **Einstellungen** > **Datenquelleneinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="4ade3-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="4ade3-117">Wählen Sie in der Liste der Datenquellen **Dynamics 365 Customer Insights-Anmeldung** und dann **Berechtigungen löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="4ade3-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="4ade3-118">Im Dialogfeld **Navigator**.</span><span class="sxs-lookup"><span data-stu-id="4ade3-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="4ade3-119">sehen Sie die Liste aller Umgebungen, auf die Sie Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="4ade3-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="4ade3-120">Erweitern Sie eine Umgebung und öffnen Sie einen der Ordner (Entitäten, Kennzahlen, Segmente, Anreicherungen).</span><span class="sxs-lookup"><span data-stu-id="4ade3-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="4ade3-121">Öffnen Sie zum Beispiel den Ordner **Entitäten**, um alle Entitäten anzuzeigen, die Sie importieren können.</span><span class="sxs-lookup"><span data-stu-id="4ade3-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="4ade3-122">![Power BI Connector-Navigator](media/power-bi-navigator.png "Power BI Connector-Navigator")</span><span class="sxs-lookup"><span data-stu-id="4ade3-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="4ade3-123">Aktivieren Sie die Kontrollkästchen neben den Entitäten, die Sie einschließen möchten, und wählen Sie **Laden** aus.</span><span class="sxs-lookup"><span data-stu-id="4ade3-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="4ade3-124">Sie können mehrere Entitäten aus mehreren Umgebungen auswählen.</span><span class="sxs-lookup"><span data-stu-id="4ade3-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="4ade3-125">Sie sehen ein Dialogfeld zum Laden, während Ihre Entitäten geladen werden.</span><span class="sxs-lookup"><span data-stu-id="4ade3-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="4ade3-126">Sobald alle Ihre ausgewählten Entitäten geladen sind, können Sie die Funktionalitäten von Power BI verwenden, um die Daten zu visualisieren.</span><span class="sxs-lookup"><span data-stu-id="4ade3-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="4ade3-127">Große Datasets</span><span class="sxs-lookup"><span data-stu-id="4ade3-127">Large data sets</span></span>

<span data-ttu-id="4ade3-128">Der Customer Insights-Konnektor für Power BI wurde für Datasets entwickelt, die bis zu 1 Million Kundenprofile enthalten.</span><span class="sxs-lookup"><span data-stu-id="4ade3-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="4ade3-129">Das Importieren größerer Datenmengen funktioniert möglicherweise, dauert jedoch lange.</span><span class="sxs-lookup"><span data-stu-id="4ade3-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="4ade3-130">Außerdem kann es aufgrund von Power BI-Einschränkungen zu einer Zeitüberschreitung kommen.</span><span class="sxs-lookup"><span data-stu-id="4ade3-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="4ade3-131">Weitere Informationen finden Sie unter [Power BI: Empfehlungen für große Datasets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="4ade3-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="4ade3-132">Arbeiten mit einer Teilmenge von Daten</span><span class="sxs-lookup"><span data-stu-id="4ade3-132">Work with a subset of data</span></span>

<span data-ttu-id="4ade3-133">Erwägen Sie die Arbeit mit einer Teilmenge Ihrer Daten.</span><span class="sxs-lookup"><span data-stu-id="4ade3-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="4ade3-134">Sie können z. B. [Segmente](segments.md) erstellen, anstatt alle Kundendatensätze nach Power BI zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="4ade3-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
