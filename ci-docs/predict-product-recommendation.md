---
title: Produktempfehlungen vorhersagen
description: Sagen Sie voraus, welche Produkte ein Kunde wahrscheinlich kaufen oder mit denen er interagieren wird.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610281"
---
# <a name="predict-product-recommendations"></a>Produktempfehlungen vorhersagen

Das Produktempfehlungsmodell erstellt Sätze von prädiktiven Produktempfehlungen. Empfehlungen basieren auf dem vorherigen Kaufverhalten und Kunden mit ähnlichen Kaufmustern. Dieses Modell ist für Privatkunden (B2C).

Sie müssen Geschäftskenntnisse über die verschiedenen Arten von Produkten für Ihr Unternehmen und wie Ihre Kunden mit ihnen interagieren haben. Wir unterstützen die Empfehlung von Produkten, die zuvor von Ihren Kunden gekauft wurden, oder Empfehlungen für neue Produkte.

Produktempfehlungen können lokalen Gesetzen und Vorschriften sowie Kundenerwartungen unterliegen, die das Modell nicht speziell berücksichtigt. Daher **müssen Sie die Empfehlungen überprüfen, bevor Sie sie an Ihre Kunden liefern**, um sicherzustellen, dass Sie alle geltenden Gesetze oder Vorschriften sowie die Kundenerwartungen für das, was Sie empfehlen, einhalten.

Die Ausgabe dieses Modells stellt Empfehlungen basierend auf der Produkt-ID bereit. Ihr Übermittlungsmechanismus muss die vorhergesagten Produkt-IDs geeigneten Inhalten zuordnen, um Ihren Kunden Inhalte unter Berücksichtigung von Lokalisierung, Bildinhalte und anderen geschäftsspezifischen Inhalten oder Verhaltensweisen zuzuweisen.

> [!TIP]
> Probieren Sie die Produktempfehlungsvorhersage mithilfe von Beispieldaten aus: [Beispielleitfaden für Produktempfehlungsvorhersage Beispielleitfaden](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Anforderungen

- Mindestens [Berechtigungen als Mitwirkender](permissions.md)
- Mindestens 100 Kunden, vorzugsweise mehr als 10.000 Kunden.
- Kundenkennung, eine eindeutige Kennung, um Transaktionen einem einzelnen Kunden zuzuordnen
- Mindestens ein Jahr Transaktionsdaten, vorzugsweise zwei bis drei Jahre, um eine gewisse Saisonalität zu berücksichtigen. Idealerweise mindestens drei oder mehr Transaktionen pro Kunden-ID. Der Transaktionsverlauf muss Folgendes enthalten:
  - **Transaktions-ID**: Eindeutiger Bezeichner eines Kaufs oder einer Transaktion.
  - **Transaktionsdatum**: Datum des Kaufs oder der Transaktion.
  - **Wert der Transaktion:** Numerischer Wert des Kaufs oder der Transaktion.
  - **Eindeutige Produkt-ID**: ID des gekauften Produkts oder Services, wenn Ihre Daten auf Einzelpostenebene sind.
  - **Kauf oder Rückgabe:** Ein boolesches Wahr-/Falsch-Feld, in dem der Wert *wahr* angibt, dass eine Transaktion eine Rückgabe war. Wenn die Kauf- oder Rückgabedaten nicht angegeben sind, sind das Modell und der **Wert der Transaktion** negativ und wir gehen von einer Rückgabe aus.
- Eine Produktkatalogdatenentität zur Verwendung als Produktfilters.

> [!NOTE]
> - Das Modell erfordert den Transaktionsverlauf Ihrer Kunden, wobei eine Transaktion alle Daten sind, die eine Benutzer-Produkt-Interaktion beschreiben. Zum Beispiel: ein Produkt kaufen, eine Klasse besuchen oder an einer Veranstaltung teilnehmen.
> - Nur eine Transaktionsverlaufsentität kann konfiguriert werden. Wenn es mehrere Kauftitäten gibt, kombinieren Sie sie vor der Datenerfassung in Power Query.
> - Wenn Bestellung und Bestelldetails unterschiedliche Entitäten sind, verbinden Sie sie, bevor Sie sie im Modell verwenden. Das Modell funktioniert nicht nur mit einer Bestell- oder Beleg-ID in einer Entität.

## <a name="create-a-product-recommendation-prediction"></a>Produktempfehlungsvorhersage erstellen

Wählen Sie **Entwurf speichern** aus, um die Vorhersage als Entwurf zu speichern. Die Entwurfsvorhersage wird in der Registerkarte **Meine Vorhersagen** angezeigt.

1. Gehen Sie zu **Intelligenz** > **Vorhersagen**.

1. Wählen Sie in der Registerkarte **Erstellen** **Modell verwenden** auf der Kachel **Produktempfehlungen (Vorschauversion)** aus.

1. Wählen Sie **Erste Schritte** aus.

1. **Dieses Modell benennen** und **Ausgabeentitätsname**, um sie von anderen Modellen oder Entitäten zu unterscheiden.

1. Wählen Sie **Weiter** aus.

### <a name="define-product-recommendation-preferences"></a>Produktempfehlungspräferenzen definieren

1. Legen Sie die **Anzahl der Produkte** fest, die einem Kunden empfohlen werden soll. Dieser Wert hängt davon ab, wie Ihre Versandmethode Daten füllt.

1. Wählen Sie aus, ob Sie Produkte, die Kunden früher gekauft haben, in das **Wiederholungskäufe erwartet** aufnehmen möchten.

1. Legen Sie im **Fenster für Vergangenheitsdaten** den Zeitrahmen an, den das Modell berücksichtigt, bevor das Produkt dem Benutzer erneut empfohlen wird. Geben Sie beispielsweise an, dass ein Kunde alle zwei Jahre einen Laptop kauft. Das Modell sieht sich den Kaufverlauf der letzten zwei Jahre an und wenn es einen Artikel findet, wird er aus den Empfehlungen herausgefiltert.

1. Klicken Sie auf **Weiter**.

### <a name="add-purchase-history"></a>Kaufverlauf hinzufügen

1. Wählen Sie **Daten hinzufügen** für **Kundentransaktionsverlauf** aus.

1. Wählen Sie den semantischen Aktivitätstyp **SalesOrderLine** aus, der die erforderlichen Transaktions- oder Kaufverlaufsinformationen enthält. Wenn die Aktivität nicht eingerichtet wurde, wählen Sie sie **hier** aus und erstellen Sie sie.

1. Wählen Sie unter **Aktivitäten**, wenn die Aktivitätsattribute der Aktivität semantisch zugeordnet wurden, die spezifischen Attribute oder Entitäten aus, auf die sich die Berechnung konzentrieren soll. Wenn keine semantische Zuordnung erfolgt ist, wählen Sie **Bearbeiten** aus und ordnen Sie Ihre Daten aus.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Seitenbereich, der die Auswahl bestimmter Aktivitäten unter dem semantischen Typ zeigt.":::

1. Wählen Sie **Nächste** und überprüfen Sie die für dieses Modell erforderlichen Attribute.

1. Wählen Sie **Save** (Speichern).

1. Wählen Sie **Weiter** aus.

### <a name="add-product-information-and-filters"></a>Produktinformationen und Filter hinzufügen

Manchmal sind nur bestimmte Produkte für die Art von Vorhersage, die Sie erstellen, nützlich oder geeignet. Verwenden Sie Produktfilter, um eine Teilmenge von Produkten mit bestimmten Merkmalen zu identifizieren, die Sie Ihren Kunden empfehlen können. Das Modell verwendet alle verfügbaren Produkte, um Muster zu lernen, verwendet jedoch nur die Produkte, die dem Produktfilter in seiner Ausgabe entsprechen.

1. Fügen Sie Ihre Produktkatalogentität hinzu, die Informationen für jedes Produkt enthält. Ordnen Sie die erforderlichen Informationen zu und wählen Sie **Speichern** aus.

1. Wählen Sie **Weiter** aus.

1. Wählen Sie **Produktfilter** aus:

   - **Keine Filter**: Verwenden Sie alle Produkte in der Produktempfehlungsvorhersage.

   - **Bestimmte Produktfilter definieren**: Verwenden Sie bestimmte Produkte in der Produktempfehlungsvorhersage. Wählen Sie im Bereich **Produktkatalogattribute** die Attribute aus Ihrer Produktkatalogentität aus, die Sie in den Filter aufnehmen möchten.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Seitenbereich, der in der Produktkatalogentität zugeordnet ist, die für Produktfilter ausgewählt wird.":::

1. Wählen Sie aus, ob der Produktfilter **Und**- oder **Oder**-Connectors verwenden soll, um Ihre Auswahl von Attributen aus dem Produktkatalog logisch zu kombinieren.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Beispielkonfiguration von Produktfiltern kombiniert mit logischen UND-Connectors.":::

1. Wählen Sie **Weiter** aus.

### <a name="set-update-schedule"></a>Zeitplanaktualisierung festlegen

1. Wählen Sie eine Häufigkeit aus, um Ihr Modell neu zu trainieren. Diese Einstellung ist wichtig, um die Genauigkeit der Vorhersagen zu aktualisieren, wenn neue Daten in Customer Insights aufgenommen werden. Die meisten Unternehmen können einmal pro Monat eine Umschulung durchführen und erhalten eine gute Genauigkeit für ihre Vorhersagen.

1. Wählen Sie **Weiter** aus.

### <a name="review-and-run-the-model-configuration"></a>Überprüfen Sie die Modellkonfiguration und führen Sie sie aus

Der Schritt **Überprüfen und ausführen** zeigt eine Zusammenfassung der Konfiguration und bietet die Möglichkeit, Änderungen vorzunehmen, bevor Sie die Datei Vorhersage erstellen.

1. Wählen Sie **Bearbeiten** bei einem der Schritte, um sie zu überprüfen und Änderungen vorzunehmen.

1. Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **Speichern und ausführen** aus, um das Modell ausführen zu lassen. Wählen Sie **Fertig** aus. Die Registerkarte **Meine Vorhersagen** wird angezeigt, während Vorhersage erstellt wird. Der Prozess kann je nach der Menge der in der Vorhersage verwendeten Daten mehrere Stunden dauern.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Vorhersageergebnisse anzeigen

1. Gehen Sie zu **Intelligenz** > **Vorhersagen**.

1. Wählen Sie in der Registerkarte **Meine Vorhersagen** die Vorhersage aus, die Sie ansehen möchten.

Auf der Ergebnisseite befinden sich fünf primäre Datenabschnitte.

- **Modelleistung:** Die Stufen A, B oder C geben die Leistung der Vorhersage an und können Ihnen bei der Entscheidung helfen, die in der Ausgabeentität gespeicherten Ergebnisse zu verwenden.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Bild des Ergebnisses der Modellleistung mit der Stufe A.":::

  Die Stufen werden nach den folgenden Regeln ermittelt:
  - **A** wenn die Metrik „Success @ K“ mindestens 10 % über der Baseline liegt.
  - **B** wenn die Metrik „Success @ K“ mindestens 0 bis 10 % über der Baseline liegt.
  - **C** wenn die Metrik „Success @ K“ unter der Baseline liegt.
  - **Baseline**: Die am häufigsten empfohlenen Produkte nach Kaufanzahl für alle Kunden und erlernte Regeln, die vom Modell identifiziert wurden = eine Reihe von Empfehlungen für die Kunden. Die Vorhersagen werden dann mit den Top-Produkten verglichen, berechnet anhand der Anzahl der Kunden, die das Produkt gekauft haben. Wenn ein Kunde mindestens ein Produkt in seinen empfohlenen Produkten hat, das auch in den am häufigsten gekauften Produkten enthalten ist, wird er als Teil der Baseline betrachtet. Wenn zum Beispiel 10 dieser Kunden ein empfohlenes Produkt von insgesamt 100 Kunden gekauft hätten, ist die Baseline 10 %.
  - **Success @ K**: Empfehlungen werden für alle Kunden erstellt und mit dem Validierungssatz des Zeitraums der Transaktionen verglichen. Beispielsweise ist in einem Zeitraum von 12 Monaten der 12. Monat als Validierungsdatensatz festgelegt. Wenn das Modell mindestens eine Sache vorhersagt, die Sie im 12. Monat kaufen würden, basierend auf den Erkenntnissen der letzten 11 Monate, würde der Kunde die Metrik „Success @ K“ erhöhen.

- **Die meisten empfohlenen Produkte (mit Tally):** Die fünf wichtigsten Produkte, die für Ihre Kunden vorhergesagt wurden.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Grafik mit den 5 am häufigsten empfohlenen Produkten.":::

- **Wichtige Empfehlungsfaktoren:** Das Modell verwendet die Transaktionshistorie der Kunden, um Produktempfehlungen abzugeben. Es lernt Muster basierend auf früheren Einkäufen und findet Ähnlichkeiten zwischen Kunden und Produkten. Diese Ähnlichkeiten werden dann verwendet, um Produktempfehlungen zu generieren.
  Die folgenden Faktoren könnten eine vom Modell generierte Produktempfehlung beeinflussen.
  - **Vergangene Transaktionen** : Ein empfohlenes Produkt basierte auf früheren Kaufmustern. Zum Beispiel kann das Modell eine *Surface Arc Mouse* empfehlen, wenn jemand vor kurzem ein *Surface Book 3* und einen *Surface Pen* gekauft hat. Das Modell erfuhr, dass in der Vergangenheit viele Kunden eine *Surface Arc Mouse* nach dem Kauf eines *Surface Book 3* und eines *Surface Pen* gekauft hatten.
  - **Kundenähnlichkeit**: Ein empfohlenes Produkt wurde in der Vergangenheit von anderen Kunden gekauft, die ähnliche Kaufmuster aufweisen. Zum Beispiel wurden John *Surface Headphones 2* empfohlen , weil Jennifer und Brad kürzlich *Surface Headphones 2* gekauft haben. Das Modell glaubt, dass John Jennifer und Brad ähnlich ist, weil sie in der Vergangenheit ähnliche Kaufmuster hatten.
  - **Produktähnlichkeit**: Ein empfohlenes Produkt ähnelt anderen Produkten, die der Kunde zuvor gekauft hat. Das Modell betrachtet zwei Produkte als ähnlich, wenn sie zusammen oder von ähnlichen Kunden gekauft wurden. Zum Beispiel bekommt jemand eine Empfehlung für ein *USB-Speicherlaufwerk*, weil sie zuvor einen *USB-C zu USB Adapter* gekauft haben und das Modell glaubt, dass *USB-Speicherlaufwerk* ähnlich ist wie *USB-C zu USB Adapter* basierend auf historischen Kaufmustern.

  Jede Produktempfehlung wird von einem oder mehreren dieser Faktoren beeinflusst. Der Prozentsatz der Empfehlungen, bei denen jeder Einflussfaktor eine Rolle spielte, wird in einem Diagramm dargestellt. Im folgenden Beispiel wurden 100 % der Empfehlungen durch vergangene Transaktionen beeinflusst, 60 % durch Kundenähnlichkeit und 22 % durch Produktähnlichkeit. Bewegen Sie den Mauszeiger über die Balken im Diagramm, um den genauen Prozentsatz anzuzeigen, zu dem die Einflussfaktoren beigetragen haben.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Wichtige Empfehlungsfaktoren, die das Modell zur Generierung von Produktempfehlungen gelernt hat.":::

- **Datenstatistik** : Ein Überblick über die Anzahl der Transaktionen, Kunden und Produkte, die das Modell berücksichtigt. Es basiert auf den Eingabedaten, die zum Lernen von Mustern und zum Generieren von Produktempfehlungen verwendet wurden.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Datenstatistik zu Eingabedaten, die vom Modell zum Lernen von Mustern verwendet werden.":::
  
  Das Modell verwendet alle verfügbaren Daten, um Muster zu lernen. Wenn Sie in der Modellkonfiguration die Produktfilterung verwenden, wird in diesem Abschnitt die Gesamtzahl der Produkte angezeigt, die das Modell analysiert hat, um Muster zu lernen, die von der Anzahl der Produkte abweichen kann, die den definierten Filterkriterien entsprechen. Die Filterung gilt für die vom Modell generierte Ausgabe.

- **Beispielproduktempfehlungen:** Eine Auswahl von Empfehlungen, von denen das Modell glaubt, dass sie wahrscheinlich vom Kunden gekauft werden. Wenn ein Produktkatalog hinzugefügt wird, werden die Produkt-IDs durch Produktnamen ersetzt.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Liste mit Vorschlägen für hohes Vertrauen für eine ausgewählte Gruppe einzelner Kunden.":::

> [!NOTE]
> In der Ausgabeentität für dieses Modell zeigt *Ergebnis* die quantitative Messung für die Empfehlung. Das Modell empfiehlt Produkte mit einer höheren Punktzahl gegenüber Produkten mit einer niedrigeren Punktzahl. Um das Ergebnis anzuzeigen, gehen Sie zu **Daten** > **Entitäten** und zeigen Sie die Registerkarte „Daten“ für die Ausgabeentität an, die Sie für dieses Modell festgelegt haben.

[!INCLUDE [footer-include](includes/footer-banner.md)]
