---
title: Beispielanleitung für die Abo-Abwanderungsvorhersage
description: Verwenden Sie diese Beispielanleitung, um das Out-of-Box-Modell zur Vorhersage der Abonnement-Abwanderung auszuprobieren.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610005"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Beispielanleitung für die Abo-Abwanderungsvorhersage

Diese Anleitung führt Sie durch ein End-to-End-Beispiel für die Vorhersage der Abonnementabwanderung mit Beispieldaten. Wir empfehlen, dass Sie diese Vorhersage [in einer neuen Umgebung](manage-environments.md) ausprobieren.

## <a name="scenario"></a>Szenario

Contoso ist ein Unternehmen, das hochwertige Kaffees und Kaffeemaschinen herstellt. Es verkauft die Produkte über die Contoso Coffee-Website. Sie haben kürzlich ein Abo-Geschäft für Ihre Kunden gestartet, um regelmäßig Kaffee zu bekommen. Ihr Ziel ist es, zu verstehen, welche abonnierten Kunden ihr Abonnement in den nächsten Monaten kündigen könnten. Zu wissen, welche ihrer Kunden **wahrscheinlich abwandern**, kann ihnen helfen, Marketingaufwand zu sparen, indem sie sich darauf konzentrieren, diese Kunden zu halten.

## <a name="prerequisites"></a>Anforderungen

- Mindestens die [Berechtigung "Mitwirkender"](permissions.md) in Customer Insights.

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

1. Speichern Sie die Datenquelle.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Kundendaten aus dem Treueschema einlesen

1. Erstellen Sie eine Datenquelle mit dem Namen **LoyaltyScheme** und wählen Sie den **Text/CSV**-Connector.

1. Geben Sie die URL für Treuekunden ein: https://aka.ms/ciadclasscustomerloyalty.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:
   - **DateOfBirth**: Datum
   - **RewardsPoints**: Ganze Zahl
   - **CreatedOn**: Datum/Uhrzeit

1. Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle in **loyCustomers** um.

1. Speichern Sie die Datenquelle.

### <a name="ingest-subscription-information"></a>Einlesen von Abonnement-Informationen

1. Erstellen Sie eine Datenquelle mit dem Namen **SubscriptionHistory** und wählen Sie den **Text/CSV**-Connector.

1. Geben Sie die URL für Abonnements ein: https://aka.ms/ciadchurnsubscriptionhistory.

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

1. Benennen Sie Ihre Datenquelle im Feld **Name** im rechten Bereich auf **SubscriptionHistory** um.

1. Speichern Sie die Datenquelle.

### <a name="ingest-customer-data-from-website-reviews"></a>Einlesen von Kundendaten aus Website-Bewertungen

1. Erstellen Sie eine Datenquelle mit dem Namen **Website** und wählen Sie den **Text/CSV**-Connector.

1. Geben Sie die URL der Website-Bewertungen ein: https://aka.ms/ciadclasswebsite.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:
   - **ReviewRating**: Ganze Zahl
   - **ReviewDate**: Datum

1. Benennen Sie Ihre Datenquelle im Feld **Name** im rechten Bereich in **webReviews** um.

## <a name="task-2---data-unification"></a>Aufgabe 2 - Daten vereinheitlichen

Lesen Sie den Artikel zur [Datenvereinheitlichung](data-unification.md). Bei den folgenden Informationen wird davon ausgegangen, dass Sie mit der Datenvereinheitlichung im Allgemeinen vertraut sind.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Aufgabe 3: Transaktionsverlaufsaktivität erstellen

Lesen Sie den Artikel zu [Kundenaktivitäten](activities.md). Bei den folgenden Informationen wird davon ausgegangen, dass Sie mit der Erstellung von Aktivitäten im Allgemeinen vertraut sind.

1. Erstellen Sie eine Aktivität namens **SubscriptionHistory** mit der Entität *Abonnement* und ihrem Primärschlüssel **CustomerId**.

1. Erstellen Sie eine Beziehung zwischen *SubscriptionHistory:Subscription* und *eCommerceContacts:eCommerce* mit **CustomerID** als Fremdschlüssel, um die beiden Entitäten zu verbinden.

1. Wählen Sie **SubscriptionType** für die **EventActivity** und **SubscriptionEndDate** für die **TimeStamp**.

1. Wählen Sie **Subscription** für die **Aktivitätstyp** und ordnen Sie die Aktivitätsdaten semantisch zu.

1. Führen Sie die Aktivität aus.

1. Fügen Sie eine andere Aktivität hinzu und ordnen Sie ihre Feldnamen den entsprechenden Feldern zu:
   - Kundenaktivitätsentität: Reviews:Website
   - Primärschlüssel: Website.Reviews.ReviewId
   - Zeitstempel: Website.Reviews.ReviewDate
   - Ereignis (Aktivitätsname): Website.Reviews.ActivityTypeDisplay
   - Details (Betrag oder Wert): Website.Reviews.ReviewRating

1. Führen Sie die Aktivität aus.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Aufgabe 4 - Konfigurieren der Abonnement-Abwanderungsprognose

Mit den vereinheitlichten Kundenprofilen und der erstellten Aktivität können wir nun die Abwanderungsvorhersage für Abonnements durchführen. Detaillierte Schritte finden Sie unter [Abonnementabwanderung vorhersagen](predict-subscription-churn.md).

1. Gehen Sie zu **Intelligenz** > **Vorhersagen**.

1. Wählen Sie auf der Registerkarte **Erstellen** auf der Kachel **Kundenabwanderungsmodell** **Modell verwenden** aus.

1. Wählen Sie **Abonnement** für die Art der Abwanderung und dann **Erste Schritte** aus.

1. Nennen Sie das Modell **OOB-Abonnementsabwanderungsvorhersage** und die Ausgabe-Entität **OOBSubscriptionChurnPrediction**.

1. Modelleinstellungen definieren:
   - **Tage seit Ende des Abonnements**: **60** Tage, um anzugeben, dass ein Kunde als abgewandert gilt, wenn er das Abonnement in diesem Zeitraum nach Ende seines Abonnements nicht verlängert.
   - **Tage in der Zukunft für die Abwanderungsprognose**: **93** Tage, was die Dauer ist, die das Modell für die Vorhersage verwendet, welche Kunden abwandern könnten. Je weiter Sie in die Zukunft schauen, desto ungenauer werden die Ergebnisse.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Wählen Sie die Modellpräferenzen und die Abwanderungsdefinition.":::

1. Wählen Sie **Weiter** aus.

1. Wählen Sie im Schritt **Erforderliche Daten** die Option **Daten hinzufügen** aus, um den Abonnementverlauf anzugeben.

1. Wählen Sie **Abonnement** und die SubscriptionHistory-Entität und dann **Weiter** aus. Die erforderlichen Daten werden automatisch aus der Aktivität entnommen. Wählen Sie **Save** (Speichern).

1. Wählen Sie unter Kundenaktivitäten **Daten hinzufügen** aus.

1. Fügen Sie für dieses Beispiel die Webbewertungsaktivität hinzu.

1. Wählen Sie **Weiter** aus.

1. Wählen Sie in dem Schritt **Datenupdates** für den Modellzeitplan **Monatlich** aus.

1. Nachdem Sie alle Details überprüft haben, wählen Sie **Speichern und Ausführen**.

## <a name="task-5---review-model-results-and-explanations"></a>Aufgabe 5 - Überprüfung der Modellergebnisse und Erklärungen

Lassen Sie das Modell das Training und das Scoring der Daten abschließen. Gehen Sie die Erläuterungen zum Abonnementabwanderungsmodell durch. Weitere Informationen finden Sie unter [Vorhersageergebnisse anzeigen](predict-subscription-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Aufgabe 6 - Erzeugen eines Segments von Kunden mit hohem Abwanderungsrisiko

Beim Ausführen des Modells wird eine neue Entität erstellt, die unter **Daten** > **Entitäten** aufgeführt ist. Sie können ein neues Segment basierend auf der vom Modell erstellten Entität erstellen.

1. Wählen Sie auf der Ergebnisseite **Segment erstellen** aus.

1. Erstellen Sie eine Regel mit der Entität **OOBSubscriptionChurnPrediction** und definieren Sie das Segment:
   - **Feld**: ChurnScore
   - **Operator**: größer als
   - **Wert**: 0.6

1. Wählen Sie **Speichern** aus und dann **Ausführen** für das Segment.

Sie haben jetzt ein Segment, das dynamisch aktualisiert wird und Kunden mit hohem Abwanderungsrisiko für dieses Abo-Geschäft identifiziert. Weitere Informationen finden Sie unter [Erstellen und Verwalten von Segmenten](segments.md).

> [!TIP]
> Sie können auch ein Segment für ein Vorhersagemodell aus der Seite **Segmente** erstellen, indem Sie **Neu** und dann **Erstellen aus** > **Intelligenz** auswählen. Weitere Informationen finden Sie unter [Ein neues Segment mit Schnellsegmenten erstellen](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
