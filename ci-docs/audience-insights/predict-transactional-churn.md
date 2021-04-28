---
title: Transaktionsbasiert Abwanderungsvorhersage
description: Sagen Sie voraus, ob bei einem Kunden das Risiko besteht, dass er Ihre Produkte oder Dienstleistungen nicht mehr kauft.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 43fcd37f8dd71e2890334a4cc53d49dae97d63c6
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906855"
---
# <a name="transactional-churn-prediction-preview"></a>Vorhersage der Transaktionsabwanderung (Vorschau)

Die Transaktionsabwanderungsvorhersage hilft bei der Vorhersage, ob ein Kunde Ihre Produkte oder Dienstleistungen in einem bestimmten Zeitfenster nicht mehr kaufen wird. Sie können neue Churn-Vorhersagen auf **Intelligenz** > **Vorhersagen** erstellen. Wählen Sie **Meine Vorhersagen**, um andere Vorhersagen anzuzeigen, die Sie erstellt haben.

> [!TIP]
> Versuchen Sie die Anleitung für eine transaktionale Abwanderungsvorhersage mit Beispieldaten: [Transaktionale Abwanderungsvorhersage (Vorschau) Beispielanleitung](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Anforderungen

- Mindestens die [Berechtigung "Mitwirkender"](permissions.md) in Customer Insights.
- Geschäftswissen, um zu verstehen, was Abwanderung für Ihr Unternehmen bedeutet. Wir unterstützen zeitbasierte Abwanderungsdefinitionen, was bedeutet, dass ein Kunde nach einem Zeitraum ohne Käufe als abgewandert gilt.
- Daten über Ihre Transaktionen/Einkäufe und deren Historie:
    - Transaktionskennungen, um Käufe/Transaktionen zu unterscheiden.
    - Kundenidentifikatoren, um Transaktionen Ihren Kunden zuzuordnen.
    - Transaktionsereignisdaten, die das Datum definieren, an dem die Transaktion stattgefunden hat.
    - Das semantische Datenschema für Käufe/Transaktionen benötigt die folgenden Informationen:
        - **Transaktions-ID:** Ein eindeutiger Bezeichner eines Kaufs oder einer Transaktion.
        - **Transaktionsdatum:** Das Datum des Kaufs oder der Transaktion.
        - **Wert der Transaktion:** Der Währungswert/numerischer Wert der Transaktion/des Elements.
        - (Optional) **Einzige Produkt-ID:** Die ID des gekauften Produkts oder Dienstes, wenn Ihre Daten auf Einzelpostenebene sind.
        - (Optional) **Ob diese Transaktion eine Rückgabe war:** Ein Wahr/Falsch-Feld, das angibt, ob die Transaktion eine Rückgabe war oder nicht. Wenn der **Wert der Transaktion** negativ ist, wird auch diese Information verwendet, um eine Rückgabe abzuleiten.
- (Optional) Daten über Kundenaktivitäten:
    - Aktivitätskennungen zur Unterscheidung von Aktivitäten desselben Typs.
    - Kundenidentifikatoren zur Zuordnung von Aktivitäten zu Ihren Kunden.
    - Aktivitätsinformationen, die den Namen und das Datum der Aktivität enthalten.
    - Das semantische Datenschema für Kundenaktivitäten umfasst
        - **Primärschlüssel:** Ein eindeutiger Identifikator für eine Aktivität. Zum Beispiel ein Website-Besuch oder ein Verwendungsnachweis, der zeigt, dass der Kunde eine Probe Ihres Produkts ausprobiert hat.
        - **Zeitstempel:** Das Datum und die Uhrzeit des durch den Primärschlüssel identifizierten Ereignisses.
        - **Ereignis:** Der Name des Ereignisses, das Sie verwenden möchten. Ein Feld namens „UserAction“ in einem Lebensmittelgeschäft könnte z.B. die Verwendung des Coupons durch den Kunden sein.
        - **Details:** Detaillierte Informationen über das Ereignis. Zum Beispiel könnte ein Feld namens „CouponValue“ in einem Lebensmittelgeschäft der Währungswert des Coupons sein.
- Vorgeschlagene Datencharakteristik:
    - Ausreichende historische Daten: Transaktionsdaten für mindestens das Doppelte des ausgewählten Zeitfensters. Vorzugsweise zwei bis drei Jahre Abonnementdaten. 
    - Mehrfachkäufe pro Kunde: Idealerweise mindestens zwei Transaktionen pro Kunde.
    - Anzahl der Kunden: Mindestens 10 Kundenprofilen, vorzugsweise mehr als 1.000 eindeutigen Kunden. Das Modell schlägt mit weniger als 10 Kunden und unzureichenden historischen Daten fehl.
    - Vollständigkeit der Daten: Weniger als 20 % der fehlenden Werte im Datenfeld der angegebenen Entität.

> [!NOTE]
> Für ein Unternehmen mit hoher Kundenkaufhäufigkeit (alle paar Wochen) wird empfohlen, ein kürzeres Vorhersage-Fenster und eine kürzere Abwanderungsdefinition auszuwählen. Wählen Sie für eine niedrige Kaufhäufigkeit (alle paar Monate oder einmal im Jahr) ein längeres Vorhersage-Fenster und eine längere Abwanderungsdefinition.

## <a name="create-a-transactional-churn-prediction"></a>Erstellen Sie eine transaktionale Abwanderungsvorhersage

1. Gehen Sie in Customer Insights zu **Intelligenz** > **Vorhersagen**.

1. Wählen Sie die Kachel **Kundenabwanderungsmodell (Vorschau)** und wählen Sie **Dieses Modell verwenden**.
   
1. Wählen Sie im Bereich **Kundenabwanderungsmodell** die Option **Transaktional** und wählen Sie **Beginnen**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Screenshot mit ausgewählter transaktionaler Option im Bereich Kundenabwanderungsmodell.":::

### <a name="name-model"></a>Modell benennen

1. Geben Sie einen Namen für das Modell an, um es von anderen Modellen zu unterscheiden.

1. Geben Sie einen Namen für die Ausgabe-Entität an, der nur Buchstaben und Zahlen ohne Leerzeichen enthält. Das ist der Name, den die Modell-Entität verwenden wird. 

1. Klicken Sie auf **Weiter**.

### <a name="define-customer-churn"></a>Kundenabwanderung definieren

1. Legen Sie im Feld **Kunden identifizieren, die im nächsten** abwandern könnten ein Zeitfenster von Tagen fest, für das die Abwanderung vorhergesagt werden soll. Sagen Sie z. B. das Abwanderungsrisiko für Ihre Kunden in den nächsten 90 Tagen voraus, um Ihre Marketing-Bindungsmaßnahmen darauf abzustimmen. Die Vorhersage des Abwanderungsrisikos über einen längeren oder kürzeren Zeitraum kann es schwieriger machen, die Faktoren in Ihrem Abwanderungsrisikoprofil zu berücksichtigen, aber das hängt von Ihren spezifischen Geschäftsanforderungen ab. 
   >[!TIP]
   > Sie können jederzeit **Speichern und schließen** wählen, um die Vorhersage als Entwurf zu speichern. Sie finden den Entwurf der Vorhersage im Register **Meine Vorhersagen**, um fortzufahren.

1. Geben Sie in das Feld **Ein Kunde ist abgewandert, wenn er keine Käufe getätigt hat in:** die Anzahl der Tage ein, um die Abwanderung zu definieren. Wenn ein Kunde z. B. in den letzten 30 Tagen keine Käufe getätigt hat, könnte er für Ihr Unternehmen als abgewandert betrachtet werden. 

1. Wählen Sie **Weiter** aus, um den Vorgang fortzusetzen

### <a name="add-required-data"></a>Erforderliche Daten hinzufügen

1. Wählen Sie **Daten hinzufügen** für **Kaufhistorie** und wählen Sie die Entität, die die Informationen zur Transaktion/Kaufhistorie bereitstellt, wie in den [Voraussetzungen](#prerequisites) beschrieben.

1. Ordnen Sie die semantischen Felder den Attributen innerhalb Ihrer Entität „Kaufhistorie“ zu und wählen Sie **Nächste**. Beschreibungen der Felder finden Sie unter [Voraussetzungen](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Zuordnung der semantischen Felder der Entität „Kauf“.":::

1. Wenn die Felder unten nicht ausgefüllt sind, konfigurieren Sie die Beziehung von Ihrer Entität „Kaufhistorie“ zur Entität „Kunde“.
    1. Wählen Sie die Entität **Kaufhistorie**.
    1. Wählen Sie das **Feld**, das den Kunden in der Entität Kaufhistorie identifiziert. Es muss sich auf die primäre Kunden-ID Ihrer Entität Kunde beziehen.
    1. Wählen Sie das Feld **Kundenentität**, das sich auf Ihre primäre Kundenentität bezieht.
    1. Geben Sie einen Namen ein, der die Beziehung beschreibt.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Kaufhistorie-Seite, die die Erstellung einer Beziehung zum Kunden anzeigt.":::
   
1. Klicken Sie auf **Weiter**.

1. Wählen Sie optional **Daten hinzufügen** für **Kundenaktivitäten**. Wählen Sie die Entität, die die Kundenaktivitätsinformationen liefert, wie in den Voraussetzungen beschrieben.

1. Ordnen Sie die semantischen Felder den Attributen innerhalb Ihrer Entität „Kundenaktivität“ zu und wählen Sie **Nächste**. Beschreibungen der Felder finden Sie unter [Voraussetzungen](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Kundenfelder für Transaktionsdaten zuordnen":::

1. Wählen Sie eine Aktivitätsart, die mit der Art der Kundenaktivität übereinstimmt, die Sie konfigurieren. Wählen Sie **Neu erstellen** und wählen Sie einen verfügbaren Aktivitätstyp oder erstellen Sie einen neuen Typ.

1. Sie müssen die Beziehung von Ihrer Entität Kundenaktivität zu der Entität Kunde konfigurieren.
    1. Wählen Sie das Feld, das den Kunden in der Kundenaktivitätstabelle identifiziert. Es kann sich direkt auf die primäre Kunden-ID Ihrer Entität „Kunde“ beziehen.
    1. Wählen Sie die Entität Kunde, die Ihrer primären Entität Kunde entspricht.
    1. Geben Sie einen Namen ein, der die Beziehung beschreibt.

1. Wählen Sie **Speichern** aus.

1. Wenn Sie weitere Kundenaktivitäten haben, die Sie einbeziehen möchten, wiederholen Sie die obigen Schritte.

1. Klicken Sie auf **Weiter**.

### <a name="set-schedule-and-review-configuration"></a>Legen Sie den Zeitplan fest und überprüfen Sie die Konfiguration

1. Legen Sie eine Häufigkeit fest, um Ihr Modell neu zu trainieren. Diese Einstellung ist wichtig, um die Genauigkeit der Vorhersagen zu aktualisieren, wenn neue Daten aufgenommen werden. Die meisten Unternehmen können einmal pro Monat eine Umschulung durchführen und erhalten eine gute Genauigkeit für ihre Vorhersagen.

1. Klicken Sie auf **Weiter**.

1. Überprüfen Sie die Konfiguration der Vorhersage. Sie können zu vorherigen Schritten zurückgehen, indem Sie **Bearbeiten** unter dem angezeigten Wert wählen. Oder Sie können einen Konfigurationsschritt aus der Fortschrittsanzeige auswählen.

1. Wenn alle Werte korrekt konfiguriert sind, wählen Sie **Speichern und ausführen**, um den Vorhersageprozess zu beginnen. Auf der Registerkarte **Meine Vorhersagen** können Sie den Status Ihrer Vorhersagen sehen. Der Prozess kann je nach der Menge der in der Vorhersage verwendeten Daten mehrere Stunden dauern.

## <a name="review-a-prediction-status-and-results"></a>Überprüfen eines Vorhersage-Status und der Ergebnisse

1. Gehen Sie zu **Intelligenz** > **Vorhersagen** und wählen Sie die Registerkarte **Meine Vorhersagen**.

1. Wählen Sie die Vorhersage aus, die Sie überprüfen möchten.
   - **Vorhersagename:** Name der Vorhersage, der beim Erstellen der Vorhersage angegeben wird.
   - **Vorhersagetyp:** Typ des für die Vorhersage verwendeten Modells
   - **Ausgabe-Entität:** Name der Entität, die die Ausgabe der Vorhersage speichern soll. Eine Entität mit diesem Namen finden Sie unter **Daten** > **Entitäten**.    
     In der Ausgabeentität ist *ChurnScore* die vorhergesagte Abwanderungswahrscheinlichkeit und *IsChurn* eine binäre Bezeichnung basierend auf *ChurnScore* mit Grenzwert 0,5. Der Standardschwellenwert funktioniert möglicherweise nicht für Ihr Szenario. [Erstellen Sie ein neues Segment](segments.md#create-a-new-segment) mit Ihrem bevorzugten Grenzwert.
     Nicht alle Kunden sind notwendigerweise aktive Kunden. Einige von ihnen hatten möglicherweise lange Zeit keine Aktivität mehr und werden aufgrund Ihrer Abwanderungsdefinition bereits als aufgewühlt angesehen. Die Vorhersage des Abwanderungsrisikos für Kunden, die bereits Abwanderung betrieben haben, ist nicht sinnvoll, da dies nicht die Publikum von Interesse sind.
   - **Vorhersagefeld:** Dieses Feld wird nur für einige Arten von Vorhersagen ausgefüllt und wird nicht für die Abwanderungsvorhersage verwendet.
   - **Status:** Status des Vorhersagelaufs.
        - **In Warteschlange:** Die Vorhersage wartet auf die Ausführung anderer Prozesse.
        - **Auffrischen:** Die Vorhersage läuft gerade, um Ergebnisse zu erzeugen, die in die Ausgabe-Entität fließen.
        - **Fehlgeschlagen:** Der Vorhersagelauf ist fehlgeschlagen. [Betrachten Sie die Protokolle](#troubleshoot-a-failed-prediction) für weitere Details.
        - **TotalPrice:** Die Vorhersage ist erfolgreich. Wählen Sie **Ansicht** unter den vertikalen Auslassungspunkten, um die Vorhersage zu überprüfen.
   - **Bearbeitet:** Das Datum, an dem die Konfiguration für die Vorhersage geändert wurde.
   - **Zuletzt aktualisiert:** Das Datum, an dem die Vorhersage in der Ausgabe-Entität aktualisiert wurde.

1. Markieren Sie die vertikalen Auslassungspunkte neben der Vorhersage, deren Ergebnisse Sie überprüfen möchten, und wählen Sie **Ansicht**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Steuerelement zum Anzeigen der Ergebnisse einer Vorhersage.":::   

1. Es gibt drei primäre Datenabschnitte innerhalb der Ergebnisseite:
    1. **Leistung des Trainingsmodells:** A, B oder C sind mögliche Bewertungen. Diese Bewertung zeigt die Leistung der Vorhersage an und kann Ihnen bei der Entscheidung helfen, die in der Ausgabe-Entität gespeicherten Ergebnisse zu verwenden. Bewertungen werden auf der Grundlage der folgenden Regeln ermittelt:
         
         - **A**, wenn das Modell mindestens 50 % der gesamten Vorhersagen richtig vorhergesagt hat und wenn der Prozentsatz der richtigen Vorhersagen für Kunden, die abgewandert sind, um mindestens 10 % größer ist als die Basisrate.
            
         - **B**, wenn das Modell mindestens 50 % der gesamten Vorhersagen richtig vorhergesagt hat und wenn der Prozentsatz der richtigen Vorhersagen für Kunden, die abgewandert sind, bis zu 10 % höher ist als die Basislinie.
            
         - **C**, wenn das Modell weniger als 50 % der gesamten Vorhersagen richtig vorhergesagt hat, oder wenn der Prozentsatz der richtigen Vorhersagen für Kunden, die abgewandert sind, kleiner ist als die Basislinie.
               
         - **Basis** nimmt das für das Modell eingegebene Vorhersage-Zeitfenster (z. B. ein Jahr) und das Modell erstellt verschiedene Zeitbruchteile, indem es durch 2 geteilt wird, bis es einen Monat oder weniger erreicht. Es verwendet diese Anteile, um eine Geschäftsregel für Kunden zu erstellen, die in diesem Zeitrahmen nicht gekauft haben. Diese Kunden werden als abgewandert betrachtet. Die zeitbasierte Geschäftsregel mit der höchsten Fähigkeit zur Vorhersage der Abwanderungswahrscheinlichkeit wird als Basismodell gewählt.
            
    1. **Wahrscheinlichkeit der Abwanderung (Anzahl der Kunden):** Kundengruppen auf der Grundlage ihres vorhergesagten Abwanderungsrisikos. Diese Daten können Ihnen später helfen, wenn Sie ein Kundensegment mit hohem Abwanderungsrisiko erstellen möchten. Solche Segmente helfen Ihnen zu verstehen, wo Ihr Grenzwert für die Segmentmitgliedschaft liegen sollte.
       
    1. **Die wichtigsten Einflussfaktoren:** Es gibt viele Faktoren, die bei der Erstellung Ihrer Vorhersage berücksichtigt werden. Für jeden der Faktoren wird seine Wichtigkeit für die aggregierten Vorhersagen, die ein Modell erstellt, berechnet. Sie können diese Faktoren verwenden, um Ihre Vorhersageergebnisse zu validieren. Oder Sie können diese Informationen später verwenden, um [Segmente](segments.md) zu erstellen, die dazu beitragen könnten, das Abwanderungsrisiko für Kunden zu beeinflussen.

## <a name="troubleshoot-a-failed-prediction"></a>Fehlersuche bei einer fehlgeschlagenen Vorhersage

1. Gehen Sie zu **Intelligenz** > **Vorhersagen** und wählen Sie die Registerkarte **Meine Vorhersagen**.

1. Wählen Sie die vertikalen Auslassungspunkte neben der Vorhersage, für die Sie Fehlerprotokolle anzeigen möchten.

1. Wählen Sie **Logs**.

1. Überprüfen Sie alle Fehler. Es gibt verschiedene Arten von Fehlern, die auftreten können, und sie beschreiben, welcher Zustand den Fehler verursacht hat. Beispielsweise wird ein Fehler, für den nicht genügend Daten zur genauen Vorhersage vorhanden sind, in der Regel dadurch behoben, dass zusätzliche Daten in Customer Insights geladen werden.

## <a name="refresh-a-prediction"></a>Aktualisieren einer Vorhersage

Vorhersagen werden automatisch zum gleichen [Zeitpunkt aktualisiert, zu dem Ihre Daten aktualisiert werden](system.md#schedule-tab), wie in den Einstellungen konfiguriert. Sie können sie auch manuell aktualisieren.

1. Gehen Sie zu **Intelligenz** > **Vorhersagen** und wählen Sie die Registerkarte **Meine Vorhersagen**.

1. Wählen Sie die vertikalen Auslassungspunkte neben der Vorhersage, die Sie aktualisieren möchten.

1. Wählen Sie **Aktualisieren** aus.

## <a name="delete-a-prediction"></a>Löschen einer Vorhersage

Das Löschen einer Vorhersage entfernt auch deren Ausgabe-Entität.

1. Gehen Sie zu **Intelligenz** > **Vorhersagen** und wählen Sie die Registerkarte **Meine Vorhersagen**.

1. Wählen Sie die vertikalen Auslassungspunkte neben der Vorhersage, die Sie löschen möchten.

1. Klicken Sie auf **Löschen**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
