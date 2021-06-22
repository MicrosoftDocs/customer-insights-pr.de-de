---
title: Geteilte Aufgaben für Vorhersageszenarien
description: Erfahren Sie, wie Sie Vorhersagen verwalten, Fehler beheben und verfeinern.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095710"
---
# <a name="manage-predictions"></a><span data-ttu-id="5c6fe-103">Verwalten von Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="5c6fe-103">Manage predictions</span></span>

<span data-ttu-id="5c6fe-104">In diesem Artikel werden einige Aufgaben behandelt, die die meisten Vorhersageszenarien teilen.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="5c6fe-105">Fehlersuche bei einer fehlgeschlagenen Vorhersage</span><span class="sxs-lookup"><span data-stu-id="5c6fe-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="5c6fe-106">Gehen Sie zu **Intelligenz** > **Vorhersagen** und wählen Sie die Registerkarte **Meine Vorhersagen**.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="5c6fe-107">Wählen Sie die vertikalen Auslassungspunkte neben der Vorhersage, für die Sie Fehlerprotokolle anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="5c6fe-108">Wählen Sie **Logs**.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-108">Select **Logs**.</span></span>

1. <span data-ttu-id="5c6fe-109">Überprüfen Sie alle Fehler.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-109">Review all the errors.</span></span> <span data-ttu-id="5c6fe-110">Es gibt verschiedene Arten von Fehlern, die auftreten können, und sie beschreiben, welcher Zustand den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="5c6fe-111">Beispielsweise wird ein Fehler, für den nicht genügend Daten zur genauen Vorhersage vorhanden sind, in der Regel dadurch behoben, dass zusätzliche Daten in Customer Insights geladen werden.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="5c6fe-112">Eingabedaten-Nutzungsbericht</span><span class="sxs-lookup"><span data-stu-id="5c6fe-112">Input data usability report</span></span>

<span data-ttu-id="5c6fe-113">Der Eingabedaten-Nutzungsbericht bietet eine konsolidierte Ansicht der Fehler und Warnungen, die Ihre sofort einsatzbereiten Vorhersagen generieren.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="5c6fe-114">Er gibt auch Empfehlungen zur Verbesserung der Modellleistung.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="5c6fe-115">Der Bericht ist verfügbar, nachdem ein Modell seinen Trainingsprozess abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="5c6fe-116">Er wird für jedes Modell separat erstellt, unabhängig davon, ob es erfolgreich abgeschlossen wurde oder nicht.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="5c6fe-117">Derzeit funktioniert diese Funktion nur für das Abwanderungsmodell für Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="5c6fe-118">Anzeigen des Eingabedaten-Nutzungsberichts</span><span class="sxs-lookup"><span data-stu-id="5c6fe-118">View the input data usability report</span></span>

<span data-ttu-id="5c6fe-119">Nachdem ein sofort einsatzbereites Modell seinen Trainingsschritt abgeschlossen hat, zeigen Sie den Bericht an:</span><span class="sxs-lookup"><span data-stu-id="5c6fe-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="5c6fe-120">Wählen Sie die Auslassungspunkte neben dem Modellnamen aus und wählen Sie dann **Eingabedaten-Nutzungsbericht** aus.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="5c6fe-121">Wählen Sie den Status eines Modells aus. Wählen Sie **Eingabedaten-Nutzungsbericht anzeigen** im Seitenbereich aus.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="5c6fe-122">Wählen Sie eines der Modelle in der Liste aus und wählen Sie dann **Eingabedaten-Nutzungsbericht** in der Befehlsleiste aus.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="5c6fe-123">Öffnen Sie Modellergebnisseite und wählen Sie **Eingabedaten-Nutzungsbericht** in der Befehlsleiste aus.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="5c6fe-124">Im Eingabedaten-Nutzungsbericht enthaltene Informationen</span><span class="sxs-lookup"><span data-stu-id="5c6fe-124">Information in the input data usability report</span></span>

<span data-ttu-id="5c6fe-125">Die folgenden Spalten im Bericht enthalten hilfreiche Informationen zur Verbesserung der Daten für das Modell.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Beispiel für einen Eingabedaten-Nutzungsbericht mit einer Tabelle mit Fehlern, Warnungen und Empfehlungen.":::

- <span data-ttu-id="5c6fe-127">Name: Ein beschreibender Name des Fehlers, der Warnung oder der Empfehlung.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="5c6fe-128">Schritt: Modellphase, Training oder Bewertung, auf die sich die Informationen beziehen.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="5c6fe-129">Status: Der Schweregrad der Information (Fehler, Warnung, Empfehlung).</span><span class="sxs-lookup"><span data-stu-id="5c6fe-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="5c6fe-130">Spaltenname: Eine Spalte in einer Entität, die geändert werden muss, um die Modellleistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="5c6fe-131">Entitätsname: Der Name der Entität, die geändert werden muss, um die Modellleistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="5c6fe-132">Details: Details zu Fehlern, Warnungen oder Empfehlungen.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="5c6fe-133">Aktualisieren einer Vorhersage</span><span class="sxs-lookup"><span data-stu-id="5c6fe-133">Refresh a prediction</span></span>

<span data-ttu-id="5c6fe-134">Vorhersagen werden automatisch zum gleichen [Zeitpunkt aktualisiert, zu dem Ihre Daten aktualisiert werden](system.md#schedule-tab), wie in den Einstellungen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="5c6fe-135">Sie können sie auch manuell aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="5c6fe-136">Gehen Sie zu **Intelligenz** > **Vorhersagen** und wählen Sie die Registerkarte **Meine Vorhersagen**.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="5c6fe-137">Wählen Sie die vertikalen Auslassungspunkte neben der Vorhersage, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="5c6fe-138">Wählen Sie **Aktualisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="5c6fe-139">Löschen einer Vorhersage</span><span class="sxs-lookup"><span data-stu-id="5c6fe-139">Delete a prediction</span></span>

<span data-ttu-id="5c6fe-140">Das Löschen einer Vorhersage entfernt auch deren Ausgabe-Entität.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="5c6fe-141">Gehen Sie zu **Intelligenz** > **Vorhersagen** und wählen Sie die Registerkarte **Meine Vorhersagen**.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="5c6fe-142">Wählen Sie die vertikalen Auslassungspunkte neben der Vorhersage, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="5c6fe-143">Klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="5c6fe-143">Select **Delete**.</span></span>
