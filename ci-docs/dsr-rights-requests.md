---
title: Anträge zu den Rechten des Datensubjekts (DSR) gemäß der DSGVO | Microsoft Docs
description: Beantworten von Datensubjekt-Anforderungen für Dynamics 365 Customer Insights
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387110"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Daten-abhängige Rechteanforderungen unter DSGVO

Die Datenschutz-Grundverordnung (DSGVO) der Europäischen Union ist seit dem 25. Mai 2018 in Kraft. Sie gibt Einzelpersonen erhebliche Rechte in Bezug auf ihre Daten. Bei der DSGVO geht es um den Schutz und die Gewährleistung der Datenschutzrechte von Einzelpersonen. Lesen Sie mehr zum Einsatz von Microsoft für Sicherheit und Compliance im [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Wir haben es uns zur Aufgabe gemacht, unsere Kunden bei der Erfüllung der DSGVO-Anforderungen zu unterstützen. Die Software beinhaltet das Recht, Daten zu löschen oder zu exportieren, die persönliche Informationen wie Benutzer-IDs, Telefonnummern und E-Mail-Adressen enthalten. Administratoren können Benutzeranforderungen zum Löschen oder Exportieren persönlicher Daten implementieren.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Reagieren auf DSGVO-Löschanfragen von betroffenen Personen für Customer Insights

Das "Recht auf Löschung" durch die Entfernung persönlicher Daten aus den Kundendaten eines Unternehmens ist ein wichtiger Schutz in der Datenschutz-Grundverordnung (DSGVO). Durch das Entfernen von persönlichen Daten zählen alle persönlichen Daten und vom System generierte Protokolle, ausgenommen Überwachungsprotokollinformationen.

### <a name="manage-data-subject-delete-requests"></a>Verwaltung von Löschungsanträgen von Betroffenen

Customer Insights bietet die folgenden produktinternen Möglichkeiten, um persönliche Daten für einen bestimmten Kunden oder Benutzer zu löschen:

- **Löschanträge für Kundendaten verwalten**: Kundendaten in Customer Insights werden aus Originaldatenquellen außerhalb von Customer Insights aufgenommen. Alle DSGVO-Löschungsanfragen zuerst in der ursprünglichen Datenquelle durchführen.
- **Löschanfragen für Customer Insights-Benutzerdaten verwalten**: Daten für Benutzer werden von Customer Insights erstellt. Alle DSGVO-Löschungsanfragen müssen in Customer Insights durchgeführt werden.

#### <a name="manage-requests-to-delete-customer-data"></a>Verwalten von Löschanforderungen für Kundendaten

Ein Administrator von Customer Insights kann die folgenden Schritte ausführen, um Customer Insight Kundendaten zu entfernen, die in der Datenquelle gelöscht wurden. Prüfen Sie, dass alle DSGVO-Löschungsanfragen in der ursprünglichen Datenquelle durchgeführt wurden.

1. Melden Sie sich bei Dynamics 365 Customer Insights an.

1. Wechseln Sie zu **Daten** > **Datenquellen**.

1. Für jede Datenquelle in der Liste, die gelöschte Kundendaten enthält:
   1. Wählen Sie die Datenquelle und dann **Aktualisieren**.
   1. Überprüfen Sie den Status der Datenquelle unter **Status**. Ein Häkchen bedeutet, dass die Aktualisierung erfolgreich war. Ein Warndreieck bedeutet, dass etwas schief gelaufen ist. Wenn ein Warndreieck angezeigt wird, wenden Sie sich an D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Umgang mit DSGVO-Löschanträgen für Kundendaten.":::

1. Führen Sie nach einer erfolgreichen Datenquellenaktualisierung auch die Downstream-Aktualisierungen aus. Vor allem, wenn Sie keine wiederkehrende vollständige Aktualisierung von Customer Insights geplant haben.

   > [!IMPORTANT]
   > Statische Segmente sind nicht in einer vollständigen Aktualisierung oder in nachgelagerten Aktualisierungen nach einer Löschanforderung enthalten. Um sicherzustellen, dass Kundendaten auch aus statischen Segmenten entfernt werden, erstellen Sie die statischen Segmente mit den aktualisierten Quelldaten neu.

#### <a name="manage-delete-requests-for-user-data"></a>Verwalten von Löschanfragen für Benutzerdaten

Als Customer Insights-Administrator löschen Sie die Customer Insights-Benutzerdaten.

1. Melden Sie sich bei Dynamics 365 Customer Insights an.

1. Gehen Sie zu **Admin** > **Sicherheit** und wählen Sie die Registerkarte **Benutzer**.

1. Markieren Sie das Kontrollkästchen für die Benutzer, die Sie löschen möchten.

1. Klicken Sie auf **Entfernen**.

1. Bestätigen Sie den Löschvorgang.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Reagieren auf DSGVO-Exportanfragen von Datensubjekten

Das Recht auf Datenportabilität ermöglicht es den betroffenen Personen, eine Kopie ihrer persönlichen Daten in einem elektronischen Format (ein "strukturiertes, allgemein verwendetes, maschinenlesbares und interoperables Format") anzufordern, das an einen anderen für die Datenverarbeitung Verantwortlichen übermittelt werden kann.

### <a name="manage-export-and-view-requests"></a>Verwalten von Export- und Anzeigeanforderungen

Verwalten von Anfragen für den Export von Kunden- oder Benutzerdaten.

#### <a name="export-customer-data-tenant-admin"></a>Kundendaten exportieren (Mandantenverwaltung)

Als Mandandt-Administrator exportieren Sie Kundendaten.

1. Senden Sie eine E-Mail an D365CI@microsoft.com und geben Sie die E-Mail-Adresse des Kunden in der Anfrage an. Das Customer Insights-Team sendet eine E-Mail an die registrierte Admin-E-Mail-Adresse des Mandanten und bittet um eine Bestätigung für den Datenexport.
2. Bestätigen Sie die Meldung zum Export der Daten für den angeforderten Kunden.
3. Erhalten Sie die exportierten Daten über die E-Mail-Adresse des Mandantenverwalters.

#### <a name="export-user-data-tenant-admin"></a>Benutzerdaten exportieren (Mandant Admin)

Als Mandandt-Administrator exportieren Sie Benutzerdaten.

1. Senden Sie eine E-Mail an D365CI@microsoft.com, wobei Sie die E-Mail-Adresse des Benutzers in der Anfrage angeben. Das Customer Insights-Team sendet eine E-Mail an die registrierte Admin-E-Mail-Adresse des Mandanten und bittet um eine Bestätigung für den Datenexport.
1. Bestätigen Sie die Meldung, um die Daten für den angeforderten Benutzer zu exportieren.
1. Erhalten Sie die exportierten Daten über die E-Mail-Adresse des Mandantenverwalters.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Umgang mit Datenlöschung in Dynamics 365 Customer Insights

Daten werden gelöscht (Datenpartitionen und Daten-Snapshots), wenn die Datenpartitionen und Daten-Snapshots länger als 30 Tage inaktiv sind, d. h. sie wurden durch eine neue Datenpartition und einen neuen Snapshot durch eine Aktualisierung der Datenquellen ersetzt.

Nicht alle Daten und Snapshots werden gelöscht. Die aktuellste Datenpartition und Datenmomentaufnahme sind aktiv, da sie in Customer Insights verwendet werden. Für die neuesten Daten spielt es keine Rolle, ob die Datenquellen nicht innerhalb der letzten 30 Tage aktualisiert wurden.

[!INCLUDE [footer-include](includes/footer-banner.md)]
