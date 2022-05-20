---
title: Produktempfehlungsvorhersage
description: Sagen Sie voraus, welche Produkte ein Kunde wahrscheinlich kaufen oder mit denen er interagieren wird.
ms.date: 05/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 9b3e60c49d294d031f43ef0594cb69707bb64019
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762731"
---
# <a name="product-recommendation-prediction"></a>Produktempfehlungsvorhersage

Das Produktempfehlungsmodell erstellt Sätze von prädiktiven Produktempfehlungen. Empfehlungen basieren auf dem vorherigen Kaufverhalten und Kunden mit ähnlichen Kaufmustern. Sie können neue Produktempfehlungsvorhersagen auf der Seite **Intelligenz** > **Vorhersagen** erstellen. Wählen Sie **Meine Vorhersagen**, um andere Vorhersagen anzuzeigen, die Sie erstellt haben.

Produktempfehlungen können lokalen Gesetzen und Vorschriften sowie Kundenerwartungen unterliegen, die das Modell nicht speziell berücksichtigt.  Als Benutzer dieser Vorhersagefähigkeit **müssen Sie die Empfehlungen überprüfen, bevor Sie sie an Ihre Kunden liefern**, um sicherzustellen, dass Sie alle geltenden Gesetze oder Vorschriften sowie die Kundenerwartungen für das, was Sie empfehlen, einhalten.

Darüber hinaus gibt Ihnen die Ausgabe dieses Modells Empfehlungen basierend auf der Produkt-ID. Ihr Übermittlungsmechanismus muss die vorhergesagten Produkt-IDs geeigneten Inhalten zuordnen, damit Ihre Kunden Lokalisierung, Bildinhalte und andere geschäftsspezifische Inhalte oder Verhaltensweisen berücksichtigen können.

## <a name="sample-guide"></a>Beispielanleitung

Wenn Sie diese Funktion ausprobieren möchten, aber keine Daten haben, um die folgenden Anforderungen zu erfüllen, können Sie [eine Beispielimplementierung erstellen](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Anforderungen

- Mindestens die [Berechtigung "Mitwirkender"](permissions.md) in Customer Insights.

- Geschäftskenntnisse, um verschiedene Arten von Produkten für Ihr Unternehmen zu verstehen und wie Ihre Kunden mit ihnen interagieren. Wir unterstützen die Empfehlung von Produkten, die zuvor von Ihren Kunden gekauft wurden, oder Empfehlungen für neue Produkte.

- Ihre Umgebung muss dafür konfiguriert sein, dass **einzelne Verbraucher** die primäre Zielgruppe sind.

- Daten über Transaktionen/Einkäufe und deren Historie:
  - Transaktionskennungen, um Käufe/Transaktionen zu unterscheiden.
  - Kundenidentifikatoren, um Transaktionen Ihren Kunden zuzuordnen.
  - Transaktionsereignisdaten, die das Datum definieren, an dem die Transaktion stattgefunden hat.
  - Produkt-ID-Informationen für die Transaktion.
  - (Optional) Eine Produktkatalogdatenentität zur Verwendung eines Produktfilters.
  - (Optional) Wenn eine Transaktion eine Rückgabe ist oder nicht.
  - Das semantische Datenschema benötigt die folgenden Informationen:
    - **Transaktions-ID:** Ein eindeutiger Bezeichner eines Kaufs oder einer Transaktion.
    - **Transaktionsdatum:** Das Datum des Kaufs oder der Transaktion.
    - **Wert der Transaktion:** Der numerische Wert des Kaufs oder der Transaktion.
    - **Eindeutige Produkt-ID:** Die ID des gekauften Produkts oder Dienstes, wenn Ihre Daten auf Einzelpostenebene sind.
    - (Optional) **Kauf oder Rückgabe:** Ein boolesches Feld, in dem der Wert *wahr* angibt, dass eine Transaktion eine Rückgabe war. Wenn die Kauf- oder Rückgabedaten nicht angegeben sind, werden das Modell und der **Wert der Transaktion** negativ sein. Wir werden diese Informationen auch verwenden, um auf eine Rückgabe zu schließen.
- Vorgeschlagene Datencharakteristik:
  - Ausreichende historische Daten: Mindestens ein Jahr Transaktionsdaten, vorzugsweise zwei bis drei Jahre, um eine gewisse Saisonalität zu berücksichtigen.
  - Mehrfachkäufe pro Kunde: Drei oder mehr Transaktionen pro Kunden-ID
  - Anzahl der Kunden: Mindestens 100 Kunden, vorzugsweise mehr als 10.000 Kunden. Das Modell wird mit weniger als 100 Kunden versagen.

> [!NOTE]
>
> - Das Modell erfordert die Transaktionshistorie Ihrer Kunden. Die Definition einer Transaktion ist sehr flexibel. Alle Daten, die eine Benutzer-Produkt-Interaktion beschreiben, können als Eingabe verwendet werden. Zum Beispiel: ein Produkt kaufen, eine Klasse besuchen oder an einer Veranstaltung teilnehmen.
> - Derzeit kann nur eine Transaktionsverlaufsentität konfiguriert werden. Wenn es mehrere Kauftitäten gibt, vereinen Sie sie vor der Datenaufnahme in Power Query.
> - Wenn Bestellung und Bestelldetails unterschiedliche Entitäten sind, verbinden Sie sie, bevor Sie sie im Modell verwenden. Das Modell funktioniert nicht nur mit einer Bestell- oder Beleg-ID in einer Entität.

## <a name="create-a-product-recommendation-prediction"></a>Produktempfehlungsvorhersage erstellen

1. Gehen Sie in Customer Insights zu **Intelligenz** > **Vorhersagen**.

1. Wählen Sie die Kachel **Modell für Produktempfehlungen** und **Dieses Modell verwenden**.
   > [!div class="mx-imgBorder"]
   > ![Produktempfehlungs-Modellkachel mit Schaltfläche „Dieses Modell verwenden“.](media/product-recommendation-usethismodel.PNG "Produktempfehlungs-Modellkachel mit Schaltfläche „Dieses Modell verwenden“")

1. Überprüfen Sie die Informationen zu den Modellanforderungen. Wenn Sie die erforderlichen Daten haben, wählen Sie **Erste Schritte**.

### <a name="name-model"></a>Modell benennen

1. Geben Sie einen Namen für das Modell an, um es von anderen Modellen zu unterscheiden.

1. Geben Sie einen Namen für die Ausgabeentität nur mit Buchstaben und Zahlen ohne Leerzeichen ein. Das ist der Name, den die Modell-Entität verwenden wird. Wählen Sie anschließend **Weiter** aus.

### <a name="define-product-recommendation-configuration"></a>Produktempfehlungskonfiguration definieren

1. Legen Sie die **Anzahl der Produkte** fest, die Sie einem Kunden empfehlen möchten. Dieser Wert hängt davon ab, wie Ihre Versandmethode Daten füllt. Wenn Sie drei Produkte empfehlen können, stellen Sie diesen Wert entsprechend ein.

   >[!TIP]
   > Sie können jederzeit **Entwurf speichern** auswählen, um die Vorhersage als Entwurf zu speichern. Die Entwurfsvorhersage finden Sie auf der **Meine Vorhersagen**-Registerkarte.

1. Wählen Sie aus, ob Sie Produkte, die Kunden kürzlich gekauft haben, in das **Wiederholungskäufe erwartet** aufnehmen möchten.

1. Legen Sie das **Fenster für Vergangenheitsdaten** fest. Diese Einstellung gibt den Zeitrahmen an, den das Modell berücksichtigt, bevor das Produkt dem Benutzer erneut empfohlen wird. Geben Sie beispielsweise an, dass ein Kunde alle zwei Jahre einen Laptop kauft. In diesem Fenster wird die Kaufhistorie der letzten zwei Jahre angezeigt. Wenn ein Artikel gefunden wird, wird der Artikel aus den Empfehlungen herausgefiltert.

1. Klicken Sie auf **Weiter**.

### <a name="add-required-data"></a>Erforderliche Daten hinzufügen

1. Wählen Sie **Daten hinzufügen** aus, und wählen Sie den Aktivitätstyp im Seitenbereich aus, der die erforderlichen Transaktions- oder Kaufverlaufsinformationen enthält.

1. Wählen Sie unter **Aktivitäten wählen** die spezifischen Aktivitäten aus der ausgewählten Aktivität aus, auf die sich die Berechnung konzentrieren soll.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Seitenbereich, der die Auswahl bestimmter Aktivitäten unter dem semantischen Typ zeigt.":::

1. Wenn Sie die Aktivität noch keinem semantischen Typ zugeordnet haben, wählen Sie hierzu **Bearbeiten** aus. Die geführte Erfahrung zur Zuordnung semantischer Aktivitäten wird geöffnet. Ordnen Sie Ihre Daten jetzt den entsprechenden Feldern im ausgewählten Aktivitätstyp zu.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Seite zum Festlegen des Aktivitätstyps.":::

1. Nachdem Sie die Aktivität dem entsprechenden semantischen Typ zugeordnet haben, wählen Sie **Weiter** aus, um fortzufahren.

1. Ordnen Sie die semantischen Attribute den Feldern zu, die zum Ausführen des Modells erforderlich sind.

1. Wählen Sie **Speichern** aus.

1. Wählen **Weiter** aus.

### <a name="configure-product-filters"></a>Produktfilter konfigurieren

Manchmal sind nur bestimmte Produkte für die Art von Vorhersage, die Sie erstellen, nützlich oder geeignet. Mit Produktfiltern können Sie eine Teilmenge von Produkten mit bestimmten Merkmalen identifizieren, die Sie Ihren Kunden empfehlen können. Das Modell verwendet alle verfügbaren Produkte, um Muster zu lernen, verwendet jedoch nur die Produkte, die dem Produktfilter in seiner Ausgabe entsprechen.

1. Im Schritt **Produktinformationen hinzufügen** fügen Sie Ihren Produktkatalog mit Informationen zu jedem Produkt hinzu. Ordnen Sie die erforderlichen Informationen zu, und wählen Sie dann **Weiter** aus.

1. Im Schritt **Produktfilter** wählen Sie zwischen den folgenden Optionen.

   - **Keine Filter**: Verwenden Sie alle Produkte in der Produktempfehlungsvorhersage.

   - **Bestimmte Produktfilter definieren**: Verwenden Sie bestimmte Produkte in der Produktempfehlungsvorhersage.

1. Klicken Sie auf **Weiter**.

1. Wenn Sie einen Produktfilter definieren möchten, müssen Sie ihn jetzt definieren. Im Bereich **Produktkatalogattribute** wählen Sie die Attribute aus Ihrer *Produktkatalog-Entität*, die Sie in den Filter aufnehmen möchten.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Seitenbereich, der in der Produktkatalogentität zugeordnet ist, die für Produktfilter ausgewählt wird.":::

1. Wählen Sie aus, ob der Produktfilter **und**- oder **oder**-Connectors verwenden soll, um Ihre Auswahl von Attributen aus dem Produktkatalog logisch zu kombinieren.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Beispielkonfiguration von Produktfiltern kombiniert mit logischen UND-Connectors.":::

1. Klicken Sie auf **Weiter**.

### <a name="set-update-schedule-and-review-configuration"></a>Updatezeitplan festlegen und Konfiguration überprüfen

1. Legen Sie eine Häufigkeit fest, um Ihr Modell neu zu trainieren. Diese Einstellung ist wichtig, um die Genauigkeit der Vorhersagen zu aktualisieren, wenn neue Daten in Customer Insights importiert werden. Die meisten Unternehmen können einmal pro Monat eine Umschulung durchführen und erhalten eine gute Genauigkeit für ihre Vorhersagen.

1. Klicken Sie auf **Weiter**.

1. Überprüfen Sie die Konfiguration. Sie können zu jedem Teil der Vorhersagekonfiguration zurückkehren, indem Sie unter dem angezeigten Wert **Bearbeiten** wählen. Oder Sie können einen Konfigurationsschritt aus der Fortschrittsanzeige auswählen.

1. Wenn alle Werte korrekt konfiguriert sind, wählen Sie **Speichern und ausführen**, um den Vorhersageprozess zu beginnen. Auf der Registerkarte **Meine Vorhersagen** können Sie den Status Ihrer Vorhersagen sehen. Der Prozess kann je nach der Menge der in der Vorhersage verwendeten Daten mehrere Stunden dauern.

## <a name="review-a-prediction-status-and-results"></a>Überprüfen eines Vorhersage-Status und der Ergebnisse

1. Gehen Sie zur Registerkarte **Meine Vorhersagen** auf **Intelligenz** > **Vorhersagen**.
   > [!div class="mx-imgBorder"]
   > ![Ansicht der Seite „Meine Vorhersagen“.](media/product-recommendation-mypredictions.PNG "Ansicht der Seite Meine Vorhersagen")

1. Wählen Sie die Vorhersage aus, die Sie überprüfen möchten.
   - **Name der Vorhersage:** Der Name der Vorhersage, der bei ihrer Erstellung angegeben wurde.
   - **Art der Vorhersage:** Typ des für die Vorhersage verwendeten Modells
   - **Ausgabe-Entität:** Name der Entität, die die Ausgabe der Vorhersage speichern soll. Eine Entität mit diesem Namen finden Sie unter **Daten** > **Entitäten**.
      *Ergebnis* in der Ausgabeeinheit ist ein quantitatives Maß für die Empfehlung. Das Modell empfiehlt Produkte mit einer höheren Punktzahl gegenüber Produkten mit einer niedrigeren Punktzahl.
   - **Vorhersagefeld:** Dieses Feld wird nur für einige Typen von Vorhersagen ausgefüllt und wird bei der Vorhersage der Produktempfehlung nicht verwendet.
   - **Status:** Der aktuelle Status des Ausführung der Vorhersage.
        - **Warteschleife:** Die Vorhersage wartet derzeit auf die Ausführung anderer Prozesse.
        - **Aktualisierung:** Die Vorhersage durchläuft derzeit die "Bewertung"-Verarbeitungsphase, um Ergebnisse zu erzeugen, die in die Ausgabe-Entität fließen werden.
        - **Fehlgeschlagen:** Die Vorhersage ist fehlgeschlagen. Wählen Sie **Protokolle** für weitere Einzelheiten.
        - **Erfolgreich:** die Vorhersage war erfolgreich. Wählen Sie **Ansicht** unter den vertikalen Auslassungspunkten, um die Vorhersage zu überprüfen.
   - **Bearbeitet:** Das Datum, an dem die Konfiguration für die Vorhersage geändert wurde.
   - **Zuletzt aktualisiert:** Das Datum, an dem die Vorhersage in der Ausgabe-Entität aktualisiert wurde.

1. Markieren Sie die vertikalen Auslassungspunkte neben der Vorhersage, deren Ergebnisse Sie überprüfen möchten, und wählen Sie **Ansicht**.
   > [!div class="mx-imgBorder"]
   > ![Anzeige der Optionen im Menü der vertikalen Auslassungspunkte für eine Vorhersage einschließlich Bearbeiten, Aktualisieren, Anzeigen, Protokolle und Löschen.](media/product-recommendation-verticalellipses.PNG "Ansicht der Optionen im Menü der vertikalen Auslassungspunkte für eine Vorhersage einschließlich Bearbeiten, Aktualisieren, Anzeigen, Protokolle und Löschen")

1. Auf der Ergebnisseite befinden sich fünf primäre Datenabschnitte:
    1. **Leistung des Trainingsmodells:** A, B oder C sind mögliche Bewertungen. Diese Bewertung zeigt die Leistung der Vorhersage an und kann Ihnen bei der Entscheidung helfen, die in der Ausgabe-Entität gespeicherten Ergebnisse zu verwenden.
        - Die Bewertungen werden nach den folgenden Regeln ermittelt:
            - **A** Das Modell wird berücksichtigt **A** Qualität, wenn die Metrik „Success @ K“ mindestens 10 % über der Basislinie liegt. 
            - **B** Das Modell wird berücksichtigt **B** Qualität, wenn die Metrik „Success @ K“ 0 % bis 10 % über der Basislinie liegt.
            - **C** Das Modell wird berücksichtigt **C** Qualität, wenn die Metrik „Success @ K“ unter der Basislinie liegt.

               > [!div class="mx-imgBorder"]
               > ![Ansicht der Modellleistungsergebnisse.](media/product-recommendation-modelperformance.PNG "Ansicht des Leistungsergebnisses des Modells")
            - **Basislinie**: Das Modell verwendet die am häufigsten empfohlenen Produkte nach Kaufanzahl für alle Kunden und verwendet erlernte Regeln, die vom Modell identifiziert wurden, um eine Reihe von Empfehlungen für die Kunden zu erstellen. Die Vorhersagen werden dann mit den Top-Produkten verglichen, berechnet anhand der Anzahl der Kunden, die das Produkt gekauft haben. Wenn ein Kunde mindestens ein Produkt in seinen empfohlenen Produkten hat, das auch in den am häufigsten gekauften Produkten enthalten ist, wird er als Teil der Baseline betrachtet. Wenn 10 dieser Kunden ein empfohlenes Produkt von insgesamt 100 Kunden gekauft hätten, wäre die Basis 10 %.
            - **Success @ K**: Mithilfe eines Validierungssatzes für den Zeitraum von Transaktionen werden Empfehlungen für alle Kunden erstellt und mit dem Validierungssatz für Transaktionen verglichen. Beispielsweise kann in einem Zeitraum von 12 Monaten der 12. Monat als Validierungsdatensatz reserviert werden. Wenn das Modell mindestens eine Sache vorhersagt, die Sie im 12. Monat kaufen würden, basierend auf den Erkenntnissen der letzten 11 Monate, würde der Kunde die Metrik „Success @ K“ erhöhen.

    1. **Die meisten empfohlenen Produkte (mit Tally):** Die fünf wichtigsten Produkte, die für Ihre Kunden vorhergesagt wurden.
       > [!div class="mx-imgBorder"]
       > ![Grafik mit den 5 am häufigsten empfohlenen Produkten.](media/product-recommendation-topproducts.PNG "Grafik mit den 5 am häufigsten empfohlenen Produkten")

    1. **Wichtige Empfehlungsfaktoren:** Das Modell verwendet die Transaktionshistorie der Kunden, um Produktempfehlungen abzugeben. Es lernt Muster basierend auf früheren Einkäufen und findet Ähnlichkeiten zwischen Kunden und Produkten. Diese Ähnlichkeiten werden dann verwendet, um Produktempfehlungen zu generieren.
    Die folgenden Faktoren können eine vom Modell generierte Produktempfehlung beeinflussen.
        - **Vergangene Transaktionen**: Kaufmuster in der Vergangenheit wurden vom Modell verwendet, um Produktempfehlungen zu generieren. Zum Beispiel kann das Modell eine *Surface Arc Mouse* empfehlen, wenn jemand vor kurzem ein *Surface Book 3* und einen *Surface Pen* gekauft hat. Das Modell erfuhr, dass in der Vergangenheit viele Kunden eine *Surface Arc Mouse* nach dem Kauf eines *Surface Book 3* und eines *Surface Pen* gekauft hatten.
        - **Kundenähnlichkeit**: Ein empfohlenes Produkt wurde in der Vergangenheit von anderen Kunden gekauft, die ähnliche Kaufmuster aufweisen. Zum Beispiel wurden John *Surface Headphones 2* empfohlen , weil Jennifer und Brad kürzlich *Surface Headphones 2* gekauft haben. Das Modell glaubt, dass John Jennifer und Brad ähnlich ist, weil sie in der Vergangenheit ähnliche Kaufmuster hatten.
        - **Produktähnlichkeit**: Ein empfohlenes Produkt ähnelt anderen Produkten, die der Kunde zuvor gekauft hat. Das Modell betrachtet zwei Produkte als ähnlich, wenn sie zusammen oder von ähnlichen Kunden gekauft wurden. Zum Beispiel bekommt jemand eine Empfehlung für ein *USB-Speicherlaufwerk*, weil sie zuvor einen *USB-C zu USB Adapter* gekauft haben und das Modell glaubt, dass *USB-Speicherlaufwerk* ähnlich ist wie *USB-C zu USB Adapter* basierend auf historischen Kaufmustern.

        Jede Produktempfehlung wird von einem oder mehreren dieser Faktoren beeinflusst. Der Prozentsatz der Empfehlungen, bei denen jeder Einflussfaktor eine Rolle spielte, wird in einem Diagramm dargestellt. Im folgenden Beispiel wurden 100 % der Empfehlungen durch vergangene Transaktionen beeinflusst, 60 % durch Kundenähnlichkeit und 22 % durch Produktähnlichkeit. Bewegen Sie den Mauszeiger über die Balken im Diagramm, um den genauen Prozentsatz anzuzeigen, zu dem die Einflussfaktoren beigetragen haben.

        > [!div class="mx-imgBorder"]
        > ![Wichtige Empfehlungsfaktoren.](media/product-recommendation-keyrecommendationfactors.png "Wichtige Empfehlungsfaktoren, die das Modell zur Generierung von Produktempfehlungen gelernt hat")

   1. **Datenstatistik** : Gibt einen Überblick über die Anzahl der Transaktionen, Kunden und Produkte, die das Modell berücksichtigt. Es basiert auf den Eingabedaten, die zum Lernen von Mustern und zum Generieren von Produktempfehlungen verwendet wurden.

      > [!div class="mx-imgBorder"]
      > ![Datenstatistiken.](media/product-recommendation-datastatistics.png "Datenstatistik zu Inout-Daten, die vom Modell zum Lernen von Mustern verwendet werden")

      Dieser Abschnitt zeigt Statistiken zu den Datenpunkten, die vom Modell verwendet wurden, um Muster zu lernen und Produktempfehlungen zu generieren. Die in der Modellkonfiguration konfigurierte Filterung gilt für die vom Modell generierte Ausgabe. Das Modell verwendet jedoch alle verfügbaren Daten, um Muster zu lernen. Wenn Sie in der Modellkonfiguration die Produktfilterung verwenden, wird in diesem Abschnitt die Gesamtzahl der Produkte angezeigt, die das Modell analysiert hat, um Muster zu lernen, die von der Anzahl der Produkte abweichen können, die den definierten Filterkriterien entsprechen.

   1. **Produktempfehlungen mit hoher Konfidenz:** Eine Auswahl von Empfehlungen an Ihre Kunden, von denen das Modell glaubt, dass sie wahrscheinlich vom Kunden gekauft werden.    
      Wenn ein Produktkatalog hinzugefügt wird, werden die Produkt-IDs durch Produktnamen ersetzt. Produktnamen bieten umsetzbarere und intuitivere Informationen zu den Vorhersagen.
       > [!div class="mx-imgBorder"]
       > ![Liste mit Vorschlägen für hohes Vertrauen für eine ausgewählte Gruppe einzelner Kunden.](media/product-recommendation-highconfidence.PNG "Liste mit Vorschlägen für hohes Vertrauen für eine ausgewählte Gruppe einzelner Kunden")

## <a name="manage-predictions"></a>Verwalten von Vorhersagen

Es ist möglich, Vorhersagen zu optimieren, zu korrigieren, zu aktualisieren oder zu löschen. Sehen Sie sich einen Eingabedaten-Nutzungsberichts an, um herauszufinden, wie Sie Vorhersagen schneller und zuverlässiger machen. Weitere Informationen finden Sie unter [Verwalten von Vorhersagen](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
