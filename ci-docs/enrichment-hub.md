---
title: 'Datenanreicherung (Vorschauversion): Übersicht'
description: Nutzen Sie Funktionen von Microsoft und anderen Diensten von Drittanbietern, um Ihre Kundendaten anzureichern.
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
ms.openlocfilehash: fb747f7adc7d87f30f66c5d0ed20bbe238558fde
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304518"
---
# <a name="data-enrichment-preview-overview"></a>Datenanreicherung (Vorschauversion): Übersicht

Nutzen Sie Daten aus Quellen wie Microsoft und anderen Partnern zur Anreicherung Ihrer Kundendaten. Anreicherungen von Drittanbietern werden mithilfe von [Verbindungen](connections.md) konfiguriert, die ein Administrator mit Anmeldeinformationen einrichtet und die Zustimmung zur Datenübertragung erteilt. Die Verbindung kann von Administratoren und Beitragenden zur Konfiguration von Anreicherungen verwendet werden.  

## <a name="multiple-enrichments-of-the-same-type"></a>Mehrfachanreicherungen des gleichen Typs

Die zu bereichernde Entität wird während der Anreicherungskonfiguration angegeben, sodass Sie nur eine Teilmenge Ihrer Profile anreichern können. Anreichern von Daten beispielsweise nur für ein bestimmtes Segment. Sie können mehrere Anreicherungen desselben Typs konfigurieren und dieselbe Verbindung wiederverwenden. Bei einigen Anreicherungen ist die Anzahl der Anreicherungen desselben Typs, die erstellt werden können, begrenzt. Die Grenzen und die aktuelle Nutzung sind auf jeder Kachel auf der Registerkarte **Entdecken** der Seite **Anreicherung** zu sehen.

## <a name="enrich-data-sources-before-unification"></a>Reichern Sie Datenquellen vor der Vereinheitlichung an

Sie können Ihre Kundendaten vor der Datenvereinheitlichung anreichern, um die Qualität eines Datenabgleichs zu verbessern. Weitere Informationen finden Sie unter [Datenquellen anreichern](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Anreicherung erstellen

Um Anreicherungen erstellen oder bearbeiten zu können, benötigen Sie die [Berechtigungen](permissions.md) eines Mitwirkenden oder Administrators.

Gehen Sie zu **Daten** > **Anreicherung**. Auf der Registerkarte **Entdecken** finden Sie alle unterstützten Anreicherungsoptionen.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Enrichment Hub-Seite.":::

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

## <a name="manage-existing-enrichments"></a>Vorhandene Anreicherungen verwalten

Gehen Sie zu **Daten** > **Anreicherung**. Auf der Registerkarte **Meine Anreicherungen** werden konfigurierte Anreicherungen, deren Status, die Anzahl der angereicherten Kunden und den Zeitpunkt der letzten Aktualisierung der Daten angezeigt. Sie können die Liste der Anreicherungen nach einer beliebigen Spalte sortieren oder das Suchfeld verwenden, um die Anreicherung zu finden, die Sie verwalten möchten.

Wählen Sie die Anreicherung aus, um verfügbare Aktionen anzuzeigen.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Optionen zum Verwalten von Anreicherungen in der Liste der Anreicherungen.":::

- **Anzeige** von Anreicherungsdetails mit der Anzahl der angereicherten Kundenprofile.
- **Bearbeiten** der Anreicherungskonfiguration.
- [**Ausführen**](#run-or-refresh-enrichments) der Anreicherung, um Kundenprofile mit den neuesten Daten zu aktualisieren. Sie können mehrere Anreicherungen gleichzeitig ausführen, indem Sie sie in der Liste auswählen.
- Eine Berechtigung **aktivieren** oder **deaktivieren**. Inaktive Anreicherungen werden während einer [geplanten Aktualisierung](schedule-refresh.md) nicht aktualisiert.
- **Löschen** Sie die Anreicherung.

Sie können auch [Segmente](segments.md) oder [Maße](measures.md) aus Anreicherungen erstellen.

## <a name="run-or-refresh-enrichments"></a>Anreicherungen ausführen oder aktualisieren

Nach der Ausführung können Anreicherungen nach einem automatischen Zeitplan oder bei Bedarf manuell aktualisiert werden.

1. Um eine oder mehrere Anreicherungen manuell zu aktualisieren, wählen Sie sie aus und wählen Sie **Ausführen**. Zum [Planen einer automatischen Aktualisierung](schedule-refresh.md) wechseln Sie zu **Administrator** > **System** > **Zeitplan**. Die Bearbeitungszeit hängt von der Größe Ihrer Kundendaten ab.

1. [Sehen Sie sich den Fortschritt des Anreicherungsprozesses an](#see-the-progress-of-the-enrichment-process).

1. Gehen Sie nach Abschluss des Anreicherungsprozesses zu **Meine Bereicherung**, um die neu angereicherten Kundenprofildaten, den Zeitpunkt der letzten Aktualisierung und die Anzahl der angereicherten Profile zu überprüfen.

1. Wählen Sie die anzuzeigende Bereicherung aus den [Anreicherungsergebnissen](#view-enrichment-results) aus.

### <a name="see-the-progress-of-the-enrichment-process"></a>Anzeigen des Fortschritts des Anreicherungsprozesses

Sie finden Details zur Verarbeitung einer Anreicherung, einschließlich ihres Status und potenzieller Probleme, während der Aktualisierung oder nach Abschluss einer Aktualisierung. Verstehen Sie, welche Prozesse beteiligt sind, um eine Anreicherung zu aktualisieren, und wie lange es dauerte, die Prozesse auszuführen. Der Anreicherungsstatus wird unterstützt für Experian, Leadspace, HERE Technologies, SFTP Import und Azure Maps.

1. Gehen Sie zu **Daten** > **Anreicherung**.
1. In der Registerkarte **Meine Bereicherung** wählen Sie auf der Registerkarte den Status der Anreicherung aus, um ein Seitenfenster zu öffnen.
1. Erweitern Sie im Bereich **Fortschrittsdetails** den Abschnitt **Anreicherungen**.
1. Wählen Sie unter der Bereicherung, deren Fortschritt Sie sehen möchten, **Details anzeigen**.
1. Im Bereich **Aufgabendetails** wählen Sie **Details anzeigen**, um die Prozesse anzuzeigen, die an der Aktualisierung der Anreicherung beteiligt sind, und deren Status.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Anreicherungsergebnisse anzeigen

Nach einem abgeschlossenen Anreicherungslauf können Sie die Anreicherungsergebnisse überprüfen.

1. Gehen Sie zu **Daten** > **Anreicherung**.
1. In der Registerkarte **Meine Anreicherungen** wählen Sie auf der Registerkarte die Anreicherung aus, die Sie anzeigen möchten.

Alle Anreicherungen zeigen grundlegende Informationen wie die Anzahl der angereicherten Profile, eine Vorschau der generierten Anreicherungsentität und die Anzahl der angereicherten Profile im Laufe der Zeit. Die **Angereicherte Kundenvorschau** Kaachel zeigt ein Beispiel der generierten Anreicherungsentität. Um eine detaillierte Ansicht zu sehen, wählen Sie die Registerkarte **Mehr anzeigen** und  **Daten** aus, um auf eine detaillierte Ansicht jedes angereicherten Profils zuzugreifen.

:::image type="content" source="media/enrichments-results.png" alt-text="Anreicherungsergebnisse pro Seite.":::

Falls vorhanden stellt **Anzahl der Kunden, angereichert nach Feld** Detailinformationen zur  Abdeckung jedes angereicherten Felds dar.

Einige Anreicherungen zeigen auch spezifische Informationen zur Art der Anreicherung an. Weitere Informationen finden Sie in der verwandten Dokumentation.

[!INCLUDE [footer-include](includes/footer-banner.md)]
