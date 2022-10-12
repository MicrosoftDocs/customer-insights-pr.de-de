---
title: Transaktionsabwanderungsvorhersage Beispielanleitung
description: Verwenden Sie diese Anleitung, um das Out-of-Box-Modell zur Vorhersage von Transaktionsabwanderung auszuprobieren.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609683"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Transaktionsabwanderungsvorhersage Beispielanleitung

Diese Anleitung führt Sie durch ein End-to-End-Beispiel für die Vorhersage der Transaktionsabwanderung mit Beispieldaten. Wir empfehlen, dass Sie diese Vorhersage [in einer neuen Umgebung](manage-environments.md) ausprobieren.

## <a name="scenario"></a>Szenario

Contoso ist ein Unternehmen, das hochwertige Kaffees und Kaffeemaschinen herstellt. Es verkauft die Produkte über die Contoso Coffee-Website. Ihr Ziel ist es, zu wissen, welche Kunden, die normalerweise regelmäßig ihre Produkte kaufen, in den nächsten 60 Tagen keine aktiven Kunden mehr sein werden. Zu wissen, welche ihrer Kunden **wahrscheinlich abwandern**, kann ihnen helfen, Marketingaufwand zu sparen, indem sie sich darauf konzentrieren, diese Kunden zu halten.

## <a name="prerequisites"></a>Anforderungen

- Mindestens [Beteiligungsberechtigungen](permissions.md).

## <a name="task-1---ingest-data"></a>Aufgabe 1 - Datenerfassung

Lesen Sie die Artikel zu [Datenerfassung](data-sources.md) und zur [Verbindung mit einer Power Query-Datenquelle](connect-power-query.md). Bei den folgenden Informationen wird davon ausgegangen, dass Sie mit der Datenerfassung im Allgemeinen vertraut sind.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Datenerfassung von Kundendaten aus der eCommerce-Plattform

1. Erstellen Sie eine Datenquelle mit dem Namen **E-Commerce** und wählen Sie den **Text/CSV**-Connector.

1. Geben Sie die URL für eCommerce-Kontakte https://aka.ms/ciadclasscontacts ein.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:

   - **DateOfBirth**: Datum
   - **CreatedOn**: Datum/Uhrzeit/Zone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="DoB in Datum umwandeln.":::

1. Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle in **eCommerceContacts** um

1. Speichern Sie die Datenquelle.

### <a name="ingest-online-purchase-data"></a>Datenerfassung von Online-Kaufdaten

1. Fügen Sie einen weiteren Datensatz zur gleichen **eCommerce** Datenquelle hinzu. Wählen Sie erneut den **Text/CSV** Konnektor.

1. Geben Sie die URL für Online-Einkaufsdaten https://aka.ms/ciadclassonline ein.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:

   - **Gekauft am**: Datum/Uhrzeit
   - **GesamtPreis**: Währung

1. Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle in **eCommercePurchases** um.

1. Speichern Sie die Datenquelle.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Kundendaten aus dem Treueschema einlesen

1. Erstellen Sie eine Datenquelle mit dem Namen **LoyaltyScheme** und wählen Sie den **Text/CSV**-Connector.

1. Geben Sie die URL für eCommerce-Kontakte https://aka.ms/ciadclasscustomerloyalty ein.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:

   - **DateOfBirth**: Datum
   - **RewardsPoints**: Ganze Zahl
   - **CreatedOn**: Datum/Uhrzeit

1. Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle in **loyCustomers** um.

1. Speichern Sie die Datenquelle.

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

## <a name="task-4---configure-transaction-churn-prediction"></a>Aufgabe 4 - Konfigurieren der Vorhersage der Transaktionsabwanderung

Mit den vereinheitlichten Kundenprofilen und der Aktivität können wir jetzt die Transaktionsabwanderungs-Vorhersage ausführen.

1. Gehen Sie zu **Intelligenz** > **Vorhersagen**.

1. Wählen Sie auf der Registerkarte **Erstellen** auf **Kundenabwanderungsmodell** **Modell verwenden** aus.

1. Wählen Sie **Transaktional** für die Art der Abwanderung und dann **Erste Schritte** aus.

1. Benennen Sie das Modell **OOB-E-Commerce-Abonnementsabwanderungsvorhersage** und die Ausgabe-Entität **OOBeCommerceChurnPrediction**.

1. Wählen Sie **Weiter** aus.

1. Modelleinstellungen definieren:

   - **Vorhersagefenster**: **60** Tage, um festzulegen, wie weit in die Zukunft wir die Kundenabwanderung vorhersagen wollen.

   - **Abwanderungsdefinition**: **60** Tage, um die Dauer ohne Kauf anzugeben, nach der ein Kunde als abgewandert gilt.

     :::image type="content" source="media/model-levers.PNG" alt-text="Wählen Sie die Modellpräferenzen „Vorhersagefenster“ und „Abwanderungsdefinition“.":::

1. Wählen Sie **Weiter** aus.

1. Wählen Sie **Kaufhistorie (erforderlich)** und wählen Sie **Daten hinzufügen** für die Kaufhistorie.

1. Wählen Sie **SalesOrderLine** und die Entität eCommercePurchases und dann **Weiter** aus. Die erforderlichen Daten werden automatisch aus der Aktivität entnommen. Wählen Sie **Speichern** und dann **Weiter**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Join von eCommerce-Entitäten.":::

1. Überspringen Sie den Schritt **Zusätzliche Daten (optional)**.

1. Wählen Sie in dem Schritt **Datenupdates** für den Modellzeitplan **Monatlich** aus.

1. Nachdem Sie alle Details überprüft haben, wählen Sie **Speichern und Ausführen**.

## <a name="task-5---review-model-results-and-explanations"></a>Aufgabe 5 - Überprüfung der Modellergebnisse und Erklärungen

Lassen Sie das Modell das Training und das Scoring der Daten abschließen. Lesen Sie die Erläuterungen zum Abwanderungsmodell durch. Weitere Informationen finden Sie unter [Vorhersageergebnisse anzeigen](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Aufgabe 6 - Erzeugen eines Segments von Kunden mit hohem Abwanderungsrisiko

Beim Ausführen des Produktionsmodells wird eine neue Entität erstellt, die unter **Daten** > **Entitäten** aufgeführt ist. Sie können ein neues Segment basierend auf der vom Modell erstellten Entität erstellen.

1. Wählen Sie auf der Ergebnisseite **Segment erstellen** aus.

1. Erstellen Sie eine Regel mit der Entität **OOBeCommerceChurnPrediction** und definieren Sie das Segment:
   - **Feld**: ChurnScore
   - **Operator**: größer als
   - **Wert**: 0.6

1. Wählen Sie **Speichern** aus und dann **Ausführen** für das Segment.

Sie haben jetzt ein dynamisch aktualisiertes Segment, das Kunden mit hohem Abwanderungsrisiko identifiziert. Weitere Informationen finden Sie unter [Erstellen und Verwalten von Segmenten](segments.md).

> [!TIP]
> Sie können auch ein Segment für ein Vorhersagemodell aus der Seite **Segmente** erstellen, indem Sie **Neu** und dann **Erstellen aus** > **Intelligenz** auswählen. Weitere Informationen finden Sie unter [Ein neues Segment mit Schnellsegmenten erstellen](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
