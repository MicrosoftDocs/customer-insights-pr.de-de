---
title: Anzeigen und Erstellen von Dimensionen
description: So erstellen, bearbeiten und löschen Sie Dimensionen.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b575c5e84197d76f53a722bac60c5af928c917f9671720ede1de38c4a7478be4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033996"
---
# <a name="view-and-create-dimensions"></a>Anzeigen und Erstellen von Dimensionen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Eine Dimension ist ein Attribut eines Ereignisses, das Daten beschreiben, filtern oder gruppieren kann. Wenn Sie auf Ihrer Website eine Marketingaktion durchführen, können Sie mithilfe von Dimensionen Besucher nach neuen und wiederkehrenden Benutzern sortieren.  

Erkenntnisse zur Kundenbindung umfassen sofort einsatzbereite Dimensionen für Ereigniseigenschaften. Beispiele beinhalten:

- Browsername
- Seitenname
- Gerätemodell
- Betriebssystem
- Land/Region

## <a name="view-dimensions"></a>Anzeigen von Dimensionen

Dimensionen basieren auf vorhandenen Ereigniseigenschaften. Wenn Sie den Nachverfolgungscode für Erkenntnisse zur Kundenbindung verwenden, werden automatisch Systemdimensionen erstellt.

1. Wechseln Sie zu **Daten** im linken Navigationsbereich. 
1. Wählen Sie **Dimensionen** aus, um eine Liste aller Dimensionen im Arbeitsbereich anzuzeigen. 
   > [!NOTE]
   > Vom System generierte Dimensionen sind schreibgeschützt. Sie können sie nicht bearbeiten. Sie können nur benutzerdefinierte Dimensionen erstellen und bearbeiten.

## <a name="create-a-dimension"></a>Dimension erstellen

Zusätzlich zu den vom System generierten Dimensionen können Umgebungs- und Arbeitsbereichsadministratoren benutzerdefinierte Dimensionen erstellen. Benutzerdefinierte Dimensionen basieren auf Standardeigenschaften von Basisereignissen oder können [benutzerdefinierte Eigenschaften eines Ereignisses](advanced-SDK-implementation.md) verwenden.

1. Wechseln Sie zu **Daten** > **Dimensionen**.
1. Wählen Sie **Dimension hinzufügen** aus.

   :::image type="content" source="media/add-dimension.png" alt-text="Hinzufügen einer Dimension zu einem Ereignis.":::

1. Wählen Sie im Bereich **Dimension erstellen** eine Eigenschaft aus, auf der die Dimension basieren soll. Die Eigenschaftenliste zeigt alle Eigenschaften im Arbeitsbereich an, die keiner Dimension zugewiesen sind.
1. Geben Sie in das Feld **Anzeigename** einen Namen ein. Optional können Sie eine Beschreibung hinzufügen.
1. Wählen Sie **Erstellen** aus, um die Dimension zu speichern. Es kann bis zu einer Minute dauern, bis Sie die Dimension in einem [benutzerdefinierten Bericht](custom-reports.md) oder [Segment](segments.md) verwenden können. 

## <a name="edit-a-dimension"></a>Bearbeiten einer Dimension

Sie können den Namen und die Beschreibung einer Dimension ändern.

1. Wechseln Sie zu **Daten** > **Dimensionen**.
1. Wählen Sie die Dimension aus, die Sie löschen möchten.
1. Aktualisieren Sie die Dimension im Bereich **Dimension bearbeiten**.
1. Wählen Sie **Übernehmen** aus, um die Änderungen zu übernehmen.

## <a name="delete-a-dimension"></a>Löschen einer Dimension

Sie können nur von Benutzern erstellte Dimensionen löschen, keine Systemdimensionen.

Das Löschen einer Dimension ist dauerhaft. Berichte und Segmente, die eine gelöschte Dimension verwenden, funktionieren nicht mehr. 

1. Wechseln Sie zu **Daten** > **Dimensionen**.
1. Wählen Sie die Dimension aus, die Sie löschen möchten.
1. Wählen Sie im Bereich **Dimension bearbeiten** die Option **Dimension löschen** aus.

   :::image type="content" source="media/delete-dimension.png" alt-text="Löschen einer Dimension aus einem Ereignis.":::

1. Geben Sie **LÖSCHEN BESTÄTIGEN** (in Großbuchstaben) ein, um das Löschen zu bestätigen. 
1. Klicken Sie auf **Löschen**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]