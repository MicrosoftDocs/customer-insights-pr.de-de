---
title: Anreichern von vereinheitlichten Kundenprofilen
description: Verwenden Sie Funktionalitäten, um Ihre Kundendaten anzureichern.
ms.date: 03/29/2022
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
ms.openlocfilehash: 5c14e6c96d2f907ba161331b6f92277191cbdbef
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653522"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Anreicherung für Kundenprofile (Vorschau)

Nutzen Sie Daten aus Quellen wie Microsoft und anderen Partnern zur Anreicherung Ihrer Kundendaten.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Enrichment Hub-Seite.":::

Gehen Sie zu **Daten** > **Anreicherung**, um mit den Anreicherungsoptionen zu arbeiten.  

Um Anreicherungen erstellen oder bearbeiten zu können, benötigen Sie die Berechtigungen eines Teilnehmers oder Administrators. Weitere Informationen finden Sie unter [Berechtigungen](permissions.md).

Auf der Registerkarte **Entdecken** finden Sie alle unterstützten Anreicherungsoptionen.

# <a name="individual-consumers-b-to-c"></a>[Einzelne Verbraucher (B2C)](#tab/b2c)

- [Marken](enrichment-microsoft.md) bereitgestellt von Microsoft
- [Interessen](enrichment-microsoft.md) bereitgestellt von Microsoft
- [Erweiterte Adressen](enrichment-enhanced-addresses.md) bereitgestellt von Microsoft 
- [Demografiedaten](enrichment-experian.md) von Experian bereitgestellt
- [Kundendaten](enrichment-SFTP-custom-import.md) über Secure File Transfer Protocol (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) bereitgestellt von Microsoft
- [Standortdaten](enrichment-here.md), bereitgestellt von HERE Technologies 
- [Identität](enrichment-liveramp.md) bereitgestellt von LiveRamp AbiliTec

# <a name="business-accounts-b-to-b"></a>[Unternehmenskonten (B2B)](#tab/b2b)

- [Unternehmensdaten](enrichment-leadspace.md) werden von Leadspace bereitgestellt
- [Erweiterte Adressen](enrichment-enhanced-addresses.md) bereitgestellt von Microsoft 
- [Erweiterte Unternehmensdaten](enrichment-enhanced-company-data.md) bereitgestellt von Microsoft
- [Standortdaten](enrichment-here.md), bereitgestellt von HERE Technologies 
- [Kundendaten](enrichment-SFTP-custom-import.md) über Secure File Transfer Protocol (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) bereitgestellt von Microsoft
- [Firmendaten](enrichment-dnb.md) von Dun & Bradstreet bereitgestellt
- [Kontobindungsdaten](enrichment-office.md), die von Microsoft bereitgestellt werden

---

Auf der Registerkarte **Meine Anreicherungen** können Sie die von Ihnen konfigurierten Anreicherungen sehen und ihre Eigenschaften bearbeiten.

## <a name="manage-existing-enrichments"></a>Vorhandene Anreicherungen verwalten

Gehen Sie zur Registerkarte **Meine Anreicherungen**, um alle konfigurierten Anreicherungen anzuzeigen. Jede Anreicherung wird als Zeile dargestellt, die zusätzliche Informationen zur Anreicherung enthält.

Wählen Sie die Anreicherung aus, um die verfügbaren Optionen anzuzeigen. Sie können auch die Auslassungspunkte (...) in einem Listenelement auswählen, um die Optionen anzuzeigen. Wenn Sie mehrere Anreicherungen konfiguriert haben, finden Sie diese schnell über das Suchfeld.

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

Die zu bereichernde Entität wird während der Anreicherungskonfiguration angegeben, sodass Sie nur eine Teilmenge Ihrer Profile anreichern können. Anreichern von Daten beispielsweise nur für ein bestimmtes Segment. Sie können mehrere Anreicherungen desselben Typs konfigurieren und dieselbe Verbindung wiederverwenden. Bei einigen Anreicherungen ist die Anzahl der Anreicherungen desselben Typs, die erstellt werden können, begrenzt. Die Grenzwerte und die aktuelle Verwendung sind auf der Seite **Anreicherung** zu sehen.

## <a name="enrich-data-sources-before-unification"></a>Reichern Sie Datenquellen vor der Vereinheitlichung an

Sie können Ihre Kundendaten vor der Datenvereinheitlichung anreichern, um die Qualität eines Datenabgleichs zu verbessern. Weitere Informationen finden Sie unter [Datenquellen anreichern](data-sources-enrichment.md).

## <a name="see-the-progress-of-the-enrichment-process"></a>Anzeigen des Fortschritts des Anreicherungsprozesses

Sie finden Details zur Verarbeitung einer Anreicherung, einschließlich ihres Status und potenzieller Probleme, während der Aktualisierung oder nach Abschluss einer Aktualisierung. Verstehen Sie, welche Prozesse beteiligt sind, um eine Anreicherung zu aktualisieren, und wie lange es dauerte, die Prozesse auszuführen. Der Anreicherungsstatus wird unterstützt für Experian, Leadspace, HERE Technologies, SFTP Import und Azure Maps.

Anzeigen des Status der Bereicherung

1. Gehen Sie zu **Daten** > **Anreicherung**. 
1. Wählen Sie auf der Registerkarte **Meine Anreicherungen** den Status einer Anreicherung aus, um einen Seitenbereich zu öffnen. 
1. Erweitern Sie im Bereich **Fortschrittsdetails** den Abschnitt **Anreicherungen**. 
1. Wählen Sie unter der Bereicherung, deren Fortschritt Sie sehen möchten, **Details anzeigen**. 
1. Im Bereich **Aufgabendetails** wählen Sie **Details anzeigen**, um die Prozesse anzuzeigen, die an der Aktualisierung der Anreicherung beteiligt sind, und deren Status. 

## <a name="enrichment-results"></a>Anreicherungsergebnisse

Nach einem abgeschlossenen Anreicherungslauf können Sie die Anreicherungsergebnisse überprüfen.

1. Gehen Sie zu **Daten** > **Anreicherung**. 
1. Wählen Sie die Anricherung, zu der Sie Informationen möchten.

Alle Anreicherungen zeigen grundlegende Informationen wie die Anzahl der angereicherten Profile, eine Vorschau der generierten Anreicherungsentität und die Anzahl der angereicherten Profile im Laufe der Zeit. Falls vorhanden stellt **Anzahl der Kunden, angereichert nach Feld** Detailinformationen zur  Abdeckung jedes angereicherten Felds dar.

:::image type="content" source="media/enrichments-results.png" alt-text="Anreicherungsergebnisse pro Seite.":::

Einige Anreicherungen zeigen auch spezifische Informationen zur Art der Anreicherung an. Weitere Informationen finden Sie in der Dokumentation der entsprechenden Anreicherung.


[!INCLUDE [footer-include](includes/footer-banner.md)]