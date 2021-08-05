---
title: Eine kostenpflichtige Version von Customer Insights erstellen und konfigurieren
description: Schritte zum Erhalten und Konfigurieren eines lizenzierten Abonnements von Dynamics 365 Customer Insights.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f8cf1be97ee8af46145a450009fd278b1821f8fe
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650470"
---
# <a name="get-started-with-a-paid-subscription"></a>Erste Schritte mit einem kostenpflichtigen Abonnement

Dieser Artikel erklärt, wie Sie eine neue Umgebung erstellen, nachdem Ihre Organisation ein Dynamics 365 Customer Insights-Abonnement gekauft hat. Wenn Sie Customer Insights erwerben möchten, finden Sie unsere Kontaktmöglichkeiten auf der [Dynamics 365 Customer Insights-Website](https://dynamics.microsoft.com/ai/customer-insights/). 

Wenn Sie den Dienst und die Funktionen ausprobieren möchten, lesen Sie [Eine Testumgebung einrichten](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Eine Umgebung in einer vorhandenen Organisation erstellen

Nach dem Kauf einer Abonnementlizenz für Customer Insights erhält der globale Administrator des Microsoft 365-Mandanten eine E-Mail, die ihn zum Erstellen der Umgebung auffordert. Gehen Sie zu [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start), um anzufangen. 

Customer Insights wird nicht pro Benutzer lizenziert, daher wird es nicht im Bereich „Lizenzen“ angezeigt. Wenn Sie im Microsoft 365 Admin Center nach der Lizenz suchen, gehen Sie zu **Ihre Produkte**. 

> [!NOTE]
> Organisationen können *zwei* Umgebungen für jede Customer Insights-Lizenz erstellen. Wenn Ihre Organisation mehr als eine Lizenz erwirbt, [kKontaktieren Sie unser Support-Team](https://go.microsoft.com/fwlink/?linkid=2079641), um die Anzahl der verfügbaren Umgebungen zu erhöhen. Für weitere Informationen zu Kapazität und Add-On-Kapazität laden Sie den [Dynamics 365-Lizenzierungsleitfaden](https://go.microsoft.com/fwlink/?LinkId=866544) herunter.

So erstellen Sie eine Umgebung:

1. In dem **Schaffen Sie eine Umgebung** Dialog, wählen Sie **Neue Umgebung**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialog zum Erstellen einer neuen Customer Insights-Umgebung.":::

   Wir empfehlen, eine Umgebung von Grund auf neu einzurichten. Wenn Sie jedoch Administrator oder Mitglied einer Testumgebung sind, können Sie [Daten aus einer anderen Umgebung kopieren](manage-environments.md#copy-the-environment-configuration), indem Sie **Aus vorhandener Umgebung kopieren** auswählen. Sie sehen eine Liste aller verfügbaren Umgebungen in Ihrer Organisation, aus der Sie Daten kopieren können.

1. Geben Sie die folgenden Informationen an:
   - **Name**: Der Name für diese Umgebung. Dieses Feld ist bereits ausgefüllt, wenn Sie eine bestehende Umgebung kopiert haben, aber Sie können es ändern.
   - **Region**: Die Region, in der der Dienst bereitgestellt und gehostet wird.
   - **Typ**: Wählen Sie, ob Sie eine Produktions- oder eine Sandbox-Umgebung erstellen möchten. Sandbox-Umgebungen lassen keine geplante Datenaktualisierung zu und sind für die Vorimplementierung und das Testen gedacht.
   
1. Optional können Sie **Erweiterte Einstellungen** auswählen:

   - **Sichern alle Daten**: Geben Sie an, wo Sie die aus Customer Insights generierten Ausgabedaten speichern möchten. Sie haben zwei Möglichkeiten: **Customer Insights-Speicher** (ein Azure Data Lake, der vom Customer Insights-Team verwaltet wird) und **Azure Data Lake Storage** (Ihr eigener Azure Data Lake Storage). Standardmäßig ist die Speicheroption „Customer Insights“ ausgewählt.

     > [!NOTE]
     > Durch die Speicherung von Daten in Azure Data Lake Storage erklären Sie sich damit einverstanden, dass die Daten an den für dieses Azure Storage-Konto geeigneten geografischen Ort übertragen und dort gespeichert werden. Dieser kann von dem Ort abweichen, an dem die Daten in Dynamics 365 Customer Insights gespeichert sind. [Weitere Informationen finden Sie im Microsoft Trust Center.](https://www.microsoft.com/trust-center)
     >
     > Derzeit werden aus Power BI-Dataflows erfasste Entitäten in dem von Microsoft Dataverse verwalteten Data Lake gespeichert. 
     > 
     > Wir unterstützen nur Azure Data Lake Storage Konten aus derselben Azure-Region, die Sie beim Erstellen der Umgebung ausgewählt haben. 
     > 
     > Wir unterstützen nur Azure Data Lake Storage Konten mit aktiviertem hierarchischen Namespace.


   - Für die Azure Data Lake Storage Option können Sie zwischen einer ressourcenbasierten Option und einer abonnementbasierten Option für die Authentifizierung wählen. Weitere Informationen finden Sie unter [Verbinden Sie Zielgruppen-Insights mit einem Azure Data Lake Storage Gen2-Konto mit einem Azure-Dienstprinzipal](connect-service-principal.md). Der Name unter **Container** kann nicht geändert werden und lautet `customerinsights`.
   
   - Wenn Sie [vorkonfigurierte Modelle](predictions-overview.md#out-of-box-models) verwenden möchten, konfigurieren Sie die Datenfreigabe mit Microsoft Dataverse oder aktivieren Sie die Datenerfassung aus lokalen Datenquellen, geben Sie die URL der Microsoft Dataverse-Umgebungs unter **Datenfreigabe mit Microsoft Dataverse konfigurieren und zusätzliche Funktionen aktivieren** ein. Wählen Sie **Datenfreigabe aktivieren** aus, um die Ausgabedaten von Customer Insights mit einem verwalteten Microsoft Dataverse Data Lake zu teilen.

     > [!NOTE]
     > - Datenaustausch mit verwaltetem Microsoft Dataverse Data Lake wird derzeit nicht unterstützt, wenn Sie alle Daten in Ihrem eigenen Azure Data Lake Storage speichern.
     > - [Vorhersage fehlender Werte in einer Entität](predictions.md) wird derzeit nicht unterstützt, wenn Sie die Datenfreigabe mit Microsoft Dataverse Managed Data Lake aktivieren.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Konfigurationsoptionen zum Aktivieren der Datenfreigabe mit Microsoft Dataverse.":::

   Wenn Systemprozesse wie die Datenerfassung abgeschlossen sind, erstellt das System entsprechende Ordner in dem von Ihnen angegebenen Speicherkonto. Datendateien und model.json-Dateien werden erstellt und Ordnern basierend auf dem Prozessnamen hinzugefügt.

   Wenn Sie mehrere Umgebungen von Customer Insights erstellen und die ausgegebenen Entitäten aus diesen Umgebungen in Ihrem Speicherkonto speichern möchten, werden für jede Umgebung separate Ordner mit ci_<environmentid> im Container erstellt.

1. Wählen Sie **Erstellen** aus, um die Umgebung einzurichten. 

## <a name="configure-an-environment"></a>Konfigurieren einer Umgebung

Lesen Sie die folgenden Artikel, die Ihnen den Einstieg in die Konfiguration von Customer Insights erleichtern. 

- [Weitere Benutzer hinzufügen und Berechtigungen zuweisen](permissions.md).
- [Erfassen Sie Ihre Datenquellen](data-sources.md) und führen sie sie mit dem [Datenvereinheitlichungsprozess](data-unification.md) aus, um [einheitliche Kundenprofile](customer-profiles.md) zu erhalten.
- [Reichern Sie die einheitlichen Kundenprofile an](enrichment-hub.md) oder [führen Sie Vorhersagemodelle aus](predictions-overview.md).
- Erstellen Sie [Segmente](segments.md), um Kunden zu gruppieren und [Kennzahlen](measures.md) zur Überprüfung von KPIs.
- Richten Sie [Verbindungen](connections.md) und [Exporte](export-destinations.md) ein, um Teilmengen Ihrer Daten in anderen Anwendungen zu verarbeiten.
