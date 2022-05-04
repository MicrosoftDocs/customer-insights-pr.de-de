---
title: Transaktions-Churn vorhersagen (enthält Video)
description: Sagen Sie voraus, ob bei einem Kunden das Risiko besteht, dass er Ihre Produkte oder Dienstleistungen nicht mehr kauft.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: e55ca8c6926fa0bda05aaf52fd799ca25f7f585f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647500"
---
# <a name="transaction-churn-prediction"></a>Transaktionsabwanderung vorhersagen

Die Transaktionsabwanderungsvorhersage hilft bei der Vorhersage, ob ein Kunde Ihre Produkte oder Dienstleistungen in einem bestimmten Zeitfenster nicht mehr kaufen wird. Sie können neue Churn-Vorhersagen auf **Intelligenz** > **Vorhersagen** erstellen. Wählen Sie **Meine Vorhersagen**, um andere Vorhersagen anzuzeigen, die Sie erstellt haben. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Für Umgebungen, die auf Geschäftskonten basieren, können wir die Transaktionsabwanderung für ein Konto und auch eine Kombination aus Konto und einer anderen Informationsebene wie Produktkategorie vorhersagen. Durch das Hinzufügen einer Dimension können Sie herausfinden, wie wahrscheinlich es ist, dass das Konto Contoso die Produktkategorie Bürobedarf nicht mehr kauft. Darüber hinaus können wir für Geschäftskonten auch KI verwenden, um eine Liste potenzieller Gründe zu erstellen, warum ein Konto wahrscheinlich nach einer Kategorie von Informationen auf sekundärer Ebene abwandert.

> [!TIP]
> Probieren Sie das Tutorial für eine Transaktionsabwanderungs-Vorhersage mit Beispieldaten aus: [Transaktionsabwanderungs-Vorhersage – Beispielanleitung](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Anforderungen

# <a name="individual-consumers-b-to-c"></a>[Einzelne Verbraucher (B2C)](#tab/b2c)

- Mindestens die [Berechtigung "Mitwirkender"](permissions.md) in Customer Insights.
- Geschäftswissen, um zu verstehen, was Abwanderung für Ihr Unternehmen bedeutet. Wir unterstützen zeitbasierte Abwanderungsdefinitionen, was bedeutet, dass ein Kunde nach einem Zeitraum ohne Käufe als abgewandert gilt.
- Daten über Ihre Transaktionen/Einkäufe und deren Historie:
    - Transaktionskennungen, um Käufe/Transaktionen zu unterscheiden.
    - Kundenidentifikatoren, um Transaktionen Ihren Kunden zuzuordnen.
    - Transaktionsereignisdaten, die das Datum definieren, an dem die Transaktion stattgefunden hat.
    - Das semantische Datenschema für Käufe/Transaktionen benötigt die folgenden Informationen:
        - **Transaktions-ID**:  Ein eindeutiger Bezeichner eines Kaufs oder einer Transaktion.
        - **Transaktionsdatum**: Das Datum des Kaufs oder der Transaktion.
        - **Wert der Transaktion**: Der Währungswert/numerischer Wert der Transaktion/des Elements.
        - (Optional) **Einzige Produkt-ID**: Die ID des gekauften Produkts oder Dienstes, wenn Ihre Daten auf Einzelpostenebene sind.
        - (Optional) **Ob diese Transaktion eine Rückgabe war**: Ein Wahr/Falsch-Feld, das angibt, ob die Transaktion eine Rückgabe war oder nicht. Wenn der **Wert der Transaktion** negativ ist, wird auch diese Information verwendet, um eine Rückgabe abzuleiten.
- (Optional) Daten über Kundenaktivitäten:
    - Aktivitätskennungen zur Unterscheidung von Aktivitäten desselben Typs.
    - Kundenidentifikatoren zur Zuordnung von Aktivitäten zu Ihren Kunden.
    - Aktivitätsinformationen, die den Namen und das Datum der Aktivität enthalten.
    - Das semantische Datenschema für Kundenaktivitäten umfasst
        - **Primärschlüssel:** Ein eindeutiger Identifikator für eine Aktivität. Zum Beispiel ein Website-Besuch oder ein Verwendungsnachweis, der zeigt, dass der Kunde eine Probe Ihres Produkts ausprobiert hat.
        - **Zeitstempel:** Das Datum und die Uhrzeit des durch den Primärschlüssel identifizierten Ereignisses.
        - **Ereignis:** Der Name des Ereignisses, das Sie verwenden möchten. Ein Feld namens „UserAction“ in einem Lebensmittelgeschäft könnte z.B. die Verwendung des Coupons durch den Kunden sein.
        - **Details:** Detaillierte Informationen über das Ereignis. Zum Beispiel könnte ein Feld namens „CouponValue“ in einem Lebensmittelgeschäft der Währungswert des Coupons sein.

# <a name="business-accounts-b-to-b"></a>[Unternehmenskonten (B2B)](#tab/b2b)

- Mindestens die [Berechtigung "Mitwirkender"](permissions.md) in Customer Insights.
- Geschäftswissen, um zu verstehen, was Abwanderung für Ihr Unternehmen bedeutet. Wir unterstützen zeitbasierte Abwanderungsdefinitionen, was bedeutet, dass ein Kunde nach einem Zeitraum ohne Käufe als abgewandert gilt.
- Daten über Ihre Transaktionen/Einkäufe und deren Historie:
    - Transaktionskennungen, um Käufe/Transaktionen zu unterscheiden.
    - Kundenidentifikatoren, um Transaktionen Ihren Kunden zuzuordnen.
    - Transaktionsereignisdaten, die das Datum definieren, an dem die Transaktion stattgefunden hat.
    - Das semantische Datenschema für Käufe/Transaktionen benötigt die folgenden Informationen:
        - **Transaktions-ID**:  Ein eindeutiger Bezeichner eines Kaufs oder einer Transaktion.
        - **Transaktionsdatum**: Das Datum des Kaufs oder der Transaktion.
        - **Wert der Transaktion**: Der Währungswert/numerischer Wert der Transaktion/des Elements.
        - (Optional) **Einzige Produkt-ID**: Die ID des gekauften Produkts oder Dienstes, wenn Ihre Daten auf Einzelpostenebene sind.
        - (Optional) **Ob diese Transaktion eine Rückgabe war**: Ein Wahr/Falsch-Feld, das angibt, ob die Transaktion eine Rückgabe war oder nicht. Wenn der **Wert der Transaktion** negativ ist, wird auch diese Information verwendet, um eine Rückgabe abzuleiten.
- (Optional) Daten über Kundenaktivitäten:
    - Aktivitätskennungen zur Unterscheidung von Aktivitäten desselben Typs.
    - Kundenidentifikatoren zur Zuordnung von Aktivitäten zu Ihren Kunden.
    - Aktivitätsinformationen, die den Namen und das Datum der Aktivität enthalten.
    - Das semantische Datenschema für Kundenaktivitäten umfasst
        - **Primärschlüssel:** Ein eindeutiger Identifikator für eine Aktivität. Zum Beispiel ein Website-Besuch oder ein Verwendungsnachweis, der zeigt, dass der Kunde eine Probe Ihres Produkts ausprobiert hat.
        - **Zeitstempel:** Das Datum und die Uhrzeit des durch den Primärschlüssel identifizierten Ereignisses.
        - **Ereignis:** Der Name des Ereignisses, das Sie verwenden möchten. Ein Feld namens „UserAction“ in einem Lebensmittelgeschäft könnte z.B. die Verwendung des Coupons durch den Kunden sein.
        - **Details:** Detaillierte Informationen über das Ereignis. Zum Beispiel könnte ein Feld namens „CouponValue“ in einem Lebensmittelgeschäft der Währungswert des Coupons sein.
- (Optional) Daten über Ihre Kunden:
    - Diese Daten sollten an eher statischen Attributen ausgerichtet sein, um sicherzustellen, dass das Modell die beste Leistung erbringt.
    - Das semantische Datenschema für Kundendaten umfasst:
        - **KundenID** Ein Eindeutiger Bezeichner für einen Kunden.
        - **Erstellungsdatum:** Das Datum, an dem der Kunde ursprünglich hinzugefügt wurde.
        - **Staat oder Provinz:** Der Staat oder die Provinz eines Kunden.
        - **Land:** Das Land eines Kunden.
        - **Branche:** Der Branchentyp eines Kunden. Beispielsweise könnte ein Feld namens Industrie in einem Kaffeeröster anzeigen, ob es sich bei dem Kunden um einen Einzelhandelskunden handelt.
        - **Einstufung:** Die Kategorisierung eines Kunden für Ihr Unternehmen. Ein Feld namens ValueSegment in einem Kaffeeröster könnte beispielsweise die Kundenstufe basierend auf der Kundengröße sein.

---

- Vorgeschlagene Datencharakteristik:
    - Ausreichende historische Daten: Transaktionsdaten für mindestens das Doppelte des ausgewählten Zeitfensters. Vorzugsweise zwei bis drei Jahre Transaktionshistorie. 
    - Mehrfachkäufe pro Kunde: Idealerweise mindestens zwei Transaktionen pro Kunde.
    - Anzahl der Kunden: Mindestens 10 Kundenprofilen, vorzugsweise mehr als 1.000 eindeutigen Kunden. Das Modell schlägt mit weniger als 10 Kunden und unzureichenden historischen Daten fehl.
    - Vollständigkeit der Daten: Weniger als 20 % der fehlenden Werte im Datenfeld der angegebenen Entität.

> [!NOTE]
> Für ein Unternehmen mit hoher Kundenkaufhäufigkeit (alle paar Wochen) wird empfohlen, ein kürzeres Vorhersage-Fenster und eine kürzere Abwanderungsdefinition auszuwählen. Wählen Sie für eine niedrige Kaufhäufigkeit (alle paar Monate oder einmal im Jahr) ein längeres Vorhersage-Fenster und eine längere Abwanderungsdefinition.

## <a name="create-a-transaction-churn-prediction"></a>Eine Transkaktionsabwanderungs-Vorhersage erstellen

1. Gehen Sie in Customer Insights zu **Intelligenz** > **Vorhersagen**.

1. Wählen Sie die Kachel **Modell für Kundenabwanderung** und **Dieses Modell verwenden**.

1. In dem Bereich **Kundenabwanderungsmodell** wählen Sie **Transaktion** und dann **Erse Schritte**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Screenshot mit ausgewählter Transaktionsoption im Bereich Kundenabwanderungsmodell.":::
 
### <a name="name-model"></a>Modell benennen

1. Geben Sie einen Namen für das Modell an, um es von anderen Modellen zu unterscheiden.

1. Geben Sie einen Namen für die Ausgabe-Entität an, der nur Buchstaben und Zahlen ohne Leerzeichen enthält. Das ist der Name, den die Modell-Entität verwenden wird. 

1. Wählen **Weiter** aus.

### <a name="define-customer-churn"></a>Kundenabwanderung definieren

1. Legen Sie das **Vorhersagefenster** fest. Sagen Sie z. B. das Abwanderungsrisiko für Ihre Kunden in den nächsten 90 Tagen voraus, um Ihre Marketing-Bindungsmaßnahmen darauf abzustimmen. Die Vorhersage des Abwanderungsrisikos über einen längeren oder kürzeren Zeitraum kann es schwieriger machen, die Faktoren in Ihrem Abwanderungsrisikoprofil zu berücksichtigen, aber das hängt von Ihren spezifischen Geschäftsanforderungen ab.
   >[!TIP]
   > Sie können jederzeit **Entwurf speichern** auswählen, um die Vorhersage als Entwurf zu speichern. Sie finden den Entwurf der Vorhersage im Register **Meine Vorhersagen**, um fortzufahren.

1. Geben Sie die Anzahl der Tage ein, um im Feld **Churn-Definition** den Churn zu definieren. Wenn ein Kunde z. B. in den letzten 30 Tagen keine Käufe getätigt hat, könnte er für Ihr Unternehmen als abgewandert betrachtet werden. 

1. Wählen Sie **Weiter** aus, um den Vorgang fortzusetzen.

### <a name="add-required-data"></a>Erforderliche Daten hinzufügen

1. Wählen Sie **Daten hinzufügen** aus, und wählen Sie den Aktivitätstyp im Seitenbereich aus, der die erforderlichen Transaktions- oder Kaufverlaufsinformationen enthält.

1. Wählen Sie unter **Aktivitäten auswählen** die spezifischen Aktivitäten aus dem ausgewählten Aktivitätstyp aus, auf die sich die Berechnung konzentrieren soll.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Seitenbereich, der die Auswahl bestimmter Aktivitäten unter dem semantischen Typ zeigt.":::

   Wenn Sie die Aktivität noch keinem semantischen Typ zugeordnet haben, wählen Sie hierzu **Bearbeiten** aus. Die geführte Erfahrung zur Zuordnung semantischer Aktivitäten wird geöffnet. Ordnen Sie Ihre Daten jetzt den entsprechenden Feldern im ausgewählten Aktivitätstyp zu.

1. Ordnen Sie die semantischen Attribute den Feldern zu, die zum Ausführen des Modells erforderlich sind. Wenn die Felder unten nicht ausgefüllt sind, konfigurieren Sie die Beziehung von Ihrer Entität „Kaufhistorie“ zur Entität *Kunde*. Wählen Sie **Speichern**.

1. Wählen Sie im Schritt **Erforderliche Daten hinzufügen** **Weiter** aus, um fortzufahren, wenn Sie keine weiteren Aktivitäten hinzufügen möchten.


# <a name="individual-consumers-b-to-c"></a>[Einzelne Verbraucher (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Zusätzliche Daten hinzufügen (optional)

Konfigurieren Sie die Beziehung von Ihrer Kundenaktivitätsentität zur *Kunde*-Entität.

1. Wählen Sie das Feld, das den Kunden in der Kundenaktivitätstabelle identifiziert. Es kann sich direkt auf die primäre Kunden-ID Ihrer Entität *Kunde* beziehen.

1. Wählen Sie die Entität aus, die Ihre primäre *Kundenentität* ist.

1. Geben Sie einen Namen ein, der die Beziehung beschreibt.

#### <a name="customer-activities"></a>Kundenaktivitäten

1. Wählen Sie optional **Daten hinzufügen** für **Kundenaktivitäten**.

1. Wählen Sie den semantischen Aktivitätstyp aus, der die Daten enthält, die Sie verwenden möchten, und wählen Sie dann eine oder mehrere Aktivitäten im Bereich **Aktivitäten** aus.

1. Wählen Sie eine Aktivitätsart, die mit der Art der Kundenaktivität übereinstimmt, die Sie konfigurieren. Wählen Sie **Neu erstellen** und wählen Sie einen verfügbaren Aktivitätstyp oder erstellen Sie einen neuen Typ.

1. Wählen Sie **Weiter** und dann **Speichern** aus.

1. Wenn Sie weitere Kundenaktivitäten haben, die Sie einbeziehen möchten, wiederholen Sie die obigen Schritte.

# <a name="business-accounts-b-to-b"></a>[Unternehmenskonten (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Vorhersagestube auswählen

Die meisten Vorhersagen werden auf Kundenebene erstellt. In einigen Situationen ist dies möglicherweise nicht granular genug, um Ihre Geschäftsanforderungen zu erfüllen. Sie können diese Funktion verwenden, um die Abwanderung beispielsweise für eine Filiale eines Kunden und nicht für den gesamten Kunden vorherzusagen.

1. Um ein Vorhersage auf einer detaillierteren Ebene als der Kunde zu erstellen, wählen Sie **Entität für eine Sekundarstufe auswählen**. Wenn die Option nicht verfügbar ist, stellen Sie sicher, dass Sie den vorherigen Abschnitt abgeschlossen haben.

1. Erweitern Sie die Entitäten, aus denen Sie die sekundäre Ebene auswählen möchten, oder verwenden Sie das Suchfilterfeld, um die ausgewählten Optionen zu filtern.

1. Wählen Sie das Attribut aus, das Sie als sekundäre Ebene verwenden möchten, und wählen Sie dann **Hinzufügen**

1. Wählen **Weiter** aus.

> [!NOTE]
> Die in diesem Abschnitt verfügbaren Entitäten werden angezeigt, da sie eine Beziehung zu der Entität haben, die Sie im vorherigen Abschnitt ausgewählt haben. Wenn die Entität, die Sie hinzufügen möchten, nicht angezeigt wird, stellen Sie sicher, dass eine gültige Beziehung vorhanden ist unter **Beziehungen**. Nur 1:1- und n:1-Beziehungen sind für diese Konfiguration gültig.

### <a name="add-additional-data-optional"></a>Zusätzliche Daten hinzufügen (optional)

Konfigurieren Sie die Beziehung von Ihrer Kundenaktivitätsentität zur *Kunde*-Entität.

1. Wählen Sie das Feld, das den Kunden in der Kundenaktivitätstabelle identifiziert. Es kann sich direkt auf die primäre Kunden-ID Ihrer Entität *Kunde* beziehen.

1. Wählen Sie die Entität aus, die Ihre primäre *Kundenentität* ist.

1. Geben Sie einen Namen ein, der die Beziehung beschreibt.

#### <a name="customer-activities"></a>Kundenaktivitäten

1. Wählen Sie optional **Daten hinzufügen** für **Kundenaktivitäten**.

1. Wählen Sie den semantischen Aktivitätstyp aus, der die Daten enthält, die Sie verwenden möchten, und wählen Sie dann eine oder mehrere Aktivitäten im Bereich **Aktivitäten** aus.

1. Wählen Sie eine Aktivitätsart, die mit der Art der Kundenaktivität übereinstimmt, die Sie konfigurieren. Wählen Sie **Neu erstellen** und wählen Sie einen verfügbaren Aktivitätstyp oder erstellen Sie einen neuen Typ.

1. Wählen Sie **Weiter** und dann **Speichern** aus.

1. Wenn Sie weitere Kundenaktivitäten haben, die Sie einbeziehen möchten, wiederholen Sie die obigen Schritte.

#### <a name="customers-data"></a>Kundendaten

1. Wählen Sie optional **Daten hinzufügen** zu **Kundendaten** aus.

1. Ordnen Sie die semantischen Attribute wie identifiziert Feldern in Ihren eigenen Kundendaten zu. Die Daten in den verwendeten Feldern sollten sich nicht oft ändern, um die beste Leistung des Modells zu gewährleisten. Wenn Sie beispielsweise ein Feld für Klassifizierung auswählen, das sich jeden Monat ändert, wird nur der letzte Wert in der Vorhersage verwendet, auch wenn in der Vergangenheit möglicherweise nicht derselbe Wert für den Kunden beim Erstellen der Vorhersagemuster gilt.

1. Wählen **Weiter** aus.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Geben Sie eine optionale Liste von Benchmark-Konten an

Fügen Sie eine Liste Ihrer Geschäftskunden und Konten hinzu, die Sie als Benchmarks verwenden möchten. Sie erhalten [Details zu diesen Benchmark-Konten](#review-a-prediction-status-and-results) einschließlich ihrer Abwanderungsbewertung und der einflussreichsten Funktionen, die sich auf ihre Abwanderungs-Vorhersage ausgewirkt haben.

1. **+ Kunden hinzufügen** auswählen.

1. Wählen Sie die Kunden aus, die als Maßstab dienen.

1. Wählen Sie **Weiter** aus, um den Vorgang fortzusetzen.

---

### <a name="set-schedule-and-review-configuration"></a>Zeitplan festlegen und Konfiguration überprüfen

1. Legen Sie eine Häufigkeit fest, um Ihr Modell neu zu trainieren. Diese Einstellung ist wichtig, um die Genauigkeit der Vorhersagen zu aktualisieren, wenn neue Daten aufgenommen werden. Die meisten Unternehmen können einmal pro Monat eine Umschulung durchführen und erhalten eine gute Genauigkeit für ihre Vorhersagen.

1. Klicken Sie auf **Weiter**.

1. Überprüfen Sie die Konfiguration der Vorhersage. Sie können zu vorherigen Schritten zurückgehen, indem Sie **Bearbeiten** unter dem angezeigten Wert wählen. Oder Sie können einen Konfigurationsschritt aus der Fortschrittsanzeige auswählen.

1. Wenn alle Werte korrekt konfiguriert sind, wählen Sie **Speichern und ausführen**, um den Vorhersageprozess zu beginnen. Auf der Registerkarte **Meine Vorhersagen** können Sie den Status Ihrer Vorhersagen sehen. Der Prozess kann je nach der Menge der in der Vorhersage verwendeten Daten mehrere Stunden dauern.

## <a name="review-a-prediction-status-and-results"></a>Überprüfen eines Vorhersage-Status und der Ergebnisse

1. Gehen Sie zu **Intelligenz** > **Vorhersagen** und wählen Sie die Registerkarte **Meine Vorhersagen**.

1. Wählen Sie die Vorhersage aus, die Sie überprüfen möchten.
   - **Vorhersagename**: Name der Vorhersage, der beim Erstellen der Vorhersage angegeben wird.
   - **Vorhersagetyp**: Typ des für die Vorhersage verwendeten Modells
   - **Ausgabeentität**: Name der Entität zum Speichern der Ausgabe der Vorhersage. Eine Entität mit diesem Namen finden Sie unter **Daten** > **Entitäten**.
     In der Ausgabeentität ist *ChurnScore* die vorhergesagte Abwanderungswahrscheinlichkeit und *IsChurn* eine binäre Bezeichnung basierend auf *ChurnScore* mit Grenzwert 0,5. Der Standardschwellenwert funktioniert möglicherweise nicht für Ihr Szenario. [Erstellen Sie ein neues Segment](segments.md#create-a-new-segment) mit Ihrem bevorzugten Grenzwert.
     Nicht alle Kunden sind notwendigerweise aktive Kunden. Einige von ihnen hatten möglicherweise lange Zeit keine Aktivität mehr und werden aufgrund Ihrer Abwanderungsdefinition bereits als aufgewühlt angesehen. Die Vorhersage des Abwanderungsrisikos für Kunden, die bereits abgewandert sind, ist nicht sinnvoll, da sie nicht die Publikum von Interesse sind.
   - **Vorhersagefeld**: Dieses Feld wird nur für einige Arten von Vorhersagen ausgefüllt und wird nicht für die Abwanderungsvorhersage verwendet.
   - **Status:** Status des Vorhersagelaufs.
        - **In Warteschlange**: Die Vorhersage wartet auf die Ausführung anderer Prozesse.
        - **Auffrischen**: Die Vorhersage läuft gerade, um Ergebnisse zu erzeugen, die in die Ausgabe-Entität fließen.
        - **Fehlgeschlagen:** Der Vorhersagelauf ist fehlgeschlagen. [Betrachten Sie die Protokolle](manage-predictions.md#troubleshoot-a-failed-prediction) für weitere Details.
        - **Erfolgreich:** Die Vorhersage ist erfolgreich. Wählen Sie **Ansicht** unter den vertikalen Auslassungspunkten, um die Vorhersage zu überprüfen.
   - **Bearbeitet:** Das Datum, an dem die Konfiguration für die Vorhersage geändert wurde.
   - **Zuletzt aktualisiert:** Das Datum, an dem die Vorhersage in der Ausgabe-Entität aktualisiert wurde.

1. Markieren Sie die vertikalen Auslassungspunkte neben der Vorhersage, deren Ergebnisse Sie überprüfen möchten, und wählen Sie **Ansicht**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Steuerelement zum Anzeigen der Ergebnisse einer Vorhersage.":::

# <a name="individual-consumers-b-to-c"></a>[Einzelne Verbraucher (B2C)](#tab/b2c)

1. Es gibt drei primäre Datenabschnitte innerhalb der Ergebnisseite:
   - **Leistung des Trainingsmodells** A, B oder C sind mögliche Bewertungen. Diese Bewertung zeigt die Leistung der Vorhersage an und kann Ihnen bei der Entscheidung helfen, die in der Ausgabe-Entität gespeicherten Ergebnisse zu verwenden. Bewertungen werden auf der Grundlage der folgenden Regeln ermittelt: 
        - **A**, wenn das Modell mindestens 50 % der gesamten Vorhersagen richtig vorhergesagt hat und wenn der Prozentsatz der richtigen Vorhersagen für Kunden, die abgewandert sind, um mindestens 10 % größer ist als die Basisrate.
            
        - **B**, wenn das Modell mindestens 50 % der gesamten Vorhersagen richtig vorhergesagt hat und wenn der Prozentsatz der richtigen Vorhersagen für Kunden, die abgewandert sind, bis zu 10 % höher ist als die Basislinie.
            
        - **C**, wenn das Modell weniger als 50 % der gesamten Vorhersagen richtig vorhergesagt hat, oder wenn der Prozentsatz der richtigen Vorhersagen für Kunden, die abgewandert sind, kleiner ist als die Basislinie.
               
        - **Basis** nimmt das für das Modell eingegebene Vorhersage-Zeitfenster (z. B. ein Jahr) und das Modell erstellt verschiedene Zeitbruchteile, indem es durch 2 geteilt wird, bis es einen Monat oder weniger erreicht. Es verwendet diese Anteile, um eine Geschäftsregel für Kunden zu erstellen, die in diesem Zeitrahmen nicht gekauft haben. Diese Kunden werden als abgewandert betrachtet. Die zeitbasierte Geschäftsregel mit der höchsten Fähigkeit zur Vorhersage der Abwanderungswahrscheinlichkeit wird als Basismodell gewählt.
            
    - **Wahrscheinlichkeit der Abwanderung (Anzahl der Kunden)**: Kundengruppen auf der Grundlage ihres vorhergesagten Abwanderungsrisikos. Diese Daten können Ihnen später helfen, wenn Sie ein Kundensegment mit hohem Abwanderungsrisiko erstellen möchten. Solche Segmente helfen Ihnen zu verstehen, wo Ihr Grenzwert für die Segmentmitgliedschaft liegen sollte.
       
    - **Die wichtigsten Einflussfaktoren**: Es gibt viele Faktoren, die bei der Erstellung Ihrer Vorhersage berücksichtigt werden. Für jeden der Faktoren wird seine Wichtigkeit für die aggregierten Vorhersagen, die ein Modell erstellt, berechnet. Sie können diese Faktoren verwenden, um Ihre Vorhersage-Ergebnisse zu validieren, oder Sie können diese Informationen später verwenden, um [Segmente zu erstellen](segments.md). Dies könnte dazu beitragen, das Abwanderungsrisiko für Kunden zu beeinflussen.


# <a name="business-accounts-b-to-b"></a>[Unternehmenskonten (B2B)](#tab/b2b)

1. Es gibt drei primäre Datenabschnitte innerhalb der Ergebnisseite:
   - **Leistung des Trainingsmodells** A, B oder C sind mögliche Bewertungen. Diese Bewertung zeigt die Leistung der Vorhersage an und kann Ihnen bei der Entscheidung helfen, die in der Ausgabe-Entität gespeicherten Ergebnisse zu verwenden. Bewertungen werden auf der Grundlage der folgenden Regeln ermittelt: 
        - **A**, wenn das Modell mindestens 50 % der gesamten Vorhersagen richtig vorhergesagt hat und wenn der Prozentsatz der richtigen Vorhersagen für Kunden, die abgewandert sind, um mindestens 10 % größer ist als die Basisrate.
            
        - **B**, wenn das Modell mindestens 50 % der gesamten Vorhersagen richtig vorhergesagt hat und wenn der Prozentsatz der richtigen Vorhersagen für Kunden, die abgewandert sind, bis zu 10 % höher ist als die Basislinie.
            
        - **C**, wenn das Modell weniger als 50 % der gesamten Vorhersagen richtig vorhergesagt hat, oder wenn der Prozentsatz der richtigen Vorhersagen für Kunden, die abgewandert sind, kleiner ist als die Basislinie.
               
        - **Basis** nimmt das für das Modell eingegebene Vorhersage-Zeitfenster (z. B. ein Jahr) und das Modell erstellt verschiedene Zeitbruchteile, indem es durch 2 geteilt wird, bis es einen Monat oder weniger erreicht. Es verwendet diese Anteile, um eine Geschäftsregel für Kunden zu erstellen, die in diesem Zeitrahmen nicht gekauft haben. Diese Kunden werden als abgewandert betrachtet. Die zeitbasierte Geschäftsregel mit der höchsten Fähigkeit zur Vorhersage der Abwanderungswahrscheinlichkeit wird als Basismodell gewählt.
            
    - **Wahrscheinlichkeit der Abwanderung (Anzahl der Kunden)**: Kundengruppen auf der Grundlage ihres vorhergesagten Abwanderungsrisikos. Diese Daten können Ihnen später helfen, wenn Sie ein Kundensegment mit hohem Abwanderungsrisiko erstellen möchten. Solche Segmente helfen Ihnen zu verstehen, wo Ihr Grenzwert für die Segmentmitgliedschaft liegen sollte.
       
    - **Die wichtigsten Einflussfaktoren**: Es gibt viele Faktoren, die bei der Erstellung Ihrer Vorhersage berücksichtigt werden. Für jeden der Faktoren wird seine Wichtigkeit für die aggregierten Vorhersagen, die ein Modell erstellt, berechnet. Sie können diese Faktoren verwenden, um Ihre Vorhersage-Ergebnisse zu validieren, oder Sie können diese Informationen später verwenden, um [Segmente zu erstellen](segments.md). Dies könnte dazu beitragen, das Abwanderungsrisiko für Kunden zu beeinflussen.


1. Für Geschäftskonten finden Sie eine **Einflussreiche Merkmalsanalyse** Informationsseite. Es enthält vier Datenabschnitte:

    - Das im rechten Bereich ausgewählte Element bestimmt den Inhalt dieser Seite. Wählen Sie einen Artikel von **Top-Kunden** oder **Benchmark-Kunden** aus. Beide Listen sind nach abnehmendem Wert der Abwanderungsbewertung geordnet, unabhängig davon, ob die Bewertung nur für den Kunden oder eine kombinierte Bewertung für Kunden und eine sekundäre Ebene wie die Produktkategorie gilt.
        
        - **Top-Kunden**: Liste der 10 Kunden mit dem höchsten Abwanderungsrisiko und dem niedrigsten Abwanderungsrisiko basierend auf ihren Abwanderungswerten. 
        - **Benchmark-Kunden**: Liste von bis zu 10 Kunden, die bei der Konfiguration des Modells ausgewählt wurden.
 
    - **Abwanderungsquote:** Zeigt die Abwanderungsbewertung für das ausgewählte Element im rechten Fensterbereich an.
    
    - **Abwanderungsrisikoverteilung:** Zeigt die Abwanderungsrisikoverteilung über die Kunden und das Perzentil an, in dem sich der ausgewählte Kunde befindet. 
    
    - **Top-Funktionen, die das Abwanderungsrisiko erhöhen und verringern:** Für das ausgewählte Element im rechten Bereich werden die fünf wichtigsten Funktionen aufgelistet, die das Abwanderungsrisiko erhöht und verringert haben. Für jedes einflussreiche Merkmal finden Sie den Wert des Merkmals für dieses Element und seinen Einfluss auf die Abwanderungsquote. Der Durchschnittswert jedes Merkmals für Kundensegmente mit geringer, mittlerer und hoher Abwanderung wird ebenfalls angezeigt. Es hilft, die Werte der wichtigsten einflussreichen Merkmale für das ausgewählte Element besser zu kontextualisieren und mit Kundensegmenten mit geringer, mittlerer und hoher Abwanderung zu vergleichen.

       - Niedrig: Konten oder Kombinationen aus Konto und Sekundarstufe mit einem Abwanderungsscore zwischen 0 und 0,33
       - Mittel: Konten oder Kombinationen aus Konto und Sekundarstufe mit einem Abwanderungsscore zwischen 0,33 und 0,66
       - Hoch: Konten oder Kombinationen aus Konto und Sekundarstufe mit einem Abwanderungsscore größer als 0,66
    
       Wenn Sie die Abwanderung auf Kontoebene vorhersagen, werden alle Konten bei der Ableitung der durchschnittlichen Merkmalswerte für Abwanderungssegmente berücksichtigt. Bei Abwanderungsvorhersagen auf sekundärer Ebene für jedes Konto hängt die Ableitung von Abwanderungssegmenten von der sekundären Ebene des im Seitenbereich ausgewählten Elements ab. Wenn ein Artikel beispielsweise eine sekundäre Produktkategorie = Büroartikel hat, werden bei der Ableitung der durchschnittlichen Merkmalswerte für Abwanderungssegmente nur Artikel mit Büroartikeln als Produktkategorie berücksichtigt. Diese Logik wird angewendet, um einen fairen Vergleich der Merkmalswerte des Artikels mit den Durchschnittswerten in Segmenten mit niedriger, mittlerer und hoher Abwanderung zu gewährleisten.

       In einigen Fällen ist der Durchschnittswert von Segmenten mit niedriger, mittlerer oder hoher Abwanderung leer oder nicht verfügbar, da keine Artikel vorhanden sind, die gemäß der obigen Definition zu den entsprechenden Abwanderungssegmenten gehören.
       
       > [!NOTE]
       > Die Interpretation der Werte in den Spalten „Durchschnitt niedrig“, „mittel“ und „hoch“ ist für kategoriale Merkmale wie Land oder Branche unterschiedlich. Da der Begriff „durchschnittlicher“ Merkmalswert nicht für kategoriale Merkmale gilt, geben die Werte in diesen Spalten den Anteil der Kunden in Segmenten mit geringer, mittlerer oder hoher Abwanderung an, die den gleichen Wert des kategorialen Merkmals wie der Artikel aufweisen im Seitenbereich ausgewählt.

---

## <a name="manage-predictions"></a>Verwalten von Vorhersagen

Es ist möglich, Vorhersagen zu optimieren, zu korrigieren, zu aktualisieren oder zu löschen. Sehen Sie sich einen Eingabedaten-Nutzungsberichts an, um herauszufinden, wie Sie Vorhersagen schneller und zuverlässiger machen. Weitere Informationen finden Sie unter [Vorhersagen verwalten](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
