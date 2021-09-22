---
title: Rollen und Berechtigungen
description: Übersicht der verfügbaren Rollen und Berechtigungen für Arbeitsbereichsmitglieder.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036692"
---
# <a name="roles-and-permissions"></a>Rollen und Berechtigungen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

In einem Arbeitsbereich speichern und verwalten Sie Ereignisse und Berichte. Ein Mitglied ist ein Benutzer, der auf einen Arbeitsbereich zugreifen kann. Sie können Ihrem Arbeitsbereich Mitglieder zuweisen und deren Rollen und Berechtigungen definieren. Administratorrollen verwalten Arbeitsbereiche und Umgebungen und konfigurieren Interaktionserkenntnisse für andere Benutzer. Die Mitwirkendenrollen richten sich an Analysten, die keine Interaktionserkenntnisse konfigurieren müssen, sondern ihre eigenen Berichte, Trichter oder Segmente erstellen möchten.

## <a name="permissions"></a>Berechtigungen
  
In der folgenden Tabelle sind die Berechtigungen für jede Rolle aufgeführt. 

| Berechtigung | Umgebungsadministrator | Arbeitsbereichsadministrator | Umgebungs-Beitragender | Arbeitsbereichs-Beitragender | 
|--|--|--|--|--|
| Umgebungen erstellen (der Ersteller wird automatisch zum Umgebungsadministrator) | X* | X* | X* | X* |  
| Umgebungen konfigurieren (Umgebungsmitglieder, Umgebung löschen) | X |  |  |  |  
| Arbeitsbereiche erstellen | X |  |  |  |  
| Arbeitsbereiche konfigurieren (Arbeitsbereichsmitglieder, Arbeitsbereich löschen) | X | X |  |  |  
| Ereignisse und verfeinerte Ereignisse konfigurieren | X | X | |  |  
| Arbeitsbereichsereignisse und verfeinerte Ereignisse anzeigen | X | X | |  |  
| Arbeitsbereichsressourcen anzeigen (Berichte, Segmente und Metriken)| X | X | X | X |  
| Benutzerdefinierte Berichte und Trichter erstellen | X | X | X | X |  
| Basismetriken und -dimensionen erstellen| X | X |  |  |  
| Segmente erstellen| X | X | X | X |  

* Kann in der Vorschauversion nur Testumgebungen erstellen. 

## <a name="add-members"></a>Mitglieder hinzufügen

Sie können Mitglieder zu Arbeitsbereichen und Umgebungen hinzufügen und daraus entfernen. Weitere Informationen finden Sie unter [Umgebungen und Arbeitsbereiche](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
