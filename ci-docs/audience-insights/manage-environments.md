---
title: Erstellen und Verwalten von Umgebungen
description: Erfahren Sie, wie Sie sich für den Dienst anmelden und wie Sie Umgebungen verwalten können.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644132"
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

So erstellen Sie eine Umgebung:

1. Wählen Sie das Symbol **Einstellungen** in der Kopfzeile der App aus.

1. Wählen Sie **Neue Umgebung** aus.

   > [!div class="mx-imgBorder"]
   > ![Umgebungseinstellungen](media/environment-settings-dialog.png)

1. Im **Neue Umgebung erstellen**-Dialog wählen Sie **Neue Umgebung** aus.

   Wenn Sie [Daten aus der aktuellen Umgebung kopieren](#additional-considerations-for-copy-configuration-preview) wollen, wählen Sie **Aus vorhandener Umgebung kopieren** aus. Sie sehen eine Liste aller verfügbaren Umgebungen in Ihrer Organisation, aus der Sie Daten kopieren können.

1. Geben Sie die folgenden Informationen an:
   - **Name**: Der Name für diese Umgebung. Dieses Feld ist bereits ausgefüllt, wenn Sie eine bestehende Umgebung kopiert haben, aber Sie können es ändern.
   - **Region**: Die Region, in der der Dienst bereitgestellt und gehostet wird.
   - **Typ**: Wählen Sie, ob Sie eine Produktions- oder Sandbox-Umgebung erstellen möchten.

2. Optional können Sie **Erweiterte Einstellungen** auswählen:

   - **Sichern alle Daten**: Geben Sie an, wo Sie die aus Customer Insights generierten Ausgabedaten speichern möchten. Sie haben zwei Möglichkeiten: **Customer Insights-Speicherung** (ein vom Customer Insights-Team verwalteter Azure Data Lake) und **Azure Data Lake Storage Gen2** (Ihre eigene Azure Data Lake Storage). Standardmäßig ist die Speicheroption „Customer Insights“ ausgewählt.

   > [!NOTE]
   > Durch die Speicherung von Daten in Azure Data Lake Storage erklären Sie sich damit einverstanden, dass die Daten an den für dieses Azure Storage-Konto geeigneten geografischen Ort übertragen und dort gespeichert werden. Dieser kann von dem Ort abweichen, an dem die Daten in Dynamics 365 Customer Insights gespeichert sind. [Weitere Informationen finden Sie im Microsoft Trust Center.](https://www.microsoft.com/trust-center)
   >
   > Derzeit werden aufgenommene Entitäten immer im verwalteten Customer Insights Data Lake gespeichert.
   > Wir unterstützen nur Azure Data Lake Gen2-Speicherkonten aus derselben Azure-Region, die Sie beim Erstellen der Umgebung ausgewählt haben.
   > Wir unterstützen nur Azure Data Lake Gen2 hierarchische Name Space (HNS) aktivierte Speicherkonten.

   - Für die Option Azure Data Lake Storage Gen2 können Sie zwischen einer ressourcenbasierten Option und einer abonnementbasierten Option für die Authentifizierung wählen. Weitere Informationen finden Sie unter [Verbinden Sie Zielgruppen-Insights mit einem Azure Data Lake Storage Gen2-Konto mit einem Azure-Dienstprinzipal](connect-service-principal.md). Der **Container**-Name kann nicht geändert werden und wird „customerinsights“ lauten.
   
   - Wenn Sie [Vorhersagen](predictions.md) verwenden wollen, geben Sie die Common Data Service Instanz-URL im Feld **Serveradresse** unter **Vorhersagen verwenden** ein.

   Wenn Sie Prozesse ausführen, wie z.B. die Datenerfassung oder die Segmenterstellung, werden entsprechende Ordner in dem oben angegebenen Speicherkonto erstellt. Datendateien und model.json-Dateien werden basierend auf dem von Ihnen ausgeführten Prozess erstellt und den jeweiligen Unterordnern hinzugefügt.

   Wenn Sie mehrere Umgebungen von Customer Insights erstellen und die ausgegebenen Entitäten aus diesen Umgebungen in Ihrem Speicherkonto speichern möchten, werden für jede Umgebung separate Ordner mit ci_<environmentid> im Container erstellt.

### <a name="additional-considerations-for-copy-configuration-preview"></a>Zusätzliche Überlegungen zur Kopierkonfiguration (Vorschau)

Folgende Konfigurationseinstellungen werden kopiert:

- Konfigurationen von Funktionen
- Inegistrierte/importierte Datenquellen
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

1. Wechseln Sie zu **Admin** > **System** > **Info**.

2. Wählen Sie **Bearbeiten**.

3. Sie können den **Anzeigename** der Umgebung aktualisieren, aber Sie können die **Region** oder **Typ** nicht ändern.

4. Wenn eine Umgebung zum Speichern von Daten in Azure Data Lake Storage Gen2 konfiguriert ist, können Sie den **Kontoschlüssel** aktualisieren. Sie können jedoch nicht den Namen **Kontoname** oder **Container** ändern.

5. Optional können Sie von einer kontoschlüsselbasierten Verbindung zu einer ressourcenbasierten oder abonnementbasierten Verbindung aktualisieren. Nach der Aktualisierung können Sie nicht mehr zum Kontenschlüssel zurückkehren. Weitere Informationen finden Sie unter [Verbinden Sie Zielgruppen-Insights mit einem Azure Data Lake Storage Gen2-Konto mit einem Azure-Dienstprinzipal](connect-service-principal.md). Sie können die **Container**-Informationen beim Aktualisieren der Verbindung nicht ändern.

## <a name="reset-an-existing-environment"></a>Zurücksetzen einer bestehenden Umgebung

Sie können eine Umgebung auf einen leeren Zustand zurücksetzen, wenn Sie alle Konfigurationen löschen und die aufgenommenen Daten entfernen möchten.

1.  Wechseln Sie zu **Admin** > **System** > **Info**.

2.  Wählen Sie **Zurücksetzen**. 

3.  Um das Löschen zu bestätigen, geben Sie den Namen der Umgebung ein und wählen Sie **Zurücksetzen**.


## <a name="delete-an-existing-environment"></a>Löschen Sie eine vorhandene Umgebung

1. Wechseln Sie zu **Admin** > **System** > **Info**.

1. Klicken Sie auf **Löschen**.

1. Um das Löschen zu bestätigen, geben Sie den Namen der Umgebung ein und wählen Sie **Löschen**.
