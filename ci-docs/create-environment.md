---
title: Vorgehensweise – Neue Umgebung erstellen
description: Schritte zum Erstellen von Umgebungen mit Dynamics 365 Customer Insights.
ms.date: 05/31/2022
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
ms.openlocfilehash: 6dfaa09cd80498e9a4e4dea6a07ce6e9d29105e2
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011610"
---
# <a name="how-to-create-a-new-environment"></a>Vorgehensweise: Neue Umgebung erstellen

Nach dem [Kauf einer Abonnementlizenz für Dynamics 365 Customer Insights](paid-license.md) erhält der globale Administrator des Microsoft 365-Mandanten eine E-Mail, die ihn auffordert, die Umgebung zu erstellen. Gehen Sie zu [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start), um anzufangen. In diesem Szenario können Sie direkt zu [Schritt 1: Geben Sie grundlegende Informationen an](#step-1-provide-basic-information) gehen.

Nachdem die erste Umgebung erstellt wurde, kann der globale Administrator des Microsoft 365-Mandanten [Benutzer aus der Organisation als Administratoren hinzufügen](permissions.md). In Zukunft können diese Administratoren Benutzer und Umgebungen verwalten. Wenn Ihre Organisation mehr als eine Lizenz für Customer Insights erwirbt, [kontaktieren Sie unser Support-Team](https://go.microsoft.com/fwlink/?linkid=2079641), um die Anzahl der verfügbaren Umgebungen zu erhöhen. Weitere Informationen zur Kapazität und zu Add-On-Kapazitäten finden Sie in der [Lizenzierungsanleitung für Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Wenn Sie den Dienst ausprobieren möchten, lesen Sie [Testumgebung einrichten](trial-signup.md).

## <a name="prerequisites"></a>Anforderungen

Sie benötigen [Administratorberechtigungen](permissions.md) in Customer Insights, um Umgebungen zu erstellen oder zu verwalten.

## <a name="start-the-environment-creation-process"></a>Starten Sie den Umgebungserstellungsprozess

1. Öffnen Sie die Umgebungsauswahl und wählen Sie **+ Neu**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Wählen Sie die Umgebung aus.":::

1. Befolgen Sie die in den folgenden Abschnitten beschriebenen Anleitungen, um alle erforderlichen Informationen für eine neue Umgebung bereitzustellen. Wenn Sie zuvor eine Umgebung konfiguriert haben, können Sie auch [die Konfiguration kopieren](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>Schritt 1: Geben Sie grundlegende Informationen an

In dem Schritt **Grundinformation** wählen Sie aus, ob Sie eine Umgebung von Grund auf neu erstellen möchten oder [Daten aus einer anderen Umgebung kopieren](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialog zum Erstellen einer neuen Customer Insights-Umgebung.":::

Geben Sie die folgenden Informationen an:

- **Name**: Der Name für diese Umgebung. Dieses Feld ist bereits ausgefüllt, wenn Sie eine bestehende Umgebung kopiert haben, aber Sie können es ändern.
- **Wählen Sie Ihr Unternehmen**: Wählen Sie die primäre Zielgruppe für die neue Umgebung. Sie können mit einzelnen Verbrauchern (B2C) oder mit [Geschäftskonten](work-with-business-accounts.md) (B2B) arbeiten. Wenn Ihre Organisation hauptsächlich mit Einzelpersonen Geschäfte macht, wie z. B. ein Einzelhändler oder ein Café, wählen Sie einzelne Verbraucher aus. Falls Ihre wichtigste Zielgruppe andere Unternehmen sind, wie z. B. ein Autohersteller oder eine Papierfirma, wählen Sie Geschäftskonten.
- **Typ**: Wählen Sie, ob Sie eine Produktions- oder eine Sandbox-Umgebung erstellen möchten. Sandbox-Umgebungen lassen keine geplante Datenaktualisierung zu und sind für die Vorimplementierung und das Testen gedacht. Sandbox-Umgebungen verwenden dieselbe primäre Zielgruppe wie die aktuell ausgewählte Produktionsumgebung.
- **Region**: Die Region, in der der Dienst bereitgestellt und gehostet wird. Um [Ihr eigenes Azure Data Lake Storage-Konto zu verwenden](own-data-lake-storage.md) oder [mit einer bestehenden Microsoft Dataverse-Organisation zu verbinden](customer-insights-dataverse.md), muss sich die Customer Insights-Umgebung in derselben Region befinden.

## <a name="step-2-configure-data-storage"></a>Schritt 2: Datenschritt konfigurieren

Im Schritt **Datenspeicherung** wählen Sie, wo die Customer Insights Daten gespeichert werden sollen.

Dafür gibt es zwei Optionen:

- **Customer Insights-Speicher**: Der Datenspeicher wird vom Customer Insights-Team verwaltet. Dies ist die Standardoption, und sofern keine besonderen Anforderungen zum Speichern von Daten in Ihrem eigenen Speicherkonto bestehen, empfehlen wir die Verwendung dieser Option.
- **Azure Data Lake Storage**: Geben Sie ein eigenes Azure Data Lake Storage-Konto an, um die Daten zu speichern, sodass Sie die volle Kontrolle darüber haben, wo die Daten gespeichert werden. Weitere Informationen finden Sie unter [Eigenes Azure Data Lake Storage-Konto verwenden](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Wählen Sie die bevorzugte Option, um Ihre Daten zu speichern.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>Schritt 3: Mit Microsoft Dataverse verbinden

Mit dem **Microsoft Dataverse** Schritt können Sie Customer Insights mit Ihrer Dataverse Umgebung verbinden. Teilen Sie Daten mit Dataverse, um sie mit Geschäftsanwendungen zu nutzen, die auf Dataverse basieren, wie Dynamics 365 Marketing oder modellgesteuerte Anwendungen in Power Apps.


Lassen Sie dieses Feld leer, wenn Sie keine eigene Dataverse-Umgebung haben und wir erstellen eine für Sie.

Weitere Informationen finden Sie unter [Mit Customer Insights-Daten in Microsoft Dataverse arbeiten](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Datenaustausch mit Microsoft Dataverse automatisch für neue Umgebungen aktiviert.":::

### <a name="step-4-finalize-the-settings"></a>Schritt 4: Einstellungen abschließen

In dem Schritt **Überprüfen** gehen Sie alle angegebenen Einstellungen durch. Wenn alles fertig aussieht, wählen Sie **Erstellen**, um die Umgebung einzurichten.

Sie können die einige Einstellungen auch später ändern. Weitere Informationen finden Sie unter [Umgebungen verwalten](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Arbeiten Sie mit Ihrer neuen Umgebung

Lesen Sie die folgenden Artikel, um Ihnen den Einstieg in die Konfiguration von Customer Insights zu erleichtern:

- [Weitere Benutzer hinzufügen und Berechtigungen zuweisen](permissions.md).
- [Erfassen Sie Ihre Datenquellen](data-sources.md) und führen sie sie mit dem [Datenvereinheitlichungsprozess](data-unification.md) aus, um [einheitliche Kundenprofile](customer-profiles.md) zu erhalten.
- [Reichern Sie die einheitlichen Kundenprofile an](enrichment-hub.md) oder [führen Sie Vorhersagemodelle aus](predictions-overview.md).
- [Erstellen Sie Segmente](segments.md), um Kunden zu gruppieren und [Maßnahmen](measures.md), um KPIs zu überprüfen.
- [Verbindungen](connections.md) und [Exporte](export-destinations.md) einrichten, um Teilmengen Ihrer Daten in anderen Anwendungen zu verarbeiten.

## <a name="copy-the-environment-configuration"></a>Umgebungskonfiguration kopieren

Als Administrator können Sie die Konfiguration aus einer vorhandenen Umgebung kopieren, wenn Sie eine neue erstellen.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Screenshot der Einstellungsoptionen in den Umgebungseinstellungen.":::

Sie sehen eine Liste aller verfügbaren Umgebungen in Ihrer Organisation, aus der Sie Daten kopieren können.

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

## <a name="set-up-a-copied-environment"></a>Einrichten einer kopierten Umgebung

Wenn Sie die Umgebungskonfiguration kopieren, müssen Sie einige zusätzliche Schritte ausführen, um die Anmeldeinformationen zu bestätigen:

- Kundenprofile. Authentifizieren und erfassen Sie zunächst Ihre Datenquellen und führen Sie die Datenvereinheitlichung aus, um die Kundenprofile neu zu erstellen.
- Anmeldeinformationen für die Datenquelle. Sie müssen die Anmeldeinformationen für jedes Datenquelle angeben, um die Datenquellen manuell zu authentifizieren und zu aktualisieren.
- Datenquellen aus dem Common Data Model-Ordner und Dataverse. Sie müssen diese Datenquellen manuell mit demselben Namen wie in der Quellumgebung erstellen.
- Verbindungsgeheimnisse, die für Exporte und Anreicherungen verwendet werden. Sie müssen die Verbindungen erneut authentifizieren und anschließend Anreicherungen und Exporte erneut aktivieren.

Sie sehen eine Bestätigungsnachricht, wenn die kopierte Umgebung erstellt wurde. Wählen Sie **Gehen Sie zu Datenquellen**, um die Liste der Datenquellen anzuzeigen.

Alle Datenquellen zeigen einen Status **Anmeldeinformationen erforderlich**. Bearbeiten Sie die Datenquellen und geben Sie die Anmeldeinformationen ein, um sie zu aktualisieren.

:::image type="content" source="media/data-sources-copied.png" alt-text="Liste der Datenquellen, die kopiert wurden und eine Authentifizierung benötigen.":::

Nachdem Sie die Datenquellen aktualisiert haben, gehen Sie zu **Daten** > **Vereinheitlichen**. Hier finden Sie Einstellungen aus der Quellumgebung. Bearbeiten Sie sie nach Bedarf oder wählen Sie **Ausführen**, um den Datenvereinheitlichungsprozess zu starten und die einheitliche Kundenentität zu erstellen.

Wenn die Datenvereinheitlichung abgeschlossen ist, gehen Sie zu **Maßnahmen** und **Segmente**, um sie auch zu aktualisieren.

Bevor Sie Exporte und Anreicherungen reaktivieren, gehen Sie zu **Administrator** > **Verbindungen**, um die Verbindungen in Ihrer neuen Umgebung erneut zu authentifizieren.

[!INCLUDE [footer-include](includes/footer-banner.md)]
