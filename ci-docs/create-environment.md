---
title: Customer Insights-Umgebungen erstellen
description: Schritte zum Erstellen von Umgebungen mit einem lizenzierten Abonnement für Dynamics 365 Customer Insights.
ms.date: 04/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0efda9d2997bcfd069b6d2445b69d159d7d3e59b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646040"
---
# <a name="create-an-environment-in-customer-insights"></a>Erstellen Sie eine Umgebung in Customer Insights

Dieser Artikel erklärt, wie Sie eine neue Umgebung erstellen, nachdem Ihre Organisation ein Dynamics 365 Customer Insights-Abonnement gekauft hat. 

Unternehmen können mehrere Umgebungen für jede Customer Insights-Lizenz erstellen. Wenn Ihre Organisation mehr als eine Lizenz erwirbt, [Kontaktieren Sie unser Support-Team](https://go.microsoft.com/fwlink/?linkid=2079641), um die Anzahl der verfügbaren Umgebungen zu erhöhen. Weitere Informationen zur Kapazität und zu Add-On-Kapazitäten finden Sie in der [Lizenzierungsanleitung für Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Wenn Sie den Dienst ausprobieren möchten, lesen Sie [Testumgebung einrichten](trial-signup.md).

## <a name="create-a-new-environment"></a>Neue Umgebung erstellen

Nach dem Kauf einer Abonnementlizenz für Customer Insights erhält der globale Administrator des Microsoft 365-Mandanten eine E-Mail, die ihn auffordert, die Umgebung zu erstellen. Gehen Sie zu [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start), um anzufangen. 

Eine geführte Erfahrung hilft Ihnen durch die Schritte, um alle erforderlichen Informationen für eine neue Umgebung zu sammeln. Sie benötigen [Administratorberechtigungen](permissions.md) in Customer Insights, um Umgebungen zu erstellen oder zu verwalten.

1. Öffnen Sie die Umgebungsauswahl und wählen Sie **+ Neu**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Wählen Sie die Umgebung aus.":::

1. Folgen Sie der geführten Erfahrung, die in den folgenden Abschnitten beschrieben wird.

### <a name="step-1-provide-environment-information"></a>Schritt 1: Geben Sie Umgebungsinformationen an

In dem Schritt **Grundinformation** wählen Sie aus, ob Sie eine Umgebung von Grund auf neu erstellen möchten oder [Daten aus einer anderen Umgebung kopieren](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialog zum Erstellen einer neuen Customer Insights-Umgebung.":::

Geben Sie die folgenden Informationen an:
   - **Name**: Der Name für diese Umgebung. Dieses Feld ist bereits ausgefüllt, wenn Sie eine bestehende Umgebung kopiert haben, aber Sie können es ändern.
   - **Wählen Sie Ihr Unternehmen**: Wählen Sie die primäre Zielgruppe für die neue Umgebung. Sie können mit einzelnen Verbrauchern (B2C) oder mit [Geschäftskonten](work-with-business-accounts.md) (B2B) arbeiten.
   - **Typ**: Wählen Sie, ob Sie eine Produktions- oder eine Sandbox-Umgebung erstellen möchten. Sandbox-Umgebungen lassen keine geplante Datenaktualisierung zu und sind für die Vorimplementierung und das Testen gedacht. Sandbox-Umgebungen verwenden dieselbe primäre Zielgruppe wie die aktuell ausgewählte Produktionsumgebung.
   - **Region**: Die Region, in der der Dienst bereitgestellt und gehostet wird.

### <a name="step-2-configure-data-storage"></a>Schritt 2: Datenschritt konfigurieren

Im Schritt **Datenspeicherung** wählen Sie, wo die Customer Insights Daten gespeichert werden sollen.

Sie haben zwei Möglichkeiten: **Customer Insights-Speicher** (ein Azure Data Lake, der vom Customer Insights-Team verwaltet wird) und **Azure Data Lake Storage** (Ihr eigener Azure Data Lake Storage). Standardmäßig ist die Speicheroption „Customer Insights“ ausgewählt.

:::image type="content" source="media/data-storage-environment.png" alt-text="Wählen Sie die Azure Data Lake Storage, um Ihre Daten zu speichern.":::

Durch das Speichern von Daten in Azure Data Lake Storage stimmen Sie zu, dass Daten an den entsprechenden geografischen Standort für dieses Azure-Speicherkonto übertragen und dort gespeichert werden. Dieser Speicherort kann sich vom Speicherort der Daten in Dynamics 365 Customer Insights unterscheiden. Weitere Informationen finden Sie im [Microsoft Trust Center](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights unterstützt derzeit Folgendes:
> - Aufgenommene Entitäten von Power BI Datenflüsse, die in einem Microsoft Dataverse -verwalteten Data Lake gespeichert sind.  
> - Azure Data Lake Storage Konten aus derselben Azure-Region, die Sie beim Erstellen der Umgebung ausgewählt haben.
> - Azure Data Lake Storage Konten der Gen2, die *hierarchischer Namensraum* aktiviert haben. Azure Data Lake Gen1-Speicherkonten werden nicht unterstützt.

Für die Azure Data Lake Storage Option können Sie zwischen einer ressourcenbasierten Option und einer abonnementbasierten Option für die Authentifizierung wählen. Weitere Informationen finden Sie unter [Stellen Sie eine Verbindung mit einem Azure Data Lake Storage-Konto mithilfe eines Azure-Dienstprinzipals her](connect-service-principal.md). Auf dem Speicherkonto muss ein Container mit dem Namen `customerinsights` vorhanden sein.

Wenn Systemprozesse wie die Datenaufnahme abgeschlossen sind, erstellt das System entsprechende Ordner in dem von Ihnen angegebenen Speicherkonto. Datendateien und *model.json*-Dateien werden erstellt und Ordnern basierend auf dem Prozessnamen hinzugefügt.

Wenn Sie mehrere Umgebungen von Customer Insights erstellen und die Ausgabeentitäten aus diesen Umgebungen in Ihrem Speicherkonto speichern, erstellt Customer Insights separate Ordner für jede Umgebung mit `ci_environmentID` im Behältnis.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Schritt 3: Mit Microsoft Dataverse verbinden
   
Mit dem **Microsoft Dataverse** Schritt können Sie Customer Insights mit Ihrer Dataverse Umgebung verbinden.

Bieten Sie Ihre eigene Microsoft Dataverse-Umgebung, um Daten (Profile und Einblicke) mit auf Dataverse basierenden Geschäftsanwendungen zu teilen, wie Dynamics 365 Marketing oder modellgesteuerte Anwendungen in Power Apps. Lassen Sie dieses Feld leer, wenn Sie keine eigene Dataverse-Umgebung haben und wir stellen Ihnen eine zur Verfügung.

Durch Verbindung zu Ihrer Dataverse-Umgebung können Sie auch [Daten aus lokalen Datenquellen mit Power Platform-Dataflows und Gateways erfassen](data-sources.md#add-data-from-on-premises-data-sources). Sie können auch [sofort einsatzbereite Vorhersage-Modelle](predictions-overview.md?tabs=b2c#out-of-box-models) durch Verbindung mit einer Dataverse-Umgebung verwenden.

> [!IMPORTANT]
> 1. Customer Insights und Dataverse müssen sich in derselben Region befinden, um die Datenfreigabe zu ermöglichen.
> 1. Sie müssen eine globale Administratorrolle in der Dataverse Umgebung haben. Überprüfen Sie, ob dieses [Dataverse Umfeld mit](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) bestimmten Sicherheitsgruppen verknüpft ist und stellen Sie sicher, dass Sie zu diesen Sicherheitsgruppen hinzugefügt werden.
> 1. Es ist noch keine vorhandene Customer Insights Umgebung mit dieser Dataverse Umgebung verknüpt. Lernen wie man eine [bestehende Verbindung in einer Dataverse Umgebung](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment) entfernt.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Datenaustausch mit Microsoft Dataverse automatisch für neue Instanzen aktiviert.":::

Weitere Informationen zum Aktivieren der Datenfreigabe für Microsoft Dataverse über Ihre eigene Azure Data Lake Storage finden Sie unter [mit Microsoft Dataverse verbinden](manage-environments.md#connect-to-microsoft-dataverse).

Customer Insights unterstützt die folgenden Datenfreigabe-Szenarien nicht:
- Wenn Sie die Datenfreigabe mit einem verwalteten Dataverse Data Lake aktivieren, können Sie keine [vorhergesagten oder fehlenden Werten in einer Entität erstellen](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Schritt 4: Einstellungen abschließen

In dem Schritt **Überprüfen**  gehen Sie alle angegebenen Einstellungen durch. Wenn alles fertig aussieht, wählen Sie **Erstellen**, um die Umgebung einzurichten. 

Sie können die meisten Einstellungen auch später ändern. Weitere Informationen finden Sie unter [Umgebungen verwalten](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Arbeiten Sie mit Ihrer neuen Umgebung

Lesen Sie die folgenden Artikel, um Ihnen den Einstieg in die Konfiguration von Customer Insights zu erleichtern: 

- [Weitere Benutzer hinzufügen und Berechtigungen zuweisen](permissions.md).
- [Erfassen Sie Ihre Datenquellen](data-sources.md) und führen sie sie mit dem [Datenvereinheitlichungsprozess](data-unification.md) aus, um [einheitliche Kundenprofile](customer-profiles.md) zu erhalten.
- [Reichern Sie die einheitlichen Kundenprofile an](enrichment-hub.md) oder [führen Sie Vorhersagemodelle aus](predictions-overview.md).
- [Erstellen Sie Segmente](segments.md), um Kunden zu gruppieren und [Maßnahmen](measures.md), um KPIs zu überprüfen.
- [Verbindungen](connections.md) und [Exporte](export-destinations.md) einrichten, um Teilmengen Ihrer Daten in anderen Anwendungen zu verarbeiten.
