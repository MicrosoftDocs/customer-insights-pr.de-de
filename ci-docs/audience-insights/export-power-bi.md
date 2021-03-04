---
title: Power BI-Connector
description: Lernen Sie, wie der Dynamics 365 Customer Insights-Connector in Power BI verwendet wird.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477087"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="161c2-103">Connector für Power BI (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="161c2-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="161c2-104">Erstellen Sie Visualisierungen für Ihre Daten mit dem Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="161c2-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="161c2-105">Generieren Sie zusätzliche Erkenntnisse und erstellen Sie Berichte mit Ihren einheitlichen Kundendaten.</span><span class="sxs-lookup"><span data-stu-id="161c2-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="161c2-106">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="161c2-106">Prerequisites</span></span>

- <span data-ttu-id="161c2-107">Sie haben einheitliche Kundenprofile.</span><span class="sxs-lookup"><span data-stu-id="161c2-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="161c2-108">Die neueste Version von [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) ist auf Ihrem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="161c2-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="161c2-109">[Weitere Informationen zu Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="161c2-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="161c2-110">Konfigurieren des Connector für Power BI</span><span class="sxs-lookup"><span data-stu-id="161c2-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="161c2-111">Wählen Sie in Power BI Desktop die Option **Datei** > **Daten empfangen** aus.</span><span class="sxs-lookup"><span data-stu-id="161c2-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="161c2-112">Wählen Sie **Mehr anzeigen** aus und suchen Sie nach **Dynamics 365 Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="161c2-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="161c2-113">Wählen Sie **Verbinden** aus.</span><span class="sxs-lookup"><span data-stu-id="161c2-113">Select **Connect**.</span></span>

1. <span data-ttu-id="161c2-114">**Melden Sie sich** mit demselben Organisationskonto an, das Sie für Customer Insights verwenden, und wählen Sie **Verbinden** aus.</span><span class="sxs-lookup"><span data-stu-id="161c2-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="161c2-115">Das Konto, das Sie in diesem Schritt angeben, wird zum Abrufen von Daten aus Customer Insights verwendet und muss nicht mit dem Konto identisch sein, bei dem Sie in Power BI angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="161c2-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="161c2-116">Um das Konto zurückzusetzen, das für den Datenabruf verwendet wird, öffnen Sie Power BI und gehen Sie zu **Datei** > **Optionen** > **Einstellungen** > **Datenquelleneinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="161c2-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="161c2-117">Wählen Sie in der Liste der Datenquellen **Dynamics 365 Customer Insights-Anmeldung** und dann **Berechtigungen löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="161c2-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="161c2-118">Im Dialogfeld **Navigator**.</span><span class="sxs-lookup"><span data-stu-id="161c2-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="161c2-119">sehen Sie die Liste aller Umgebungen, auf die Sie Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="161c2-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="161c2-120">Erweitern Sie eine Umgebung und öffnen Sie einen der Ordner (Entitäten, Kennzahlen, Segmente, Anreicherungen).</span><span class="sxs-lookup"><span data-stu-id="161c2-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="161c2-121">Öffnen Sie zum Beispiel den Ordner **Entitäten**, um alle Entitäten anzuzeigen, die Sie importieren können.</span><span class="sxs-lookup"><span data-stu-id="161c2-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="161c2-122">![Power BI Connector-Navigator](media/power-bi-navigator.png "Power BI Connector-Navigator")</span><span class="sxs-lookup"><span data-stu-id="161c2-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="161c2-123">Aktivieren Sie die Kontrollkästchen neben den Entitäten, die Sie einschließen möchten, und wählen Sie **Laden** aus.</span><span class="sxs-lookup"><span data-stu-id="161c2-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="161c2-124">Sie können mehrere Entitäten aus mehreren Umgebungen auswählen.</span><span class="sxs-lookup"><span data-stu-id="161c2-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="161c2-125">Sie sehen ein Dialogfeld zum Laden, während Ihre Entitäten geladen werden.</span><span class="sxs-lookup"><span data-stu-id="161c2-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="161c2-126">Sobald alle Ihre ausgewählten Entitäten geladen sind, können Sie die Funktionalitäten von Power BI verwenden, um die Daten zu visualisieren.</span><span class="sxs-lookup"><span data-stu-id="161c2-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="161c2-127">Große Datasets</span><span class="sxs-lookup"><span data-stu-id="161c2-127">Large data sets</span></span>

<span data-ttu-id="161c2-128">Der Customer Insights-Konnektor für Power BI wurde für Datasets entwickelt, die bis zu 1 Million Kundenprofile enthalten.</span><span class="sxs-lookup"><span data-stu-id="161c2-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="161c2-129">Das Importieren größerer Datenmengen funktioniert möglicherweise, dauert jedoch lange.</span><span class="sxs-lookup"><span data-stu-id="161c2-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="161c2-130">Außerdem kann es aufgrund von Power BI-Einschränkungen zu einer Zeitüberschreitung kommen.</span><span class="sxs-lookup"><span data-stu-id="161c2-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="161c2-131">Weitere Informationen finden Sie unter [Power BI: Empfehlungen für große Datasets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="161c2-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="161c2-132">Arbeiten mit einer Teilmenge von Daten</span><span class="sxs-lookup"><span data-stu-id="161c2-132">Work with a subset of data</span></span>

<span data-ttu-id="161c2-133">Erwägen Sie die Arbeit mit einer Teilmenge Ihrer Daten.</span><span class="sxs-lookup"><span data-stu-id="161c2-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="161c2-134">Sie können z. B. [Segmente](segments.md) erstellen, anstatt alle Kundendatensätze nach Power BI zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="161c2-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="161c2-135">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="161c2-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="161c2-136">Die Customer Insights-Umgebung wird nicht in Power BI angezeigt</span><span class="sxs-lookup"><span data-stu-id="161c2-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="161c2-137">Umgebungen mit mehr als einer definierten [Beziehung](relationships.md) zwischen zwei identischen Entitäten in Zielgruppenerkenntnissen sind im Power BI-Konnektor nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="161c2-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="161c2-138">Sie können das duplizierte Beziehungen identifizieren und entfernen.</span><span class="sxs-lookup"><span data-stu-id="161c2-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="161c2-139">Gehen Sie in Zielgruppenerkenntnissen zu **Daten** > **Beziehungen** in der Umgebung, die in Power BI fehlt.</span><span class="sxs-lookup"><span data-stu-id="161c2-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="161c2-140">Identifizieren Sie duplizierte Beziehungen:</span><span class="sxs-lookup"><span data-stu-id="161c2-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="161c2-141">Überprüfen Sie, ob zwischen denselben beiden Entitäten mehr als eine Beziehung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="161c2-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="161c2-142">Überprüfen Sie, ob eine Beziehung zwischen zwei Entitäten erstellt wurde, die beide im Vereinigungsprozess enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="161c2-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="161c2-143">Zwischen allen am Vereinigungsprozess beteiligten Entitäten ist eine implizite Beziehung definiert.</span><span class="sxs-lookup"><span data-stu-id="161c2-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="161c2-144">Entfernen Sie alle identifizierten doppelten Beziehungen.</span><span class="sxs-lookup"><span data-stu-id="161c2-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="161c2-145">Versuchen Sie nach dem Entfernen des duplizierten Beziehungen, den Power BI-Konnektor wieder zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="161c2-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="161c2-146">Die Umgebung sollte jetzt verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="161c2-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

