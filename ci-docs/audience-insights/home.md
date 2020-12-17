---
title: Startseite in Zielgruppen-Insights
description: Starten Sie die Erkundung der App auf der Startseite.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405780"
---
# <a name="create-a-new-environment"></a>Neue Umgebung erstellen

## <a name="create-a-trial-environment"></a>Testumgebung erstellen

Sie können sich für eine Testversion registrieren auf der [Registrierungsseite für die Testversion](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Testversionen laufen nach 30 Tagen ab.

1. Wählen Sie die Option **Für eine kostenlose Testversion registrieren** und wählen Sie **Jetzt registrieren** aus.

1. Geben Sie Ihre Arbeits- oder Schul-E-Mail-Adresse an, erzählen Sie uns mehr über sich selbst und wählen Sie **Weiter** aus.

1. Geben Sie einen **Namen** für Ihre neue Umgebung an. 

1. Wählen Sie den Testversionstyp aus.

1. Wählen Sie die **Region** für Ihre Umgebung.

1. Optional für Administratoren einer Dynamics 365-Organisation: Wählen Sie **Erweiterte Einstellungen** aus und geben Sie die URL Ihrer Organisation an, um Vorhersagefunktionen wie Kundenabwanderung zu verwenden.

1. Wählen Sie **Erstellen** aus. 

Nachdem die Umgebung erstellt wurde, sehen Sie die **Demo**-Umgebung, in der Sie die App mit fiktiven Daten erkunden können. Sie können die Beispieldaten an Ihre Branche anpassen. Wählen Sie das **Einstellungen**-Symbol in der Kopfzeile aus und wählen Sie **Demo-Einstellungen** aus. Darüber hinaus können Sie das visuelle Thema ändern. 

Sie [wechseln in die Umgebung](#change-between-environments), die Sie während des Registrierungsvorgangs erstellt haben, um mit Ihren eigenen Daten zu arbeiten.

## <a name="create-a-new-production-or-sandbox-environment"></a>Eine neue Produktions- oder Sandbox-Umgebung erstellen

Wählen Sie in Ihrer Umgebung das **Einstellungen**-Symbol in der Kopfzeile aus und wählen Sie **Neue Umgebung** aus.

Folgen Sie den Schritten, als ob Sie [eine Testumgebung erstellen](#create-a-trial-environment). Sie erhalten eine zusätzliche Option, wenn Sie **Erweiterte Einstellungen** auswählen, um Ihre Daten in Ihrem eigenen Azure Data Lake zu speichern. Geben Sie Ihren Kontonamen und Ihren Kontoschlüssel an, um eine Verbindung zu Ihrem Azure Data Lake herzustellen. Standardmäßig werden Daten im von Customer Insights verwalteten Data Lake gespeichert.

> [!IMPORTANT]
> Durch die Speicherung von Daten Ihrem Azure Data Lake Storage erklären Sie sich damit einverstanden, dass die Daten an den für dieses Azure Storage-Konto geeigneten geografischen Ort übertragen und dort gespeichert werden. Dieser kann von dem Ort abweichen, an dem die Daten in Dynamics 365 Customer Insights gespeichert sind. [Weitere Informationen finden Sie im Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Erkunden Sie die Homepage

Sie können [auf Ihre Customer Insights Umgebung](https://home.ci.ai.dynamics.com/) unter der folgenden URL zugreifen: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
Die Seite **Home** zeigt eine Übersicht über Ihren Kundenstamm und wichtige Kennzahlen, um den Zustand Ihres Unternehmens zu verfolgen.

> [!div class="mx-imgBorder"] 
> ![Einblicke auf der Startseite](media/home-page-insights.png "Einblicke auf der Startseite")

Unter **Aktuelle Segmente** sehen Sie Kundengruppen basierend auf demografischen, Verhaltens- oder Transaktionsattributen, die Sie definiert haben. [Segmente erstellen](segments.md) hilft Ihnen, Ihre Geschäftsaktivitäten besser auszurichten.

**Aktuelle Maßnahmen** zeigten Kacheln mit [Maßnahmen](measures.md). Maßnahmen sind von Ihnen definierte Key Performance Indicators (KPIs). Zum Beispiel die durchschnittliche Wahrscheinlichkeit einer Kundenabwanderung oder die durchschnittlichen Online-Ausgaben pro Kunde.

Der Abschnitt **Aktuelle Erweiterungen** listet die Ergebnisse der kürzlich abgeschlossenen Erweiterungsläufe auf. Durch Erweiterungen werden Informationen über Ihren Kundenstamm hinzugefügt. Zum Beispiel durch das Verständnis der Interessen und Marken, für die sie eine Affinität haben. Diese Informationen können mit Hilfe der Funktionen [Anreicherung](enrichment-microsoft-graph.md) freigeschaltet werden, nachdem Sie die Phasen [Zuordnung](map-entities.md), [Übereinstimmung](match-entities.md) und [Zusammenführung](merge-entities.md) abgeschlossen haben.

## <a name="change-between-environments"></a>Wechsel zwischen Umgebungen

Sobald Sie [Datenquellen](data-sources.md) eingerichtet und konfiguriert haben, werden Sie von einer Demo-Umgebung zu einer Live-Umgebung wechseln wollen. Mit der Produktionsumgebung können Sie mit Ihren eigenen Kundendaten arbeiten. Wählen Sie die Option **Umgebung** in der rechten oberen Ecke der Seite, um die Umgebung zu ändern.

> [!div class="mx-imgBorder"] 
> ![Umgebung wechseln](media/home-page-environment-switcher.png "Umgebung wechseln")

Administratoren können [Mehrfachumgebungen](manage-environments.md) erstellen und verwalten. Die Pflege von mehr als einer Umgebung kann nützlich sein, wenn Ihr Unternehmen beispielsweise international tätig ist und Sie Daten und Informationen auf unterschiedliche Weise trennen müssen.

## <a name="next-step"></a>Nächster Schritt

Um Ihre eigenen Informationen auf der Homepage anzuzeigen, müssen Sie zunächst [Datenquellen hinzufügen](data-sources.md) und [Ihre Daten vereinheitlichen](data-unification.md), um Kundenprofile zu erstellen.
