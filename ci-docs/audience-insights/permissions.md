---
title: Verwalten von Benutzerberechtigungen
description: Erfahren Sie mehr über Berechtigungen und Benutzerrollen.
ms.date: 10/27/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7de78c0ef71ec5b83870d396de36a7dcabbd14e5
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689219"
---
# <a name="user-permissions"></a>Benutzerberechtigungen

Auf der Seite **Berechtigungen** richten Sie Rollen und Berechtigungen für die Verwendung von Zielgruppen-Insights ein.

Sie benötigen Administratorberechtigungen, um diese Seite zu sehen. Um auf die Seite mit den Berechtigungen in Zielgruppen-Insights zuzugreifen, gehen Sie zu **Admin** > **Berechtigungen**.

Es gibt drei Arten von Rollen:

## <a name="viewer"></a>Zuschauer

- Erkunden Sie Insights und Segmente innerhalb der Seiten **Home** und **Segmente**.
- Suchen und filtern Sie Kundenprofile mit Hilfe der Seite **Kunden**. Felder müssen durchsuchbar sein.
- Erkunden Sie die Seite **Bereicherung**.
- Erforschen und exportieren Sie Entitäten mit Hilfe der Seite **Entitäten**.
- Den Status von Systemprozessen können Sie über die Seite **System** einsehen.
- Exportieren Sie Segmente von der Seite **Segmente**.
- Installieren und verwenden Sie das **Power BI Customer Insights** Dashboard.

## <a name="contributor"></a>Mitwirkender

- Alle dem Betrachter zur Verfügung stehenden Berechtigungen.
- Laden und transformieren Sie die Daten mithilfe der Seite **Datenquellen**.
- Vervollständigen Sie die Abschnitte *Datenvereinheitlichung* (**Zuordnen**, **Abgleichen** und **Zusammenführen**), die zu der vereinheitlichten Entität „Kundenprofil“ führen.
- Definieren Sie **Beziehungen** und **Aktivitäten**.
- Erstellen Sie Segmente mit der Seite **Segmente**.
- Legen Sie Kennzahlen mit Hilfe der Seite **Kennzahlen** an.
- Verwalten Sie die Konfiguration und reichern Sie Kundenprofile über die Seite **Anreicherung** an (nur für First-Party-Anreicherungen).

## <a name="administrator"></a>Administrator

- Alle dem Beitragenden zur Verfügung stehenden Berechtigungen.
- Ändern Sie die Einstellungen auf der Seite **System**, einschließlich der Arbeitssprache und der Aktualisierungszeitpläne für Ihre Systemprozesse.
- Anzeigen und Hinzufügen von Berechtigungen über die Seite **Berechtigungen**.
- Legen Sie Such- und Filterdefinitionen für die Seite „Kunden“ über die Seite **Such- & Filterindex** fest (Zugriff über die Seite **Kunden**).
- Definieren Sie Dynamics 365 Sales-Segmentziele über die Seite **Ziele exportieren**.
- Verwalten Sie die Konfiguration und reichern Sie Kundenprofile über die Seite **Anreicherung** an (für alle Anreicherungen).
- Installieren und verwenden Sie das **Kundenkarten-Add-in**.
- Fügen Sie den **Power Apps-Konnektor** hinzu und verwenden Sie ihn.
- Aktivieren Sie die Verwendung der [Customer Insights APIs](apis.md).

## <a name="assign-roles-and-permissions"></a>Rollen und Berechtigungen zuweisen

1. Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Berechtigungen**.

1. Wählen Sie **Benutzer hinzufügen**, um den Bereich **Berechtigungen hinzufügen/bearbeiten** zu öffnen.

1. Verwenden Sie das Feld **Suchen**, um den Benutzer oder die Gruppe Azure Active Directory zu finden, deren Berechtigungen Sie anpassen möchten. Wählen Sie ein **Rolle**, das Sie diesem Benutzer oder dieser Gruppe zuweisen möchten.

1. Wählen Sie **Speichern** aus. Die aktuelle Umgebung wird automatisch für den Benutzer oder die Mitglieder der Gruppe freigegeben, deren Berechtigungen Sie geändert haben. Benutzer können auf die Customer Insights App zugreifen und entsprechend ihrer angegebenen Rolle arbeiten.

## <a name="view-current-permissions"></a>Aktuelle Berechtigungen anzeigen

Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Berechtigungen**, um zu sehen, welche Rollenzuweisungen gerade aktiv sind.

- Die Spalte **Typ** gibt einen einzelnen Benutzer, eine Gruppe oder eine Anwendung an. Das System unterstützt einzelne Benutzer und Gruppen.
- Die Rollen werden in der Spalte **Rolle** angegeben.
- Wählen Sie einen beliebigen Spaltentitel, um die Ergebnisse nach dem Wert dieser Spalte zu sortieren.
- Verwenden Sie das Feld **Suchen** oben auf der Seite, um bestimmte Benutzer zu finden.
