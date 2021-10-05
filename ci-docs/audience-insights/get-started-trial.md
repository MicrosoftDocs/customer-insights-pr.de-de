---
title: Eine Testversion von Customer Insights erstellen und konfigurieren
description: Schritte zum Erhalten und Konfigurieren eines Probeabonnements von Dynamics 365 Customer Insights.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 3a235e924395a606b9332de3d205289288a597a9
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558822"
---
# <a name="set-up-a-trial-environment"></a>Eine Testumgebung einrichten 

Mit einer Testversion von Dynamics 365 Customer Insights können Sie die wichtigsten Funktionen kennenlernen und mehr über die verschiedenen Funktionen erfahren. Ein Probeabonnement wird nach Ablauf gelöscht. Testumgebungen werden von einzelnen Benutzern erstellt, die Administrator ihrer Testumgebung werden. Sie können die Testumgebung für weitere Benutzer freigeben und die verschiedenen Funktionen konfigurieren.

## <a name="create-a-trial-environment"></a>Testumgebung erstellen

Sie können sich für eine Testversion registrieren auf der [Registrierungsseite für die Testversion](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Wählen Sie die Option **Für eine kostenlose Testversion registrieren** und wählen Sie **Jetzt registrieren** aus.

1. Geben Sie Ihre Geschäfts-, Schul- oder Uni-E-Mail-Adresse an, erzählen Sie uns mehr über sich und wählen Sie **Los geht's** aus.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialogfeld zum Registrieren für eine kostenlose Testversion":::

1. Wiederholen Sie die Bedingungen, und wählen Sie dann **Weiter** zur Bestätigung aus.

1. Geben Sie einen **Namen** für Ihre neue Umgebung an. 

1. Stellen Sie den **Typ** der Umgebung auf **Testversion** ein.

1. Im Feld **Branchendemo auswählen** können Sie optional ein branchenspezifisches Dataset auswählen. Sie können auch später [zu einer Branchendemo wechseln](#use-industry-specific-demo-data-sets-in-audience-insights) und mit dem Standard-Dataset beginnen.

1. Wählen Sie die **Region** für Ihre Umgebung.

1. Wenn Sie der Administrator einer Dynamics 365-Organisation sind, können Sie optional **Erweiterte Einstellungen** auswählen und die URL Ihrer Organisation an, um Vorhersagefunktionen wie die Vorhersage der Kundenabwanderung zu verwenden. 

1. Wählen Sie **Erstellen** aus. 

Die Einrichtung der Umgebung nimmt einige Augenblicke in Anspruch. Nach der Fertigstellung werden Sie zur Demoumgebung oder zur Branchendemo weitergeleitet, die Sie im obigen Schritt ausgewählt haben. Sie können die App jetzt mit schreibgeschützten Demodaten kennenlernen. Informationen zum Hinzufügen eigener Daten zur Umgebung finden Sie unter [Szenariospezifische Demodaten in Ihrer eigenen Umgebung erstellen](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Screenshot einer neu erstellten Testumgebung.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Branchenspezifische Demo-Datasets in Zielgruppenerkenntnissen verwenden

Die Verbindung echter Datenquellen ist einer der kritischen Schritte bei der Nutzung der Leistungsstärke von Customer Insights. Um Funktionen auszuprobieren, ohne Ihre eigenen Daten zu beeinträchtigen, können Sie optional branchenspezifische Demodaten verwenden. Für die folgenden Branchen stehen einige Demo-Datasets zur Verfügung: 

-   Automobilbranche
-   Bankwesen
-   Konsumgüter
-   Behörden
-   Gesundheitswesen
-   Hotel- und Gaststättengewerbe
-   Versicherung
-   Verarbeitendes Gewerbe
-   Freiberufliche Dienstleistungen
-   Einzelhandel

### <a name="see-industry-specific-demo-data-in-trials"></a>Branchenspezifische Demodaten in Testversionen ansehen

Beginnen Sie bei einer schreibgeschützte, Version von Customer Insights, die auf eine bestimmte Branche oder ein bestimmtes Szenario zugeschnitten ist, in der Demoumgebung. 
 
1.  Wählen Sie in den Zielgruppenerkenntnissen die **Demo** umgebung in der Umgebungsauswahl aus.

2.  Wählen Sie auf **Home** eine Option aus dem Dropdownmenü „Auswählen“ eine Branchendemo aus.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Wählen Sie eine Branche für die Testumgebung aus.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Szenariospezifische Demodaten in Ihrer eigenen Umgebung erstellen

Wählen Sie als Administrator die Umgebungsauswahl in der App-Kopfzeile aus, um eine neue Umgebung zu erstellen. In der neuen Umgebung können Sie Ihre eigenen Datenquellen konfigurieren und die App nach Ihren Anforderungen einrichten. 

1.  Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Datenquellen**.

2.  Um Ihre eigenen Datenquellen zu importieren, gehen Sie zur [Anleitung zur Datenerfassung](data-sources.md).     
   Wenn Sie es vorziehen, mit Beispieldaten zu arbeiten, mit denen Sie die Datenerfassung ausprobieren können, können Sie die Branchendemodaten in Ihrer Umgebung erfassen. Wählen Sie die Option **Aus Datahub importieren** und folgen Sie den unten stehenden Schritten.

3.  Wählen Sie die Branchenkarte aus, die zu Ihrem Szenario passt. 

4.  Überprüfen und aktualisieren Sie gegebenenfalls den vorgeschlagenen Namen von Datenquelle. 

5.  Wählen Sie **Weiter** aus, um die Beispieldaten zu erfassen. 

Sie können jetzt die erfassten Daten verwenden, um Customer Insights an Ihr Szenario anzupassen. Um eine Umgebung anzuzeigen, die für die erfassten Demodaten spezifisch ist, wählen Sie die Option **<Industry>-Demo** in der Umgebungsauswahl aus.

## <a name="limitations-in-trials"></a>Einschränkungen von Testversionen

- Testversionen sind standardmäßig 30 Tage lang aktiv. Sie können sie jedoch nach dem 23. Tag verlängern, wenn Sie sich in Ihrer Testversion anmelden.
- Sie können Ihr eigenes Azure Data Lake Storage-Konto nicht zum Speichern von Ausgabedaten verwenden, wenn Sie mit einer Testversion arbeiten. Sie können jedoch Daten aus einem Data Lake Storage-Konto erfassen.
- Sie können bis zu 3 GB Daten in der Dataverse-Umgebung speichern, die automatisch bereitgestellt wird, wenn Sie eine Customer Insights-Testversion starten.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Daten aus einer Testversion in ein kostenpflichtiges Abonnement kopieren

Wir empfehlen grundsätzlich, beim Upgrade auf die kostenpflichtige Version von Customer Insights mit Ihren eigenen Daten neu zu beginnen. 

Optional können Sie Ihre Daten aus einer Testumgebung kopieren, wenn Sie Customer Insights erwerben. Sie müssen Administrator der Customer Insights-Testversion und der globale Administrator Ihres Microsoft 365-Mandanten oder Dynamics 365-Administrator in Ihrer Organisation sein, um die Einstellungen von einer Testumgebung in eine kostenpflichtige Umgebung zu migrieren. 

Nachdem Sie sich zum ersten Mal bei Ihrer kostenpflichtigen Instanz von Customer Insights angemeldet haben, werden Sie aufgefordert, eine neue Umgebung zu erstellen. In diesem Prozess können Sie die Konfiguration aus einer vorhandenen Umgebung kopieren und die meisten Einstellungen migrieren. Wenn Sie über die oben genannten Berechtigungen verfügen, wird die Testumgebung in dieser Liste angezeigt. Weitere Informationen finden Sie unter [Die Umgebungskonfiguration kopieren](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Nächste Schritte

Lesen Sie die folgenden Artikel, die Ihnen den Einstieg in die Konfiguration von Customer Insights erleichtern. 

- [Weitere Benutzer hinzufügen und Berechtigungen zuweisen](permissions.md).
- [Erfassen Sie Ihre Datenquellen](data-sources.md) und führen sie sie mit dem [Datenvereinheitlichungsprozess](data-unification.md) aus, um [einheitliche Kundenprofile](customer-profiles.md) zu erhalten.
- [Reichern Sie die einheitlichen Kundenprofile an](enrichment-hub.md) oder [führen Sie Vorhersagemodelle aus](predictions-overview.md).
- Erstellen Sie [Segmente](segments.md), um Kunden zu gruppieren und [Kennzahlen](measures.md) zur Überprüfung von KPIs.
- Richten Sie [Verbindungen](connections.md) und [Exporte](export-destinations.md) ein, um Teilmengen Ihrer Daten in anderen Anwendungen zu verarbeiten.
