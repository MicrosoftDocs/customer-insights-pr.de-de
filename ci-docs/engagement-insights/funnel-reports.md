---
title: Verkaufstrichterberichte
description: So verwenden Sie Verkaufstrichterberichte, um zu verstehen, wie Ihre Zielgruppe Entscheidungen trifft.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 09/21/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7bb961c5ba8d42f704eefe0dcb22e561367f3efb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226259"
---
# <a name="create-and-manage-funnel-reports"></a>Erstellen und Verwalten von Verkaufstrichter-Berichten

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ein Verkaufstrichterbericht sammelt Informationen über die Schritte, die während eines Kundenkontaktverlauf über Ihre Website oder mobile App ausgeführt werden. Er hilft Ihnen zu verstehen, wie eine Zielgruppe einen Prozess durchläuft, und identifiziert Abgabepunkte. Sie können einen Verkaufstrichterbericht beispielsweise verwenden, um Pfade zu identifizieren, denen Ihre Kunden folgen, bevor sie einen Kauf tätigen. Ein Verkaufstrichterbericht liefert Daten, um Entscheidungen zu treffen und Bereiche für Optimierungen und Prozessverbesserungen zu identifizieren.

## <a name="create-a-funnel-report"></a>Erstellen eines Verkaufstrichterberichts

Geben Sie zum Erstellen des Verkaufstrichterberichts die Schritte an, die Sie einschließen möchten, sowie die Aktivität für jeden Schritt. Eine Aktivität ist ein [Ereignis](glossary.md), das das Benutzerverhalten repräsentiert. Der Verkaufstrichterbericht zeigt die Anzahl der Benutzer an, die jeden definierten Schritt ausgeführt haben. 

1. Wechseln Sie zu **Verkaufstrichter** und wählen Sie **+Neuer Verkaufstrichter** aus, um einen Verkaufstrichterbericht zu starten.

1. Wählen Sie im **Verkaufstrichter-Editor** unter **Schritte** die Option **+Schritt hinzufügen** aus. 

1. Geben Sie unter **Schritttitel** einen Namen ein.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Neuer Verkaufstrichterbericht.":::

1. Wählen Sie eine **Aktivität** aus. Eine Aktivität zeichnet auf, wann ein Benutzer eine Seite anzeigt (Aktivität **Anzeige**) oder mit Inhalten interagiert (Aktivität **Aktion**).

1. Verwenden Sie **Schrittkriterien**, um die Dimension der Aktivität anzugeben. [Dimensionen](dimensions.md) sind Attribute, die Daten beschreiben, filtern oder gruppieren können.

1. Optional können Sie Verkaufstrichterschritte mit mehreren Bedingungen konfigurieren. Wählen Sie **Bedingung hinzufügen** aus, um weitere Dimensionen in einem Schritt anzugeben. Zusätzliche Kriterien müssen denselben Aktivitätstyp verwenden. Sie können wählen, ob mehrere Bedingungen mit einem UND- oder einem ODER-Operator verbunden sind.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Verkaufstrichtereditor, der die Schrittkonfiguration für Schritte mit mehreren Bedingungen zeigt.":::

1. Wählen Sie **Schritt hinzufügen** aus, bis Sie alle gewünschten Schritte für den Bericht hinzugefügt haben.

1. Wählen Sie **Speichern** aus, benennen Sie den Bericht und wählen Sie erneut **Speichern** aus. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Beispiel: Verkaufstrichterbericht des Unternehmens Fourth Coffee

Das folgende Szenario zeigt eine Einsatzmöglichkeit für einen Verkaufstrichterbericht. Eine Analystin des Unternehmens Fourth Coffee möchte die Auswirkungen einer kürzlich durchgeführten Werbeaktion auf die Abonnementraten verstehen. Die Analystin erstellt einen Verkaufstrichterbericht, um die Kundenaktivität zu untersuchen. Er beginnt mit dem Aufruf der Homepage des Unternehmens durch den Kunden und endet bei der Nutzung des Werbeaktionscodes für das Abonnement. Die Analystin erstellt einen Verkaufstrichterbericht mit den folgenden Schritten:

Schritt 1: Kunden, die die Homepage aufrufen   
Schritt 2: Kunden, die einen Kauf tätigen   
Schritt 3: Kunden, die den Werbeaktionscode nutzen, um einen Rabatt auf ein Abonnement zu erhalten   
Schritt 4: Abonnementanmeldung   

:::image type="content" source="media/funnel-report-example.png" alt-text="Beispiel für einen Verkaufstrichterbericht.":::
  
Dieser Verkaufstrichter zeigt Ihnen die Anzahl der Benutzer an, die den Werbeaktionscode nach einem einmaligen Kauf verwendet haben, um sich für das Abonnementprogramm anzumelden.

### <a name="configure-advanced-settings"></a>Erweiterte Einstellungen konfigurieren 

In Verkaufstrichterberichten können Sie eine Begrenzung für die Zeit festlegen, die zum Abschließen eines Verkaufstrichters benötigt wird. Legen Sie die Zeit für die Fertigstellung des Verkaufstrichters beispielsweise auf vier Tage fest. Bei dieser Einstellung werden nur erfolgreiche Abonnementanmeldungen gezählt, die innerhalb von vier Tagen nach dem Besuch der Homepage durch einen Benutzer erfolgt sind.

1. Wechseln Sie zu **Verkaufstrichter**, um die **Verkaufstrichterbibliothek** zu öffnen.

1. Wählen Sie einen Namen aus, um den Bericht zu öffnen. 

1. Wählen Sie im Bereich **Verkaufstrichtereditor** die Option **Erweiterte Einstellungen** aus. 

1. Legen Sie für die Beschränkung der Abschlusszeit des Verkaufstrichters **Ein** fest.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Verkaufstrichtereditor mit erweiterten Einstellungen und Optionen zum Begrenzen der Abschlusszeit eines Verkaufstrichters":::

1. Wählen Sie die Zeit, zu der der Verkaufstrichter in der Dropdown-Liste **Grenze festlegen auf** abgeschlossen haben muss.

1. Wählen Sie **Speichern**, um Ihre Änderungen zu übernehmen.


## <a name="cross-channel-funnel-reports"></a>Kanalübergreifende Verkaufstrichterberichte 

Kunenbindungserkenntnisse können auch Verhaltensdaten von Kunden in Ihrer mobilen App sammeln. Sobald Sie Ihre mobile App mit den Kundenbindungs-Erkenntnissen [Android SDK](get-started-android.md) oder [iOS-SDK](get-started-ios.md) ausgestattet haben, können Sie kanalübergreifende Verkaufstrichterberichte erstellen. 

### <a name="create-a-cross-channel-funnel-report"></a>Kanalübergreifender Verkaufstrichterbericht erstellen 

1. Folgen Sie den Schritten, um [einen Verkaufstrichterbericht zu erstellen](#create-a-funnel-report).    

1. Um zu verfolgen, wie Ihre Kunden auf Ihrer Website und in Ihrer mobilen App oder auf mehreren Websites mit Ihrer Marke interagieren, verwenden Sie den Arbeitsbereich-Switcher, um Verkaufstrichterschritte mit Daten aus anderen Arbeitsbereichen zu erstellen. In dem **Verkaufstrichter-Editor**, unter **Schritte** wählen Sie aus, aus welchem Arbeitsbereich die Daten für Ihren Verkaufstrichterschritt stammen sollen.

## <a name="manage-funnel-reports"></a>Verwalten von Verkaufstrichterberichten

Sie können Verkaufstrichterberichte überprüfen, um Daten zu analysieren, die Leistung zu verfolgen und Erkenntnisse zu sammeln.

> [!NOTE]
> - Verkaufstrichterberichte zu Kundenbindungserkenntnissen unterstützen derzeit Szenarien, in denen alle Benutzer im Verkaufstrichter anonym oder alle Benutzer authentifiziert sind. 
> - Historische Daten in Verkaufstrichterberichten sind für die letzten 30 Tage verfügbar.

### <a name="view-funnel-reports"></a>Anzeigen von Verkaufstrichterberichten

1. Wechseln Sie zu **Verkaufstrichter**, um die **Verkaufstrichterbibliothek** zu öffnen.
1. Wählen Sie einen Namen aus, um den Bericht zu öffnen.    

### <a name="see-the-data-collected-for-a-report"></a>Anzeigen der für einen Bericht gesammelten Daten   

Anzeigen von Informationen zu einer Phase

- Zeigen Sie auf einen Schritt im Bericht.

:::image type="content" source="media/funnel-step-data.png" alt-text="Verkaufstrichterdaten.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Ändern des Datumsbereich für den Verkaufstrichterbericht

1. Wechseln Sie zu **Verkaufstrichter**, um die **Verkaufstrichterbibliothek** zu öffnen.

1. Wählen Sie einen Namen aus, um den Bericht zu öffnen.

1. Öffnen Sie den **Zeitbereich** und wählen Sie aus der Liste einen neuen Zeitraum aus oder verwenden Sie **Fester Datumsbereich**, um einen Datumsbereich anzugeben.

## <a name="edit-or-delete-funnel-reports"></a>Bearbeiten oder Löschen von Verkaufstrichterberichten

Sie können den Namen eines Verkaufstrichterberichts ändern, löschen oder die Schritte im Bericht ändern.

### <a name="rename-or-delete-a-funnel-report"></a>Umbenennen oder Löschen eines Verkaufstrichterberichts

1. Wechseln Sie zu **Verkaufstrichter**, um die **Verkaufstrichterbibliothek** zu öffnen. 

1. Wählen Sie neben dem Bericht, den Sie ändern möchten, **Mehr** aus, und wählen Sie dann **Name bearbeiten** oder **Löschen** aus.

### <a name="edit-a-funnel-step"></a>Bearbeiten eines Verkaufstrichterschritts  

1. Wechseln Sie zu **Verkaufstrichter**, um die **Verkaufstrichterbibliothek** zu öffnen. 

1. Wählen Sie einen Namen aus, um den Bericht zu öffnen.

1. Wählen Sie den zu bearbeitenden Schritt aus.

1. Wählen Sie **Bearbeiten**.

1. Aktualisieren Sie im **Verkaufstrichter-Editor** die Informationen, die Sie ändern möchten.  

1. Wählen Sie **Speichern** aus.

### <a name="reorder-a-funnel-step"></a>Ändern der Anordnung von Verkaufstrichterschritten

1. Wechseln Sie zu **Verkaufstrichter**, um die **Verkaufstrichterbibliothek** zu öffnen. 

1. Wählen Sie einen Namen aus, um den Bericht zu öffnen.

1. Wählen Sie den Schritt aus, der neu angeordnet werden soll.

1. Wählen Sie **Verschieben** und dann **Nach oben**, **Nach unten**, **Ganz nach oben** oder **Ganz nach unten** aus, um den Schritt zu verschieben.

### <a name="delete-a-funnel-step"></a>Löschen eines Verkaufstrichterschritts

1. Wechseln Sie zu **Verkaufstrichter**, um die **Verkaufstrichterbibliothek** zu öffnen. 

1. Wählen Sie einen Namen aus, um den Bericht zu öffnen.

1. Wählen Sie den Schritt aus, den Sie entfernen möchten, und wählen Sie dann **Löschen** aus.

## <a name="funnel-insights"></a>Verkaufstrichtererkenntnisse 

Interaktionserkenntnisse bieten jetzt Verkaufstrichtererkenntnisse für Kunden. Nutzen Sie Verkaufstrichtererkenntnisse, um tiefere Einblicke in das Kundenverhalten zu den Schritten in Ihrem Verkaufstrichterbericht zu erhalten. Wenn Sie einen neuen Verkaufstrichterbericht erstellen und speichern, werden automatisch Verkaufstrichtererkenntnisse für Ihren Bericht generiert. 

:::image type="content" source="media/funnel-insights.png" alt-text="Verkaufstrichtererkenntnisse.":::

> [!NOTE]
> Verkaufstrichtererkenntnisse können nur für Verkaufstrichterschritte generiert werden, die **nicht** benutzerdefinierte Dimensionen enthalten. Um Verkaufstrichtererkenntnisse für alle Schritte in Ihrem Verkaufstrichter zu generieren, verwenden Sie vordefinierte Dimensionen von Interaktionserkenntnissen, um Ihre Verkaufstrichtererkenntnisse zu erstellen. 

Sie können Verkaufstrichtererkenntnisse aus den folgenden Kategorien sowohl auf Haupt- als auch auf Schrittebene anzeigen: 

 - Konversionsrate
 -    Die Konversionsrate zwischen Auschecken und Kauf beträgt 22 %.
 - Übergangszeit 
 -    Die durchschnittliche Übergangszeit zwischen Warenkorb und Auschecken ist 23 Minuten. 
 - Abschlusszeit 
 -    Die durchschnittliche Zeit, die Kunden zum Abschließen des Trichters benötigen, beträgt 47 Minuten. 

Nutzen Sie diese Einblicke, um das Kundenverhalten genauer zu untersuchen und Absprungpunkte und Konvertierungen für Ihren Verkaufstrichterbericht besser zu verstehen. 

Um Erkenntnisse über verschiedene Schritte hinweg zu vergleichen, wählen Sie **Schrittaufschlüsselung anzeigen** oder **Mit anderen Schritten vergleichen** über die Erkenntniskarten aus. Diese zeigen ein Balkendiagramm an, das Metriken für jeden Schritt des Trichters vergleicht. 

Verkaufstrichtererkenntnisse werden alle 24 Stunden neu berechnet, oder wenn Sie den Verkaufstrichterbericht **speichern**. 

> [!NOTE]
> Um Erkenntnisse für Ihren Verkaufstrichter anzuzeigen, müssen Sie Ihren Bericht jedes Mal speichern, wenn Sie Änderungen vornehmen. 

