---
title: Anreichern von vereinheitlichten Kundenprofilen
description: Verwenden Sie Funktionalitäten, um Ihre Kundendaten anzureichern.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 3bbe8b829a6698da55d84709dbab6c36aa76792a
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954040"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Anreicherung für Kundenprofile (Vorschau)

Nutzen Sie Daten aus Quellen wie Microsoft und anderen Partnern zur Anreicherung Ihrer Kundendaten.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Enrichment Hub-Seite.":::

Gehen Sie zu **Daten** > **Anreicherung**, um mit den Anreicherungsoptionen zu arbeiten.  

Um Anreicherungen erstellen oder bearbeiten zu können, benötigen Sie die Berechtigungen eines Teilnehmers oder Administrators. Weitere Informationen finden Sie unter [Berechtigungen](permissions.md).

Auf der Registerkarte **Entdecken** finden Sie alle unterstützten Anreicherungsoptionen.

# <a name="individual-consumers-b-to-c"></a>[Einzelne Verbraucher (B2C)](#tab/b2c)

- [AbiliTec Identität](enrichment-liveramp.md) bereitgestellt von LiveRamp AbiliTec
- [Marken](enrichment-microsoft.md) bereitgestellt von Microsoft
- [Demografiedaten](enrichment-experian.md) von Experian bereitgestellt
- [Erweiterte Adressen](enrichment-enhanced-addresses.md) bereitgestellt von Microsoft
- [Interessen](enrichment-microsoft.md) bereitgestellt von Microsoft
- [Standortdaten](enrichment-azure-maps.md) bereitgestellt von Microsoft Azure Maps
- [Standortdaten](enrichment-here.md), bereitgestellt von HERE Technologies
- [SFTP benutzerdefinierte Daten](enrichment-SFTP-custom-import.md) über Secure File Transfer Protocol (SFTP)

# <a name="business-accounts-b-to-b"></a>[Unternehmenskonten (B2B)](#tab/b2b)

- [Kontobindungsdaten](enrichment-office.md), die von Microsoft bereitgestellt werden
- [Firmendaten](enrichment-dnb.md) von Dun & Bradstreet bereitgestellt
- [Unternehmensdaten](enrichment-leadspace.md) werden von Leadspace bereitgestellt
- [Erweiterte Adressen](enrichment-enhanced-addresses.md) bereitgestellt von Microsoft
- [Erweiterte Unternehmensdaten](enrichment-enhanced-company-data.md) bereitgestellt von Microsoft
- [Standortdaten](enrichment-azure-maps.md) bereitgestellt von Microsoft Azure Maps
- [Standortdaten](enrichment-here.md), bereitgestellt von HERE Technologies
- [SFTP benutzerdefinierte Daten](enrichment-SFTP-custom-import.md) über Secure File Transfer Protocol (SFTP)

---

Auf der Registerkarte **Meine Anreicherungen** können Sie die von Ihnen konfigurierten Anreicherungen sehen und ihre Eigenschaften bearbeiten. Sie können auch [Segmente](segments.md) oder [Maße](measures.md) aus Anreicherungen erstellen.

## <a name="manage-existing-enrichments"></a>Vorhandene Anreicherungen verwalten

Gehen Sie zur Registerkarte **Meine Anreicherungen**, um alle konfigurierten Anreicherungen anzuzeigen. Jede Anreicherung wird als Zeile dargestellt, die zusätzliche Informationen zur Anreicherung enthält.

Wählen Sie die Anreicherung aus, um die verfügbaren Optionen anzuzeigen. Sie können auch die vertikalen Auslassungspunkte (&vellip;) auf einem Listenelement auswählen, um die Optionen anzuzeigen. Wenn Sie mehrere Anreicherungen konfiguriert haben, finden Sie diese schnell über das Suchfeld.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Optionen zum Verwalten von Anreicherungen in der Liste der Anreicherungen.":::

- **Anzeige** von Anreicherungsdetails mit der Anzahl der angereicherten Kundenprofile.
- **Bearbeiten** der Anreicherungskonfiguration.
- **Ausführen** der Bereicherung, um Kundenprofile mit den neuesten Daten zu aktualisieren.
- **Deaktivieren** einer vorhandenen Anreicherung, um zu verhindern, dass sie bei jeder geplanten Aktualisierung automatisch aktualisiert wird. Die Daten der letzten erfolgreichen Aktualisierung sind weiterhin verfügbar. **Aktivieren** eine inaktiven Anreicherung, um die automatische Aktualisierung bei jeder geplanten Aktualisierung neu zu starten.
- **Löschen** Sie die Anreicherung.

Führen Sie mehrere Anreicherungen gleichzeitig aus oder deaktivieren Sie sie, indem Sie sie in der Liste auswählen. Ansichts- und Bearbeitungsoptionen sind nicht als Massenaktion verfügbar. Sie funktionieren jeweils nur für eine Anreicherung.

## <a name="enrichments-and-connections"></a>Anreicherungen und Verbindungen

Anreicherungen von Drittanbietern werden mithilfe von [Verbindungen](connections.md) konfiguriert, die ein Administrator mit Anmeldeinformationen einrichtet und die Zustimmung zur Datenübertragung erteilt. Die Verbindung kann von Administratoren und Beitragenden zur Konfiguration von Anreicherungen verwendet werden.  

## <a name="multiple-enrichments-of-the-same-type"></a>Mehrfachanreicherungen des gleichen Typs

Die zu bereichernde Entität wird während der Anreicherungskonfiguration angegeben, sodass Sie nur eine Teilmenge Ihrer Profile anreichern können. Anreichern von Daten beispielsweise nur für ein bestimmtes Segment. Sie können mehrere Anreicherungen desselben Typs konfigurieren und dieselbe Verbindung wiederverwenden. Bei einigen Anreicherungen ist die Anzahl der Anreicherungen desselben Typs, die erstellt werden können, begrenzt. Die Grenzen und die aktuelle Nutzung sind auf jeder Kachel auf der Registerkarte **Entdecken** der Seite **Anreicherung** zu sehen.

## <a name="enrich-data-sources-before-unification"></a>Reichern Sie Datenquellen vor der Vereinheitlichung an

Sie können Ihre Kundendaten vor der Datenvereinheitlichung anreichern, um die Qualität eines Datenabgleichs zu verbessern. Weitere Informationen finden Sie unter [Datenquellen anreichern](data-sources-enrichment.md).

## <a name="run-or-refresh-enrichments"></a>Anreicherungen ausführen oder aktualisieren

1. Um den Anreicherungsprozess zu starten, wählen Sie **Ausführen** aus. Oder Sie können das System die Anreicherung auch automatisch als Teil von einer [geplante Aktualisierung](system.md#schedule-tab) ausführen lassen. Die Bearbeitungszeit hängt von der Größe Ihrer Kundendaten ab.

1. [Sehen Sie sich den Fortschritt des Anreicherungsprozesses an](#see-the-progress-of-the-enrichment-process).

1. Gehen Sie nach Abschluss des Anreicherungsprozesses zu **Meine Bereicherung**, um die neu angereicherten Kundenprofildaten, den Zeitpunkt der letzten Aktualisierung und die Anzahl der angereicherten Profile zu überprüfen.

1. Wählen Sie die anzuzeigende Bereicherung aus den [Anreicherungsergebnissen](#enrichment-results) aus.

### <a name="see-the-progress-of-the-enrichment-process"></a>Anzeigen des Fortschritts des Anreicherungsprozesses

Sie finden Details zur Verarbeitung einer Anreicherung, einschließlich ihres Status und potenzieller Probleme, während der Aktualisierung oder nach Abschluss einer Aktualisierung. Verstehen Sie, welche Prozesse beteiligt sind, um eine Anreicherung zu aktualisieren, und wie lange es dauerte, die Prozesse auszuführen. Der Anreicherungsstatus wird unterstützt für Experian, Leadspace, HERE Technologies, SFTP Import und Azure Maps.

1. Gehen Sie zu **Daten** > **Anreicherung**.
1. In der Registerkarte **Meine Bereicherung** wählen Sie auf der Registerkarte den Status der Anreicherung aus, um ein Seitenfenster zu öffnen.
1. Erweitern Sie im Bereich **Fortschrittsdetails** den Abschnitt **Anreicherungen**.
1. Wählen Sie unter der Bereicherung, deren Fortschritt Sie sehen möchten, **Details anzeigen**.
1. Im Bereich **Aufgabendetails** wählen Sie **Details anzeigen**, um die Prozesse anzuzeigen, die an der Aktualisierung der Anreicherung beteiligt sind, und deren Status.

## <a name="enrichment-results"></a>Anreicherungsergebnisse

Nach einem abgeschlossenen Anreicherungslauf können Sie die Anreicherungsergebnisse überprüfen.

1. Gehen Sie zu **Daten** > **Anreicherung**.
1. In der Registerkarte **Meine Bereicherung** wählen Sie auf der Registerkarte die Anreicherung aus, zu der Sie Informationen wünschen.

Alle Anreicherungen zeigen grundlegende Informationen wie die Anzahl der angereicherten Profile, eine Vorschau der generierten Anreicherungsentität und die Anzahl der angereicherten Profile im Laufe der Zeit. Die **Angereicherte Kundenvorschau** Kaachel zeigt ein Beispiel der generierten Anreicherungsentität. Um eine detaillierte Ansicht zu sehen, wählen Sie die Registerkarte **Mehr anzeigen** und  **Daten** aus, um auf eine detaillierte Ansicht jedes angereicherten Profils zuzugreifen.

:::image type="content" source="media/enrichments-results.png" alt-text="Anreicherungsergebnisse pro Seite.":::

Falls vorhanden stellt **Anzahl der Kunden, angereichert nach Feld** Detailinformationen zur  Abdeckung jedes angereicherten Felds dar.

Einige Anreicherungen zeigen auch spezifische Informationen zur Art der Anreicherung an. Weitere Informationen finden Sie in der verwandten Dokumentation.

[!INCLUDE [footer-include](includes/footer-banner.md)]
