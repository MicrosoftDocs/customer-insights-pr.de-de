---
title: Neue Umgebung erstellen
description: Schritte zum Erstellen von Umgebungen in Dynamics 365 Customer Insights.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304242"
---
# <a name="create-a-new-environment"></a>Neue Umgebung erstellen

Nach dem [Kauf einer Abonnementlizenz für Dynamics 365 Customer Insights](paid-license.md) erhält der globale Administrator des Microsoft 365-Mandanten eine E-Mail, die ihn auffordert, die Umgebung zu erstellen. Gehen Sie zu [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start), um anzufangen. In diesem Szenario können Sie direkt zu [Schritt 1: Geben Sie grundlegende Informationen an](#step-1-provide-basic-information) gehen.

Nachdem die erste Umgebung erstellt wurde, kann der globale Administrator des Microsoft 365-Mandanten [Benutzer aus der Organisation als Administratoren hinzufügen](permissions.md). Diese  Administratoren können dann Benutzer und Umgebungen verwalten. Wenn Ihre Organisation mehr als eine Lizenz für Customer Insights erwirbt, [kontaktieren Sie unser Support-Team](https://go.microsoft.com/fwlink/?linkid=2079641), um die Anzahl der verfügbaren Umgebungen zu erhöhen. Weitere Informationen zur Kapazität und zu Add-On-Kapazitäten finden Sie in der [Lizenzierungsanleitung für Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544). Sobald Sie die Möglichkeit haben, zusätzliche Umgebungen zu erstellen, gehen Sie zu [ Starten Sie den Umgebungserstellungsprozess](#start-the-environment-creation-process).

> [!TIP]
> Wenn Sie den Dienst ausprobieren möchten, lesen Sie [Testumgebung einrichten](trial-signup.md).

## <a name="prerequisites"></a>Anforderungen

[Administratorberechtigungen](permissions.md) in Customer Insights

## <a name="start-the-environment-creation-process"></a>Starten Sie den Umgebungserstellungsprozess

1. Öffnen Sie die Umgebungsauswahl und wählen Sie **+ Neu**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Wählen Sie die Umgebung aus.":::

1. Befolgen Sie die in den folgenden Abschnitten beschriebenen Anleitungen, um alle erforderlichen Informationen für eine neue Umgebung bereitzustellen.

## <a name="step-1-provide-basic-information"></a>Schritt 1: Geben Sie grundlegende Informationen an

1. Wählen Sie, ob Sie eine Umgebung von Grund auf neu erstellen möchten oder Daten aus einer anderen Umgebung kopieren. [Kopieren von Daten aus einer anderen Umgebung](#copy-the-environment-configuration) erfordert zusätzliche Schritte.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialog zum Erstellen einer neuen Customer Insights-Umgebung.":::

1. Geben Sie die folgenden Informationen an:

   - **Name**: Name für diese Umgebung. Dieses Feld ist bereits ausgefüllt, wenn Sie eine bestehende Umgebung kopiert haben, aber Sie können es ändern.
   - **Unternehmen wählen**: Primäre Zielgruppe für die neue Umgebung: individuelle Konsumenten (B-to-C) oder [Geschäftskunden](work-with-business-accounts.md) (B-to-B). Wenn Ihre Organisation hauptsächlich mit Einzelpersonen Geschäfte macht, wie z. B. ein Einzelhändler oder ein Café, wählen Sie einzelne Verbraucher aus. Falls Ihre wichtigste Zielgruppe andere Unternehmen sind, wie z. B. ein Autohersteller oder eine Papierfirma, wählen Sie Geschäftskonten.
   - **Typ**: Umgebungstyp: Produktion oder Sandbox. Sandbox-Umgebungen lassen keine geplante Datenaktualisierung zu und sind für die Vorimplementierung und das Testen gedacht. Sandbox-Umgebungen verwenden dieselbe primäre Zielgruppe wie die aktuell ausgewählte Produktionsumgebung.
   - **Region**: Region, in der der Dienst bereitgestellt und gehostet wird. Um [Ihr eigenes Azure Data Lake Storage-Konto zu verwenden](own-data-lake-storage.md) oder [mit einer bestehenden Microsoft Dataverse-Organisation zu verbinden](customer-insights-dataverse.md), muss sich die Customer Insights-Umgebung in derselben Region befinden.

1. Wählen Sie **Weiter** aus.

## <a name="step-2-configure-data-storage"></a>Schritt 2: Datenschritt konfigurieren

1. Wählen Sie ais, wo die Customer Insights Daten gespeichert werden:

   - **Customer Insights-Speicher**: Der Datenspeicher wird automatisch verwaltet. Dies ist die Standardoption, und sofern keine besonderen Anforderungen zum Speichern von Daten in Ihrem eigenen Speicherkonto bestehen, empfehlen wir die Verwendung dieser Option.
   - **Azure Data Lake Storage**: Geben Sie ein eigenes Azure Data Lake Storage-Konto an, um die Daten zu speichern, sodass Sie die volle Kontrolle darüber haben, wo die Daten gespeichert werden. Folgen Sie den Schritten in [Verwenden Sie Ihr eigenes Azure Data Lake Storage Konto](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Wählen Sie die bevorzugte Option, um Ihre Daten zu speichern.":::

1. Wählen Sie **Weiter** aus.

## <a name="step-3-connect-to-microsoft-dataverse"></a>Schritt 3: Mit Microsoft Dataverse verbinden

Wenn Sie eine Dataverse Umgebung haben, verbinden Sie Customer Insights. Teilen Sie Daten mit Dataverse, um sie mit Geschäftsanwendungen zu nutzen, die auf Dataverse basieren, wie Dynamics 365 Marketing oder modellgesteuerte Anwendungen in Power Apps.

1. Folgen Sie den Schritten in [Arbeiten Sie mit Customer Insights-Daten in Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="Datenaustausch mit Microsoft Dataverse automatisch für neue Umgebungen aktiviert.":::

1. Wählen Sie **Weiter** aus.

## <a name="step-4-finalize-the-settings"></a>Schritt 4: Einstellungen abschließen

Spezifische Einstellungen überprüfen. Wenn alles fertig aussieht, wählen Sie **Erstellen**, um die Umgebung einzurichten.

Informationen zum späteren Ändern einiger Einstellungen finden Sie unter [Umgebungen verwalten](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Arbeiten Sie mit Ihrer neuen Umgebung

Lesen Sie die folgenden Artikel, um Ihnen den Einstieg in die Konfiguration von Customer Insights zu erleichtern:

- [Weitere Benutzer hinzufügen und Berechtigungen zuweisen](permissions.md).
- [Erfassen Sie Ihre Datenquellen](data-sources.md) und führen sie sie mit dem [Datenvereinheitlichungsprozess](data-unification.md) aus, um [einheitliche Kundenprofile](customer-profiles.md) zu erhalten.
- [Reichern Sie die einheitlichen Kundenprofile an](enrichment-hub.md) oder [führen Sie Vorhersagemodelle aus](predictions-overview.md).
- [Erstellen Sie Segmente](segments.md), um Kunden zu gruppieren und [Maßnahmen](measures.md), um KPIs zu überprüfen.
- [Verbindungen](connections.md) und [Exporte](export-destinations.md) einrichten, um Teilmengen Ihrer Daten in anderen Anwendungen zu verarbeiten.

## <a name="copy-the-environment-configuration"></a>Umgebungskonfiguration kopieren

Wenn Sie als Administrator die Konfiguration aus einer vorhandenen Umgebung kopieren möchten, wählen Sie aus der Liste aller verfügbaren Umgebungen in Ihrer Organisation aus.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Screenshot der Einstellungsoptionen in den Umgebungseinstellungen.":::

Folgende Konfigurationseinstellungen werden kopiert:

- Mit Power Query importierte Datenquellen
- Konfiguration der Datenvereinheitlichung
- Segmente
- Measures
- Beziehungen
- Aktivitäten
- Such- und Filterindex
- Exporte
- Zeitplan aktualisieren
- Anreicherungen
- Vorhersagemodelle
- Zuweisungen von Rollen

### <a name="set-up-a-copied-environment"></a>Einrichten einer kopierten Umgebung

Wenn Sie die Umgebungskonfiguration kopieren, wird eine Bestätigungsmeldung angezeigt, dass die Umgebung kopiert wurde. Um die Anmeldeinformationen auszuführen, müssen Sie die folgenden Schritte durchführen:

1. Wählen Sie **Gehen Sie zu Datenquellen**, um die Liste der Datenquellen anzuzeigen. Alle Datenquellen zeigen einen Status **Anmeldeinformationen erforderlich**.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Liste der Datenquellen, die kopiert wurden und eine Authentifizierung benötigen.":::

1. Bearbeiten Sie die Datenquellen und geben Sie die Anmeldeinformationen ein, um sie zu aktualisieren. Datenquellen aus dem Common Data Model-Ordner und Dataverse muss manuell mit demselben Namen wie in der Quellumgebung erstellt werden.

1. Nachdem Sie die Datenquellen aktualisiert haben, gehen Sie zu **Daten** > **Vereinheitlichen**. Hier finden Sie Einstellungen aus der Quellumgebung. Bearbeiten Sie sie nach Bedarf oder wählen Sie **Vereinheitlichen** > **Kundenprofile und Abhängigkeiten vereinheitlichen**, um den Datenvereinheitlichungsprozess zu starten und die einheitliche Kundenentität zu erstellen.

   > [!TIP]
   > Wählen Sie für Konten und Kontakte **Konten vereinheitlichen** > **Profile und Abhängigkeiten vereinheitlichen**.

1. Wenn die Datenvereinheitlichung abgeschlossen ist, gehen Sie zu **Maßnahmen** und **Segmente**, um sie auch zu aktualisieren.

1. Gehen Sie zu **Administrator** > **Verbindungen**, um die Verbindungen in Ihrer neuen Umgebung erneut zu authentifizieren.

1. Gehen Sie zu **Daten** > **Anreicherung** und **Daten** > **Exporte**, um sie zu reaktivieren.

[!INCLUDE [footer-include](includes/footer-banner.md)]
