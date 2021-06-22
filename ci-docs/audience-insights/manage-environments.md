---
title: Erstellen und Verwalten von Umgebungen
description: Erfahren Sie, wie Sie sich für den Dienst anmelden und wie Sie Umgebungen verwalten können.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 06310ea6fc72f26e21e185a6abcb5d19d4b201f6
ms.sourcegitcommit: e5425f060c8d80f9510283dc610ce70a4e709b1e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2021
ms.locfileid: "6259098"
---
# <a name="manage-environments"></a>Umgebungen verwalten

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dieser Artikel erklärt, wie Sie eine neue Organisation erstellen und wie Sie eine Umgebung bereitstellen.

## <a name="sign-up-and-create-an-organization"></a>Melden Sie sich an und erstellen Sie eine Organisation

1. Wechseln Sie zur Website von [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).

2. Wählen Sie **Erste Schritte** aus.

3. Wählen Sie Ihr bevorzugtes Anmeldeszenario und wählen Sie den entsprechenden Link aus.

4. Akzeptieren Sie die allgemeinen Geschäftsbedingungen und wählen Sie **Fortsetzen** aus, um mit dem Erstellen der Organisation zu beginnen.

5. Nachdem die Umgebung erstellt wurde, werden Sie zu [Customer Insights](https://home.ci.ai.dynamics.com) weitergeleitet.

6. Verwenden Sie die Demo-Umgebung, um die Anwendung zu erkunden, oder erstellen Sie eine neue Umgebung, indem Sie den Schritten im nächsten Abschnitt folgen.

7. Nachdem Sie die Umgebungseinstellungen angegeben haben, wählen Sie **Erstellen** aus.

8. Nachdem die Umgebung erfolgreich erstellt wurde, werden Sie angemeldet.

## <a name="create-an-environment-in-an-existing-organization"></a>Eine Umgebung in einer vorhandenen Organisation erstellen

Beim Erstellen einer neuen Umgebung, gibt es zwei Möglichkeiten. Sie können entweder eine völlig neue Konfiguration angeben oder Sie können einige Konfigurationseinstellungen aus einer vorhandenen Umgebung kopieren.

> [!NOTE]
> Organisationen können *zwei* Umgebungen für jede Customer Insights-Lizenz erstellen. Wenn Ihre Organisation mehr als eine Lizenz erwirbt, [kKontaktieren Sie unser Support-Team](https://go.microsoft.com/fwlink/?linkid=2079641), um die Anzahl der verfügbaren Umgebungen zu erhöhen. Weitere Informationen zu Kapazität und Zusatzkapazität finden Sie im [Dynamics 365-Lizenzierungshandbuch](https://go.microsoft.com/fwlink/?LinkId=866544).

So erstellen Sie eine Umgebung:

1. Wählen Sie die **Umgebung**-Auswahl in der Kopfzeile der App aus.

1. Wählen Sie **Neu**.

   > [!div class="mx-imgBorder"]
   > ![Umgebungseinstellungen](media/environment-settings-dialog.png)

1. Im **Neue Umgebung erstellen**-Dialog wählen Sie **Neue Umgebung** aus.

   Wenn Sie [Daten aus der aktuellen Umgebung kopieren](#considerations-for-copy-configuration-preview) wollen, wählen Sie **Aus vorhandener Umgebung kopieren** aus. Sie sehen eine Liste aller verfügbaren Umgebungen in Ihrer Organisation, aus der Sie Daten kopieren können.

1. Geben Sie die folgenden Informationen an:
   - **Name**: Der Name für diese Umgebung. Dieses Feld ist bereits ausgefüllt, wenn Sie eine bestehende Umgebung kopiert haben, aber Sie können es ändern.
   - **Region**: Die Region, in der der Dienst bereitgestellt und gehostet wird.
   - **Typ**: Wählen Sie, ob Sie eine Produktions- oder Sandbox-Umgebung erstellen möchten.

1. Optional können Sie **Erweiterte Einstellungen** auswählen:

   - **Sichern alle Daten**: Geben Sie an, wo Sie die aus Customer Insights generierten Ausgabedaten speichern möchten. Sie haben zwei Möglichkeiten: **Customer Insights-Speicherung** (ein vom Customer Insights-Team verwalteter Azure Data Lake) und **Azure Data Lake Storage Gen2** (Ihre eigene Azure Data Lake Storage). Standardmäßig ist die Speicheroption „Customer Insights“ ausgewählt.

   > [!NOTE]
   > Durch die Speicherung von Daten in Azure Data Lake Storage erklären Sie sich damit einverstanden, dass die Daten an den für dieses Azure Storage-Konto geeigneten geografischen Ort übertragen und dort gespeichert werden. Dieser kann von dem Ort abweichen, an dem die Daten in Dynamics 365 Customer Insights gespeichert sind. [Weitere Informationen finden Sie im Microsoft Trust Center.](https://www.microsoft.com/trust-center)
   >
   > Derzeit werden aufgenommene Entitäten immer im verwalteten Customer Insights Data Lake gespeichert.
   > Wir unterstützen nur Azure Data Lake Gen2-Speicherkonten aus derselben Azure-Region, die Sie beim Erstellen der Umgebung ausgewählt haben.
   > Wir unterstützen nur Azure Data Lake Gen2 hierarchische Name Space (HNS) aktivierte Speicherkonten.

   - Für die Option Azure Data Lake Storage Gen2 können Sie zwischen einer ressourcenbasierten Option und einer abonnementbasierten Option für die Authentifizierung wählen. Weitere Informationen finden Sie unter [Verbinden Sie Zielgruppen-Insights mit einem Azure Data Lake Storage Gen2-Konto mit einem Azure-Dienstprinzipal](connect-service-principal.md). Der Name unter **Container** kann nicht geändert werden und lautet `customerinsights`.
   
   - Wenn Sie [Vorhersagen](predictions.md) verwenden möchten, konfigurieren Sie die Datenfreigabe mit Microsoft Dataverse oder aktivieren Sie die Datenerfassung aus lokalen Datenquellen, stellen Sie die Microsoft Dataverse-Umgebungs-URL unter **Datenfreigabe mit Microsoft Dataverse konfigurieren** bereit und aktivieren Sie zusätzliche Funktionen. Wählen Sie **Datenfreigabe aktivieren** aus, um die Ausgabedaten von Customer Insights mit einem verwalteten Microsoft Dataverse Data Lake zu teilen.

     > [!NOTE]
     > - Datenaustausch mit verwaltetem Microsoft Dataverse Data Lake wird derzeit nicht unterstützt, wenn Sie alle Daten in Ihrem eigenen Azure Data Lake Storage speichern.
     > - [Vorhersage fehlenden Werte in einer Entität](predictions.md) wird derzeit nicht unterstützt, wenn Sie die Datenfreigabe mit verwaltetem Microsoft Dataverse Data Lake aktivieren.

     > [!div class="mx-imgBorder"]
     > ![Konfigurationsoptionen zum Aktivieren der Datenfreigabe mit Microsoft Dataverse](media/datasharing-with-DataverseMDL.png)

   Wenn Sie Prozesse ausführen, wie z.B. die Datenerfassung oder die Segmenterstellung, werden entsprechende Ordner in dem oben angegebenen Speicherkonto erstellt. Abhängig vom ausgeführten Prozess werden Datendateien und model.json-Dateien erstellt und basierend auf dem Prozessnamen Ordnern hinzugefügt.

   Wenn Sie mehrere Umgebungen von Customer Insights erstellen und die ausgegebenen Entitäten aus diesen Umgebungen in Ihrem Speicherkonto speichern möchten, werden für jede Umgebung separate Ordner mit ci_<environmentid> im Container erstellt.

### <a name="considerations-for-copy-configuration-preview"></a>Überlegungen zur Kopierkonfiguration (Vorschau)

Folgende Konfigurationseinstellungen werden kopiert:

- Konfigurationen von Funktionen
- Aufgenommene/importierte Datenquellen
- Datenvereinheitlichung (Map, Match, Merge) Konfiguration
- Segmente
- Kennzahlen
- Beziehungen
- Aktivitäten
- Index suchen & filtern
- Exportziele
- Geplante Aktualisierung
- Ergänzungen
- Modell-Management
- Zuweisungen von Rollen

Folgende Konfigurationseinstellungen werden *nicht* kopiert:

- Kundenprofile.
- Anmeldeinformationen für die Datenquelle. Sie müssen die Anmeldeinformationen für jede Datenquelle angeben und die Datenquellen manuell aktualisieren.
- Datenquellen aus dem Common Data Model-Ordner und Common Data Service verwalteter Lake. Sie müssen diese Datenquellen manuell mit demselben Namen wie in der Quellumgebung erstellen.

Wenn Sie eine Umgebung kopieren, wird eine Bestätigungsmeldung angezeigt, dass die neue Umgebung erstellt wurde. Wählen Sie **Gehen Sie zu Datenquellen**, um die Liste der Datenquellen anzuzeigen.

Alle Datenquellen zeigen einen Status **Anmeldeinformationen erforderlich**. Bearbeiten Sie die Datenquellen und geben Sie die Anmeldeinformationen ein, um sie zu aktualisieren.

> [!div class="mx-imgBorder"]
> ![Datenquellen kopiert](media/data-sources-copied.png)

Nachdem Sie die Datenquellen aktualisiert haben, gehen Sie zu **Daten** > **Vereinheitlichen**. Hier finden Sie Einstellungen aus der Quellumgebung. Bearbeiten Sie sie nach Bedarf oder wählen Sie **Ausführen**, um den Datenvereinheitlichungsprozess zu starten und die einheitliche Kundenentität zu erstellen.

Wenn die Datenvereinheitlichung abgeschlossen ist, gehen Sie zu **Maßnahmen** und **Segmente**, um sie auch zu aktualisieren.

## <a name="edit-an-existing-environment"></a>So bearbeiten Sie eine bestehende Umgebung

Sie können einige Details vorhandener Umgebungen bearbeiten.

1.  Wählen Sie die **Umgebung**-Auswahl in der Kopfzeile der App aus.

2.  Wählen Sie das Symbol **Bearbeiten** aus.

3. Im Feld **Umgebung bearbeiten** können Sie den **Anzeigename** der Umgebung aktualisieren, Sie können jedoch nicht die **Region** oder den **Art** ändern.

4. Wenn eine Umgebung zum Speichern von Daten in Azure Data Lake Storage Gen2 konfiguriert ist, können Sie den **Kontoschlüssel** aktualisieren. Sie können jedoch nicht den Namen **Kontoname** oder **Container** ändern.

5. Optional können Sie von einer kontoschlüsselbasierten Verbindung zu einer ressourcenbasierten oder abonnementbasierten Verbindung aktualisieren. Nach der Aktualisierung können Sie nicht mehr zum Kontenschlüssel zurückkehren. Weitere Informationen finden Sie unter [Verbinden Sie Zielgruppen-Insights mit einem Azure Data Lake Storage Gen2-Konto mit einem Azure-Dienstprinzipal](connect-service-principal.md). Sie können die **Container**-Informationen beim Aktualisieren der Verbindung nicht ändern.

6. Optional können Sie eine Microsoft Dataverse-Umgebungs-URL unter **Datenfreigabe mit Microsoft Dataverse konfigurieren und zusätzliche Funktionen aktivieren** bereitstellen. Diese Funktionen umfassen die gemeinsame Nutzung von Daten mit Anwendungen und Lösungen, die auf Microsoft Dataverse, der Datenerfassung aus lokalen Datenquellen oder der Verwendung von [Vorhersagen](predictions.md) basieren. Wählen Sie **Datenfreigabe aktivieren** aus, um die Ausgabedaten von Customer Insights mit einem verwalteten Microsoft Dataverse Data Lake zu teilen.

   > [!NOTE]
   > - Datenaustausch mit verwaltetem Microsoft Dataverse Data Lake wird derzeit nicht unterstützt, wenn Sie alle Daten in Ihrem eigenen Azure Data Lake Storage speichern.
   > - [Vorhersage fehlender Werte in einer Entität](predictions.md) wird derzeit nicht unterstützt, wenn Sie die Datenfreigabe mit Microsoft Dataverse Managed Data Lake aktivieren.

   Nach der Aktivierung der Datenfreigabe in Microsoft Dataverse startet eine vollständige Aktualisierung der Datenquellen und anderer Prozesse. Wenn derzeit Prozesse ausgeführt werden, wird die Option zum Aktivieren der Datenfreigabe mit Microsoft Dataverse nicht angezeigt. Warten Sie, bis diese Prozesse abgeschlossen sind, oder brechen Sie sie ab, um die gemeinsame Nutzung von Daten zu ermöglichen. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Konfigurationsoptionen zum Aktivieren der Datenfreigabe mit Microsoft Dataverse.":::
   
   Wenn Sie Prozesse ausführen, wie z.B. die Datenerfassung oder die Segmenterstellung, werden entsprechende Ordner in dem oben angegebenen Speicherkonto erstellt. Abhängig vom ausgeführten Prozess werden Datendateien und model.json-Dateien erstellt und den jeweiligen Unterordnern hinzugefügt.

## <a name="reset-an-existing-environment"></a>Zurücksetzen einer bestehenden Umgebung

Als Administrator können Sie eine Umgebung auf einen leeren Zustand zurücksetzen, wenn Sie alle Konfigurationen löschen und die aufgenommenen Daten entfernen möchten.

1.  Wählen Sie die **Umgebung**-Auswahl in der Kopfzeile der App aus. 

2.  Wählen Sie die Umgebung aus, die Sie zurücksetzen möchten, und wählen Sie die Auslassungspunkte **...** aus. 

3. Wählen Sie die Option **Zurücksetzen** aus. 

4.  Um das Löschen zu bestätigen, geben Sie den Namen der Umgebung ein und wählen Sie **Zurücksetzen**.

## <a name="delete-an-existing-environment-available-only-for-admins"></a>Löschen Sie eine vorhandene Umgebung (nur für Administratoren verfügbar).

Als Administrator können Sie eine von Ihnen verwaltete Umgebung löschen.

1.  Wählen Sie die **Umgebung**-Auswahl in der Kopfzeile der App aus.

2.  Wählen Sie die Umgebung aus, die Sie zurücksetzen möchten, und wählen Sie die Auslassungspunkte **...** aus. 

3. Wählen Sie die Option **Löschen** aus. 

4.  Um das Löschen zu bestätigen, geben Sie den Namen der Umgebung ein und wählen Sie **Löschen**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
