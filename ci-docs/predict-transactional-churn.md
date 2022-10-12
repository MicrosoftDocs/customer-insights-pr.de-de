---
title: Transaktions-Churn vorhersagen (enthält Video)
description: Sagen Sie voraus, ob bei einem Kunden das Risiko besteht, dass er Ihre Produkte oder Dienstleistungen nicht mehr kauft.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610511"
---
# <a name="predict-transaction-churn"></a>Transaktionsabwanderung vorhersagen

Die Transaktionsabwanderungsvorhersage hilft bei der Vorhersage, ob ein Kunde Ihre Produkte oder Dienstleistungen in einem bestimmten Zeitfenster nicht mehr kaufen wird.

Sie benötigen Geschäftswissen, um zu verstehen, was Abwanderung für Ihr Unternehmen bedeutet. Wir unterstützen zeitbasierte Abwanderungsdefinitionen, was bedeutet, dass ein Kunde nach einem Zeitraum ohne Käufe als abgewandert gilt.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Für Umgebungen, die auf Geschäftskonten basieren, können wir die Transaktionsabwanderung für ein Konto und auch eine Kombination aus Konto und einer anderen Informationsebene wie Produktkategorie vorhersagen. Durch das Hinzufügen einer Dimension können Sie zum Beispiel bestimmen, wie wahrscheinlich es ist, dass das Konto „Contoso“ die Produktkategorie „Bürobedarf“ nicht mehr kauft. Darüber hinaus können wir für Geschäftskonten auch KI verwenden, um eine Liste potenzieller Gründe zu erstellen, warum ein Konto wahrscheinlich nach einer Kategorie von Informationen auf sekundärer Ebene abwandert.

> [!TIP]
> Probieren Sie die Transaktionsabwanderungsvorhersage mit Beispieldaten aus: [Transaktionsabwanderungsvorhersage – Beispielanleitung](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Anforderungen

- Mindestens [Beteiligungsberechtigungen](permissions.md).
- Mindestens 10 Kundenprofile, vorzugsweise mehr als 1.000 eindeutigen Kunden.
- Kundenbezeichner, ein eindeutiger Bezeichner zur Zuordnung von Transaktionen zu Ihren Kunden.
- Transaktionsdaten für mindestens das Doppelte des gewählten Zeitfensters wie z. B. zwei bis drei Jahre Transaktionsverlauf. Idealerweise mindestens zwei Transaktionen pro Kunde. Der Transaktionsverlauf muss Folgendes enthalten:
  - **Transaktions-ID**: Eindeutiger Bezeichner eines Kaufs oder einer Transaktion.
  - **Transaktionsdatum**: Datum des Kaufs oder der Transaktion.
  - **Wert der Transaktion**: Die Währung oder der numerische Wert der Transaktion.
  - **Eindeutige Produkt-ID**: ID des gekauften Produkts oder Services, wenn Ihre Daten auf Einzelpostenebene sind.
  - **Ob diese Transaktion eine Rückgabe war**: Ein Wahr/Falsch-Feld, das angibt, ob die Transaktion eine Rückgabe war oder nicht. Wenn der **Wert der Transaktion** negativ ist, gehen wir von einer Rückgabe aus.
- Kundenaktivitätsdaten:
  - Kundenbezeichner, ein eindeutiger Bezeichner zur Zuordnung von Aktivitäten zu Ihren Kunden.
  - **Primärschlüssel:** Eindeutiger Bezeichner für eine Aktivität. Zum Beispiel ein Website-Besuch oder ein Verwendungsnachweis, der zeigt, dass der Kunde eine Probe Ihres Produkts ausprobiert hat.
  - **Zeitstempel:** Datum und die Uhrzeit des Ereignisses, identifiziert durch den Primärschlüssel.
  - **Ereignis:** Name des Ereignisses, das Sie verwenden möchten. Ein Feld namens „UserAction“ in einem Lebensmittelgeschäft könnte z.B. die Verwendung des Coupons durch den Kunden sein.
  - **Details:** Detaillierte Informationen über das Ereignis. Zum Beispiel könnte ein Feld namens „CouponValue“ in einem Lebensmittelgeschäft der Währungswert des Coupons sein.
- Weniger als 20 % der fehlenden Werte im Datenfeld der angegebenen Entität

Fügen Sie für Geschäftskonten (B2B) Kundendaten hinzu, die auf statischere Attribute ausgerichtet sind, um sicherzustellen, dass das Modell die bestmögliche Leistung erbringt:
- **Kunden-ID:** Eindeutiger Bezeichner für einen Kunden.
- **Erstellungsdatum:** Datum, an dem der Kunde ursprünglich hinzugefügt wurde.
- **Bundesland oder Provinz:** Das Bundesland oder die Provinz eines Kunden.
- **Land:** Land eines Kunden.
- **Branche:** Branchentyp eines Kunden. Beispielsweise könnte ein Feld namens Industrie in einem Kaffeeröster anzeigen, ob es sich bei dem Kunden um einen Einzelhandelskunden handelt.
- **Einstufung:** Kategorisierung eines Kunden für Ihr Unternehmen. Ein Feld namens ValueSegment in einem Kaffeeröster könnte beispielsweise die Kundenstufe basierend auf der Kundengröße sein.

> [!NOTE]
> Für ein Unternehmen mit hoher Kundenkaufhäufigkeit (alle paar Wochen) wird empfohlen, ein kürzeres Vorhersage-Fenster und eine kürzere Abwanderungsdefinition auszuwählen. Wählen Sie für eine niedrige Kaufhäufigkeit (alle paar Monate oder einmal im Jahr) ein längeres Vorhersage-Fenster und eine längere Abwanderungsdefinition.

## <a name="create-a-transaction-churn-prediction"></a>Eine Transkaktionsabwanderungs-Vorhersage erstellen

1. Gehen Sie zu **Intelligenz** > **Vorhersagen**.

1. Wählen Sie auf der Registerkarte **Erstellen** auf der Kachel **Kundenabwanderungsmodell** **Modell verwenden** aus.

1. Wählen Sie **Transaktion** für die Art der Abwanderung und dann **Erste Schritte** aus.

1. **Dieses Modell benennen** und **Ausgabeentitätsname**, um sie von anderen Modellen oder Entitäten zu unterscheiden.

1. Wählen Sie **Weiter** aus.

### <a name="define-customer-churn"></a>Kundenabwanderung definieren

Wählen Sie **Entwurf speichern** aus, um die Vorhersage als Entwurf zu speichern. Die Entwurfsvorhersage wird in der Registerkarte **Meine Vorhersagen** angezeigt.

1. Legen Sie das **Vorhersagefenster** fest. Sagen Sie z. B. das Abwanderungsrisiko für Ihre Kunden in den nächsten 90 Tagen voraus, um Ihre Marketing-Bindungsmaßnahmen darauf abzustimmen. Die Vorhersage des Abwanderungsrisikos über einen längeren oder kürzeren Zeitraum kann es schwieriger machen, die Faktoren in Ihrem Abwanderungsrisikoprofil zu berücksichtigen, aber das hängt von Ihren spezifischen Geschäftsanforderungen ab.

1. Geben Sie die Anzahl der Tage ein, um im Feld **Churn-Definition** den Churn zu definieren. Wenn ein Kunde z. B. in den letzten 30 Tagen keine Käufe getätigt hat, könnte er für Ihr Unternehmen als abgewandert betrachtet werden.

1. Wählen Sie **Weiter** aus.

### <a name="add-purchase-history"></a>Kaufverlauf hinzufügen

1. Wählen Sie **Daten hinzufügen** für **Kundentransaktionsverlauf** aus.

1. Wählen Sie den semantischen Aktivitätstyp, **SalesOrder** oder **SalesOrderLine** aus, der die Transaktionsverlaufsinformationen enthält. Wenn die Aktivität nicht eingerichtet wurde, wählen Sie sie **hier** aus und erstellen Sie sie.

1. Wählen Sie unter **Aktivitäten**, wenn die Aktivitätsattribute der Aktivität semantisch zugeordnet wurden, die spezifischen Attribute oder Entitäten aus, auf die sich die Berechnung konzentrieren soll. Wenn keine semantische Zuordnung erfolgt ist, wählen Sie **Bearbeiten** aus und ordnen Sie Ihre Daten aus.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Seitenbereich, der die Auswahl bestimmter Aktivitäten unter dem semantischen Typ zeigt.":::

1. Wählen Sie **Nächste** und überprüfen Sie die für dieses Modell erforderlichen Attribute.

1. Wählen Sie **Save** (Speichern).

1. Fügen Sie weitere Aktivitäten hinzu oder wählen Sie **Weiter** aus.

# <a name="individual-consumers-b-to-c"></a>[Einzelne Verbraucher (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Zusätzliche Daten hinzufügen (optional)

1. Wählen Sie **Daten hinzufügen** für **Kundenaktivitäten** aus.

1. Wählen Sie den semantischen Aktivitätstyp aus, der die Daten enthält, die Sie verwenden möchten. Wenn die Aktivität nicht eingerichtet wurde, wählen Sie sie **hier** aus und erstellen Sie sie.

1. Wählen Sie unter **Aktivitäten**, wenn die Aktivitätsattribute der Aktivität semantisch zugeordnet wurden, die spezifischen Attribute oder Entitäten aus, auf die sich die Berechnung konzentrieren soll. Wenn keine semantische Zuordnung erfolgt ist, wählen Sie **Bearbeiten** aus und ordnen Sie Ihre Daten aus.

1. Wählen Sie **Nächste** und überprüfen Sie die für dieses Modell erforderlichen Attribute.

1. Wählen Sie **Save** (Speichern).

1. Klicken Sie auf **Weiter**.

# <a name="business-accounts-b-to-b"></a>[Unternehmenskonten (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Vorhersagestube auswählen

Die meisten Vorhersagen werden auf Kundenebene erstellt. In einigen Situationen ist dies möglicherweise nicht granular genug, um Ihre Geschäftsanforderungen zu erfüllen. Verwenden Sie diese Funktion, um die Abwanderung beispielsweise für eine Filiale eines Kunden und nicht für den gesamten Kunden vorherzusagen.

1. Wählen Sie **Entität für sekundäre Ebene auswählen**. Wenn die Option nicht verfügbar ist, stellen Sie sicher, dass Sie den vorherigen Abschnitt abgeschlossen haben.

1. Erweitern Sie die Entitäten, aus denen Sie die sekundäre Ebene auswählen möchten, oder verwenden Sie das Suchfilterfeld, um die ausgewählten Optionen zu filtern.

1. Wählen Sie das Attribut aus, das Sie als sekundäre Ebene verwenden möchten, und wählen Sie dann **Hinzufügen**

1. Wählen **Weiter** aus.

> [!NOTE]
> Die in diesem Abschnitt verfügbaren Entitäten werden angezeigt, da sie eine Beziehung zu der Entität haben, die Sie im vorherigen Abschnitt ausgewählt haben. Wenn die Entität, die Sie hinzufügen möchten, nicht angezeigt wird, stellen Sie sicher, dass eine gültige Beziehung vorhanden ist unter **Beziehungen**. Nur 1:1- und n:1-Beziehungen sind für diese Konfiguration gültig.

### <a name="add-additional-data-optional"></a>Zusätzliche Daten hinzufügen (optional)

1. Wählen Sie **Daten hinzufügen** für **Kundenaktivitäten** aus.

1. Wählen Sie den semantischen Aktivitätstyp aus, der die Daten enthält, die Sie verwenden möchten. Wenn die Aktivität nicht eingerichtet wurde, wählen Sie sie **hier** aus und erstellen Sie sie.

1. Wählen Sie unter **Aktivitäten**, wenn die Aktivitätsattribute der Aktivität semantisch zugeordnet wurden, die spezifischen Attribute oder Entitäten aus, auf die sich die Berechnung konzentrieren soll. Wenn keine semantische Zuordnung erfolgt ist, wählen Sie **Bearbeiten** aus und ordnen Sie Ihre Daten aus.

1. Wählen Sie **Nächste** und überprüfen Sie die für dieses Modell erforderlichen Attribute.

1. Wählen Sie **Save** (Speichern).

1. Klicken Sie auf **Weiter**.

1. Wählen Sie optional **Daten hinzufügen** zu **Kundendaten** aus.

1. Ordnen Sie die semantischen Attribute wie identifiziert Feldern in Ihren eigenen Kundendaten zu. Die Daten in den verwendeten Feldern sollten sich nicht oft ändern, um die beste Leistung des Modells zu gewährleisten. Wenn Sie beispielsweise ein Feld für Klassifizierung auswählen, das sich jeden Monat ändert, wird nur der letzte Wert in der Vorhersage verwendet, auch wenn in der Vergangenheit möglicherweise nicht derselbe Wert für den Kunden beim Erstellen der Vorhersagemuster gilt.

1. Wählen **Weiter** aus.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Geben Sie eine optionale Liste von Benchmark-Konten an

Fügen Sie eine Liste Ihrer Geschäftskunden und Konten hinzu, die Sie als Benchmarks verwenden möchten. Die [Details zu diesen Benchmark-Konten](#view-prediction-results) enthalten ihre Abwanderungsbewertung und die einflussreichsten Funktionen, die sich auf ihre Abwanderungsvorhersage ausgewirkt haben.

1. **+ Kunden hinzufügen** auswählen.

1. Wählen Sie die Kunden aus, die als Maßstab dienen.

1. Wählen Sie **Weiter** aus.

---

### <a name="set-update-schedule"></a>Zeitplanaktualisierung festlegen

1. Wählen Sie für den Schritt **Datenaktualisierungen** eine Häufigkeit aus, um Ihr Modell neu zu trainieren. Diese Einstellung ist wichtig, um die Genauigkeit der Vorhersagen zu aktualisieren, wenn neue Daten in Customer Insights aufgenommen werden. Die meisten Unternehmen können einmal pro Monat eine Umschulung durchführen und erhalten eine gute Genauigkeit für ihre Vorhersagen.

1. Wählen Sie **Weiter** aus.

### <a name="review-and-run-the-model-configuration"></a>Überprüfen Sie die Modellkonfiguration und führen Sie sie aus

Der Schritt **Überprüfen und ausführen** zeigt eine Zusammenfassung der Konfiguration und bietet die Möglichkeit, Änderungen vorzunehmen, bevor Sie die Datei Vorhersage erstellen.

1. Wählen Sie **Bearbeiten** bei einem der Schritte, um sie zu überprüfen und Änderungen vorzunehmen.

1. Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **Speichern und ausführen** aus, um das Modell ausführen zu lassen. Wählen Sie **Fertig** aus. Die Registerkarte **Meine Vorhersagen** wird angezeigt, während Vorhersage erstellt wird. Der Prozess kann je nach der Menge der in der Vorhersage verwendeten Daten mehrere Stunden dauern.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Vorhersageergebnisse anzeigen

1. Gehen Sie zu **Intelligenz** > **Vorhersagen**.

1. Wählen Sie in der Registerkarte **Meine Vorhersagen** die Vorhersage aus, die Sie ansehen möchten.

# <a name="individual-consumers-b-to-c"></a>[Einzelne Verbraucher (B2C)](#tab/b2c)

Es gibt drei primäre Datenabschnitte innerhalb der Ergebnisseite:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Unternehmenskonten (B2B)](#tab/b2b)

Es gibt drei primäre Datenabschnitte innerhalb der Ergebnisseite:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

Eine Seite mit Informationen zu **Analyse einflussreicher Funktionen** enthält vier Datenabschnitte:

- Wählen Sie im rechten Bereich ein Element aus **Top-Kunden** oder **Benchmark-Kunden** aus. Beide Listen sind nach abnehmendem Wert der Abwanderungsbewertung geordnet, unabhängig davon, ob die Bewertung nur für den Kunden oder eine kombinierte Bewertung für Kunden und eine sekundäre Ebene wie die Produktkategorie gilt. Das ausgewählte Element bestimmt den Inhalt dieser Seite.

  - **Top-Kunden**: Liste der 10 Kunden mit dem höchsten Abwanderungsrisiko und dem niedrigsten Abwanderungsrisiko basierend auf ihren Abwanderungswerten.
  - **Benchmark-Kunden**: Liste von bis zu 10 Kunden, die bei der Konfiguration des Modells ausgewählt wurden.

- **Abwanderungsquote:** Zeigt die Abwanderungsbewertung für das ausgewählte Element im rechten Fensterbereich an.

- **Abwanderungsrisikoverteilung:** Zeigt die Abwanderungsrisikoverteilung über die Kunden und das Perzentil an, in dem sich der ausgewählte Kunde befindet.

- **Top-Funktionen, die das Abwanderungsrisiko erhöhen und verringern:** Führt die fünf wichtigsten Funktionen auf, die das Abwanderungsrisiko für das ausgewählte Element im rechten Bereich erhöht und verringert haben. Zeigt den Wert die Funktion für dieses Element und seinen Einfluss auf die Abwanderungsscore für jede einflussreiche Funktion. Der Durchschnittswert jedes Merkmals für Kundensegmente mit geringer, mittlerer und hoher Abwanderung wird ebenfalls angezeigt. Es hilft, die Werte der wichtigsten einflussreichen Merkmale für das ausgewählte Element besser zu kontextualisieren und mit Kundensegmenten mit geringer, mittlerer und hoher Abwanderung zu vergleichen.

  - Niedrig: Konten oder Kombinationen aus Konto und sekundärer Ebene mit einem Abwanderungsscore zwischen 0 und 0,33.
  - Mittel: Konten oder Kombinationen aus Konto und sekundärer Ebene mit einem Abwanderungsscore zwischen 0,33 und 0,66.
  - Hoch: Konten oder Kombinationen aus Konto und sekundärer Ebene mit einem Abwanderungsscore größer als 0,66.

  Wenn Sie die Abwanderung auf Kontoebene vorhersagen, werden alle Konten bei der Ableitung der durchschnittlichen Merkmalswerte für Abwanderungssegmente berücksichtigt. Bei Abwanderungsvorhersagen auf sekundärer Ebene für jedes Konto hängt die Ableitung von Abwanderungssegmenten von der sekundären Ebene des im Seitenbereich ausgewählten Elements ab. Wenn ein Artikel beispielsweise eine sekundäre Produktkategorie (Büroartikel) hat, werden bei der Ableitung der durchschnittlichen Merkmalswerte für Abwanderungssegmente nur Artikel mit Büroartikeln als Produktkategorie berücksichtigt. Diese Logik wird angewendet, um einen fairen Vergleich der Merkmalswerte des Artikels mit den Durchschnittswerten in Segmenten mit niedriger, mittlerer und hoher Abwanderung zu gewährleisten.

  In einigen Fällen ist der Durchschnittswert von Segmenten mit niedriger, mittlerer oder hoher Abwanderung leer oder nicht verfügbar, da keine Artikel vorhanden sind, die gemäß der obigen Definition zu den entsprechenden Abwanderungssegmenten gehören.

  Die Interpretation der Werte in den Spalten „Durchschnitt niedrig“, „mittel“ und „hoch“ ist für kategoriale Merkmale wie Land oder Branche unterschiedlich. Da der Begriff „durchschnittlicher“ Merkmalswert nicht für kategoriale Merkmale gilt, geben die Werte in diesen Spalten den Anteil der Kunden in Segmenten mit geringer, mittlerer oder hoher Abwanderung an, die den gleichen Wert des kategorialen Merkmals wie der Artikel aufweisen im Seitenbereich ausgewählt.

---

 > [!NOTE]
 > In der Ausgabeentität für dieses Modell zeigt *ChurnScore* die vorhergesagte Abwanderungswahrscheinlichkeit und *IsChurn* eine binäre Bezeichnung basierend auf *ChurnScore* mit Grenzwert 0,5 an. Wenn dieser Standardgrenzwert für Ihr Szenario nicht funktioniert, [erstellen Sie ein neues Segment](segments.md#create-a-segment) mit Ihrem bevorzugten Grenzwert. Nicht alle Kunden sind notwendigerweise aktive Kunden. Einige von ihnen hatten möglicherweise lange Zeit keine Aktivität mehr und werden aufgrund Ihrer Abwanderungsdefinition bereits als aufgewühlt angesehen. Die Vorhersage des Abwanderungsrisikos für Kunden, die bereits abgewandert sind, ist nicht sinnvoll, da sie nicht die Publikum von Interesse sind.
>
> Um das Abwanderungsergebnis anzuzeigen, gehen Sie zu **Daten** > **Entitäten** und zeigen Sie die Registerkarte „Daten“ für die Ausgabeentität an, die Sie für dieses Modell festgelegt haben.

[!INCLUDE [footer-include](includes/footer-banner.md)]
