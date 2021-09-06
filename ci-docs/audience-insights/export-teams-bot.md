---
title: Bot für Microsoft Teams
description: Suchen Sie mit Hilfe eines Bots nach einheitlichen Kundenprofilen in Microsoft Teams.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 9bf401124b0ffb21b046954056141e7703386d4911f89f34ffc0fcb84bf0f4be
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032481"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Teams Bot für Dynamics 365 Customer Insights (Vorschau)

Verbinden Sie mit Microsoft Teams, um einen Bot in Teams-Kanälen nach vereinheitlichten Kundenprofilen suchen zu lassen.

> [!div class="mx-imgBorder"]
> ![Der Teams-Bot zeigt einen Kundendatensatz an.](media/teams-bot.png "Teams Bot zeigt einen Kundendatensatz an")

## <a name="prerequisites"></a>Anforderungen

Um den Bot einzurichten und zu konfigurieren, müssen folgende Voraussetzungen erfüllt sein:

- Es gibt mindestens einen [Datenquelle hinzugefügt](data-sources.md).
- Der [Vereinheitlichungsprozess](data-unification.md) ist abgeschlossen.
- Felder werden dem [Index suchen und filtern](search-filter-index.md) hinzugefügt.
- Customer Insights und Teams befinden sich in derselben Organisation.

## <a name="configure-the-bot"></a>Konfigurieren des Bots

1. Gehen Sie in Zielgruppen-Insights zu **Admin** > **Ziele exportieren**.
1. Auf der Microsoft Teams Kachel wählen Sie **Installieren**.
1. Sie werden zum **Apps** Bereich in Teams weitergeleitet. Sie können auch Teams öffnen und **Apps** in der unteren linken Ecke auswählen oder [dirket aus AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) abrufen.
1. Suchen nach **Customer Insights** und App auswählen.
1. Wählen Sie **Hinzufügen**.
1. Nachdem Sie sich bei Customer Insights in Teams angemeldet haben, wird eine Begrüßungsnachricht angezeigt, und Sie können loslegen.

## <a name="things-you-can-do-with-the-bot"></a>Diese Dinge können Sie mit dem Bot tun

Der Bot bietet Suchfunktionen für einheitliche Kundenprofile.

- Geben Sie **Suche** ein gefolgt von einem Namen, einer E-Mail-Adresse oder einem anderen Feld im einheitlichen Kundenprofil, das dem Such- und Filterindex hinzugefügt wird.

  Sie erhalten eine Karte mit bis zu 15 Feldern aus dem resultierenden Kundenprofil. Mehrere Übereinstimmungen geben eine Liste mit Ergebnissen zurück, in der Sie ein Profil auswählen können. Sie können den Suchbegriff in doppelte Anführungszeichen setzen, um eine genaue Übereinstimmung zu ermitteln.

- Wenn Ihr Unternehmen mehrere Customer Insights-Umgebungen in der gleichen Organisation unterhält, können Sie **switchinstance** eingeben, um zu wählen, mit welcher Umgebung Sie den Bot verbinden wollen.

- Eingeben von **Hilfe**, um eine Liste der verfügbaren Befehle für den Bot anzuzeigen.  


[!INCLUDE[footer-include](../includes/footer-banner.md)]