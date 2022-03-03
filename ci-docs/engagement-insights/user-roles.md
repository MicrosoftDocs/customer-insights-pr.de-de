---
title: Rollen und Berechtigungen
description: Übersicht der verfügbaren Rollen und Berechtigungen für Arbeitsbereichsmitglieder.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ccc6a1b87b4cc28701e276b6e35432356e7647c4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227538"
---
# <a name="roles-and-permissions"></a>Rollen und Berechtigungen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

In einem Arbeitsbereich speichern und verwalten Sie Ereignisse und Berichte. Weitere Informationen finden Sie unter [Erstellen Sie einen Arbeitsbereich und fügen Sie Mitglieder hinzu](create-workspace.md). 

Ein Arbeitsbereich kann die folgenden Rollen und Berechtigungen umfassen:

- *Mitgliederrollen* sind Benutzer, die auf einen Arbeitsbereich zugreifen können. Sie können Ihrem Arbeitsbereich Mitglieder zuweisen und deren Rollen und Berechtigungen definieren. 
- *Administratorrollen* verwalten Arbeitsbereiche und Umgebungen und konfigurieren Interaktionserkenntnisse für andere Benutzer. 
- *Teilnehmerrollen* richten sich an Analysten, die keine Einblicke in die Kundenbindung konfigurieren müssen, sondern ihre eigenen Berichte, Trichter oder Segmente erstellen möchten.

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
