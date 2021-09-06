---
title: Verwalten von Benutzerberechtigungen
description: Erfahren Sie mehr über Berechtigungen und Benutzerrollen.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 430ad902a5a75552243bc4a094361a749364383717278f687dd6e8ef33749c6f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7028313"
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
- Exporte auf der Seite **Exporte** anzeigen.
- Installieren und verwenden Sie das **Power BI Customer Insights** Dashboard.

## <a name="contributor"></a>Beitragender

- Alle dem Betrachter zur Verfügung stehenden Berechtigungen.
- Laden und transformieren Sie die Daten mithilfe der Seite **Datenquellen**.
- Vervollständigen Sie die Abschnitte *Datenvereinheitlichung* (**Zuordnen**, **Abgleichen** und **Zusammenführen**), die zu der vereinheitlichten Entität „Kundenprofil“ führen.
- Definieren Sie **Beziehungen** und **Aktivitäten**.
- Erstellen Sie Segmente mit der Seite **Segmente**.
- Legen Sie Kennzahlen mit Hilfe der Seite **Kennzahlen** an.
- Verwalten Sie die Konfiguration und reichern Sie Kundenprofile über die Seite **Anreicherung** an (nur für First-Party-Anreicherungen).
- Verwalten und erstellen Sie Exporte basierend auf Verbindungen, die mit Mitwirkenden geteilt werden. [Erfahren Sie mehr darüber, wie Administratoren Mitwirkenden erlauben, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="administrator"></a>Administrator

- Alle dem Beitragenden zur Verfügung stehenden Berechtigungen.
- Ändern Sie die Einstellungen auf der Seite **System**, einschließlich der Arbeitssprache und der Aktualisierungszeitpläne für Ihre Systemprozesse.
- Anzeigen und Hinzufügen von Berechtigungen über die Seite **Berechtigungen**.
- Legen Sie Such- und Filterdefinitionen für die Seite „Kunden“ über die Seite **Such- & Filterindex** fest (Zugriff über die Seite **Kunden**).
- Verwalten Sie Verbindungen und lassen Sie sie für andere Benutzerrollen auf der Seite **Verbindungen** zu.
- Verwalten Sie die Konfiguration und reichern Sie Kundenprofile über die Seite **Anreicherung** an (für alle Anreicherungen).
- Verwalten und Erstellen von Exporten auf der **Exporte**-Seite.
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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
