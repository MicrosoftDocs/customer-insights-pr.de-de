---
title: Erstellen und Verwalten von Umgebungen
description: Erfahren Sie, wie Sie sich für den Dienst anmelden und wie Sie Umgebungen verwalten können.
ms.date: 12/06/2021
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: d9e0ee726dbbfcf330022c4d95747551d3114e7e
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354278"
---
# <a name="manage-environments"></a>Umgebungen verwalten



## <a name="switch-environments"></a>Umgebungen wechseln

Wählen Sie die Option **Umgebung** in der rechten oberen Ecke der Seite, um die Umgebung zu ändern.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Screenshot des Steuerelements zum Wechseln der Umgebung.":::

Administratoren können Umgebungen [erstellen](create-environment.md) und verwalten.

## <a name="edit-an-existing-environment"></a>So bearbeiten Sie eine bestehende Umgebung

Sie können einige Details vorhandener Umgebungen bearbeiten.

1.  Wählen Sie die **Umgebung**-Auswahl in der Kopfzeile der App aus.

2.  Wählen Sie das Symbol **Bearbeiten** aus.

3. In dem Kästchen **Umgebung bearbeiten** können Sie die Umgebungseinstellungen aktualisieren.

Weitere Informationen zu Umgebungseinstellungen finden Sie unter [Schaffen Sie eine neue Umgebung](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Mit Microsoft Dataverse verbinden
   
Mit dem **Microsoft Dataverse** Schritt können Sie Customer Insights mit Ihrer Dataverse Umgebung verbinden.

Benutzen Sie [Standardmäßige Vorhersage-Modelle](predictions-overview.md#out-of-box-models), konfigurieren Sie Datenfreigaben mit Dataverse. Oder Sie können die Datenaufnahme aus lokale Datenquellen aktivieren, indem Sie die Microsoft Dataverse Umgebungs-URL bereitstellen, die Ihre Organisation verwaltet.

> [!IMPORTANT]
> Customer Insights und Dataverse müssen sich in derselben Region befinden, um die Datenfreigabe zu ermöglichen.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Konfigurationsoptionen zum Aktivieren der Datenfreigabe mit Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights unterstützt die folgenden Datenfreigabe-Szenarien nicht:
> - Wenn Sie alle Daten selbst speichern in Azure Data Lake Storage können Sie die Datenfreigabe mit einem verwalteten Dataverse Data Lake nicht aktivieren.
> - Wenn Sie die Datenfreigabe mit einem verwalteten Dataverse Data Lake aktivieren, können Sie keine [vorhergesagten oder fehlenden Werten in einer Entität erstellen](predictions.md).

## <a name="copy-the-environment-configuration"></a>Umgebungskonfiguration kopieren

Wenn Sie eine neue Umgebung erstellen, können Sie die Konfiguration aus einer vorhandenen Umgebung kopieren. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Screenshot der Einstellungsoptionen in den Umgebungseinstellungen.":::

Sie sehen eine Liste aller verfügbaren Umgebungen in Ihrer Organisation, aus der Sie Daten kopieren können.

Folgende Konfigurationseinstellungen werden kopiert:

- Aufgenommene/importierte Datenquellen
- Datenvereinheitlichung (Map, Match, Merge) Konfiguration
- Segmente
- Kennzahlen
- Beziehungen
- Aktivitäten
- Index suchen & filtern
- Exportziele
- Geplante Aktualisierung
- Anreicherungen
- Modell-Management
- Zuweisungen von Rollen

Die folgenden Daten werden *nicht* kopiert:

- Kundenprofile.
- Anmeldeinformationen für die Datenquelle. Sie müssen die Anmeldeinformationen für jede Datenquelle angeben und die Datenquellen manuell aktualisieren.

- Datenquellen aus dem Common Data Model-Ordner und Dataverse-verwalteter Data Lake. Sie müssen diese Datenquellen manuell mit demselben Namen wie in der Quellumgebung erstellen.

Wenn Sie eine Umgebung kopieren, wird eine Bestätigungsmeldung angezeigt, dass die neue Umgebung erstellt wurde. Wählen Sie **Gehen Sie zu Datenquellen**, um die Liste der Datenquellen anzuzeigen.

Alle Datenquellen zeigen einen Status **Anmeldeinformationen erforderlich**. Bearbeiten Sie die Datenquellen und geben Sie die Anmeldeinformationen ein, um sie zu aktualisieren.

:::image type="content" source="media/data-sources-copied.png" alt-text="Liste der Datenquellen, die kopiert wurden und eine Authentifizierung benötigen.":::

Nachdem Sie die Datenquellen aktualisiert haben, gehen Sie zu **Daten** > **Vereinheitlichen**. Hier finden Sie Einstellungen aus der Quellumgebung. Bearbeiten Sie sie nach Bedarf oder wählen Sie **Ausführen**, um den Datenvereinheitlichungsprozess zu starten und die einheitliche Kundenentität zu erstellen.

Wenn die Datenvereinheitlichung abgeschlossen ist, gehen Sie zu **Maßnahmen** und **Segmente**, um sie auch zu aktualisieren.

## <a name="reset-an-existing-environment"></a>Zurücksetzen einer bestehenden Umgebung

Als Administrator können Sie eine Umgebung auf einen leeren Zustand zurücksetzen, wenn Sie alle Konfigurationen löschen und die aufgenommenen Daten entfernen möchten.

1.  Wählen Sie die **Umgebung**-Auswahl in der Kopfzeile der App aus. 

2.  Wählen Sie die Umgebung aus, die Sie zurücksetzen möchten, und wählen Sie die Auslassungspunkte (**...**) aus. 

3. Wählen Sie die Option **Zurücksetzen** aus. 

4.  Um das Löschen zu bestätigen, geben Sie den Namen der Umgebung ein und wählen Sie **Zurücksetzen**.

## <a name="delete-an-existing-environment"></a>Löschen Sie eine vorhandene Umgebung

Als Administrator können Sie eine von Ihnen verwaltete Umgebung löschen.

1.  Wählen Sie die **Umgebung**-Auswahl in der Kopfzeile der App aus.

2.  Wählen Sie die Umgebung aus, die Sie zurücksetzen möchten, und wählen Sie die Auslassungspunkte (**...**) aus. 

3. Wählen Sie die Option **Löschen** aus. 

4.  Um das Löschen zu bestätigen, geben Sie den Namen der Umgebung ein und wählen Sie **Löschen**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
