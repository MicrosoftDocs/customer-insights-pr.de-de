---
title: Abonnementabwanderung vorhersagen (enthält Video)
description: Sagen Sie voraus, ob für einen Kunden das Risiko besteht, dass er die Abonnementprodukte oder -dienste Ihres Unternehmens nicht mehr nutzt.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 415cd5d675512b4f434998afaa8265c8e45c562b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647340"
---
# <a name="subscription-churn-prediction"></a>Vorhersage von Abonnementabwanderung

Die Vorhersage der Abwanderung von Abonnenten hilft bei der Vorhersage, ob ein Kunde möglicherweise die Abonnementprodukte oder -dienste Ihres Unternehmens nicht mehr nutzt. Sie können auf der Seite **Intelligenz** > **Vorhersagen** neue Abonnement-Wechselprognosen erstellen. Wählen Sie **Meine Vorhersagen**, um andere Vorhersagen anzuzeigen, die Sie erstellt haben.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Versuchen Sie die Anleitung für eine Abo-Abwanderungsvorhersage mit Beispieldaten: [Beispielanleitung für die Vorhersage der Abonnement-Abwanderung](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Anforderungen

- Mindestens [Beteiligungsberechtigungen](permissions.md).
- Geschäftswissen, um zu verstehen, was Abwanderung für Ihr Unternehmen bedeutet. Wir unterstützen zeitbasierte Abwanderungsdefinitionen, d. h. ein Kunde gilt eine Zeit lang nach Ablauf seines Abonnements als abgewandert.
- Daten über Ihre Abonnements und deren Geschichte:
    - Abonnementkennungen zur Unterscheidung der Abonnements.
    - Kundenidentifikatoren zur Zuordnung von Abonnements zu Ihren Kunden.
    - Abonnement-Ereignisdaten, die Anfangs- und Enddaten sowie die Daten definieren, an denen die Abonnement-Ereignisse aufgetreten sind.
    - Abonnementinformationen, um festzulegen, ob es sich um ein wiederkehrendes Abonnement handelt und wie oft es sich erneuert.
    - Das semantische Datenschema für Abonnements erfordert die folgenden Informationen:
        - **Abonnement-ID:** Eine eindeutige Kennung eines Abonnements.
        - **Abonnement-Enddatum:** Das Datum, an dem das Abonnement für den Kunden abläuft.
        - **Abonnement-Startdatum:** Das Datum, an dem das Abonnement für den Kunden beginnt.
        - **Transaktionsdatum:** Das Datum, an dem eine Abonnementänderung stattgefunden hat. Zum Beispiel ein Kunde, der ein Abonnement kauft oder kündigt.
        - **Ist es ein wiederkehrendes Abonnement:** Ein boolesches Wahr/Falsch-Feld, das festlegt, ob das Abonnement ohne Eingreifen des Kunden mit derselben Abonnement-ID erneuert wird.
        - **Häufigkeit der Serie (in Monaten):** Bei wiederkehrenden Abonnements ist dies der Zeitraum, für den das Abonnement erneuert wird. Sie wird in Monaten angegeben. Zum Beispiel hat ein Jahresabonnement, das sich für einen Kunden jedes Jahr automatisch um ein weiteres Jahr verlängert, den Wert 12.
        - (Optional) **Abonnementbetrag:** Der Währungsbetrag, den ein Kunde für die Abonnementverlängerung bezahlt. Sie kann helfen, Muster für verschiedene Abonnementstufen zu erkennen.
- Daten über Kundenaktivitäten:
    - Aktivitätskennungen zur Unterscheidung von Aktivitäten desselben Typs.
    - Kundenidentifikatoren zur Zuordnung von Aktivitäten zu Ihren Kunden.
    - Aktivitätsinformationen, die den Namen und das Datum der Aktivität enthalten.
    - Das semantische Datenschema für Kundenaktivitäten umfasst
        - **Primärschlüssel:** Ein eindeutiger Identifikator für eine Aktivität. Zum Beispiel ein Website-Besuch oder ein Datensatz, der zeigt, dass der Kunde eine TV-Show-Episode angesehen hat.
        - **Zeitstempel:** Das Datum und die Uhrzeit des durch den Primärschlüssel identifizierten Ereignisses.
        - **Ereignis:** Der Name des Ereignisses, das Sie verwenden möchten. Beispielsweise könnte ein Feld mit dem Namen "UserAction" in einem Streaming-Video-Dienst den Wert "Viewed" haben.
        - **Details:** Detaillierte Informationen über das Ereignis. Beispielsweise könnte ein Feld namens "ShowTitle" in einem Streaming-Video-Dienst den Wert eines Videos haben, das ein Kunde angesehen hat.
- Vorgeschlagene Datencharakteristik:
    - Ausreichende historische Daten: Abonnementdaten für mindestens das Doppelte des ausgewählten Zeitfensters. Vorzugsweise zwei bis drei Jahre Abonnementdaten.
    - Abonnementstatus: Die Daten enthalten aktive und inaktive Abonnements für jeden Kunden, sodass pro Kunden-ID mehrere Einträge vorhanden sind.
    - Anzahl der Kunden: Mindestens 10 Kundenprofilen, vorzugsweise mehr als 1.000 eindeutigen Kunden. Das Modell schlägt mit weniger als 10 Kunden und unzureichenden historischen Daten fehl.
    - Vollständigkeit der Daten: Weniger als 20 % der fehlenden Werte im Datenfeld der angegebenen Entität.
   
   > [!NOTE]
   > Sie benötigen mindestens zwei Aktivitätsdatensätze für 50 % der Kunden, für die Sie die Abwanderung berechnen möchten.

## <a name="create-a-subscription-churn-prediction"></a>Erstellen Sie eine Vorhersage zur Abonnementabwanderung.

1. Gehen Sie zu **Intelligenz** > **Vorhersagen**.
1. Wählen Sie die Kachel **Modell für Abonnementabwanderung** und **Dieses Modell verwenden**.
   > [!div class="mx-imgBorder"]
   > ![Abonnement-Abwanderungsmodell-Kachel mit der Schaltfläche „Dieses Modell verwenden“.](media/subscription-churn-usethismodel.PNG "Abonnement Abwanderungsmodell-Kachel mit Schaltfläche Dieses Modell verwenden")

### <a name="name-model"></a>Modell benennen

1. Geben Sie einen Namen für das Modell an, um es von anderen Modellen zu unterscheiden.
1. Geben Sie einen Namen für die Ausgabe-Entität an, der nur Buchstaben und Zahlen ohne Leerzeichen enthält. Das ist der Name, den die Modell-Entität verwenden wird. Klicken Sie anschließend auf **Weiter**.

### <a name="define-customer-churn"></a>Kundenabwanderung definieren

1. Geben Sie die Anzahl von **Tagen seit Ende des Abonnements** ein, die Ihr Unternehmen einen Kunden in einem abgewanderten Zustand betrachtet. Dieser Zeitraum wird in der Regel gern für Geschäftsaktivitäten wie Angebote oder andere Marketingmaßnahmen genutzt, um den Verlust des Kunden zu verhindern.
1. Geben Sie die Anzahl von **Tagen ein, um die Zukunft zu prognostizieren und die Abwanderung vorherzusagen** und ein Fenster für die Vorhersage der Abwanderung festzulegen. Zum Beispiel, um das Risiko einer Abwanderung für Ihre Kunden in den nächsten 90 Tagen vorherzusagen und sich an Ihren Bemühungen zur Marketingbindung auszurichten. Die Vorhersage des Abwanderungsrisikos für längere oder kürzere Zeiträume könnte es schwieriger machen, die Faktoren in Ihrem Abwanderungsrisikoprofil zu berücksichtigen, je nach spezifischen Unternehmensanforderungen. Wählen Sie **Weiter** aus, um den Vorgang fortzusetzen
   >[!TIP]
   > Sie können jederzeit **Entwurf speichern** auswählen, um die Vorhersage als Entwurf zu speichern. Sie finden den Entwurf der Vorhersage im Register **Meine Vorhersagen**, um fortzufahren.

### <a name="add-required-data"></a>Erforderliche Daten hinzufügen

1. Wählen Sie **Daten hinzufügen** für **Abonnementshistorie** und wählen Sie die Entität, die die Informationen zur Abonnementshistorie bereitstellt, wie unter [Voraussetzungen](#prerequisites) beschrieben.
1. Wenn die folgenden Felder nicht ausgefüllt sind, konfigurieren Sie die Beziehung von Ihrer Abonnementshistorie-Entität zur Entität Kunde.
    1. Wählen Sie die Entität **Abonnementhistorie**.
    1. Wählen Sie das Feld **Feld**, das den Kunden in der Entität Abonnementshistorie identifiziert. Es muss sich auf die primäre Kunden-ID Ihrer Entität Kunde beziehen.
    1. Wählen Sie das Feld **Kundenentität**, das sich auf Ihre primäre Kundenentität bezieht.
    1. Geben Sie einen Namen ein, der die Beziehung beschreibt.
       > [!div class="mx-imgBorder"]
       > ![Abonnementhistorie-Seite, die die Erstellung einer Beziehung zum Kunden zeigt.](media/subscription-churn-subscriptionhistoryrelationship.PNG "Seite der Abonnementshistorie, die den Aufbau einer Beziehung zum Kunden zeigt")
1. Klicken Sie auf **Weiter**.
1. Ordnen Sie die semantischen Felder den Attributen innerhalb Ihrer Abonnementshistorien-Entität zu und wählen Sie **Speichern**. Beschreibungen der Felder finden Sie unter [Voraussetzungen](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Die Seite Abonnementshistorie zeigt semantische Attribute, die Feldern in der ausgewählten Entität der Abonnementhistorie zugeordnet sind.](media/subscription-churn-subscriptionhistorymapping.PNG "Die Seite Abonnementshistorie zeigt semantische Attribute, die Feldern in der ausgewählten Entität der Abonnementshistorie zugeordnet sind.")
1. Wählen Sie **Daten hinzufügen** für **Kundenaktivitäten** und wählen Sie die Entität, die die Informationen zu den Kundenaktivitäten liefert, wie in den Voraussetzungen beschrieben.
1. Wählen Sie eine Aktivitätsart, die mit der Art der Kundenaktivität übereinstimmt, die Sie konfigurieren.  Wählen Sie **Neu anlegen** und geben Sie einen Namen an, wenn Sie keine Option sehen, die der von Ihnen benötigten Aktivitätsart entspricht.
1. Sie müssen die Beziehung von Ihrer Entität Kundenaktivität zu der Entität Kunde konfigurieren.
    1. Wählen Sie das Feld, das den Kunden in der Kundenaktivitätstabelle identifiziert, die direkt mit der primären Kunden-ID Ihrer Entität Kunde verknüpft werden kann.
    1. Wählen Sie die Entität Kunde, die Ihrer primären Entität Kunde entspricht.
    1. Geben Sie einen Namen ein, der die Beziehung beschreibt.
1. Klicken Sie auf **Weiter**.
1. Ordnen Sie die semantischen Felder den Attributen innerhalb Ihrer Entität Kundenaktivität zu und wählen Sie **Speichern**. Beschreibungen der Felder finden Sie unter [Voraussetzungen](#prerequisites).
1. (Optional) Wenn Sie weitere Kundenaktivitäten einbeziehen möchten, wiederholen Sie die obigen Schritte.
   > [!div class="mx-imgBorder"]
   > ![Definieren der Entitätsbeziehung.](media/subscription-churn-customeractivitiesmapping.PNG "Kundenaktivitäten-Seite mit semantischen Attributen, die Feldern in der ausgewählten Entität der Kundenaktivität zugeordnet sind")
1. Klicken Sie auf **Weiter**.

### <a name="set-schedule-and-review-configuration"></a>Zeitplan festlegen und Konfiguration überprüfen

1. Legen Sie eine Häufigkeit fest, um Ihr Modell neu zu trainieren. Diese Einstellung ist wichtig, um die Genauigkeit der Vorhersagen zu aktualisieren, wenn neue Daten in Customer Insights eingebunden werden. Die meisten Unternehmen können einmal pro Monat eine Umschulung durchführen und erhalten eine gute Genauigkeit für ihre Vorhersagen.
1. Klicken Sie auf **Weiter**.
1. Überprüfen Sie die Konfiguration. Sie können zu jedem Teil der Vorhersagekonfiguration zurückkehren, indem Sie unter dem angezeigten Wert **Bearbeiten** wählen. Oder Sie können einen Konfigurationsschritt aus der Fortschrittsanzeige auswählen.
1. Wenn alle Werte korrekt konfiguriert sind, wählen Sie **Speichern und ausführen**, um den Vorhersageprozess zu beginnen. Auf der Registerkarte **Meine Vorhersagen** können Sie den Status Ihrer Vorhersagen sehen. Der Prozess kann je nach der Menge der in der Vorhersage verwendeten Daten mehrere Stunden dauern.

## <a name="review-a-prediction-status-and-results"></a>Überprüfen eines Vorhersage-Status und der Ergebnisse

1. Gehen Sie zur Registerkarte **Meine Vorhersagen** auf **Intelligenz** > **Vorhersagen**.
   > [!div class="mx-imgBorder"]
   > ![Ansicht der Seite „Meine Vorhersagen“.](media/subscription-churn-mypredictions.PNG "Ansicht der Seite Meine Vorhersagen")
1. Wählen Sie die Vorhersage aus, die Sie überprüfen möchten.
   - **Name der Vorhersage:** Der Name der Vorhersage, der bei ihrer Erstellung angegeben wurde.
   - **Art der Vorhersage:** Typ des für die Vorhersage verwendeten Modells
   - **Ausgabe-Entität:** Name der Entität, die die Ausgabe der Vorhersage speichern soll. Eine Entität mit diesem Namen finden Sie unter **Daten** > **Entitäten**.    
     In der Ausgabeentität ist *ChurnScore* die vorhergesagte Abwanderungswahrscheinlichkeit und *IsChurn* eine binäre Bezeichnung basierend auf *ChurnScore* mit Grenzwert 0,5. Der Standardschwellenwert funktioniert möglicherweise nicht für Ihr Szenario. [Erstellen Sie ein neues Segment](segments.md#create-a-new-segment) mit Ihrem bevorzugten Grenzwert.
   - **Vorhergesagtes Feld:** Dieses Feld wird nur für einige Arten von Vorhersagen ausgefüllt und wird nicht für die Vorhersage der Abonnentenabwanderung verwendet.
   - **Status:** Der aktuelle Status des Ausführung der Vorhersage.
        - **Warteschleife:** Die Vorhersage wartet derzeit auf die Ausführung anderer Prozesse.
        - **Aktualisierung:** Die Vorhersage durchläuft derzeit die "Bewertung"-Verarbeitungsphase, um Ergebnisse zu erzeugen, die in die Ausgabe-Entität fließen werden.
        - **Fehlgeschlagen:** Die Vorhersage ist fehlgeschlagen. Wählen Sie **Protokolle** für weitere Einzelheiten.
        - **Erfolgreich:** die Vorhersage war erfolgreich. Wählen Sie **Ansicht** unter den vertikalen Auslassungspunkten, um die Vorhersage zu überprüfen.
   - **Bearbeitet:** Das Datum, an dem die Konfiguration für die Vorhersage geändert wurde.
   - **Zuletzt aktualisiert:** Das Datum, an dem die Vorhersage in der Ausgabe-Entität aktualisiert wurde.
1. Markieren Sie die vertikalen Auslassungspunkte neben der Vorhersage, deren Ergebnisse Sie überprüfen möchten, und wählen Sie **Ansicht**.
   > [!div class="mx-imgBorder"]
   > ![Anzeige der Optionen im Menü der vertikalen Auslassungspunkte für eine Vorhersage einschließlich Bearbeiten, Aktualisieren, Anzeigen, Protokolle und Löschen.](media/subscription-churn-verticalellipses.PNG "Ansicht der Optionen im Menü der vertikalen Auslassungspunkte für eine Vorhersage einschließlich Bearbeiten, Aktualisieren, Anzeigen, Protokolle und Löschen")
1. Es gibt drei primäre Datenabschnitte innerhalb der Ergebnisseite:
    1. **Leistung des Trainingsmodells:** A, B oder C sind mögliche Bewertungen. Diese Bewertung zeigt die Leistung der Vorhersage an und kann Ihnen bei der Entscheidung helfen, die in der Ausgabe-Entität gespeicherten Ergebnisse zu verwenden.
        - Bewertungen werden auf der Grundlage der folgenden Regeln ermittelt:
            - **EIN** wenn das Modell mindestens 50% der Gesamtvorhersagen genau vorhergesagt hat und wenn der Prozentsatz der genauen Vorhersagen für Kunden, die Abwanderung betrieben haben, um mindestens 10% der historischen Abwanderungsrate über der historischen durchschnittlichen Abwanderungsrate liegt.
            - **B** wenn das Modell mindestens 50% der Gesamtvorhersagen genau vorhergesagt hat und wenn der Prozentsatz der genauen Vorhersagen für Kunden, die Abwanderung betrieben haben, um mindestens 10% der historischen Abwanderungsrate über der historischen durchschnittlichen Abwanderungsrate liegt.
            - **C** wenn das Modell weniger als 50% der Gesamtvorhersagen genau vorhergesagt hat oder wenn der Prozentsatz der genauen Vorhersagen für Kunden, die Abwanderung betrieben haben, geringer ist als die historische durchschnittliche Abwanderungsrate.
               > [!div class="mx-imgBorder"]
               > ![Ansicht der Modellleistungsergebnisse.](media/subscription-churn-modelperformance.PNG "Ansicht des Leistungsergebnisses des Modells")
    1. **Wahrscheinlichkeit der Abwanderung (Anzahl der Kunden):** Kundengruppen auf der Grundlage ihres vorhergesagten Abwanderungsrisikos. Diese Daten können Ihnen später helfen, wenn Sie ein Kundensegment mit hohem Abwanderungsrisiko erstellen möchten. Solche Segmente helfen Ihnen zu verstehen, wo Ihr Grenzwert für die Segmentmitgliedschaft liegen sollte.
       > [!div class="mx-imgBorder"]
       > ![Grafik zur Verteilung der Abwanderungsergebnisse, unterteilt in Bereiche von 0–100 %.](media/subscription-churn-resultdistribution.PNG "Grafik zur Verteilung der Abwanderungsergebnisse, unterteilt in Bereiche von 0 bis 100 %.")
    1. **Die wichtigsten Einflussfaktoren:** Es gibt viele Faktoren, die bei der Erstellung Ihrer Vorhersage berücksichtigt werden. Für jeden dieser Faktoren wird ihre Bedeutung für die aggregierten Vorhersagen, die ein Modell erstellt, berechnet. Sie können diese Faktoren verwenden, um Ihre Vorhersageergebnisse zu validieren. Oder Sie können diese Informationen später verwenden, um [Segmente](segments.md) zu erstellen, die dazu beitragen könnten, das Abwanderungsrisiko für Kunden zu beeinflussen.
       > [!div class="mx-imgBorder"]
       > ![Liste, die die Einflussfaktoren und ihre Bedeutung bei der Vorhersage des Abwanderungsergebnisses zeigt.](media/subscription-churn-influentialfactors.PNG "Liste mit Einflussfaktoren und deren Bedeutung für die Vorhersage des Abwanderungsergebnisses")

## <a name="manage-predictions"></a>Verwalten von Vorhersagen

Es ist möglich, Vorhersagen zu optimieren, zu korrigieren, zu aktualisieren oder zu löschen. Sehen Sie sich einen Eingabedaten-Nutzungsberichts an, um herauszufinden, wie Sie Vorhersagen schneller und zuverlässiger machen. Weitere Informationen finden Sie unter [Verwalten von Vorhersagen](manage-predictions.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]