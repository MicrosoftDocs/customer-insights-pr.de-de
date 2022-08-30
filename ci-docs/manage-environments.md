---
title: Umgebungen verwalten
description: Erfahren Sie, wie Sie vorhandene Customer Insights-Umgebungen als Administrator verwalten.
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 8b4a88bdb75c6e638a76c39d18647681ad4556d7
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304279"
---
# <a name="manage-environments"></a>Umgebungen verwalten

Administratoren [erstellen](create-environment.md) und verwalten Umgebungen. Sie können einige Einstellungen in bestehenden Umgebungen ändern. Unternehmen, Typ, Region, Speicheroption und Dataverse-Einstellungen werden nach dem Erstellen der Umgebung festgelegt. Wenn Sie diese Einstellungen ändern möchten, [setzen Sie die Umgebung zurück](#reset-an-existing-environment-preview) oder [erstellen Sie eine neue Umgebung](create-environment.md).

## <a name="edit-an-existing-environment"></a>So bearbeiten Sie eine bestehende Umgebung

Bearbeiten Sie Details einer vorhandenen Umgebung, z. B. den Namen oder das Festlegen der Standardumgebung.

1. Wählen Sie die **Umgebung**-Auswahl in der Kopfzeile der App aus.

1. Wählen Sie das Symbol **Bearbeiten** aus.

   :::image type="content" source="media/edit-environment.png" alt-text="Symbol zum Bearbeiten der Umgebungseinstellungen.":::

1. In dem Bereich **Umgebung bearbeiten** können Sie die Umgebungseinstellungen aktualisieren.

1. Wählen Sie **Überprüfen und beenden** und dann **Aktualisieren**, um die Änderungen zu übernehmen.

## <a name="change-the-owner-of-an-environment"></a>Den Besitzer einer Umgebung ändern

Mehrere Benutzer können Administratorberechtigungen haben, jedoch ist nur ein Benutzer der Besitzer einer Umgebung. Standardmäßig erstellt zunächst der Administrator eine Umgebung. Als Administrator einer Umgebung können Sie einem anderen Benutzer mit Administratorberechtigungen die Eigentümerschaft zuweisen.

1. Wählen Sie die **Umgebung**-Auswahl in der Kopfzeile der App aus.

1. Wählen Sie das Symbol **Bearbeiten** aus.

1. In dem Bereich **Umgebung bearbeiten** gehen Sie zum Schritt **Grundinformation**.

1. In dem Feld **Eigentümer der Umgebung ändern** wählen Sie den neuen Eigentümer der Umgebung aus.  

1. Wählen Sie **Überprüfen und beenden** und dann **Aktualisieren**, um die Änderungen zu übernehmen.

## <a name="claim-ownership-of-an-environment"></a>Beanspruchen Sie den Besitz einer Umgebung

Wenn das Benutzerkonto des Eigentümers gelöscht oder gesperrt wird, hat die Umgebung keinen Eigentümer mehr. Jeder Benutzer mit Administratorberechtigungen kann die Eigentümerschaft beanspruchen und der neue Eigentümer werden. Der Besitzer Admin kann weiterhin die Umgebung besitzen oder [den Besitz auf einen anderen Administrator übertragen](#change-the-owner-of-an-environment).

Um den Besitz zu beanspruchen, wählen Sie die Schaltfläche **In Besitz nehmen** aus, die oben auf jeder Seite in Customer Insights angezeigt wird, wenn der ursprüngliche Eigentümer die Organisation verlassen hat.

## <a name="reset-an-existing-environment-preview"></a>Eine vorhandene Umgebung zurücksetzen (Vorschauversion)

Als Besitzer einer Umgebung können Sie eine Umgebung auf einen leeren Zustand zurücksetzen, wenn Sie nur die Konfigurationen und eingebundene Daten entfernen, die Umgebung jedoch behalten möchten.

1. Wählen Sie die **Umgebung**-Auswahl in der Kopfzeile der App aus.

1. Wählen Sie die Umgebung aus, die Sie zurücksetzen möchten, und wählen Sie die vertikalen Auslassungspunkte (&vellip;).

1. Wählen Sie **Zurücksetzen (Vorschauversion)** aus.

   :::image type="content" source="media/reset-environment.png" alt-text="Steuerelement zum Zurücksetzen einer Umgebung.":::

1. Wählen Sie aus, ob Sie die gesamte Umgebung zurücksetzen möchten, alles außer den Datenquellen oder alles, was über dem Unified Customer Profile konfiguriert ist.

1. Geben Sie zur Bestätigung den Namen der Umgebung ein und wählen Sie **Zurücksetzen**.

## <a name="delete-an-existing-environment"></a>Löschen Sie eine vorhandene Umgebung

Als Eigentümer einer Umgebung können Sie diese löschen.

> [!IMPORTANT]
> Das Löschen einer Umgebung entfernt nicht die Verbindung zu einer Dataverse Umgebung. Wenn Sie vorhaben, dieselbe Dataverse Umgebung mit einer neuen Customer Insights-Umgebung in der Zukunft zu verbinden, müssen Sie diese Verbindung entfernen. Erfahren Sie, wie Sie [eine bestehende Verbindung zu einer Dataverse Umgebung entfernen](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

1. Wählen Sie die **Umgebung**-Auswahl in der Kopfzeile der App aus.

1. Wählen Sie die Umgebung aus, die Sie löschen möchten, und wählen Sie die vertikalen Auslassungspunkte (&vellip;). 

1. Wählen Sie **Löschen**.

   :::image type="content" source="media/delete-environment.png" alt-text="Steuerelement zum Löschen der Umgebung":::

1. Um das Löschen zu bestätigen, geben Sie den Namen der Umgebung ein und wählen Sie **Löschen**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
