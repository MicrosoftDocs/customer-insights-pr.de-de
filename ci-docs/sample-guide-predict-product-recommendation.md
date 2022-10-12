---
title: Beispielanleitung für Produktempfehlungsvorhersage
description: Verwenden Sie diese , um das Out-of-Box-Modell zur Vorhersage von Produktempfehlungen auszuprobieren.
ms.date: 09/19/2022
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
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610143"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Beispielanleitung für Produktempfehlungsvorhersage

Diese Anleitung führt Sie durch ein End-to-End-Beispiel für die Vorhersage von Produktempfehlungen mithilfe von Beispieldaten. Wir empfehlen, dass Sie diese Vorhersage [in einer neuen Umgebung](manage-environments.md) ausprobieren.

## <a name="scenario"></a>Szenario

Contoso ist ein Unternehmen, das hochwertige Kaffees und Kaffeemaschinen herstellt. Es verkauft die Produkte über die Contoso Coffee-Website. Ihr Ziel ist es zu verstehen, welche Produkte sie ihren wiederkehrenden Kunden empfehlen sollten. Das Wissen darüber, was Kunden **wahrscheinlich eher kaufen**, kann ihnen helfen, Marketingbemühungen zu sparen, indem sie sich auf bestimmte Elemente konzentrieren.

## <a name="prerequisites"></a>Anforderungen

- Mindestens die [Berechtigung "Mitwirkender"](permissions.md) in Customer Insights.

## <a name="task-1---ingest-data"></a>Aufgabe 1 - Datenerfassung

Lesen Sie die Artikel zu [Datenerfassung](data-sources.md) und zur [Verbindung mit einer Power Query-Datenquelle](connect-power-query.md). Bei den folgenden Informationen wird davon ausgegangen, dass Sie mit der Datenerfassung im Allgemeinen vertraut sind.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Datenerfassung von Kundendaten aus der eCommerce-Plattform

1. Erstellen Sie eine Power Query-Datenquelle mit dem Namen **E-Commerce** und wählen Sie den **Text/CSV**-Connector.

1. Geben Sie die URL für eCommerce-Kontakte ein: https://aka.ms/ciadclasscontacts.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:
   - **DateOfBirth**: Datum
   - **CreatedOn**: Datum/Uhrzeit/Zone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Geburtsdatum in Datum umwandeln":::

1. Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle in **eCommerceContacts** um.

1. **Speichern** Sie die Datenquelle.

### <a name="ingest-online-purchase-data"></a>Datenerfassung von Online-Kaufdaten

1. Fügen Sie einen weiteren Datensatz zur gleichen **eCommerce** Datenquelle hinzu. Wählen Sie erneut den **Text/CSV** Konnektor.

1. Geben Sie die URL für Online-Einkaufsdaten https://aka.ms/ciadclassonline ein.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:
   - **Gekauft am**: Datum/Uhrzeit
   - **GesamtPreis**: Währung

1. Benennen Sie im Feld **Name** im rechten Seitenbereich Ihre Datenquelle in **eCommercePurchases** um.

1. **Speichern** Sie die Datenquelle.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Kundendaten aus dem Treueschema einlesen

1. Erstellen Sie eine Datenquelle mit dem Namen **LoyaltyScheme** und wählen Sie den **Text/CSV**-Connector.

1. Geben Sie die URL für treue Kunden ein: https://aka.ms/ciadclasscustomerloyalty.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:
   - **DateOfBirth**: Datum
   - **RewardsPoints**: Ganze Zahl
   - **CreatedOn**: Datum/Uhrzeit

1. Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle in **loyCustomers** um.

1. **Speichern** Sie die Datenquelle.

## <a name="task-2---data-unification"></a>Aufgabe 2 - Daten vereinheitlichen

Lesen Sie den Artikel zur [Datenvereinheitlichung](data-unification.md). Bei den folgenden Informationen wird davon ausgegangen, dass Sie mit der Datenvereinheitlichung im Allgemeinen vertraut sind.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Aufgabe 3: Transaktionsverlaufsaktivität erstellen

Lesen Sie den Artikel zu [Kundenaktivitäten](activities.md). Bei den folgenden Informationen wird davon ausgegangen, dass Sie mit der Erstellung von Aktivitäten im Allgemeinen vertraut sind.

1. Erstellen Sie eine Aktivität namens **eCommercePurchases** mit der Entität *eCommercePurchases:eCommerce* und ihrem Primärschlüssel **PurchaseId**.

1. Erstellen Sie eine Beziehung zwischen *eCommercePurchases:eCommerce* und *eCommerceContacts:eCommerce* mit **ContactID** als Fremdschlüssel, um die beiden Entitäten zu verbinden.

1. Wählen Sie **TotalPrice** für die **EventActivity** und **PurchasedOn** für die **TimeStamp**.

1. Wählen Sie **SalesOrderLine** für die **Aktivitätstyp** und ordnen Sie die Aktivitätsdaten semantisch zu.

1. Führen Sie die Aktivität aus.

## <a name="task-4---configure-product-recommendation-prediction"></a>Aufgabe 4 – Konfigurieren Sie die Produktempfehlungsvorhersage

Mit den vereinheitlichten Kundenprofilen und der erstellten Aktivität können wir jetzt die Produktempfehlungsvorhersage ausführen.

1. Gehen Sie zu **Intelligenz** > **Vorhersagen**.

1. Wählen Sie in der Registerkarte **Erstellen** **Modell verwenden** auf der Kachel **Produktempfehlungen (Vorschauversion)** aus.

1. Wählen Sie **Erste Schritte** aus.

1. Nennen Sie das Modell **OOB-Produktempfehlungsmodell-Vorhersage** und die Ausgabeentität **OOBProductRecommendationModelPrediction**.

1. Wählen Sie **Weiter** aus.

1. Modelleinstellungen definieren:
   - **Anzahl der Produkte**: **5**, um festzulegen, wie viele Produkte Sie Ihren Kunden empfehlen möchten.
   - **Wiederholungskäufe erwartet**: **Ja**, um bereits gekaufte Produkte in die Empfehlung aufzunehmen.
   - **Fenster für Vergangenheitsdaten:** **365 Tage**, um festzulegen, wie weit das Modell zurückblickt, bevor es ein Produkt erneut empfiehlt.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modelleinstellungen für das Produktempfehlungsmodell":::

1. Wählen Sie **Weiter** aus.

1. Wählen Sie im Schritt **Kaufverlauf hinzufügen** **Daten hinzufügen** aus.

1. Wählen Sie **SalesOrderLine** und die Entität eCommercePurchases und dann **Weiter** aus. Die erforderlichen Daten werden automatisch aus der Aktivität entnommen. Wählen Sie **Speichern** und dann **Weiter**.

1. Überspringen Sie die Schritte **Produktinformationen hinzufügen** und **Produktfilter**, da wir keine Produktinformationsdaten haben.

1. Wählen Sie in dem Schritt **Datenupdates** für den Modellzeitplan **Monatlich** aus.

1. Wählen Sie **Weiter** aus.

1. Nachdem Sie alle Details überprüft haben, wählen Sie **Speichern und Ausführen**.

## <a name="task-5---review-model-results-and-explanations"></a>Aufgabe 5 - Überprüfung der Modellergebnisse und Erklärungen

Lassen Sie das Modell das Training und das Scoring der Daten abschließen. Gehen Sie die [Erklärungen zum Produktempfehlungsmodell](predict-transactional-churn.md#view-prediction-results) durch.

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>Aufgabe 6 – Erstellen Sie ein Segment mit häufig gekauften Produkten

Beim Ausführen des Modells wird eine neue Entität erstellt, die unter **Daten** > **Entitäten** aufgeführt ist. Sie können ein neues Segment basierend auf der vom Modell erstellten Entität erstellen.

1. Wählen Sie auf der Ergebnisseite **Segment erstellen** aus.

1. Erstellen Sie eine Regel mit der Entität **OOBProductRecommendationModelPrediction** und definieren Sie das Segment:
   - **Feld**: ProductID
   - **Wert**: Wählen Sie die drei wichtigsten Produkt-IDs aus

1. Wählen Sie **Speichern** aus und dann **Ausführen** für das Segment.

Sie haben jetzt ein Segment, das dynamisch aktualisiert wird und die Kunden identifiziert, die daran interessiert sein könnten, die fünf am meisten empfohlenen Produkte zu kaufen. Weitere Informationen finden Sie unter [Erstellen und Verwalten von Segmenten](segments.md).

> [!TIP]
> Sie können auch ein Segment für ein Vorhersagemodell aus der Seite **Segmente** erstellen, indem Sie **Neu** und dann **Erstellen aus** > **Intelligenz** auswählen. Weitere Informationen finden Sie unter [Ein neues Segment mit Schnellsegmenten erstellen](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
