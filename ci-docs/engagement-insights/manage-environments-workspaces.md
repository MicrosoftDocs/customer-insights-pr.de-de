---
title: Verwalten von Arbeitsbereichen und Umgebungen
description: So können Sie Arbeitsbereiche und Umgebungen erstellen, umbenennen und löschen.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 279af24358a1d6ea2b4cc75d5496042af73a7cae
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645445"
---
# <a name="manage-environments-and-workspaces"></a>Verwalten von Umgebungen und Arbeitsbereichen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Überblick

In diesem Thema wird erläutert, wie Arbeitsbereiche und Umgebungen verwaltet werden, nachdem sie bereits erstellt wurden. 

- In einem *Arbeitsbereich* werden Ereignisse und Berichte gespeichert und verwaltet. Hier können Sie Benutzeraktivitäten in Echtzeit anzeigen. Wenn Sie einen Arbeitsbereich erstellen, wählen Sie den Datentyp aus, den Sie an den Arbeitsbereich senden. Derzeit werden Webdaten und mobile Apps unterstützt. Weitere Informationen finden Sie unter [Erstellen Sie einen Arbeitsbereich und fügen Sie Mitglieder hinzu](create-workspace.md).

- Eine *Umgebung* ist ein Bereich, in dem Sie Ihre Arbeitsbereiche und Verbindungen verwalten. Weitere Informationen finden Sie unter [Eine neue Umgebung erstellen](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Verwalten eines vorhandenen Arbeitsbereichs

Sie können mehrere Arbeitsbereiche gleichzeitig in einer Umgebung verwalten. Ihre [Rolle](user-roles.md) legt fest, wie Sie darin arbeiten können. 

 - Sie müssen ein Umgebungsadministrator oder ein Arbeitsbereichsadministrator sein, um den Arbeitsbereich verwalten zu können.
 - Als Arbeitsbereichsadministrator können Sie vorhandene Arbeitsbereiche umbenennen oder löschen. 

:::image type="content" source="media/workspace-edit.png" alt-text="Arbeitsbereichsadministratorcenter.":::

### <a name="edit-a-workspace-name"></a>Bearbeiten eines Arbeitsbereichsnamens

1. Wechseln Sie zu **Administrator** > **Arbeitsbereich** und wählen Sie **Einstellungen** aus.

1. Geben Sie im Feld **Arbeitsbereichsname** einen neuen Namen ein.

1. Wählen Sie **Speichern**, um Ihre Änderungen zu übernehmen.

### <a name="delete-a-workspace"></a>Löschen eines Arbeitsbereichs

Durch Löschen eines Arbeitsbereichs werden alle Inhalte, Daten, Einstellungen und Berechtigungen dauerhaft entfernt. Diese Aktion kann nicht rückgängig gemacht werden.

1. Wechseln Sie zu **Administrator** > **Arbeitsbereich** und wählen Sie **Einstellungen** aus.

1. Wählen Sie **Arbeitsbereich löschen** aus. 

1. In dem **Arbeitsbereich löschen** Dialog, geben Sie **LÖSCHEN BESTÄTIGEN** in Großbuchstaben ein. 

1. Wählen Sie **Löschen** aus, um den Arbeitsbereich dauerhaft zu löschen.

### <a name="manage-workspace-members"></a>Verwalten von Arbeitsbereichsmitgliedern

1. Wechseln Sie zu **Administrator** > **Arbeitsbereich** und wählen Sie **Mitglieder** aus.

1. Wählen Sie **Mitglieder hinzufügen** aus, um selbigen den Zugriff zu gewähren und [Rollen zuzuweisen](user-roles.md). Derzeit ist nur die Rolle **Arbeitsbereichsadministrator** verfügbar.

1. Wählen Sie **Mitglieder hinzufügen** aus, um sie Ihrem Arbeitsbereich hinzuzufügen.

## <a name="manage-an-existing-environment"></a>Eine bestehende Umgebung verwalten

Als Umgebungsadministrator können Sie auf eine Umgebung über den linken Navigationsbereich zugreifen. Sie können Umgebungseinstellungen, andere Umgebungsadministratoren und Arbeitsbereiche konfigurieren. Wählen Sie Registerkarten aus, um zwischen verschiedenen Bereichen im Admin Center zu wechseln.

:::image type="content" source="media/environment-edit.png" alt-text="Admin Center für Umgebungen.":::

### <a name="rename-an-environment"></a>Umbenennen einer Umgebung

1. Wechseln Sie zu **Administrator** > **Umgebung** und wählen Sie **Einstellungen** aus.

1. Aktualisieren Sie den **Umgebungsnamen** und wählen Sie **Speichern** aus, um die Änderungen zu übernehmen.

### <a name="manage-environment-members"></a>Verwalten von Umgebungsmitgliedern

1. Wechseln Sie zu **Administrator** > **Umgebung** und wählen Sie **Mitglieder** aus.

1. Wählen Sie **Mitglieder hinzufügen** aus, um Mitglieder zu aktualisieren und ihnen [Rollen zuzuweisen](user-roles.md). Derzeit ist nur die Rolle **Umgebungsadministrator** verfügbar.

1. Wählen Sie **Mitglieder hinzufügen** aus, um sie Ihrer Umgebung hinzuzufügen.

### <a name="delete-an-environment"></a>Eine Umgebung löschen

Umgebungsadministratoren können Umgebungen löschen. Bevor Sie eine Umgebung löschen können, müssen Sie alle darunter liegenden Arbeitsbereiche entfernen.

1. Wechseln Sie zu **Administrator** > **Umgebung** und wählen Sie **Einstellungen** aus.

1. Wählen Sie **Umgebung löschen** aus. 

1. In dem **Arbeitsbereich löschen** Dialog, geben Sie **LÖSCHEN BESTÄTIGEN** in Großbuchstaben ein. 

1. Wählen Sie **Löschen**, um die Umgebung dauerhaft zu löschen.

## <a name="manage-connections"></a>Verbindungen verwalten

Durch das Herstellen von Verbindungen zur Funktion Zielgruppenerkenntnisse können Sie Berichte in Zielgruppenerkenntnisse anzeigen, die auf einheitlichen Kundenprofilen basieren. 

Weitere Informationen finden Sie unter [Erstellen Sie eine Verknüpfung zwischen Zielgruppenerkenntnissen und Kundenbindungserkenntnissen](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Verwalten persönlicher Daten

Um die persönlichen Daten Ihres Kunden zu schützen, können Sie Endbenutzerinformationen löschen oder exportieren.

Weitere Informationen finden Sie unter [Löschen und Exportieren von Ereignisdaten mit persönlichen Informationen](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
