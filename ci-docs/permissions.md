---
title: Zuweisung von Benutzerrechten
description: Erfahren Sie mehr über Berechtigungen und Benutzerrollen.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245418"
---
# <a name="assign-user-permissions"></a>Zuweisung von Benutzerrechten

Der Zugriff auf Customer Insights ist auf Benutzer in Ihrem Unternehmen beschränkt, die von einem Admin zu der Anwendung hinzugefügt wurden. Ein Administrator kann Benutzer hinzufügen, bearbeiten und löschen. Ein Benutzer kann ein einzelner Benutzer, eine Gruppe oder eine Anwendung sein. Es gibt drei Arten von Rollen, die ein Benutzer haben kann:

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
- Schließen Sie die **Datenvereinheitlichung** ab, die zu der Entität „Unified customer profile“ führt.
- Definieren Sie **Beziehungen** und **Aktivitäten**.
- Erstellen Sie Segmente mit der Seite **Segmente**.
- Legen Sie Kennzahlen mit Hilfe der Seite **Kennzahlen** an.
- Verwalten Sie die Konfiguration und reichern Sie Kundenprofile über die Seite **Anreicherung** an (nur für First-Party-Anreicherungen).
- Verwalten und erstellen Sie Exporte basierend auf [Verbindungen, die mit Mitwirkenden](connections.md#allow-contributors-to-use-a-connection-for-exports) geteilt werden.

## <a name="admin"></a>Administrator

- Alle dem Beitragenden zur Verfügung stehenden Berechtigungen.
- Ändern Sie die Einstellungen auf der Seite **System**, einschließlich der Arbeitssprache und der Aktualisierungszeitpläne für Ihre Systemprozesse und für den Export von Diagnoseprotokollen.
- Ändern Sie die Einstellungen auf der **Sicherheit** Seite, einschließlich Benutzer, API-Schlüssel, Private Links und Schlüsseltresor.
- Legen Sie Such- und Filterdefinitionen für die Seite „Kunden“ über die Seite **Such- & Filterindex** fest (Zugriff über die Seite **Kunden**).
- Verwalten Sie Verbindungen und lassen Sie sie für andere Benutzerrollen auf der Seite **Verbindungen** zu.
- Verwalten Sie die Konfiguration und reichern Sie Kundenprofile über die Seite **Anreicherung** an (für alle Anreicherungen).
- Verwalten und Erstellen von Exporten auf der **Exporte**-Seite.
- Installieren und verwenden Sie das **Kundenkarten-Add-in**.
- Fügen Sie den **Power Apps-Konnektor** hinzu und verwenden Sie ihn.
- Aktivieren Sie die Verwendung der [Customer Insights APIs](apis.md).
- [Umgebungsbesitz zuweisen](manage-environments.md#change-the-owner-of-an-environment) an einen anderen Administrator.

## <a name="admin-owner"></a>Admin (Besitzer)

- Alle Berechtigungen, die dem Administrator zur Verfügung stehen.
- Die Umgebung [zurücksetzen und löschen](manage-environments.md#reset-an-existing-environment-preview).

## <a name="add-users"></a>Benutzer hinzufügen

1. Gehen Sie zu **Admin** > **Sicherheit** und wählen Sie die Registerkarte **Benutzer**.

1. Wählen Sie **Benutzer hinzufügen**, um den Bereich **Berechtigungen hinzufügen/bearbeiten** zu öffnen.

1. Verwenden Sie das Feld **Suchen**, um den Benutzer oder die Gruppe Azure Active Directory zu finden, die Sie hinzufügen möchten. Wählen Sie ein **Rolle**, das Sie diesem Benutzer oder dieser Gruppe zuweisen möchten.

1. Wählen Sie **Save** (Speichern). Die aktuelle Umgebung wird automatisch für den Benutzer oder die Mitglieder der Gruppe freigegeben, deren Berechtigungen Sie geändert haben. Benutzer können auf die Customer Insights App zugreifen und entsprechend ihrer angegebenen Rolle arbeiten.

## <a name="view-current-permissions"></a>Aktuelle Berechtigungen anzeigen

Gehen Sie zu **Administrator** > **Sicherheit** und wählen Sie die **Benutzer** Registerkarte, um die Liste der aktiven Benutzer und ihre Rollenzuweisungen anzuzeigen. Sie können die Liste der Benutzer nach einer beliebigen Spalte sortieren oder das Suchfeld verwenden, um einen bestimmten Benutzer zu finden.

## <a name="manage-current-users"></a>Aktuelle Benutzer verwalten

Wechseln Sie zu **Administrator** > **Sicherheit** und wählen Sie **Benutzer** aus. Sie können die Liste der Benutzer nach einer beliebigen Spalte sortieren oder das Suchfeld verwenden, um einen bestimmten Benutzer zu finden.

Wählen Sie einen Benutzer aus, um verfügbare Aktionen anzuzeigen.

- **Bearbeiten**, um die Rolle des Benutzers in Customer Insights zu bearbeiten. Wählen Sie **Speichern** aus, um die Änderung zu bestätigen.
- **Entfernen** um dem Benutzer den Zugriff auf Customer Insights zu entziehen. Um den Löschvorgang zu bestätigen, wählen Sie **Löschen**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
