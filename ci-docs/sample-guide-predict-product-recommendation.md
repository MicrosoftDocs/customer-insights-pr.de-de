---
title: Beispielanleitung für Produktempfehlungsvorhersage
description: Verwenden Sie diese , um das Out-of-Box-Modell zur Vorhersage von Produktempfehlungen auszuprobieren.
ms.date: 05/16/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762685"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Beispielanleitung für Produktempfehlungsvorhersage

Wir führen Sie durch ein End-to-End-Beispiel für die Vorhersage von Produktempfehlungen anhand der unten bereitgestellten Beispieldaten.

## <a name="scenario"></a>Szenario

Contoso ist ein Unternehmen, das hochwertigen Kaffee und Kaffeemaschinen herstellt, die es über seine Website Contoso Coffee verkauft. Ihr Ziel ist es zu verstehen, welche Produkte sie ihren wiederkehrenden Kunden empfehlen sollten. Das Wissen darüber, was Kunden **wahrscheinlich eher kaufen**, kann ihnen helfen, Marketingbemühungen zu sparen, indem sie sich auf bestimmte Elemente konzentrieren.

## <a name="prerequisites"></a>Anforderungen

- Mindestens die [Berechtigung "Mitwirkender"](permissions.md) in Customer Insights.
- Wir empfehlen, dass Sie die folgenden Schritte [in einer neuen Umgebung](manage-environments.md) implementieren.

## <a name="task-1---ingest-data"></a>Aufgabe 1 - Datenerfassung

Lesen Sie insbesondere die Artikel zu [Datenerfassung](data-sources.md) und [Importieren von Datenquellen mit Power Query-Konnektoren](connect-power-query.md). Die folgenden Informationen setzen voraus, dass Sie mit der Datenerfassung im Allgemeinen vertraut sind.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Datenerfassung von Kundendaten aus der eCommerce-Plattform

1. Erstellen Sie eine Datenquelle mit dem Namen **eCommerce**, wählen Sie die Importoption und wählen Sie den **Text/CSV** Konnektor.

1. Geben Sie die URL für eCommerce-Kontakte ein: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts)

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:
   - **DateOfBirth**: Datum
   - **CreatedOn**: Datum/Uhrzeit/Zone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Geburtsdatum in Datum umwandeln":::

1. Benennen Sie im Feld 'Name' im rechten Fensterbereich Ihre Datenquelle von **Abfrage** in **eCommerceContacts** um

1. **Speichern** Sie die Datenquelle.

### <a name="ingest-online-purchase-data"></a>Datenerfassung von Online-Kaufdaten

1. Fügen Sie einen weiteren Datensatz zur gleichen **eCommerce** Datenquelle hinzu. Wählen Sie erneut den **Text/CSV** Konnektor.

1. Geben Sie die URL für **Online-Einkäufe**-Daten [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline) ein.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:
   - **Gekauft am**: Datum/Uhrzeit
   - **GesamtPreis**: Währung

1. Benennen Sie im Feld **Name** im rechten Seitenbereich Ihre Datenquelle von **Abfrage** in **eCommercePurchases** um.

1. **Speichern** Sie die Datenquelle.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Kundendaten aus dem Treueschema einlesen

1. Erstellen Sie eine Datenquelle mit dem Namen **LoyaltyScheme**, wählen Sie die Importoption und wählen Sie den Konnektor **Text/CSV**.

1. Geben Sie die URL für eCommerce-Kontakte [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty) ein.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:
   - **DateOfBirth**: Datum
   - **RewardsPoints**: Ganze Zahl
   - **CreatedOn**: Datum/Uhrzeit

1. Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle von **Query** in **loyCustomers** um.

1. **Speichern** Sie die Datenquelle.

## <a name="task-2---data-unification"></a>Aufgabe 2 - Daten vereinheitlichen

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Aufgabe 3 – Konfigurieren Sie die Produktempfehlungsvorhersage

Mit den Unified customer profiles können wir jetzt die Produktempfehlungsvorhersage ausführen.

1. Gehen Sie zu **Intelligenz** > **Vorhersage** und wählen Sie **Produktempfehlung** aus.

1. Wählen Sie **Erste Schritte** aus.

1. Nennen Sie das Modell **OOB-Produktempfehlungsmodell-Vorhersage** und die Ausgabeentität **OOBProductRecommendationModelPrediction**.

1. Definieren Sie drei Bedingungen für das Modell:

   - **Anzahl der Produkte**: Setzen Sie diesen Wert auf **5**. Diese Einstellung definiert, wie viele Produkte Sie Ihren Kunden empfehlen möchten.

   - **Erwartete wiederholte Einkäufe**: Wählen Sie **Ja** aus, um anzugeben, dass Sie Produkte in die Empfehlung aufnehmen möchten, die Ihre Kunden bereits gekauft haben.

   - **Fenster für Vergangenheitsdaten:** Wählen Sie mindestens **365 Tage**. Diese Einstellung legt fest, wie weit das Modell die Aktivität des Kunden zurückverfolgt, um sie als Eingabe für Empfehlungen zu verwenden.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modelleinstellungen für das Produktempfehlungsmodell":::

1. Wählen Sie im Schritt **Erforderliche Daten hinzufügen** **Daten hinzufügen** aus.

1. In dem Bereich **Daten hinzufügen** wählen Sie die **SalesOrderLine** als Entität der Kaufhistorie. Zu diesem Zeitpunkt ist sie wahrscheinlich noch nicht konfiguriert. Öffnen Sie den Link im Bereich, um die Aktivität mit den folgenden Schritten zu erstellen:
   1. Geben Sie einen **Aktivitätsnamen** ein und wählen Sie *eCommercePurchases:eCommerce* als **Aktivitätsentität**. Der **Primärschlüssel** ist *PurchaseId*.
   1. Definieren und benennen Sie die Beziehung zu der *eCommerceContacts:eCommerce-Entität* und wählen Sie **ContactId** als Fremdschlüssel.
   1. Legen Sie für die Aktivitätsvereinheitlichung **Ereignisaktivität** als *TotalPrice* und für den Zeitstempel *PurchasedOn* fest. Sie können weitere Felder angeben, wie in [Kundenaktivitäten](activities.md) beschrieben.
   1. Für **Aktivitätstyp** wählen Sie *SalesOrderLine*. Ordnen Sie die folgenden Aktivitätsfelder zu:
      - Auftragspositions-ID: PurchaseId
      - Auftrags-ID: PurchaseId
      - Bestellungsdatum: PurchasedOn
      - Produkt-ID: ProductId
      - Betrag: TotalPrice
   1. Überprüfen und beenden Sie die Aktivität, bevor Sie zur Modellkonfiguration zurückkehren.

1. Zurück im Schritt **Aktivitäten auswählen** wählen Sie die neu erstellte Aktivität im Abschnitt **Aktivitäten** aus. Wählen Sie **Weiter** aus und die Attributzuordnung ist bereits ausgefüllt. Wählen Sie **Speichern**.

1. In diesem Beispielleitfaden überspringen wir **Produktinformationen hinzufügen** und festgelegten **Produktfilter**, da wir keine Produktinformationsdaten haben.

1. In dem Schritt **Datenupdates** legen Sie den Modellzeitplan fest.

   Das Modell muss regelmäßig trainieren, um neue Muster zu lernen, wenn neue Daten erfasst werden. Wählen Sie für dieses Beispiel **Monatlich**.

1. Nachdem Sie alle Details überprüft haben, wählen Sie **Speichern und Ausführen**. Die erste Ausführung des Modells dauert einige Minuten.

## <a name="task-4---review-model-results-and-explanations"></a>Aufgabe 4 - Überprüfung der Modellergebnisse und Erklärungen

Lassen Sie das Modell das Training und das Scoring der Daten abschließen. Sie können nun die Erklärungen zum Produktempfehlungsmodell überprüfen. Weitere Informationen finden Sie unter [Überprüfen eines Vorhersagestatus und der Ergebnisse](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Aufgabe 5 – Erstellen Sie ein Segment mit häufig gekauften Produkten

Das Ausführen des Produktionsmodells erstellt eine neue Entität, die Sie in **Daten** > **Entitäten** sehen können.

Sie können ein neues Segment basierend auf der vom Modell erstellten Entität erstellen.

1. Gehen Sie zu **Segmente**. Wählen Sie **Neu** aus und wechseln Sie dann zu **Erstellen aus Intelligenz**.

   ![Erstellen eines Segments mit der Modellausgabe.](media/segment-intelligence.png)

1. Wählen Sie den Endpunkt **OOBProductRecommendationModelPrediction** und definieren Sie das Segment:

   - Feld: ProductID
   - Wert: Wählen Sie die drei wichtigsten Produkt-IDs aus

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Erstellen Sie ein Segment aus den Modellergebnissen.":::

Sie haben jetzt ein Segment, das dynamisch aktualisiert wird und die Kunden identifiziert, die daran interessiert sein könnten, die drei am meisten empfohlenen Produkte zu kaufen.

Weitere Informationen finden Sie unter [Erstellen und Verwalten von Segmenten](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
