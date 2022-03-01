---
title: Beispielanleitung für die Vorhersage des langfristigen Kundenwerts
description: Verwenden Sie diese Beispielanleitung, um das Modell zur Vorhersage des langfristigen Kundenwerts auszuprobieren.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 19c1fbadb79ba22c0dc11aa7c3b5b2415add70a7
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306348"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Beispielanleitung für die Vorhersage des langfristigen Kundenwerts (Customer Lifetime Value, CLV)

In dieser Anleitung wird Ihnen ein End-to-End-Beispiel zur Vorhersage des CLV in Customer Insights anhand von Beispieldaten erläutert.

## <a name="scenario"></a>Szenario

Contoso ist ein Unternehmen, das hochwertigen Kaffee und Kaffeemaschinen herstellt. Die Produkte werden über Website Contoso Coffee vertrieben. Das Unternehmen möchte den Wert (Umsatz) verstehen, den seine Kunden in den nächsten 12 Monaten generieren können. Wenn der erwartete Wert für die nächsten 12 Monaten bekannt ist, kann das Unternehmen seine Marketingbemühungen auf hochwertige Kunden ausrichten.

## <a name="prerequisites"></a>Anforderungen

- Mindestens [Berechtigungen für Mitwirkende](permissions.md) für Zielgruppenerkenntnisse.
- Wir empfehlen, dass Sie die folgenden Schritte [in einer neuen Umgebung](manage-environments.md) implementieren.

## <a name="task-1---ingest-data"></a>Aufgabe 1 - Datenerfassung

Lesen Sie die Artikel [zur Datenerfassung](data-sources.md) und zum [Importieren von Datenquellen mit Power Query-Konnektoren](connect-power-query.md). Die folgenden Informationen setzen voraus, dass Sie mit der Datenerfassung im Allgemeinen vertraut sind.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Datenerfassung von Kundendaten aus der eCommerce-Plattform

1. Erstellen Sie eine Datenquelle mit dem Namen **eCommerce**, wählen Sie die Importoption und wählen Sie den **Text/CSV** Konnektor.

1. Geben Sie die URL für eCommerce-Kontakte ein: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:
   - **DateOfBirth**: Datum
   - **CreatedOn**: Datum/Uhrzeit/Zone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Geburtsdatum in Datum umwandeln":::

1. Benennen Sie im Feld 'Name' im rechten Fensterbereich Ihre Datenquelle von **Abfrage** in **eCommerceContacts** um

1. **Speichern** Sie die Datenquelle.

### <a name="ingest-online-purchase-data"></a>Datenerfassung von Online-Kaufdaten

1. Fügen Sie einen weiteren Datensatz zur gleichen **eCommerce** Datenquelle hinzu. Wählen Sie erneut den **Text/CSV** Konnektor.

1. Geben Sie die URL für **Online-Einkäufe** Daten https://aka.ms/ciadclassonline ein.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:
   - **Gekauft am**: Datum/Uhrzeit
   - **GesamtPreis**: Währung

1. Benennen Sie im Feld **Name** im rechten Seitenbereich Ihre Datenquelle von **Abfrage** in **eCommercePurchases** um.

1. **Speichern** Sie die Datenquelle.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Kundendaten aus dem Treueschema einlesen

1. Erstellen Sie eine Datenquelle mit dem Namen **LoyaltyScheme**, wählen Sie die Importoption und wählen Sie den Konnektor **Text/CSV**.

1. Geben Sie die URL für eCommerce-Kontakte https://aka.ms/ciadclasscustomerloyalty ein.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:
   - **DateOfBirth**: Datum
   - **RewardsPoints**: Ganze Zahl
   - **CreatedOn**: Datum/Uhrzeit

1. Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle von **Query** in **loyCustomers** um.

1. **Speichern** Sie die Datenquelle.

### <a name="ingest-customer-data-from-website-reviews"></a>Einlesen von Kundendaten aus Website-Bewertungen

1. Erstellen Sie eine Datenquelle mit dem Namen **Website**, wählen Sie die Importoption und wählen Sie den **Text/CSV**-Konnektor.

1. Geben Sie die URL für eCommerce-Kontakte https://aka.ms/CI-ILT/WebReviews ein.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:

   - **ReviewRating**: Dezimalzahl
   - **ReviewDate**: Datum

1. Benennen Sie Ihre Datenquelle im Feld „Name“ im rechten Bereich von **Abfrage** in **Überprüfungen** um.

1. **Speichern** Sie die Datenquelle.

## <a name="task-2---data-unification"></a>Aufgabe 2 - Daten vereinheitlichen

Nach dem Erfassen der Daten beginnen wir nun mit der Datenvereinheitlichung, um ein vereinheitlichtes Kundenprofil zu erstellen. Weitere Informationen finden Sie unter [Datenvereinheitlichung](data-unification.md).

### <a name="map"></a>Zuordnung

1. Nach der Datenerfassung ordnen Sie die Kontakte aus den eCommerce- und Loyalty-Daten den gemeinsamen Datentypen zu. Gehen Sie zu **Daten** > **Vereinheitlichen** > **Karten**.

1. Wählen Sie die Entitäten, die das Kundenprofil darstellen - **eCommerceContacts** und **loyCustomers**. Wählen Sie dann **Übernehmen** aus.

   ![Vereinheitlichen Sie E-Commerce- und Treue-Datenquellen.](media/unify-ecommerce-loyalty.png)

1. Wählen Sie **KontaktId** als Primärschlüssel für **eCommerceKontakte** und **LoyaltyID** als Primärschlüssel für **loyCustomers**.

   ![Vereinheitlichen Sie LoyaltyId als Primärschlüssel.](media/unify-loyaltyid.png)

1. Wählen Sie **Speichern** aus.

### <a name="match"></a>Abgleichen

1. Gehen Sie auf die Registerkarte **Abgleichen** und wählen Sie **Reihenfolge festlegen**.

1. Wählen Sie in der Dropdown-Liste **Primär** und wählen Sie **eCommerceKontakte: eCommerce** als Primärquelle aus, und wählen Sie dann Alle Datensätze einbinden aus.

1. Wählen Sie in der Dropdownliste **Entität 2** den Eintrag **loyCustomers: LoyaltyScheme** und dann Alle Datensätze berücksichtigen aus.

   ![Abgleich eCommerce und Loyalty vereinheitlichen.](media/unify-match-order.png)

1. Wählen Sie **Regel hinzufügen** aus.

1. Fügen Sie Ihre erste Bedingung mit FullName hinzu.

   - Für eCommerceKontakte wählen Sie **Vollständiger Name** in der Dropdown-Liste.
   - Für loyCustomers wählen Sie **Vollständiger Name** in der Dropdown-Liste.
   - Wählen Sie aus der Dropdownliste **Normalisieren** und wählen Sie **Typ (Telefon, Name, Adresse, ...)**.
   - Setzen Sie **Präzisionsstufe**: **Basis** und **Wert**: **Hoch**.

1. Geben Sie als Regelname **FullName, Email** ein.

   - Fügen Sie eine zweite Bedingung für E-Mail-Adressen hinzu, indem Sie **Bedingung hinzufügen** wählen.
   - Wählen Sie für eCommerce-Kontakte der Entität **Email** im Dropdown-Menü.
   - Wählen Sie für loyCustomers der Entität **Email** im Dropdown-Menü.
   - Lassen Sie Normalisieren leer.
   - Setzen Sie **Präzisionsstufe**: **Basis** und **Wert**: **Hoch**.

   ![Übereinstimmungsregel für Name und E-Mail vereinheitlichen.](media/unify-match-rule.png)

1. Wählen Sie **Fertig** aus.

1. Wählen Sie **Speichern** und **Ausführen**.

### <a name="merge"></a>Zusammenführen

1. Gehen Sie auf die Registerkarte **Zusammenführen**.

1. Ändern Sie auf der **ContactId** für die Entität **loyCustomers** den Anzeigenamen in **ContactIdLOYALTY**, um sie von den anderen aufgenommenen IDs zu unterscheiden.

   ![Contactid aus Treue-ID umbenennen:](media/unify-merge-contactid.png)

1. Wählen Sie **Speichern** und **Merge- und Downstream-Prozesse ausführen** aus.

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Aufgabe 3 – Konfigurieren der Vorhersage des langfristigen Kundenwerts

Mit den vereinheitlichten Kundenprofilen können wir jetzt die Vorhersage des langfristigen Kundenwerts ausführen. Detaillierte Schritte finden Sie unter [Vorhersage des langfristigen Kundenwerts (Vorschau)](predict-customer-lifetime-value.md).

1. Wechseln Sie zu **Intelligenz**  > **Vorhersagen** und wählen Sie **Kundenlebensdauerwert-Modell** aus.

1. Gehen Sie die Informationen im Seitenbereich durch und wählen Sie **Los geht's** aus.

1. Nennen Sie das Modell **OOB eCommerce CLV-Vorhersage** und die Ausgabeentität **OOBeCommerceCLVPrediction**.

1. Definieren Sie Modellpräferenzen für das CLV-Modell:
   - **Vorhersagezeitraum**:**12 Monate oder 1 Jahr**. Diese Einstellung definiert, wie weit in die Zukunft der langfristige Kundenwert vorhergesagt werden soll.
   - **Aktive Kunden**: Geben Sie an, was aktive Kunden für Ihr Unternehmen bedeuten. Legen Sie den historischen Zeitrahmen fest, in dem ein Kunde mindestens eine Transaktion durchgeführt haben muss, um als aktiv zu gelten. Das Modell sagt CLV nur für aktive Kunden voraus. Wählen Sie aus, ob das Modell den Zeitraum basierend auf historischen Transaktionsdaten berechnen soll oder ob Sie einen bestimmten Zeitrahmen angeben möchten. In dieser Beispielanleitung **lassen wir das Kaufintervall vom Modell berechnen**, was die Standardoption ist.
   - **Kunden mit hohem Wert**: Definieren Sie hochwertige Kunden als Perzentil der am meisten bezahlenden Kunden. Das Modell verwendet diese Eingabe, um Ergebnisse bereitzustellen, die Ihrer Geschäftsdefinition von Kunden mit hohem Wert entsprechen. Sie können Kunden mit hohem Wert vom Modell definieren lassen. Es verwendet eine heuristische Regel, die das Perzentil ableitet. Sie können Kunden mit hohem Wert auch als Perzentil der zukünftig am meisten bezahlenden Kunden definieren. In dieser Beispielanleitung definieren wir Kunden mit hohem Wert manuell als **Top 30 % der aktiv zahlenden Kunden** und wählen dann **Weiter** aus.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Einstellungsschritt in der Anleitung für das CLV-Modell.":::

1. Wählen Sie im Schritt **Erforderliche Daten** die Option **Daten hinzufügen** aus, um die Daten zum Transaktionsverlauf anzugeben.

1. Fügen Sie die Entität **eCommercePurchases : eCommerce** hinzu und ordnen Sie die Attribute zu, die für das Modell erforderlich sind:
   - Transaktions-ID: eCommerce.eCommercePurchases.PurchaseId
   - Transaktionsdatum: eCommerce.eCommercePurchases.PurchasedOn
   - Transaktionsbetrag: eCommerce.eCommercePurchases.TotalPrice
   - Produkt-ID: eCommerce.eCommercePurchases.ProductId

1. Klicken Sie auf **Weiter**.

1. Richten Sie die Beziehung zwischen der Entität **eCommercePurchases : eCommerce** und **eCommerceContacts : eCommerce** ein.

1. Der Schritt **Zusätzliche Daten (optional)** ermöglicht das Hinzufügen weiterer Kundenaktivitätsdaten. Diese Daten können dazu beitragen, mehr Erkenntnisse zu den Kundeninteraktionen mit Ihrem Unternehmen zu erhalten, die zum CLV beitragen können. Das Hinzufügen wichtiger Kundeninteraktionen – wie Webprotokolle, Protokolle des Kundenservice oder der Verlauf des Prämienprogramms – kann die Genauigkeit der Vorhersagen verbessern. Wählen Sie **Daten hinzufügen** aus, um mehr Kundenaktivitätsdaten aufzunehmen.

1. Fügen Sie die Kundenaktivitätsentität hinzu und ordnen Sie ihre Feldnamen den entsprechenden Feldern zu, die für das Modell erforderlich sind:
   - Kundenaktivitätsentität: Reviews:Website
   - Primärschlüssel: Website.Reviews.ReviewId
   - Zeitstempel: Website.Reviews.ReviewDate
   - Ereignis (Aktivitätsname): Website.Reviews.ActivityTypeDisplay
   - Details (Betrag oder Wert): Website.Reviews.ReviewRating

1. Wählen Sie **Weiter** aus und konfigurieren Sie die Aktivität und die Beziehung zwischen den Transaktionsdaten und den Kundendaten:  
   - Aktivitätstyp: Vorhandene auswählen
   - Aktivitätsbeschriftung: Überprüfung
   - Entsprechende Beschriftung: Website.Reviews.UserId
   - Kundenentität: eCommerceContacts:eCommerce
   - Beziehung: WebsiteReviews

1. Wählen Sie **Weiter**, um den Modellplan einzustellen.

   Das Modell muss regelmäßig trainiert werden, um neue Muster zu lernen, wenn neue Daten erfasst werden. Wählen Sie für dieses Beispiel **Monatlich** aus.

1. Nachdem Sie alle Details überprüft haben, wählen Sie **Speichern und ausführen**.

## <a name="task-4---review-model-results-and-explanations"></a>Aufgabe 4 - Überprüfung der Modellergebnisse und Erklärungen

Lassen Sie das Modell das Training und das Scoring der Daten abschließen. Als Nächstes können Sie die Ergebnisse und Erläuterungen des CLV-Modells überprüfen. Weitere Informationen finden Sie unter [Überprüfen eines Vorhersagestatus und der Ergebnisse](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Aufgabe 5 – Erstellen eines Segments mit Kunden mit hohem Wert

Beim Ausführen des Modells wird eine neue Entität erstellt, die unter **Daten** > **Entitäten** aufgeführt ist. Sie können ein neues Kundensegment basierend auf der vom Modell erstellten Entität erstellen.

1. Gehen Sie zu **Segmente**. 

1. Wählen Sie **Neu** aus und wechseln Sie dann zu **Erstellen aus** > **Intelligenz**.

   ![Erstellen eines Segments mit der Modellausgabe.](media/segment-intelligence.png)

1. Wählen Sie die Entität **OOBeCommerceCLVPrediction** aus und definieren Sie das Segment:
  - Feld: CLVScore
  - Operator: größer als
  - Wert: 1500

1. Wählen Sie **Überprüfung** aus und wählen Sie dann für das Segment **Speichern** aus.

Sie haben jetzt ein Segment, das Kunden identifiziert, die in den kommenden 12 Monaten voraussichtlich mehr als 1.500 US-Dollar Umsatz generieren werden. Dieses Segment wird dynamisch aktualisiert, wenn mehr Daten erfasst werden.

Weitere Informationen finden Sie unter [Erstellen und Verwalten von Segmenten](segments.md).
