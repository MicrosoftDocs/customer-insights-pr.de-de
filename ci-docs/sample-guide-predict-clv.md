---
title: Beispielanleitung für die Vorhersage des langfristigen Kundenwerts (Customer Lifetime Value, CLV)
description: Verwenden Sie diese Beispielanleitung, um das Modell zur Vorhersage des langfristigen Kundenwerts auszuprobieren.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609637"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Beispielanleitung für die Vorhersage des langfristigen Kundenwerts (Customer Lifetime Value, CLV)

In dieser Anleitung wird Ihnen ein End-to-End-Beispiel zur Vorhersage des langfristigen Kundenwerts (CLV) in Customer Insights anhand von Beispieldaten erläutert. Wir empfehlen, dass Sie diese Vorhersage [in einer neuen Umgebung](manage-environments.md) ausprobieren.

## <a name="scenario"></a>Szenario

Contoso ist ein Unternehmen, das hochwertige Kaffees und Kaffeemaschinen herstellt. Es verkauft die Produkte über die Contoso Coffee-Website. Das Unternehmen möchte den Wert (Umsatz) verstehen, den seine Kunden in den nächsten 12 Monaten generieren können. Wenn der erwartete Wert für die nächsten 12 Monaten bekannt ist, kann das Unternehmen seine Marketingbemühungen auf hochwertige Kunden ausrichten.

## <a name="prerequisites"></a>Anforderungen

- Mindestens [Beteiligungsberechtigungen](permissions.md).

## <a name="task-1---ingest-data"></a>Aufgabe 1 - Datenerfassung

Lesen Sie die Artikel zu [Datenerfassung](data-sources.md) und zur [Verbindung mit einer Power Query-Datenquelle](connect-power-query.md). Bei den folgenden Informationen wird davon ausgegangen, dass Sie mit der Datenerfassung im Allgemeinen vertraut sind.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Datenerfassung von Kundendaten aus der eCommerce-Plattform

1. Erstellen Sie eine Power Query-Datenquelle mit dem Namen **E-Commerce** und wählen Sie den **Text/CSV**-Connector.

1. Geben Sie die URL für eCommerce-Kontakte https://aka.ms/ciadclasscontacts ein.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:
   - **DateOfBirth**: Datum
   - **CreatedOn**: Datum/Uhrzeit/Zone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Geburtsdatum in Datum umwandeln":::

1. Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle in **eCommerceContacts** um

1. **Speichern** Sie die Datenquelle.

### <a name="ingest-online-purchase-data"></a>Datenerfassung von Online-Kaufdaten

1. Fügen Sie einen weiteren Datensatz zur gleichen **eCommerce** Datenquelle hinzu. Wählen Sie erneut den **Text/CSV** Konnektor.

1. Geben Sie die URL für **Online-Einkäufe** Daten https://aka.ms/ciadclassonline ein.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:
   - **Gekauft am**: Datum/Uhrzeit
   - **GesamtPreis**: Währung

1. Benennen Sie im Feld **Name** im rechten Seitenbereich Ihre Datenquelle in **eCommercePurchases** um.

1. **Speichern** Sie die Datenquelle.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Kundendaten aus dem Treueschema einlesen

1. Erstellen Sie eine Datenquelle mit dem Namen **LoyaltyScheme** und wählen Sie den **Text/CSV**-Connector.

1. Geben Sie die URL für Treuekunden ein: https://aka.ms/ciadclasscustomerloyalty.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:
   - **DateOfBirth**: Datum
   - **RewardsPoints**: Ganze Zahl
   - **CreatedOn**: Datum/Uhrzeit

1. Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle in **loyCustomers** um.

1. **Speichern** Sie die Datenquelle.

### <a name="ingest-customer-data-from-website-reviews"></a>Einlesen von Kundendaten aus Website-Bewertungen

1. Erstellen Sie eine Datenquelle mit dem Namen **Website** und wählen Sie den **Text/CSV**-Connector.

1. Geben Sie die URL der Website-Bewertungen ein: https://aka.ms/CI-ILT/WebReviews.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:
   - **ReviewRating**: Dezimalzahl
   - **ReviewDate**: Datum

1. Benennen Sie Ihre Datenquelle im Feld **Name** im rechten Bereich in **Bewertungen** um.

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

1. Fügen Sie eine andere Aktivität hinzu und ordnen Sie ihre Feldnamen den entsprechenden Feldern zu:
   - **Aktivitätsentität**: Reviews:Website
   - **Primärschlüssel**: ReviewId
   - **Zeitstempel**: ReviewDate
   - **Ereignisaktivität**: ActivityTypeDisplay
   - **Zusätzliches Detail**: ReviewRating
   - **Aktivitätstyp**: Bewertung

1. Führen Sie die Aktivität aus.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Aufgabe 4 – Konfigurieren der Vorhersage des langfristigen Kundenwerts

Mit den vereinheitlichten Kundenprofilen und der erstellten Aktivität können wir jetzt die Vorhersage des langfristigen Kundenwerts (CLV) ausführen. Detaillierte Schritte finden Sie unter [Langfristiger Kundenwert (Vorhersage)](predict-customer-lifetime-value.md).

1. Gehen Sie zu **Intelligenz** > **Vorhersagen**.

1. Wählen Sie auf der Registerkarte **Erstellen** auf der Kachel **Langfristiger Kundenwert** **Modell verwenden** aus.

1. Wählen Sie **Erste Schritte** aus.

1. Nennen Sie das Modell **OOB eCommerce CLV-Vorhersage** und die Ausgabeentität **OOBeCommerceCLVPrediction**.

1. Modelleinstellungen definieren:
   - **Vorhersagezeitraum**: **12 Monate oder ein Jahr**, um festzulegen wie weit in die Zukunft der CLV vorhergesagt werden soll.
   - **Aktive Kunden**: **Kaufintervall durch das Modell berechnen lassen**, um den Zeitrahmen festzulegen, in dem ein Kunde mindestens eine Transaktion gehabt haben muss, um als aktiv zu gelten.
   - **Kunde mit hohem Wert**: Kunden mit hohem Wert manuell als **Top 30 % der aktiven Kunden** festlegen.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Einstellungsschritt in der Anleitung für das CLV-Modell.":::

1. Wählen Sie **Weiter** aus.

1. Wählen Sie im Schritt **Erforderliche Daten** die Option **Daten hinzufügen** aus, um die Daten zum Transaktionsverlauf anzugeben.

    :::image type="content" source="media/clv-model-required.png" alt-text="Schritt „Erforderliche Daten hinzufügen“ in der Anleitung für das CLV-Modell.":::

1. Wählen Sie **SalesOrderLine** und die Entität eCommercePurchases und dann **Weiter** aus. Die erforderlichen Daten werden automatisch aus der Aktivität entnommen. Wählen Sie **Speichern** und dann **Weiter**.

1. Der Schritt **Zusätzliche Daten (optional)** erlaubt Ihnen, weitere Kundenaktivitätsdaten hinzuzufügen, um mehr Erkenntnisse für Kundeninteraktionen zu erhalten. Wählen Sie für dieses Beispiel **Daten hinzufügen** aus und fügen Sie die Webbewertungsaktivität hinzu.

1. Wählen Sie **Weiter** aus.

1. Wählen Sie in dem Schritt **Datenupdates** für den Modellzeitplan **Monatlich** aus.

1. Wählen Sie **Weiter** aus.

1. Nachdem Sie alle Details überprüft haben, wählen Sie **Speichern und Ausführen**.

## <a name="task-5---review-model-results-and-explanations"></a>Aufgabe 5 - Überprüfung der Modellergebnisse und Erklärungen

Lassen Sie das Modell das Training und das Scoring der Daten abschließen. Gehen Sie die [CLV-Modellergebnisse und Erklärungen](predict-customer-lifetime-value.md#view-prediction-results) durch.

## <a name="task-6---create-a-segment-of-high-value-customers"></a>Aufgabe 6 – Erstellen eines Segments mit Kunden mit hohem Wert

Beim Ausführen des Modells wird eine neue Entität erstellt, die unter **Daten** > **Entitäten** aufgeführt ist. Sie können ein neues Kundensegment basierend auf der vom Modell erstellten Entität erstellen.

1. Wählen Sie auf der Ergebnisseite **Segment erstellen** aus.

1. Erstellen Sie eine Regel mit der Entität **OOBeCommerceCLVPrediction** und definieren Sie das Segment:
   - **Feld**: CLVScore
   - **Operator**: größer als
   - **Wert**: 1500

1. Wählen Sie **Speichern** aus und dann **Ausführen** für das Segment.

Sie haben jetzt ein Segment, das Kunden identifiziert, die in den kommenden 12 Monaten voraussichtlich mehr als 1.500 US-Dollar Umsatz generieren werden. Dieses Segment wird dynamisch aktualisiert, wenn mehr Daten erfasst werden. Weitere Informationen finden Sie unter [Erstellen und Verwalten von Segmenten](segments.md).

> [!TIP]
> Sie können auch ein Segment für ein Vorhersagemodell aus der Seite **Segmente** erstellen, indem Sie **Neu** und dann **Erstellen aus** > **Intelligenz** auswählen. Weitere Informationen finden Sie unter [Ein neues Segment mit Schnellsegmenten erstellen](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
