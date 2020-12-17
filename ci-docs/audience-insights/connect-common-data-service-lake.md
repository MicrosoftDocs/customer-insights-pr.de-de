---
title: Verbindung zu Entitäten im verwalteten Common Data Service Lake
description: Importieren Sie Daten aus einem verwalteten Common Data Service-Data Lake.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643397"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="a9b33-103">Verbindung zu Daten in einem Common Data Service verwalteten Data Lake</span><span class="sxs-lookup"><span data-stu-id="a9b33-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a9b33-104">Dieser Artikel enthält Informationen darüber, wie vorhandene Dynamics 365-Kunden schnell eine Verbindung zu ihren Analyseentitäten im verwalteten Common Data Service-Lake herstellen können.</span><span class="sxs-lookup"><span data-stu-id="a9b33-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="a9b33-105">Sie müssen ein Administrator in der Common Data Service-Organisation sein, um fortzufahren und die Liste der im verwalteten Lake verfügbaren Entitäten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a9b33-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="a9b33-106">Wichtige Überlegungen</span><span class="sxs-lookup"><span data-stu-id="a9b33-106">Important considerations</span></span>

<span data-ttu-id="a9b33-107">In Online-Diensten gespeicherte Daten, wie z.B. Azure Data Lake Storage, können an einem anderen Ort gespeichert werden als dort, wo die Daten verarbeitet oder in Dynamics 365 Customer Insights gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="a9b33-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="a9b33-108"> Durch das Importieren von oder Verbinden mit Daten, die in Online-Diensten gespeichert sind, erklären Sie sich damit einverstanden, dass Daten an das Microsoft Trust Center übertragen und dort mit Dynamics 365 Customer Insights gespeichert werden können. [Lernen Sie mehr im Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="a9b33-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="a9b33-109">Verbindung zu einem Common Data Service verwalteten Lake</span><span class="sxs-lookup"><span data-stu-id="a9b33-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="a9b33-110">Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.</span><span class="sxs-lookup"><span data-stu-id="a9b33-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="a9b33-111">Wählen Sie **Datenquelle hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a9b33-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="a9b33-112">Wählen Sie **Verbinden mit Common Data Service** und wählen Sie **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a9b33-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="a9b33-113">Geben Sie einen **Namen** für das Team ein und wählen Sie **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a9b33-113">Enter a **Name** for the data source and select **Next**.</span></span>

5. <span data-ttu-id="a9b33-114">Stellen Sie die **Serveradresse** für Ihre Common Data Service Organisation bereit und wählen Sie **Anmeldung**.</span><span class="sxs-lookup"><span data-stu-id="a9b33-114">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a9b33-115">![Dialogfeld zum Eingeben der Common Data Service Serveradresse](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="a9b33-115">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="a9b33-116">Wählen Sie die Entitäten, die Sie aufnehmen wollen, aus der verfügbaren Liste.</span><span class="sxs-lookup"><span data-stu-id="a9b33-116">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="a9b33-117">Wenn einige Entitäten bereits ausgewählt sind, können sie von anderen Dynamics 365 Anwendungen verwendet werden (z. B. Dynamics 365 Sales Insights oder Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="a9b33-117">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="a9b33-118">Die Auswahl kann nicht mehr geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a9b33-118">You can't change the selection.</span></span> <span data-ttu-id="a9b33-119">Diese Entitäten sind verfügbar, sobald die Datenquelle erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a9b33-119">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a9b33-120">![Dialogfeld mit einer Liste der Entitäten in der Common Data Service Org](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="a9b33-120">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="a9b33-121">Speichern Sie Ihre Auswahl, um die Synchronisierung der ausgewählten Objekte mit dem Common Data Service verwalteten Lake zu starten.</span><span class="sxs-lookup"><span data-stu-id="a9b33-121">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="a9b33-122">Die neu hinzugefügte Verbindung finden Sie auf der Seite **Datenquellen**.</span><span class="sxs-lookup"><span data-stu-id="a9b33-122">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="a9b33-123">Es wird zur Aktualisierung in die Warteschlange gestellt und zeigt die Anzahl der Entitäten als 0 an, bis alle Entitäten synchronisiert sind.</span><span class="sxs-lookup"><span data-stu-id="a9b33-123">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="a9b33-124">Nur eine Datenquelle einer Umgebung kann gleichzeitig denselben Common Data Service verwalteten Lake verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9b33-124">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="a9b33-125">Bearbeiten von einer Common Data Service verwalteten Datenquelle</span><span class="sxs-lookup"><span data-stu-id="a9b33-125">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="a9b33-126">Sie bearbeiten die Entitätsauswahl erst, nachdem Sie die Datenquelle erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a9b33-126">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="a9b33-127">Zum Beispiel, wenn zusätzliche Entitäten zu Common Data Service hinzugefügt wurden, und Sie sie auch importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a9b33-127">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="a9b33-128">Stellen Sie eine Verbindung zu einer anderen Common Data Service her, [Eine neue Datenquelle erstelle](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="a9b33-128">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="a9b33-129">Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.</span><span class="sxs-lookup"><span data-stu-id="a9b33-129">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="a9b33-130">Wählen Sie neben der Datenquelle, die Sie aktualisieren möchten, die Auslassungspunkte aus.</span><span class="sxs-lookup"><span data-stu-id="a9b33-130">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="a9b33-131">Wählen Sie eine Option **Bearbeiten** in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="a9b33-131">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="a9b33-132">Wählen Sie zusätzliche Entitäten aus der verfügbaren Liste der Entitäten aus und wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a9b33-132">Select additional entities from the available list of entities and select **Save**.</span></span>
