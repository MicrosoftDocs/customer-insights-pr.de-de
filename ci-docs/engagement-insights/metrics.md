---
title: Anzeigen und Erstellen von Metriken
description: So erstellen, bearbeiten und löschen Sie Metriken.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 97189168e0f5586aad8be8089a1f9e27893c2115c7e805ddaab1efc00e11b860
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034268"
---
# <a name="view-and-create-metrics"></a>Anzeigen und Erstellen von Metriken

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Metriken helfen, das Verhalten Ihrer Besucher zu verstehen. Sie aggregieren Ereigniseigenschaften, messen Statistiken und erfassen die Leistung Ihrer Webeigenschaften.  

Angenommen, Sie führen eine Marketingaktion auf Ihrer Website durch. Sie können Metriken verwenden, um die Anzahl der einzelnen Besucher oder Benutzer zu verfolgen, die Ihre Website während der Werbeaktion besucht haben. Die Analyse von Metriken hilft Ihnen, die Zielgruppe Ihrer Website besser zu verstehen. Durch das Kombinieren von Metriken mit [Dimensionen](dimensions.md) in einem [benutzerdefinierten Bericht](custom-reports.md) können Sie das Verhalten messen, um Ihre Benutzer zu verstehen. Beispielsweise können Sie Besucher als neue und wiederkehrende Besucher kategorisieren, um die Unterschiede in den Interessen und Absichten zwischen den Gruppen zu identifizieren.

## <a name="view-metrics"></a>Anzeigen von Metriken

Interaktionserkenntnisse umfassen häufig verwendete Aggregationen von Ereigniseigenschaften als Systemmetriken: 

- Besucher
- Besuche
- Seitenaufrufe
- Klicks

Diese Systemmetriken basieren auf vorhandenen Ereigniseigenschaften in Basisereignissen.

1. Wechseln Sie zu **Daten** im linken Navigationsbereich. 
1. Wählen Sie die Registerkarte **Metriken** aus, um eine Liste aller Metriken im Arbeitsbereich anzuzeigen. 
   > [!NOTE]
   > Vom System generierte Metriken sind schreibgeschützt. Sie können sie nicht ändern oder löschen. Sie können nur benutzerdefinierte Metriken erstellen und bearbeiten.

## <a name="create-a-metric"></a>Erstellen einer Metrik

Umgebungs- und Arbeitsbereichsadministratoren können Metriken erstellen. Ereigniseigenschaften müssen an den Arbeitsbereich gesendet werden, bevor Sie eine Metrik erstellen. Sie können Metriken basierend auf Ereigniseigenschaften erstellen, die von Basisereignissen gesendet werden, oder Sie verwenden das Web-SDK, um [benutzerdefinierte Ereigniseigenschaften zu senden](advanced-SDK-implementation.md).

1. Wechseln Sie zu **Daten** > **Metriken**.
1. Wählen Sie **Neue Metrik** aus.

   :::image type="content" source="media/new-metric.png" alt-text="Hinzufügen einer Metrik zu einem Ereignis.":::

1. Wählen Sie für das Format den Datentyp **Integer** oder **Double** aus. Der Datentyp „Integer“ steht für eine ganze Zahl. Bei Auswahl des Datentyps „Double“ können Sie zwischen einer und drei Dezimalstellen wählen.
1. Suchen Sie im Bereich **Ressourcenbibliothek** die Ereigniseigenschaft, auf der die Metrik basieren soll.
1. Wählen Sie das **Pluszeichen (+)** neben der Eigenschaft aus, um sie in der Formel zu verwenden. Sie können eine Formel nur basierend auf einer Eigenschaft erstellen. 
1. Wählen Sie eine der folgenden Aggregatfunktionen aus. 

   - Summe: die arithmetische Summe aller Werte 
   - Durchschnitt: der mittlere Durchschnitt aller Werte
   - Anzahl: die Gesamtzahl der Werte
   - Diskrete Anzahl: die Gesamtzahl der diskreten Werte

   Nachdem Sie die Metrik definiert haben, sehen Sie eine Aktivitätsvorschau der Metrik für die letzte Stunde.

1. Wählen Sie **Speichern** aus. 
1. Geben Sie einen Namen für die Metrik ein und wählen Sie anschließend **Speichern** aus.

Es kann bis zu einer Minute dauern, bis die Metrik angezeigt wird und Sie sie zur [Erstellung benutzerdefinierter Berichte](custom-reports.md) verwenden können.

## <a name="edit-a-metric"></a>Bearbeiten einer Metrik

1. Wechseln Sie zu **Daten** > **Metriken**.
1. Wählen Sie die Metrik in der Liste aus.
1. Ändern der Definition der Metrik
1. Wählen Sie **Speichern** aus.

## <a name="change-the-name-of-a-metric"></a>Ändern des Namens einer Metrik

1. Wechseln Sie zu **Daten** > **Metriken**.
1. Wählen Sie für eine Metrik **Mehr [...]** aus und wählen Sie dann **Name bearbeiten** aus.
1. Ändern Sie den Namen. 
1. Klicken Sie auf **Umbenennen**.

## <a name="delete-a-metric"></a>Löschen einer Metrik

1. Wechseln Sie zu **Daten** > **Metriken**.
1. Wählen Sie für eine Metrik **Mehr [...]** aus und wählen Sie dann **Löschen** aus.

   :::image type="content" source="media/delete-metric.png" alt-text="Löschen einer Metrik aus einem Ereignis.":::

1. Um den Löschvorgang zu bestätigen, wählen Sie **Löschen**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
