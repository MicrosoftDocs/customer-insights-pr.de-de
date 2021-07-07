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
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315877"
---
# <a name="manage-predictions"></a><span data-ttu-id="e65c8-103">Verwalten von Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="e65c8-103">Manage predictions</span></span>

<span data-ttu-id="e65c8-104">In diesem Artikel werden einige Aufgaben behandelt, die die meisten Vorhersageszenarien teilen.</span><span class="sxs-lookup"><span data-stu-id="e65c8-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="e65c8-105">Fehlersuche bei einer fehlgeschlagenen Vorhersage</span><span class="sxs-lookup"><span data-stu-id="e65c8-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="e65c8-106">Gehen Sie zu **Intelligenz** > **Vorhersagen** und wählen Sie die Registerkarte **Meine Vorhersagen**.</span><span class="sxs-lookup"><span data-stu-id="e65c8-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="e65c8-107">Wählen Sie die vertikalen Auslassungspunkte neben der Vorhersage, für die Sie Fehlerprotokolle anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="e65c8-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="e65c8-108">Wählen Sie **Logs**.</span><span class="sxs-lookup"><span data-stu-id="e65c8-108">Select **Logs**.</span></span>

1. <span data-ttu-id="e65c8-109">Überprüfen Sie alle Fehler.</span><span class="sxs-lookup"><span data-stu-id="e65c8-109">Review all the errors.</span></span> <span data-ttu-id="e65c8-110">Es gibt verschiedene Arten von Fehlern, die auftreten können, und sie beschreiben, welcher Zustand den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="e65c8-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="e65c8-111">Beispielsweise wird ein Fehler, für den nicht genügend Daten zur genauen Vorhersage vorhanden sind, in der Regel dadurch behoben, dass zusätzliche Daten in Customer Insights geladen werden.</span><span class="sxs-lookup"><span data-stu-id="e65c8-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="e65c8-112">Eingabedaten-Nutzungsbericht</span><span class="sxs-lookup"><span data-stu-id="e65c8-112">Input data usability report</span></span>

<span data-ttu-id="e65c8-113">Der Eingabedaten-Nutzungsbericht bietet eine konsolidierte Ansicht der Fehler und Warnungen, die Ihre sofort einsatzbereiten Vorhersagen generieren.</span><span class="sxs-lookup"><span data-stu-id="e65c8-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="e65c8-114">Er gibt auch Empfehlungen zur Verbesserung der Modellleistung.</span><span class="sxs-lookup"><span data-stu-id="e65c8-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="e65c8-115">Der Bericht ist verfügbar, nachdem ein Modell seinen Trainingsprozess abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="e65c8-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="e65c8-116">Er wird für jedes Modell separat erstellt, unabhängig davon, ob es erfolgreich abgeschlossen wurde oder nicht.</span><span class="sxs-lookup"><span data-stu-id="e65c8-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="e65c8-117">Anzeigen des Eingabedaten-Nutzungsberichts</span><span class="sxs-lookup"><span data-stu-id="e65c8-117">View the input data usability report</span></span>

<span data-ttu-id="e65c8-118">Nachdem ein sofort einsatzbereites Modell seinen Trainingsschritt abgeschlossen hat, zeigen Sie den Bericht an:</span><span class="sxs-lookup"><span data-stu-id="e65c8-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="e65c8-119">Wählen Sie die Auslassungspunkte neben dem Modellnamen aus und wählen Sie dann **Eingabedaten-Nutzungsbericht** aus.</span><span class="sxs-lookup"><span data-stu-id="e65c8-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="e65c8-120">Wählen Sie den Status eines Modells aus. Wählen Sie **Eingabedaten-Nutzungsbericht anzeigen** im Seitenbereich aus.</span><span class="sxs-lookup"><span data-stu-id="e65c8-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="e65c8-121">Wählen Sie eines der Modelle in der Liste aus und wählen Sie dann **Eingabedaten-Nutzungsbericht** in der Befehlsleiste aus.</span><span class="sxs-lookup"><span data-stu-id="e65c8-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="e65c8-122">Öffnen Sie Modellergebnisseite und wählen Sie **Eingabedaten-Nutzungsbericht** in der Befehlsleiste aus.</span><span class="sxs-lookup"><span data-stu-id="e65c8-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="e65c8-123">Im Eingabedaten-Nutzungsbericht enthaltene Informationen</span><span class="sxs-lookup"><span data-stu-id="e65c8-123">Information in the input data usability report</span></span>

<span data-ttu-id="e65c8-124">Die folgenden Spalten im Bericht enthalten hilfreiche Informationen zur Verbesserung der Daten für das Modell.</span><span class="sxs-lookup"><span data-stu-id="e65c8-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Beispiel für einen Eingabedaten-Nutzungsbericht mit einer Tabelle mit Fehlern, Warnungen und Empfehlungen.":::

- <span data-ttu-id="e65c8-126">Name: Ein beschreibender Name des Fehlers, der Warnung oder der Empfehlung.</span><span class="sxs-lookup"><span data-stu-id="e65c8-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="e65c8-127">Schritt: Modellphase, Training oder Bewertung, auf die sich die Informationen beziehen.</span><span class="sxs-lookup"><span data-stu-id="e65c8-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="e65c8-128">Status: Der Schweregrad der Information (Fehler, Warnung, Empfehlung).</span><span class="sxs-lookup"><span data-stu-id="e65c8-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="e65c8-129">Spaltenname: Eine Spalte in einer Entität, die geändert werden muss, um die Modellleistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="e65c8-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="e65c8-130">Entitätsname: Der Name der Entität, die geändert werden muss, um die Modellleistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="e65c8-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="e65c8-131">Details: Details zu Fehlern, Warnungen oder Empfehlungen.</span><span class="sxs-lookup"><span data-stu-id="e65c8-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="e65c8-132">Aktualisieren einer Vorhersage</span><span class="sxs-lookup"><span data-stu-id="e65c8-132">Refresh a prediction</span></span>

<span data-ttu-id="e65c8-133">Vorhersagen werden automatisch zum gleichen [Zeitpunkt aktualisiert, zu dem Ihre Daten aktualisiert werden](system.md#schedule-tab), wie in den Einstellungen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="e65c8-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="e65c8-134">Sie können sie auch manuell aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e65c8-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="e65c8-135">Gehen Sie zu **Intelligenz** > **Vorhersagen** und wählen Sie die Registerkarte **Meine Vorhersagen**.</span><span class="sxs-lookup"><span data-stu-id="e65c8-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="e65c8-136">Wählen Sie die vertikalen Auslassungspunkte neben der Vorhersage, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e65c8-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="e65c8-137">Wählen Sie **Aktualisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="e65c8-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="e65c8-138">Löschen einer Vorhersage</span><span class="sxs-lookup"><span data-stu-id="e65c8-138">Delete a prediction</span></span>

<span data-ttu-id="e65c8-139">Das Löschen einer Vorhersage entfernt auch deren Ausgabe-Entität.</span><span class="sxs-lookup"><span data-stu-id="e65c8-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="e65c8-140">Gehen Sie zu **Intelligenz** > **Vorhersagen** und wählen Sie die Registerkarte **Meine Vorhersagen**.</span><span class="sxs-lookup"><span data-stu-id="e65c8-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="e65c8-141">Wählen Sie die vertikalen Auslassungspunkte neben der Vorhersage, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="e65c8-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="e65c8-142">Klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="e65c8-142">Select **Delete**.</span></span>
