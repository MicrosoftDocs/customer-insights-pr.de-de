---
title: Exportieren Sie Daten aus Customer Insights
description: Verwalten Sie Datenexporte, um Daten freizugeben.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016613"
---
# <a name="exports-preview-overview"></a>Exporte (Vorschau) – Übersicht

Die Seite **Exporte** zeigt Ihnen alle konfigurierten Exporte. Exporte teilen bestimmte Daten mit verschiedenen Anwendungen. Sie können Kundenprofile oder -entitäten, Schemas und Zuordnungsdetails enthalten. Jeder Export erfordert eine [Verbindung, die von einem Administrator eingerichtet wurde, um die Authentifizierung und den Zugriff zu verwalten](connections.md).

Gehen Sie zu **Daten** > **Exporte**, um die Exportseite anzuzeigen. Alle Benutzerrollen haben Zugriff auf die angezeigten Exporte. Verwenden Sie das Suchfeld in der Befehlsleiste, um Exporte nach Name, Verbindungsname oder Verbindungstyp zu suchen.

## <a name="set-up-a-new-export"></a>Einen neuen Export einrichten

Um einen Export einzurichten oder zu bearbeiten, müssen Verbindungen verfügbar sein. Verbindungen hängen von Ihrer [Benutzerrolle](permissions.md) ab:
- Administratoren haben Zugriff auf alle Verbindungen. Sie können beim Einrichten eines Exports auch neue Verbindungen herstellen.
- Mitwirkende können auf bestimmte Verbindungen zugreifen. Sie hängen von Administratoren ab, um Verbindungen zu konfigurieren und gemeinsam zu nutzen. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Betrachter können nur vorhandene Exporte anzeigen, aber nicht erstellen.

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**, um ein neues Exportziel zu erstellen.

1. Im Bereich **Export einrichten** wählen Sie aus, welche Verbindung verwendet werden soll. [Verbindungen](connections.md) werden von Administratoren verwaltet. 

1. Geben Sie die erforderlichen Details ein und wählen Sie **Speichern**, um den Export zu erstellen.

### <a name="edit-an-export"></a>Einen Export bearbeiten

1. Wählen Sie die vertikale Auslassung für das Exportziel aus, das Sie bearbeiten möchten.

1. Wählen Sie **Bearbeiten** aus dem Dropdownmenü aus.

1. Ändern Sie die gewünschten Werte zur Aktualisierung und wählen **Speichern** aus.

## <a name="view-exports-and-export-details"></a>Exporte anzeigen und Details exportieren

Nach dem Erstellen von Exportzielen werden diese in **Daten** > **Exporte** aufgelistet. Alle Benutzer können sehen, welche Daten gemeinsam genutzt werden und welchen Status sie haben.

1. Gehen Sie zu **Daten** > **Exporte**.

1. Benutzer ohne Bearbeitungsberechtigung wählen **Anzeigen** statt **Bearbeiten** aus, um die Exportdetails anzuzeigen.

1. Dieser Seitenbereich zeigt die Einrichtung dieses Exports. Ohne Bearbeitungsberechtigungen können Sie keine Werte ändern. Wählen Sie **Schließen** aus, um zur Exportseite zurückzukehren.

## <a name="run-exports-on-demand"></a>Exporte Bedarfsgesteuert ausführen

Nach dem Konfigurieren eines Exports wird er mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt, solange es eine funktionierende Verbindung gibt.

Um Daten zu exportieren, ohne auf eine geplante Aktualisierung zu warten, gehen Sie zu **Daten** > **Exporte**. Sie haben zwei Möglichkeiten:

- Um alle Exporte auszuführen, wählen Sie **Alle ausführen** in der Befehlsleiste aus. 
- Um einen einzelnen Export auszuführen, wählen Sie die Auslassungspunkte (...) in einem Listenelement aus und wählen Sie dann **Ausführen**.

## <a name="remove-an-export"></a>Einen Export entfernen

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie die vertikale Auslassung für den Export aus, den Sie entfernen möchten.

1. Klicken Sie im Dropdown-Menü auf **Entfernen**.

1. Bestätigen Sie das Entfernen, indem Sie **Entfernen** auf dem Bestätigungsbildschirm wählen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
