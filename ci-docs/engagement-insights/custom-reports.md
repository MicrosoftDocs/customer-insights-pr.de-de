---
title: Info über benutzerdefinierte Berichte
description: Erfahren Sie, wie Sie benutzerdefinierte Berichte erstellen.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3fa801bfc8b0aee65c21b90de2423a3d5d5e4e26
ms.sourcegitcommit: d9965f4bfc09391698a34042f6b44367e53819e3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "7582876"
---
# <a name="create-and-edit-custom-reports"></a>Erstellen und Bearbeiten enutzerdefinierter Berichte

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Zusätzlich zu vorgefertigten Berichten können Sie einen Standard-Bericht (OOB) mit Diagramm- und Tabellenvisualisierungen erstellen, um das Benutzerverhalten nachzuvollziehen. In diesem Artikel wird erläutert, wie Sie mithilfe von Tabellen- und Diagrammvisualisierungen einen Bericht mit den benötigten Daten erstellen. Informationen zu OOB-Berichten finden Sie unter [Berichte anzeigen](view-reports.md).

## <a name="create-a-custom-report"></a>Erstellen eines benutzerdefinierten Berichts

1. Wechseln Sie zu **Analysieren** > **Benutzerdefiniert**, um auf die Liste der benutzerdefinierten Berichte zuzugreifen.

1. Wählen Sie **Neuer Bericht** aus, um mit der Erstellung eines benutzerdefinierten Berichts zu beginnen.

   :::image type="content" source="media/new-custom-report.png" alt-text="Neue benutzerdefinierte Berichte.":::

1. Wählen Sie den Typ des zu erstellenden Berichts aus:

    - Wählen Sie in der Befehlsleiste **Visuelles Element hinzufügen** aus, um eine Standardtabellenvisualisierung zu erstellen.
    - Oder wählen Sie im Bereich **Berichts-Editor** eine Spalten-, Balken-, Linien-, Flächen-, Kuchen-, Donut- oder Tabellenvisualisierung aus.

1. In dem **Daten** Abschnitt im Bereich **Visualisierungseditor** wählen Sie eine der verfügbaren Optionen (z. B. Seitenaufrufe) aus der **Metrik** Dropdown-Liste. Sie können auch **Dimensionen** (z. B. Land) hinzufügen, um in der Visualisierung angezeigt zu werden. Weitere Informationen finden Sie unter [Metriken anzeigen und erstellen](metrics.md) und [Dimensionen anzeigen und erstellen](dimensions.md).

   :::image type="content" source="media/page-views.png" alt-text="Wählen Sie eine Metrik für Ihren Bericht aus.":::

1. Wählen sie den Abschnitt **Entwurf** im Bereich **Visualisierungseditor** zum Hinzufügen von **Titeltext** und schalten Sie den **Titel** an und aus.  Sie können den Visualisierungstyp auch ändern, indem Sie ein anderes Diagramm auswählen, z.B **Kreisdiagramm**.

1. So ändern Sie die Größe und Position einer Visualisierung:
   - Wählen Sie die Visualisierung aus und ziehen Sie eine der Ecken oder einen der Ränder, um die Größe anzupassen.
   - Wählen Sie die Visualisierung aus und verschieben Sie sie an eine neue Position. Sie können auch die Pfeiltasten verwenden, um die Position zu ändern.
1. Um eine weitere Visualisierung hinzuzufügen, wählen Sie in der Befehlsleiste **Visuelles Element hinzufügen** aus.
1. Wählen Sie nach dem Hinzufügen der für den Bericht gewünschten Visualisierungen in der Befehlsleiste **Speichern** aus.

1. Geben Sie einen Namen für den benutzerdefinierten Bericht ein und wählen Sie **Speichern** aus, um ihn zu erstellen.
 
## <a name="filter-a-custom-report"></a>Einen benutzerdefinierten Bericht filtern

Sie können den Zeitrahmen- oder Datumsbereich in einem benutzerdefinierten Bericht auswählen, um sich auf einen Wert oder Zeitraum zu konzentrieren.

Um eine Zeitrahmen auszuwählen, wählen Sie in der oberen rechten Ecke der Berichtsansicht einen Wert aus der Dropdown-Liste des Berichts aus. Sie können auch einen **Festen Datumsbereich* auswählen.

:::image type="content" source="media/filter-time-date-range.png" alt-text="Nach Zeit oder Datumsbereich filtern.":::

Wählen Sie für die meisten Berichte **+ Bedingung hinzufügen** aus, um eine Dimension oder ein Segment zum Filtern des Berichts auszuwählen. Weitere Informationen finden Sie unter [Segmente erstellen und bearbeiten](segments.md).

## <a name="edit-a-custom-report"></a>Bearbeiten eines benutzerdefinierten Berichts

1. Wechseln Sie zu **Analysieren** > **Benutzerdefiniert**, um auf die Liste der benutzerdefinierten Berichte zuzugreifen.

1. Wählen Sie in der Liste der benutzerdefinierten Berichte **Mehr [...]** aus. 

1. Wählen Sie **Namen bearbeiten**, um den Namen des Berichts zu ändern.

1. Wählen Sie den Namen des Berichts aus und verwenden Sie die Optionen **+Visuelles Element hinzufügen** und **Bearbeiten** aus, um Visualisierungen hinzuzufügen, zu entfernen, neu zu positionieren oder ihre Größe zu ändern.

1. Um die Eigenschaften einer Visualisierung zu ändern, wählen Sie das visuelle Element aus, wählen Sie **...** und dann **Bild bearbeiten**.

   :::image type="content" source="media/edit-visual-control.png" alt-text="Bearbeiten von Diagrammeigenschaften für benutzerdefinierte Berichte.":::

1. Wählen Sie nach der Bearbeitung des Berichts **Speichern** aus, um die Änderungen zu übernehmen. 

## <a name="delete-a-custom-report"></a>Löschen eines benutzerdefinierten Berichts

1. Wechseln Sie zu **Analysieren** > **Benutzerdefiniert**, um auf die Liste der benutzerdefinierten Berichte zuzugreifen.

1. Wählen Sie in der Liste der benutzerdefinierten Berichte **...** aus.

1. Wählen Sie **Löschen** aus, um den Bericht zu entfernen.

1. Bestätigen Sie den Löschvorgang, um den Bericht dauerhaft zu entfernen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
