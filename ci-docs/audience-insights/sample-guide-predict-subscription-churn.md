---
title: Beispielanleitung für die Abo-Abwanderungsvorhersage
description: Verwenden Sie diese Beispielanleitung, um das Out-of-Box-Modell zur Vorhersage der Abonnement-Abwanderung auszuprobieren.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: fa460fa5c79bc8a356ec5e90050ec85e05c55be8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306302"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a>Anleitung zur Vorhersage von Abonnement-Abwanderung (Vorschau)

Wir führen Sie durch ein End-to-End-Beispiel für die Vorhersage der Abwanderung von Abonnenten anhand der unten bereitgestellten Beispieldaten. 

## <a name="scenario"></a>Szenario

Contoso ist ein Unternehmen, das hochwertigen Kaffee und Kaffeemaschinen herstellt. Beides wird über die Website von Contoso Kaffee vertrieben. Sie haben kürzlich ein Abo-Geschäft für Ihre Kunden gestartet, um regelmäßig Kaffee zu bekommen. Ihr Ziel ist es, zu verstehen, welche abonnierten Kunden ihr Abonnement in den nächsten Monaten kündigen könnten. Zu wissen, welche ihrer Kunden **wahrscheinlich abwandern**, kann ihnen helfen, Marketingaufwand zu sparen, indem sie sich darauf konzentrieren, diese Kunden zu halten.

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

1. Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle von **Abfrage** in **eCommerceContacts** um

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

### <a name="ingest-subscription-information"></a>Einlesen von Abonnement-Informationen

1. Erstellen Sie eine Datenquelle mit dem Namen **SubscriptionHistory**, wählen Sie die Importoption und wählen Sie den Konnektor **Text/CSV**.

1. Geben Sie die URL für eCommerce-Kontakte https://aka.ms/ciadchurnsubscriptionhistory ein.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:

   - **SubscriptioID**: Ganze Zahl
   - **SubscriptionAmount**: Währung
   - **SubscriptionEndDate**: Datum/Uhrzeit
   - **SubscriptionStartDate**: Datum/Uhrzeit
   - **TransactionDate**: Datum/Uhrzeit
   - **IsRecurring**: Wahr/Falsch
   - **Is_auto_renew**: Wahr/Falsch
   - **RecurringFrequencyInMonths**: Ganze Zahl

1. Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle von **Query** in **SubscriptionHistory** um.

1. Speichern Sie die Datenquelle.

### <a name="ingest-customer-data-from-website-reviews"></a>Einlesen von Kundendaten aus Website-Bewertungen

1. Erstellen Sie eine Datenquelle mit dem Namen **Website**, wählen Sie die Importoption und wählen Sie den **Text/CSV**-Konnektor.

1. Geben Sie die URL für eCommerce-Kontakte https://aka.ms/ciadclasswebsite ein.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:

   - **ReviewRating**: Ganze Zahl
   - **ReviewDate**: Datum

1. Benennen Sie im Feld „Name“ im rechten Fensterbereich Ihre Datenquelle von **Query** in **WebReviews** um.

## <a name="task-2---data-unification"></a>Aufgabe 2 - Daten vereinheitlichen

Nach der Datenerfassung beginnen wir nun mit dem **Zuordnen, Abgleichen, Zusammenführen** Prozess, um ein einheitliches Kundenprofil zu erstellen. Weitere Informationen finden Sie unter [Datenvereinheitlichung](data-unification.md).

### <a name="map"></a>Zuordnung

1. Nach der Datenerfassung ordnen Sie die Kontakte aus den eCommerce- und Loyalty-Daten den gemeinsamen Datentypen zu. Gehen Sie zu **Daten** > **Vereinheitlichen** > **Karten**.

1. Wählen Sie die Entitäten, die das Kundenprofil darstellen - **eCommerceContacts** und **loyCustomers**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="Vereinheitlichen Sie E-Commerce- und Treue-Datenquellen.":::

1. Wählen Sie **KontaktId** als Primärschlüssel für **eCommerceKontakte** und **LoyaltyID** als Primärschlüssel für **loyCustomers**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Vereinheitlichen Sie LoyaltyId als Primärschlüssel.":::

### <a name="match"></a>Abgleichen

1. Gehen Sie auf die Registerkarte **Abgleichen** und wählen Sie **Reihenfolge festlegen**.

1. Wählen Sie in der Dropdown-Liste **Primär** und wählen Sie **eCommerceKontakte: eCommerce** als Primärquelle aus, und wählen Sie dann Alle Datensätze einbinden aus.

1. Wählen Sie in der Dropdownliste **Entität 2** den Eintrag **loyCustomers: LoyaltyScheme** und dann Alle Datensätze berücksichtigen aus.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Abgleich eCommerce und Loyalty vereinheitlichen.":::

1. Wählen Sie **Eine neue Regel erstellen**

1. Fügen Sie Ihre erste Bedingung mit FullName hinzu.

   * Für eCommerceKontakte wählen Sie **Vollständiger Name** in der Dropdown-Liste.
   * Für loyCustomers wählen Sie **Vollständiger Name** in der Dropdown-Liste.
   * Wählen Sie das Dropdown-Menü **Normalisieren** und wählen Sie **Typ (Telefon, Name, Adresse, ...)**.
   * Setzen Sie **Präzisionsstufe**: **Basis** und **Wert**: **Hoch**.

1. Geben Sie als Regelname **FullName, Email** ein.

   * Fügen Sie eine zweite Bedingung für E-Mail-Adressen hinzu, indem Sie **Bedingung hinzufügen** wählen.
   * Wählen Sie für eCommerce-Kontakte der Entität **Email** im Dropdown-Menü.
   * Wählen Sie für loyCustomers der Entität **Email** im Dropdown-Menü. 
   * Lassen Sie Normalisieren leer. 
   * Setzen Sie **Präzisionsstufe**: **Basis** und **Wert**: **Hoch**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Übereinstimmungsregel für Name und E-Mail vereinheitlichen.":::

7. Wählen Sie **Speichern** und **Ausführen**.

### <a name="merge"></a>Mergen

1. Gehen Sie auf die Registerkarte **Zusammenführen**.

1. Ändern Sie auf der **ContactId** für die Entität **loyCustomers** den Anzeigenamen in **ContactIdLOYALTY**, um sie von den anderen aufgenommenen IDs zu unterscheiden.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Contactid aus Treue-ID umbenennen:":::

1. Wählen Sie **Speichern** und **Ausführen**, um den Zusammenführungsprozess zu starten.


## <a name="task-3---configure-the-subscription-churn-prediction"></a>Aufgabe 3 - Konfigurieren der Abonnement-Abwanderungsprognose

Mit den vereinheitlichten Kundenprofilen können wir nun die Abwanderungsvorhersage für Abonnements durchführen. Detaillierte Schritte finden Sie im Artikel [Abonnement-Abwanderungsvorhersage (Vorschau)](predict-subscription-churn.md). 

1. Gehen Sie zu **Intelligenz** > **Erkennen** und wählen Sie das Modell **Kundenabwanderung**.

1. Wählen Sie die Option **Abonnement** und wählen Sie **Beginnen**.

1. Nennen Sie das Modell **OOB-Abonnementsabwanderungsvorhersage** und die Ausgabe-Entität **OOBSubscriptionChurnPrediction**.

1. Definieren Sie zwei Bedingungen für das Churn-Modell:

   * **Tage seit Ende des Abonnements**: **mindestens 60** Tage. Wenn ein Kunde nach Ablauf seines Abonnements das Abonnement in diesem Zeitraum nicht erneuert, wird er als abgewandert betrachtet. 

   * **Abwanderungsdefinition**: **mindestens 93** Tage. Die Dauer, die das Modell vorhersagt, nach der Kunden abwandern könnten. Je weiter Sie in die Zukunft schauen, desto ungenauer werden die Ergebnisse.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Wählen Sie die Modellhebel Vorhersage-Fenster und Abwanderungs-Definition.":::

1. Wählen Sie **Erforderliche Daten hinzufügen** und wählen Sie **Daten hinzufügen** für die Abo-Historie.

1. Fügen Sie die Entität **Subscription : SubscriptionHistory** hinzu und ordnen Sie die Felder von eCommerce den entsprechenden, vom Modell benötigten Feldern zu.

1. Verbinden Sie die Entität **Subscription : SubscriptionHistory** mit **eCommerceContacts : eCommerce**, nennen Sie die Beziehung **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Join von eCommerce-Entitäten.":::

1. Fügen Sie unter Kundenaktivitäten die Entität **webReviews : Website** hinzu und ordnen Sie die Felder von webReviews den entsprechenden vom Modell benötigten Feldern zu. 
   - Primärschlüssel: ReviewId
   - Zeitstempel: ReviewDate
   - Ereignis: ReviewRating

1. Konfigurieren Sie eine Aktivität für Website-Bewertungen. Wählen Sie die Aktivität **Review** und verbinden Sie die Entität **webReviews : Website** mit **eCommerceContacts : eCommerce**.

1. Wählen Sie **Weiter**, um den Modellplan einzustellen.

   Das Modell muss regelmäßig trainieren, um neue Muster zu lernen, wenn neue Daten erfasst werden. Wählen Sie für dieses Beispiel **Monatlich**.

1. Nachdem Sie alle Details überprüft haben, wählen Sie **Speichern und Ausführen**.

## <a name="task-4---review-model-results-and-explanations"></a>Aufgabe 4 - Überprüfung der Modellergebnisse und Erklärungen

Lassen Sie das Modell das Training und das Scoring der Daten abschließen. Sie können nun die Erklärungen zum Abonnement-Abwanderungsmodell überprüfen. Weitere Informationen finden Sie unter [Überprüfen eines Vorhersagestatus und der Ergebnisse](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Aufgabe 5 - Erzeugen eines Segments von Kunden mit hohem Abwanderungsrisiko

Das Ausführen des Produktionsmodells erstellt eine neue Entität, die Sie in **Daten** > **Entitäten** sehen können.   

Sie können ein neues Segment basierend auf der vom Modell erstellten Entität erstellen.

1.  Gehen Sie zu **Segmente**. Wählen Sie **Neu** und wählen Sie **Erstellen aus** > **Intelligenz**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Erstellen eines Segments mit der Modellausgabe.":::

1. Wählen Sie den Endpunkt **OOBSubscriptionChurnPrediction** und definieren Sie das Segment: 
   - Feld: ChurnScore
   - Operator: größer als
   - Wert: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Abonnement-Abwanderungssegment einrichten.":::

Sie haben jetzt ein Segment, das dynamisch aktualisiert wird und Kunden mit hohem Abwanderungsrisiko für dieses Abo-Geschäft identifiziert.

Weitere Informationen finden Sie unter [Erstellen und Verwalten von Segmenten](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]