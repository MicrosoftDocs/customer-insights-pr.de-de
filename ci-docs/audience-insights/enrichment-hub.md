---
title: Anreichern von vereinheitlichten Kundenprofilen
description: Verwenden Sie Funktionalitäten, um Ihre Kundendaten anzureichern.
ms.date: 11/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: de27da92118b83dafa0742b6a1e10ee315750c61
ms.sourcegitcommit: 6efcba688d1db1a5d6343c229f292a26c48fc007
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2021
ms.locfileid: "7770121"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Anreicherung für Kundenprofile (Vorschau)

Nutzen Sie Daten aus Quellen wie Microsoft und anderen Partnern zur Anreicherung Ihrer Kundendaten.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Enrichment Hub-Seite.":::

Gehen Sie in Zielgruppen-Insights zu **Daten** > **Anreicherung**, um mit Anreicherungsoptionen zu arbeiten.  

Um Anreicherungen erstellen oder bearbeiten zu können, benötigen Sie die Berechtigungen eines Teilnehmers oder Administrators. Weitere Informationen finden Sie unter [Berechtigungen](permissions.md).

Auf der Registerkarte **Entdecken** finden Sie alle unterstützten Anreicherungsoptionen.

# <a name="individual-consumers-b-to-c"></a>[Einzelne Verbraucher (B2C)](#tab/b2c)

- [Marken](enrichment-microsoft.md) bereitgestellt von Microsoft
- [Interessen](enrichment-microsoft.md) bereitgestellt von Microsoft
- [Erweiterte Adressen](enrichment-enhanced-addresses.md) bereitgestellt von Microsoft 
- [Demografiedaten](enrichment-experian.md) von Experian bereitgestellt
- [Kundendaten](enrichment-SFTP-custom-import.md) über Secure File Transfer Protocol (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) bereitgestellt von Microsoft

# <a name="business-accounts-b-to-b"></a>[Unternehmenskonten (B2B)](#tab/b2b)

- [Unternehmensdaten](enrichment-leadspace.md) werden von Leadspace bereitgestellt
- [Erweiterte Adressen](enrichment-enhanced-addresses.md) bereitgestellt von Microsoft 
- [Erweiterte Unternehmensdaten](enrichment-enhanced-company-data.md) bereitgestellt von Microsoft
- [Standortdaten](enrichment-here.md), bereitgestellt von HERE Technologies 
- [Kundendaten](enrichment-SFTP-custom-import.md) über Secure File Transfer Protocol (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) bereitgestellt von Microsoft

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

## <a name="see-the-progress-of-the-enrichment-process"></a>Anzeigen des Fortschritts des Anreicherungsprozesses

Sie finden Details zur Verarbeitung einer Anreicherung, einschließlich ihres Status und potenzieller Probleme, während der Aktualisierung oder nach Abschluss einer Aktualisierung. Verstehen Sie, welche Prozesse beteiligt sind, um eine Anreicherung zu aktualisieren, und wie lange es dauerte, die Prozesse auszuführen. Der Anreicherungsstatus wird unterstützt für Experian, Leadspace, HERE Technologies, SFTP Import und Azure Maps.

Anzeigen des Status der Bereicherung

1. Gehen Sie zu **Daten** > **Anreicherung**. 
1. Wählen Sie auf der Registerkarte **Meine Anreicherungen** den Status einer Anreicherung aus, um einen Seitenbereich zu öffnen. 
1. Erweitern Sie im Bereich **Fortschrittsdetails** den Abschnitt **Anreicherungen**. 
1. Wählen Sie unter der Bereicherung, deren Fortschritt Sie sehen möchten, **Details anzeigen**. 
1. Im Bereich **Aufgabendetails** wählen Sie **Details anzeigen**, um die Prozesse anzuzeigen, die an der Aktualisierung der Anreicherung beteiligt sind, und deren Status. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
