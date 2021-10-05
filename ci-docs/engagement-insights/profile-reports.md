---
title: Aktivieren von sofort einsatzbereiten Profilberichten
description: So erstellen Sie sofort einsatzbereite Profilberichte, die nach Geschlecht, Alter und Landkreis oder Region gruppiert sind.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bf2ec67c9fb99918b87841d3c0b131934e31b58b
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486119"
---
# <a name="out-of-box-profile-reports"></a>Sofort einsatzbereite Profilberichte

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ein Bericht ist eine Sammlung von Datenvisualisierungen, mit denen Sie das Benutzerverhalten besser verstehen können. Durch die Verbindung zur Funktion Zielgruppenerkenntnisse von Customer Insights kann die Funktion Kundenbindungserkenntnisse einen Bericht mit Informationen zu einheitlichen Kundenprofilen anzeigen. Dieser Bericht enthält die Anzahl Ihrer Profile, gruppiert nach Geschlecht, Alter und geografischem Standort.

## <a name="prerequisites"></a>Anforderungen

Die Umgebung für Zielgruppenerkenntnisse muss Daten in einem vom Kunden verwalteten Azure Data Lake Storage-Konto speichern.

Wenn Sie eine Testversion der Funktion Zielgruppenerkenntnisse oder eine Umgebung in einem von Customer Insights verwalteten Data Lake verwenden, [kontaktieren Sie uns](https://go.microsoft.com/fwlink/?linkid=2145734), um Hilfe zu erhalten.  


## <a name="enable-the-customer-profile-report"></a>Aktivieren des Kundenprofilberichts

Ein Umgebungsadministrator muss [Bindungserkenntnisse und Zielgruppenerkenntnisse verknüpfen](integrate-audience-insights-engagement-insights.md).

Nach Angabe der Verbindungsdetails kann der Administrator anderen Personen in der Organisation Zugriff gewähren, um den Bericht anzuzeigen. Der Umgebungsadministrator, der die Verbindung einrichtet, hat automatisch Zugriff auf den Bericht. 

Nach dem Herstellen der Verbindung steht die Funktion **Profile** im linken Navigationsbereich zur Verfügung. 

- Wechseln Sie zu **Entdecken** > **Profile**, um den Bericht anzuzeigen.

Der Bericht **Profile** enthält Visualisierungen zu Geschlecht, Alter und geografischem Standort der verbundenen Kundenprofile.

:::image type="content" source="media/customer-profiles.png" alt-text="Kundenprofilbericht.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]