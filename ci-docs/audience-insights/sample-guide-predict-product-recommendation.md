---
title: Beispielanleitung für Produktempfehlungsvorhersage
description: Verwenden Sie diese , um das Out-of-Box-Modell zur Vorhersage von Produktempfehlungen auszuprobieren.
ms.date: 02/10/2021
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ee873d9b7caa5f891cb2d5b8c665dec90ad0e59
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270492"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>Beispielanleitung für Produktempfehlungsvorhersage (Vorschau)

Wir führen Sie durch ein End-to-End-Beispiel für die Vorhersage von Produktempfehlungen anhand der unten bereitgestellten Beispieldaten.

## <a name="scenario"></a>Szenario

Contoso ist ein Unternehmen, das hochwertigen Kaffee und Kaffeemaschinen herstellt, die es über seine Website Contoso Coffee verkauft. Ihr Ziel ist es zu verstehen, welche Produkte sie ihren wiederkehrenden Kunden empfehlen sollten. Das Wissen darüber, was Kunden **wahrscheinlich eher kaufen**, kann ihnen helfen, Marketingbemühungen zu sparen, indem sie sich auf bestimmte Elemente konzentrieren.

## <a name="prerequisites"></a>Anforderungen

- Mindestens die [Berechtigung "Mitwirkender"](permissions.md) in Customer Insights.
- Wir empfehlen, dass Sie die folgenden Schritte [in einer neuen Umgebung](manage-environments.md) implementieren.

## <a name="task-1---ingest-data"></a>Aufgabe 1 - Datenerfassung

Lesen Sie speziell die Artikel [über die Datenerfassung](data-sources.md) und [Importieren von Datenquellen mit Power Query Konnektoren](connect-power-query.md). Die folgenden Informationen setzen voraus, dass Sie mit der Datenerfassung im Allgemeinen vertraut sind.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Datenerfassung von Kundendaten aus der eCommerce-Plattform

1. Erstellen Sie eine Datenquelle mit dem Namen **eCommerce**, wählen Sie die Importoption und wählen Sie den **Text/CSV** Konnektor.

1. Geben Sie die URL für eCommerce-Kontakte https://aka.ms/ciadclasscontacts ein.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:
   - **DateOfBirth**: Datum
   - **CreatedOn**: Datum/Uhrzeit/Zone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Geburtsdatum in Datum umwandeln":::

5. Benennen Sie im Feld 'Name' im rechten Fensterbereich Ihre Datenquelle von **Abfrage** in **eCommerceContacts** um

6. **Speichern** Sie die Datenquelle.

### <a name="ingest-online-purchase-data"></a>Datenerfassung von Online-Kaufdaten

1. Fügen Sie einen weiteren Datensatz zur gleichen **eCommerce** Datenquelle hinzu. Wählen Sie erneut den **Text/CSV** Konnektor.

1. Geben Sie die URL für **Online-Einkäufe** Daten https://aka.ms/ciadclassonline ein.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:
   - **Gekauft am**: Datum/Uhrzeit
   - **GesamtPreis**: Währung

1. Benennen Sie im Feld **Name** im rechten Seitenbereich Ihre Datenquelle von **Abfrage** in **eCommercePurchases** um.

1. Speichern Sie die Datenquelle.


### <a name="ingest-customer-data-from-loyalty-schema"></a>Kundendaten aus dem Treueschema einlesen

1. Erstellen Sie eine Datenquelle mit dem Namen **LoyaltyScheme**, wählen Sie die Importoption und wählen Sie den Konnektor **Text/CSV**.

1. Geben Sie die URL für eCommerce-Kontakte https://aka.ms/ciadclasscustomerloyalty ein.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:
   - **DateOfBirth**: Datum
   - **RewardsPoints**: Ganze Zahl
   - **CreatedOn**: Datum/Uhrzeit

1. Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle von **Query** in **loyCustomers** um.

1. Speichern Sie die Datenquelle.

## <a name="task-2---data-unification"></a>Aufgabe 2 - Daten vereinheitlichen

Nach der Datenerfassung beginnen wir nun mit dem **Zuordnen, Abgleichen, Zusammenführen** Prozess, um ein einheitliches Kundenprofil zu erstellen. Weitere Informationen finden Sie unter [Datenvereinheitlichung](data-unification.md).

### <a name="map"></a>Zuordnung

1. Nach der Datenerfassung ordnen Sie die Kontakte aus den eCommerce- und Loyalty-Daten den gemeinsamen Datentypen zu. Gehen Sie zu **Daten** > **Vereinheitlichen** > **Karten**.

2. Wählen Sie die Entitäten, die das Kundenprofil darstellen - **eCommerceContacts** und **loyCustomers**.

   ![Vereinheitlichen Sie E-Commerce- und Treue-Datenquellen.](media/unify-ecommerce-loyalty.png)

3. Wählen Sie **KontaktId** als Primärschlüssel für **eCommerceKontakte** und **LoyaltyID** als Primärschlüssel für **loyCustomers**.

   ![Vereinheitlichen Sie LoyaltyId als Primärschlüssel.](media/unify-loyaltyid.png)

### <a name="match"></a>Abgleichen

1. Gehen Sie auf die Registerkarte **Abgleichen** und wählen Sie **Reihenfolge festlegen**.

2. In der Dropdown-Liste **Primär** wählen Sie **eCommerceContacts : eCommerce** als primäre Quelle und schließen alle Datensätze ein.

3. Wählen Sie in der Dropdown-Liste **Entität 2** die Option **loyCustomers : LoyaltyScheme** und schließen Sie alle Datensätze ein.

   ![Abgleich eCommerce und Loyalty vereinheitlichen.](media/unify-match-order.png)

4. Wählen Sie **Eine neue Regel erstellen**

5. Fügen Sie Ihre erste Bedingung mit FullName hinzu.

   - Für eCommerceContacts wählen Sie **FullName** in der Dropdown-Liste.
   - Für loyCustomers wählen Sie **FullName** im Dropdown.
   - Wählen Sie das Dropdown-Menü **Normalisieren** und wählen Sie **Typ (Telefon, Name, Adresse, ...)**.
   - Setzen Sie **Präzisionsstufe**: **Basis** und **Wert**: **Hoch**.

6. Geben Sie als Regelname **FullName, Email** ein.

   - Fügen Sie eine zweite Bedingung für E-Mail-Adressen hinzu, indem Sie **Bedingung hinzufügen** wählen.
   - Für die Entität eCommerceContacts wählen Sie **EMail** im Dropdown.
   - Für die Entität loyCustomers wählen Sie **EMail** im Drop-Down.
   - Lassen Sie Normalisieren leer.
   - Setzen Sie **Präzisionsstufe**: **Basis** und **Wert**: **Hoch**.

   ![Übereinstimmungsregel für Name und E-Mail vereinheitlichen.](media/unify-match-rule.png)

7. Wählen Sie **Speichern** und **Ausführen**.

### <a name="merge"></a>Mergen

1. Gehen Sie auf die Registerkarte **Zusammenführen**.

1. Ändern Sie auf der **ContactId** für die Entität **loyCustomers** den Anzeigenamen in **ContactIdLOYALTY**, um sie von den anderen aufgenommenen IDs zu unterscheiden.

   ![Contactid aus Treue-ID umbenennen:](media/unify-merge-contactid.png)

1. Wählen Sie **Speichern** und **Ausführen**, um den Zusammenführungsprozess zu starten.

## <a name="task-3---configure-product-recommendation-prediction"></a>Aufgabe 3 – Konfigurieren Sie die Produktempfehlungsvorhersage

Mit den vereinheitlichten Kundenprofilen können wir nun die Abwanderungsvorhersage für Abonnements durchführen.

1. Gehen Sie zu **Intelligenz** > **Vorhersage** und wählen Sie **Produktempfehlung** aus.

1. Wählen Sie **Erste Schritte** aus.

1. Nennen Sie das Modell **OOB-Produktempfehlungsmodell-Vorhersage** und die Ausgabeentität **OOBProductRecommendationModelPrediction**.

1. Definieren Sie drei Bedingungen für das Modell:

   - **Anzahl der Produkte**: Setzen Sie diesen Wert auf **5**. Diese Einstellung definiert, wie viele Produkte Sie Ihren Kunden empfehlen möchten.

   - **Produkte vorschlagen, die Kunden kürzlich gekauft haben?**: Wählen **Ja**, um anzuzeigen, dass Sie Produkte in die Empfehlung aufnehmen möchten, die Ihre Kunden zuvor gekauft haben.

   - **Fenster für Vergangenheitsdaten:** Wählen Sie mindestens **365 Tage**. Diese Einstellung legt fest, wie weit das Modell die Aktivität des Kunden zurückverfolgt, um sie als Eingabe für Empfehlungen zu verwenden.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modelleinstellungen für das Produktempfehlungsmodell":::

1. Wählen Sie **Erforderliche Daten** und wählen Sie **Daten hinzufügen** für die Einkaufshistorie.

1. Fügen Sie die Entität **eCommercePurchases : eCommerce** hinzu und ordnen Sie die Felder von eCommerce den entsprechenden vom Modell benötigten Feldern zu.

1. Verbinden Sie die Entität **eCommercePurchases : eCommerce** mit **eCommerceContacts : eCommerce**.

   ![Join von eCommerce-Entitäten.](media/model-purchase-join.png)

1. Wählen Sie **Weiter**, um den Modellplan einzustellen.

   Das Modell muss regelmäßig trainieren, um neue Muster zu lernen, wenn neue Daten erfasst werden. Wählen Sie für dieses Beispiel **Monatlich**.

1. Nachdem Sie alle Details überprüft haben, wählen Sie **Speichern und Ausführen**.


## <a name="task-4---review-model-results-and-explanations"></a>Aufgabe 4 - Überprüfung der Modellergebnisse und Erklärungen

Lassen Sie das Modell das Training und das Scoring der Daten abschließen. Sie können nun die Erklärungen zum Produktempfehlungsmodell überprüfen. Weitere Informationen finden Sie unter [Überprüfen eines Vorhersagestatus und der Ergebnisse](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Aufgabe 5 – Erstellen Sie ein Segment mit häufig gekauften Produkten

Das Ausführen des Produktionsmodells erstellt eine neue Entität, die Sie in **Daten** > **Entitäten** sehen können.

Sie können ein neues Segment basierend auf der vom Modell erstellten Entität erstellen.

1. Gehen Sie zu **Segmente**. Wählen Sie **Neu** und wählen Sie **Erstellen aus** > **Intelligenz**.

   ![Erstellen eines Segments mit der Modellausgabe.](media/segment-intelligence.png)

1. Wählen Sie den Endpunkt **OOBProductRecommendationModelPrediction** und definieren Sie das Segment:

   - Feld: ProductID
   - Operator: Wert
   - Wert: Wählen Sie die drei wichtigsten Produkt-IDs aus

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Erstellen Sie ein Segment aus den Modellergebnissen.":::

Sie haben jetzt ein Segment, das dynamisch aktualisiert wird und die Kunden identifiziert, die eher bereit sind, die drei am meisten empfohlenen Produkte zu kaufen 

Weitere Informationen finden Sie unter [Erstellen und Verwalten von Segmenten](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]