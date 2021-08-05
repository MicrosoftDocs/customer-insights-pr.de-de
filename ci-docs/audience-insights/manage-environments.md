---
title: Erstellen und Verwalten von Umgebungen
description: Erfahren Sie, wie Sie sich für den Dienst anmelden und wie Sie Umgebungen verwalten können.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 2f115269b9d07dd118ec18cc48b55de8aea9b5bb
ms.sourcegitcommit: 98267da3f3eddbdfbc89600a7f54e5e664a8f069
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2021
ms.locfileid: "6683472"
---
# <a name="manage-environments"></a>Umgebungen verwalten

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Umgebungen wechseln

Wählen Sie die Option **Umgebung** in der rechten oberen Ecke der Seite, um die Umgebung zu ändern.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Screenshot des Steuerelements zum Wechseln der Umgebung.":::

Administratoren können Umgebungen [erstellen](get-started-paid.md) und verwalten.

## <a name="edit-an-existing-environment"></a>So bearbeiten Sie eine bestehende Umgebung

Sie können einige Details vorhandener Umgebungen bearbeiten.

1.  Wählen Sie die **Umgebung**-Auswahl in der Kopfzeile der App aus.

2.  Wählen Sie das Symbol **Bearbeiten** aus.

3. Im Feld **Umgebung bearbeiten** können Sie den **Anzeigename** der Umgebung aktualisieren, Sie können jedoch nicht die **Region** oder den **Art** ändern.

4. Wenn eine Umgebung zum Speichern von Daten konfiguriert ist in Azure Data Lake Storage, können Sie die **Kontoschlüssel** aktualisieren. Sie können jedoch nicht den Namen **Kontoname** oder **Container** ändern.

5. Optional können Sie von einer kontoschlüsselbasierten Verbindung zu einer ressourcenbasierten oder abonnementbasierten Verbindung aktualisieren. Nach der Aktualisierung können Sie nicht mehr zum Kontenschlüssel zurückkehren. Weitere Informationen finden Sie unter [Verbinden Sie Zielgruppen-Insights mit einem Azure Data Lake Storage Gen2-Konto mit einem Azure-Dienstprinzipal](connect-service-principal.md). Sie können die **Container**-Informationen beim Aktualisieren der Verbindung nicht ändern.

6. Optional können Sie eine Microsoft Dataverse-Umgebungs-URL unter **Datenfreigabe mit Microsoft Dataverse konfigurieren und zusätzliche Funktionen aktivieren** bereitstellen. Diese Funktionen umfassen die gemeinsame Nutzung von Daten mit Anwendungen und Lösungen, die auf Microsoft Dataverse, der Datenerfassung aus lokalen Datenquellen oder der Verwendung von [Vorhersagen](predictions.md) basieren. Wählen Sie **Datenfreigabe aktivieren** aus, um die Ausgabedaten von Customer Insights mit einem verwalteten Microsoft Dataverse Data Lake zu teilen.

   > [!NOTE]
   > - Datenaustausch mit verwaltetem Microsoft Dataverse Data Lake wird derzeit nicht unterstützt, wenn Sie alle Daten in Ihrem eigenen Azure Data Lake Storage speichern.
   > - [Vorhersage fehlender Werte in einer Entität](predictions.md) und PowerBI Embedded-Berichte in Zielgruppenerkenntnisse werden (sofern in Ihrer Umgebung aktiviert) derzeit nicht unterstützt, wenn Sie die Datenfreigabe mit verwalteten Microsoft Dataverse Data Lakes aktivieren.

   Nach der Aktivierung der Datenfreigabe in Microsoft Dataverse startet eine vollständige Aktualisierung der Datenquellen und anderer Prozesse. Wenn derzeit Prozesse ausgeführt werden, wird die Option zum Aktivieren der Datenfreigabe mit Microsoft Dataverse nicht angezeigt. Warten Sie, bis diese Prozesse abgeschlossen sind, oder brechen Sie sie ab, um die gemeinsame Nutzung von Daten zu ermöglichen. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Konfigurationsoptionen zum Aktivieren der Datenfreigabe mit Microsoft Dataverse.":::
   
   Wenn Sie Prozesse ausführen, wie z.B. die Datenerfassung oder die Segmenterstellung, werden entsprechende Ordner in dem oben angegebenen Speicherkonto erstellt. Abhängig vom ausgeführten Prozess werden Datendateien und model.json-Dateien erstellt und den jeweiligen Unterordnern hinzugefügt.

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
- Datenquellen aus dem Ordner Common Data Model und Dataverse verwalteten Data Lake. Sie müssen diese Datenquellen manuell mit demselben Namen wie in der Quellumgebung erstellen.

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
