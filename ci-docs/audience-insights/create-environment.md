---
title: Customer Insights-Umgebungen erstellen
description: Schritte zum Erstellen von Umgebungen mit einem lizenzierten Abonnement für Dynamics 365 Customer Insights.
ms.date: 10/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 95afd1fedb98a451e4978ee66be2ea98ad7a4a76
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645688"
---
# <a name="create-an-environment-in-audience-insights"></a>Eine Umgebung für Zielgruppenerkenntnisse erstellen

Dieser Artikel erklärt, wie Sie eine neue Umgebung erstellen, nachdem Ihre Organisation ein Dynamics 365 Customer Insights-Abonnement gekauft hat. 

Organisationen können *zwei* Umgebungen für jede Customer Insights-Lizenz erstellen. Wenn Ihre Organisation mehr als eine Lizenz erwirbt, [Kontaktieren Sie unser Support-Team](https://go.microsoft.com/fwlink/?linkid=2079641), um die Anzahl der verfügbaren Umgebungen zu erhöhen. Für weitere Informationen zu Kapazität und Add-On-Kapazität laden Sie den [Dynamics 365-Lizenzierungsleitfaden](https://go.microsoft.com/fwlink/?LinkId=866544) herunter.

> [!NOTE]
> Wenn Sie den Dienst ausprobieren möchten, lesen Sie [Testumgebung einrichten](../trial-signup.md).

## <a name="create-a-new-environment"></a>Neue Umgebung erstellen

Nach dem Kauf einer Abonnementlizenz für Customer Insights erhält der globale Administrator des Microsoft 365-Mandanten eine E-Mail, die ihn zum Erstellen der Umgebung auffordert. Gehen Sie zu [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start), um anzufangen. 

Eine geführte Erfahrung hilft Ihnen durch die Schritte, um alle erforderlichen Informationen für eine neue Umgebung zu sammeln. Sie benötigen [Administrator-Berechtigungen](permissions.md) in Zielgruppenerkenntnissen zum Erstellen oder Verwalten von Umgebungen.

1. Öffnen Sie in Zielgruppenerkenntnissen die Umgebungsauswahl und wählen Sie **+ Neu**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Wählen Sie die Umgebung aus.":::

1. Folgen Sie der geführten Erfahrung, die in den folgenden Abschnitten beschrieben wird.

### <a name="step-1-provide-environment-information"></a>Schritt 1: Geben Sie Umgebungsinformationen an

In dem Schritt **Grundinformation** wählen Sie aus, ob Sie eine Umgebung von Grund auf neu erstellen möchten oder [Daten aus einer anderen Umgebung kopieren](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialog zum Erstellen einer neuen Customer Insights-Umgebung.":::

Geben Sie die folgenden Informationen an:
   - **Name**: Der Name für diese Umgebung. Dieses Feld ist bereits ausgefüllt, wenn Sie eine bestehende Umgebung kopiert haben, aber Sie können es ändern.
   - **Wählen Sie Ihr Unternehmen**: Wählen Sie die primäre Zielgruppe für die neue Umgebung. Sie können mit einzelnen Kunden (B2C) oder [Geschäftskonten](work-with-business-accounts.md) (B2B) arbeiten.
   - **Typ**: Wählen Sie, ob Sie eine Produktions- oder eine Sandbox-Umgebung erstellen möchten. Sandbox-Umgebungen lassen keine geplante Datenaktualisierung zu und sind für die Vorimplementierung und das Testen gedacht. Sandbox-Umgebungen verwenden dieselbe primäre Zielgruppe wie die aktuell ausgewählte Produktionsumgebung.
   - **Region**: Die Region, in der der Dienst bereitgestellt und gehostet wird.

### <a name="step-2-configure-data-storage"></a>Schritt 2: Datenschritt konfigurieren

In dem Schritt **Datenspeicher** wählen Sie aus, wo die Daten aus Zielgruppenerkenntnissen gespeichert werden sollen.

Sie haben zwei Möglichkeiten: **Customer Insights-Speicher** (ein Azure Data Lake, der vom Customer Insights-Team verwaltet wird) und **Azure Data Lake Storage** (Ihr eigener Azure Data Lake Storage). Standardmäßig ist die Speicheroption „Customer Insights“ ausgewählt.

:::image type="content" source="media/data-storage-environment.png" alt-text="Wählen Sie das Azure Data Lake Storage aus, um Ihre Zielgruppenerkenntnis-Daten zu speichern.":::

Durch das Speichern von Daten in Azure Data Lake Storage stimmen Sie zu, dass Daten an den entsprechenden geografischen Standort für dieses Azure-Speicherkonto übertragen und dort gespeichert werden. Dieser Speicherort kann sich vom Speicherort der Daten in Dynamics 365 Customer Insights unterscheiden. Weitere Informationen finden Sie im [Microsoft Trust Center](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights unterstützt derzeit Folgendes:
> - Aufgenommene Entitäten von Power BI Datenflüsse, die in einem Microsoft Dataverse -verwalteten Data Lake gespeichert sind.  
> - Azure Data Lake Storage Konten aus derselben Azure-Region, die Sie beim Erstellen der Umgebung ausgewählt haben.
> - Azure Data Lake Storage Konten, die *hierarchischer Namensraum* aktiviert haben.

Für die Azure Data Lake Storage Option können Sie zwischen einer ressourcenbasierten Option und einer abonnementbasierten Option für die Authentifizierung wählen. Weitere Informationen finden Sie unter [Verbinden Sie Zielgruppen-Insights mit einem Azure Data Lake Storage Gen2-Konto mit einem Azure-Dienstprinzipal](connect-service-principal.md). Der **Container** Name wird `customerinsights` lauten und kann nicht geändert werden.

Wenn Systemprozesse wie die Datenaufnahme abgeschlossen sind, erstellt das System entsprechende Ordner in dem von Ihnen angegebenen Speicherkonto. Datendateien und *model.json*-Dateien werden erstellt und Ordnern basierend auf dem Prozessnamen hinzugefügt.

Wenn Sie mehrere Umgebungen von Customer Insights erstellen und die Ausgabeentitäten aus diesen Umgebungen in Ihrem Speicherkonto speichern, erstellt Customer Insights separate Ordner für jede Umgebung mit `ci_environmentID` im Behältnis.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Schritt 3: Mit Microsoft Dataverse verbinden
   
Mit dem **Microsoft Dataverse** Schritt können Sie Customer Insights mit Ihrer Dataverse Umgebung verbinden.

Benutzen Sie [Standardmäßige Vorhersage-Modelle](predictions-overview.md#out-of-box-models), konfigurieren Sie Datenfreigaben mit Dataverse. Oder Sie können die Datenaufnahme aus lokale Datenquellen aktivieren, indem Sie die Microsoft Dataverse Umgebungs-URL bereitstellen, die Ihre Organisation verwaltet. Wählen Sie **Datenfreigabe aktivieren** aus, um die Ausgabedaten von Customer Insights mit einem verwalteten Dataverse Data Lake zu teilen.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Konfigurationsoptionen zum Aktivieren der Datenfreigabe mit Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights unterstützt die folgenden Datenfreigabe-Szenarien nicht:
> - Wenn Sie alle Daten selbst speichern in Azure Data Lake Storage können Sie die Datenfreigabe mit einem Microsoft Dataverse Verwalteten Data Lake nicht aktivieren.
> - Wenn Sie die Datenfreigabe mit einem Microsoft Dataverse verwalteten Data Lake aktivieren, können Sie keine [vorhergesagten oder fehlenden Werten in einer Entität erstellen](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Schritt 4: Einstellungen abschließen

In dem Schritt **Überprüfen**  gehen Sie alle angegebenen Einstellungen durch. Wenn alles fertig aussieht, wählen Sie **Erstellen**, um die Umgebung einzurichten. 

Sie können die meisten Einstellungen auch später ändern. Weitere Informationen finden Sie unter [Umgebungen verwalten](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Arbeiten Sie mit Ihrer neuen Umgebung

Lesen Sie die folgenden Artikel, die Ihnen den Einstieg in die Konfiguration von Customer Insights erleichtern. 

- [Weitere Benutzer hinzufügen und Berechtigungen zuweisen](permissions.md).
- [Erfassen Sie Ihre Datenquellen](data-sources.md) und führen sie sie mit dem [Datenvereinheitlichungsprozess](data-unification.md) aus, um [einheitliche Kundenprofile](customer-profiles.md) zu erhalten.
- [Reichern Sie die einheitlichen Kundenprofile an](enrichment-hub.md) oder [führen Sie Vorhersagemodelle aus](predictions-overview.md).
- [Segmente erstellen](segments.md), um Kunden und [Kennzahlen](measures.md) zur Überprüfung von KPIs zu gruppieren.
- [Verbindungen](connections.md) und [Exporte](export-destinations.md) einrichten, um Teilmengen Ihrer Daten in anderen Anwendungen zu verarbeiten.
