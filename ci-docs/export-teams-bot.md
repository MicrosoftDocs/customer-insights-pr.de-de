---
title: Teams Bot für Dynamics 365 Customer Insights (Vorschauversion)
description: Suchen Sie mit Hilfe eines Bots nach einheitlichen Kundenprofilen in Microsoft Teams.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195841"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Teams Bot für Dynamics 365 Customer Insights (Vorschauversion)

Verbinden Sie mit Microsoft Teams, um einen Bot in Teams-Kanälen nach vereinheitlichten Kundenprofilen suchen zu lassen.

:::image type="content" source="media/teams-bot.png" alt-text="Teams Bot zeigt einen Kundendatensatz an":::

## <a name="prerequisites"></a>Anforderungen

- Mindestens einen [Datenquelle hinzugefügt](data-sources.md).
- Der [Vereinheitlichungsprozess](data-unification.md) ist abgeschlossen.
- Felder werden dem [Index suchen und filtern](search-filter-index.md) hinzugefügt.
- Customer Insights und Teams befinden sich in derselben Organisation.
- In Ihrer Umgebung ist die primäre Zielgruppe auf einzelne Kunden festgelegt. Geschäftskonten werden nicht unterstützt.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Konfigurieren des Bots

1. Gehen Sie zu **Administrator** > **Verbindungen**.
1. Auf der Microsoft Teams Kachel wählen Sie **Installieren**.
1. Sie werden zum **Apps** Bereich in Teams weitergeleitet. Sie können auch Teams öffnen und **Apps** in der unteren linken Ecke auswählen oder [dirket aus AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) abrufen.
1. Suchen nach **Customer Insights** und App auswählen.
1. Wählen Sie **Hinzufügen**.
1. Anmelden bei Customer Insights in Teams Eine Willkommensnachricht wird angezeigt

## <a name="things-you-can-do-with-the-bot"></a>Diese Dinge können Sie mit dem Bot tun

Der Bot bietet Suchfunktionen für einheitliche Kundenprofile.

- Geben Sie **Suche** ein gefolgt von einem Namen, einer E-Mail-Adresse oder einem anderen Feld im einheitlichen Kundenprofil, das dem Such- und Filterindex hinzugefügt wird.

  Sie erhalten eine Karte mit bis zu 15 Feldern aus dem resultierenden Kundenprofil. Mehrere Übereinstimmungen geben eine Liste mit Ergebnissen zurück, in der Sie ein Profil auswählen können. Sie können den Suchbegriff in doppelte Anführungszeichen setzen, um eine genaue Übereinstimmung zu ermitteln.

- Wenn Ihr Unternehmen mehrere Customer Insights-Umgebungen in der gleichen Organisation unterhält, können Sie **switchinstance** eingeben, um zu wählen, mit welcher Umgebung Sie den Bot verbinden wollen.

- Eingeben von **Hilfe**, um eine Liste der verfügbaren Befehle für den Bot anzuzeigen.  

[!INCLUDE [footer-include](includes/footer-banner.md)]