---
title: Verwalten von Arbeitsbereichen und Umgebungen
description: So können Sie Arbeitsbereiche und Umgebungen erstellen, umbenennen und löschen.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 07/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: bf310b1a50ba7baac5d11d5f22ff42003fbba516efd7d165c00b59adc958da2e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034041"
---
# <a name="manage-environments-and-workspaces"></a>Verwalten von Umgebungen und Arbeitsbereichen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Überblick

In einem Arbeitsbereich werden Ereignisse und Berichte gespeichert und verwaltet. Hier können Sie Benutzeraktivitäten in Echtzeit anzeigen. Wenn Sie einen Arbeitsbereich erstellen, wählen Sie den Datentyp aus, den Sie an den Arbeitsbereich senden. Derzeit werden Webdaten und mobile Apps unterstützt.

Eine Umgebung ist ein Bereich, in dem Sie Ihre Arbeitsbereiche und Verbindungen verwalten. Wie Sie Umgebungen nutzen, hängt von Ihrer Organisation und Ihrem Anwendungsfall ab. So können beispielsweise Folgendes erstellen:

-   Eine einzelne Umgebung.
-   Separate Test- und Produktionsumgebungen.
-   Separate Umgebungen für bestimmte Teams oder Abteilungen in Ihrer Organisation, die relevante Ereignisse für jede Zielgruppe enthalten.
-   Separate Umgebungen für verschiedene Niederlassungen Ihres Unternehmens.
-   Verbindungen zur Funktion Zielgruppenerkenntnisse von Customer Insights.

## <a name="choose-an-environment-and-create-a-workspace"></a>Auswählen einer Umgebung und Erstellen eines Arbeitsbereichs 

Jeder Arbeitsbereich muss sich in einer Umgebung befinden. Sie können eine bereits vorhandene Umgebung auswählen oder eine neue erstellen, wenn Sie einen Arbeitsbereich erstellen. Anschließend können Sie Arbeitsbereichsmitglieder hinzufügen und mit dem Sammeln von Daten beginnen.

**Erstellen Ihres ersten Arbeitsbereichs**

1. Wählen Sie in der Funktion Kundenbindungserkenntnisse im Arbeitsbereichsumschalter die Option **Neu** aus. 

   :::image type="content" source="media/New-workspace.png" alt-text="Arbeitsbereichsauswahl auf der Customer Insights-Seite.":::

1. Wählen Sie eine Umgebung aus der Liste aus oder wählen Sie **Neue Umgebung erstellen** aus.

1. Geben Sie einen Namen in das Feld **Arbeitsbereichsname** ein. 

1. Wählen Sie die Art der Umgebung aus, die Sie erstellen möchten, je nachdem, ob Sie messen möchten, was auf einer Website oder in einer mobilen App passiert. 

1. Sie können Mitglieder hinzufügen und ihre Berechtigungsstufe über die Liste **Rolle** zuweisen. Wählen Sie dann **Fertigstellen** aus, um den Arbeitsbereich zu erstellen, oder **Weiter**, um Code zu installieren. 

1. Installieren Sie den Codeausschnitt, um Daten zu empfangen, und wählen Sie dann **Fertig** aus. 

## <a name="manage-a-workspace"></a>Verwalten eines Arbeitsbereichs

Sie können mehrere Arbeitsbereiche gleichzeitig in einer Umgebung verwalten. Ihre [Rolle](user-roles.md) legt fest, wie Sie darin arbeiten können. 

 - Sie müssen ein Umgebungsadministrator oder ein Arbeitsbereichsadministrator sein, um den Arbeitsbereich verwalten zu können.
 - Als Arbeitsbereichsadministrator können Sie vorhandene Arbeitsbereiche umbenennen oder löschen. 

### <a name="edit-a-workspace-name"></a>Bearbeiten eines Arbeitsbereichsnamens

1. Wechseln Sie zu **Administrator** > **Arbeitsbereich** und wählen Sie **Einstellungen** aus.

1. Geben Sie im Feld **Arbeitsbereichsname** einen neuen Namen ein.

1. Wählen Sie **Speichern**, um Ihre Änderungen zu übernehmen.

### <a name="delete-a-workspace"></a>Löschen eines Arbeitsbereichs

Durch Löschen eines Arbeitsbereichs werden alle Inhalte, Daten, Einstellungen und Berechtigungen dauerhaft entfernt. Diese Aktion kann nicht rückgängig gemacht werden.

1. Wechseln Sie zu **Administrator** > **Arbeitsbereich** und wählen Sie **Einstellungen** aus.

1. Wählen Sie **Arbeitsbereich löschen** aus. 

1. Geben Sie im Dialog **Arbeitsbereich löschen** den Text **LÖSCHEN BESTÄTIGEN** ein. 

1. Wählen Sie **Löschen** aus, um den Arbeitsbereich dauerhaft zu löschen.

### <a name="manage-workspace-members"></a>Verwalten von Arbeitsbereichsmitgliedern

1. Wechseln Sie zu **Administrator** > **Arbeitsbereich** und wählen Sie **Mitglieder** aus.

1. Wählen Sie **Mitglieder hinzufügen** aus, um selbigen den Zugriff zu gewähren und [Rollen zuzuweisen](user-roles.md). Derzeit ist nur die Rolle **Arbeitsbereichsadministrator** verfügbar.

1. Wenn Sie eine [Verbindung zur Funktion Zielgruppenerkenntnisse](configure-connections.md) einrichten, können Sie **Zugriff auf Profildaten erlauben** auswählen, damit das Mitglied Berichte basierend auf dem [Benutzerprofil](profile-reports.md) anzeigen kann.

1. Wählen Sie **Mitglieder hinzufügen** aus, um sie Ihrem Arbeitsbereich hinzuzufügen.

## <a name="manage-an-environment"></a>Umgebung verwalten

Als Umgebungsadministrator können Sie über den linken Navigationsbereich auf eine Umgebung zugreifen. Sie können Umgebungseinstellungen, andere Umgebungsadministratoren, Arbeitsbereiche und [Verbindungen zu Zielgruppenerkenntnisse](configure-connections.md) konfigurieren. Wählen Sie Registerkarten aus, um zwischen verschiedenen Bereichen im Admin Center zu wechseln.

:::image type="content" source="media/New-environment.png" alt-text="Admin Center für Umgebungen.":::

### <a name="create-an-environment"></a>Umgebung erstellen

1. Wählen Sie in der Arbeitsbereichsauswahl **+Neu** aus.

1. Öffnen Sie in der geführten Umgebung das Dropdownmenü **Umgebung** und wählen Sie **Neue Umgebung erstellen** aus. 

1. Geben Sie einen **Umgebungsnamen** an.

   :::image type="content" source="media/create-environment.png" alt-text="Führen Sie die geführte Umgebung aus, um die Umgebungsdetails anzugeben.":::

1. Wählen Sie die **Region** und dann **Weiter** aus. 

1. Geben Sie einen Arbeitsbereichsnamen an und wählen Sie aus, welchen Arbeitsbereichstyp Sie erstellen möchten. 

1.  Fügen Sie optional Mitglieder hinzu und kopieren Sie den Codeausschnitt, um den Erstellungsprozess abzuschließen.

### <a name="rename-an-environment"></a>Umbenennen einer Umgebung

1. Wechseln Sie zu **Administrator** > **Umgebung** und wählen Sie **Einstellungen** aus.

1. Aktualisieren Sie den **Umgebungsnamen** und wählen Sie **Speichern** aus, um die Änderungen zu übernehmen.

### <a name="manage-environment-members"></a>Verwalten von Umgebungsmitgliedern

1. Wechseln Sie zu **Administrator** > **Umgebung** und wählen Sie **Mitglieder** aus.

1. Wählen Sie **Mitglieder hinzufügen** aus, um Mitglieder zu aktualisieren und ihnen [Rollen zuzuweisen](user-roles.md). Derzeit ist nur die Rolle **Umgebungsadministrator** verfügbar.

1. Wenn Sie eine [Verbindung zur Funktion Zielgruppenerkenntnisse](configure-connections.md) einrichten, können Sie **Zugriff auf Profildaten erlauben** auswählen, damit das Mitglied Berichte basierend auf dem [Benutzerprofil](profile-reports.md) anzeigen kann.

1. Wählen Sie **Mitglieder hinzufügen** aus, um sie Ihrer Umgebung hinzuzufügen.

### <a name="delete-an-environment"></a>Eine Umgebung löschen

Umgebungsadministratoren können Umgebungen löschen. Bevor Sie eine Umgebung löschen können, müssen Sie alle darunter liegenden Arbeitsbereiche entfernen.

1. Wechseln Sie zu **Administrator** > **Umgebung** und wählen Sie **Einstellungen** aus.

1. Wählen Sie **Umgebung löschen** aus. 

1. Geben Sie im Dialog **Arbeitsbereich löschen** den Text **LÖSCHEN BESTÄTIGEN** ein. 

1. Wählen Sie **Löschen**, um die Umgebung dauerhaft zu löschen.

## <a name="manage-connections"></a>Verbindungen verwalten

Durch das Herstellen von Verbindungen zur Funktion Zielgruppenerkenntnisse können Sie Berichte in Zielgruppenerkenntnisse anzeigen, die auf einheitlichen Kundenprofilen basieren. 

Weitere Informationen finden Sie unter [Konfigurieren von Verbindungen](configure-connections.md).

## <a name="manage-personal-data"></a>Verwalten persönlicher Daten

Um die persönlichen Daten Ihres Kunden zu schützen, können Sie Endbenutzerinformationen löschen oder exportieren.

Weitere Informationen finden Sie unter [Löschen und Exportieren von Ereignisdaten mit persönlichen Informationen](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
