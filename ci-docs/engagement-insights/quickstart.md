---
title: Schnellstart-Produkteinführung
description: Erste Erfahrungen mit der Einrichtung der Funktion Kundenbindungserkenntnisse.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 11/05/2020
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6690b016be4ad26faa797e5f87aba60caa48ddff
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232969"
---
# <a name="first-run-experience"></a>Erste Ausführung

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

mit der Funktion Kundenbindungserkenntnisse, einer Funktion von Dynamics 365 Customer Insights, können Sie das Kundenverhalten auf Ihrer Website erfassen und messen. In diesem Artikel wird erläutert, wie Sie sich für die Funktion Kundenbindungserkenntnisse anmelden, einen Arbeitsbereich einrichten, Mitglieder hinzufügen und Änderungen vornehmen.

## <a name="sign-up-for-a-demo-of-engagement-insights"></a>Melden Sie sich für eine Demo zur Funktion Kundenbindungserkenntnisse an

Hierfür benötigen Sie ein aktives Microsoft Azure Active Directory-Benutzerkonto. 

1. Öffnen Sie die Website zur Funktion [Kundenbindungserkenntnisse](https://home.ci.ai.dynamics.com/app/engagement-insights). 

1. Melden Sie sich mit Ihrem Schul- oder Geschäftskonto an.

1. Wählen Sie Ihre Region aus und geben Sie über das Kontrollkästchen an, ob Sie den Erhalt von Updates und Angeboten per E-Mail abonnieren möchten.

1. Lesen Sie die **Nutzungsbedingungen für Kundenbindungserkenntnisse (Vorschauversion)** und die **Datenschutzerklärung**. Wählen Sie anschließend **Erkunden der Demo** aus, um sie zu akzeptieren.

1. Erkunden Sie das Produkt anhand einer Reihe von Beispieldaten. 

## <a name="set-up-your-first-workspace-in-engagement-insights"></a>Einrichten Ihres ersten Arbeitsbereichs in der Funktion Kundenbindungserkenntnisse

In einem Arbeitsbereich speichern und verwalten Sie Ereignisse und Berichte.

Erstellen Ihres ersten Arbeitsbereichs

1. Wählen Sie in der Funktion Kundenbindungserkenntnisse die Option **Verbindung mit Ihren Daten herstellen** aus, um den Assistenten zu starten. 

:::image type="content" source="media/banner.png" alt-text="Customer Insights-Seite mit Schaltfläche zum Verbinden Ihrer Daten.":::

2. Wählen Sie die Art der Aktivität aus, die Sie in einem neuen Arbeitsbereich messen möchten. Derzeit ist nur die Option **Website-Aktivität** verfügbar. **Anwendungsaktivität** und **Geräteaktivität** werden in zukünftigen Versionen verfügbar sein.

1. Wählen Sie **Weiter** aus, um den Arbeitsbereich zu bestätigen und zu erstellen.

1. Fügen Sie Ihrer Website den Codeausschnitt hinzu, um in der Funktion Kundenbindungserkenntnisse Daten zu erhalten. Sie können diesen Codeausschnitt sofort implementieren oder den Code zusammen mit den Anweisungen an Ihren Website-Administrator weitergeben. Um den Codeausschnitt später zu finden, wechseln Sie zu **Administrator** > **Arbeitsbereich** > **Installationsanleitung**.

   > [!IMPORTANT]
   > Daten werden im Arbeitsbereich erst dann angezeigt, wenn der Code auf Ihrer Website implementiert wurde.

1. Wählen Sie **Fertig** aus, um Ihren neuen Arbeitsbereich zu öffnen. 

## <a name="add-members-to-an-existing-workspace"></a>Hinzufügen von Mitgliedern zu einem vorhandenen Arbeitsbereich

Standardmäßig hat nur die Person, die den Arbeitsbereich erstellt hat, Zugriff darauf. Sie können jederzeit andere Benutzer aus Ihrer Organisation zu einem vorhandenen Arbeitsbereich hinzufügen.

:::image type="content" source="media/add-members.png" alt-text="Mitgliederseite mit Legende zur Schaltfläche „Mitglieder hinzufügen“.":::

1. Wechseln Sie zu **Administrator** > **Arbeitsbereich** > **Mitglieder**.

2. Wählen Sie **Mitglieder hinzufügen** aus. Verwenden Sie das Feld **Mitglieder**, um weitere Personen aus Ihrer Organisation hinzuzufügen. Sie können mehrere Mitglieder gleichzeitig hinzufügen.

3. Wählen Sie eine **Rolle** aus, um sie den neuen Mitgliedern zuzuweisen. Derzeit steht nur die Rolle **Arbeitsbereichsadministrator** zur Verfügung. Weitere Rollen werden in zukünftigen Versionen hinzugefügt.

4. Wählen Sie zur Bestätigung **Mitglieder hinzufügen** aus.

Um Mitglieder aus einem Arbeitsbereich zu entfernen, wählen Sie **...** neben ihren Namen auf der Seite **Mitglieder** und wählen Sie dann **Löschen** aus dem Dropdown-Menü aus.

## <a name="edit-a-workspace"></a>Bearbeiten eines Arbeitsbereichs

Sie können die Details vorhandener Arbeitsbereiche jederzeit bearbeiten.

:::image type="content" source="media/change-workspace-settings.png" alt-text="Seite mit den Arbeitsbereichseinstellungen mit Legende zum Namen und zur Beschreibung des Arbeitsbereichs.":::

1. Wechseln Sie zu **Administrator** > **Arbeitsbereich** > **Einstellungen**.

1. Geben Sie unter **Name** einen neuen Namen für Ihren Arbeitsbereich ein.

1. Wählen Sie **Speichern**, um Ihre Änderungen zu übernehmen.

## <a name="add-another-new-workspace"></a>Hinzufügen eines weiteren neuen Arbeitsbereichs

:::image type="content" source="media/workspace-switcher.png" alt-text="Seite der Kundenerkenntnisse mit Legende zum Navigationsbereich und Beschreibung.":::

Sie können zusätzliche Arbeitsbereiche erstellen, um Ihre Daten zu klassifizieren.

1. Wählen Sie in der Arbeitsbereichsauswahl **Neuer Arbeitsbereich** aus.

1. Geben Sie einen **Namen** und eine optionale **Beschreibung** ein.

1. Wählen Sie **Erstellen** aus.

## <a name="switch-between-workspaces"></a>Umschalten zwischen Arbeitsbereichen

Um zwischen Arbeitsbereichen zu wechseln, wählen Sie den Arbeitsbereichsumschalter aus. Sie können auch einen neuen Arbeitsbereich erstellen oder **Webbeispiel** auswählen, um Berichte anzuzeigen und Funktionen anhand von Beispieldaten zu testen. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]