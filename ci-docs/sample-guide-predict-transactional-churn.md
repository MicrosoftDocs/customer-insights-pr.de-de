---
title: Transaktionsabwanderungsvorhersage Beispielanleitung
description: Verwenden Sie diese Anleitung, um das Out-of-Box-Modell zur Vorhersage von Transaktionsabwanderung auszuprobieren.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741318"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Transaktionsabwanderungsvorhersage Beispielanleitung

Diese Anleitung führt Sie durch ein End-to-End-Beispiel für die Vorhersage der Transaktionsabwanderung in Customer Insights unter Verwendung der unten angegebenen Daten. Alle in dieser Anleitung verwendeten Daten sind keine echten Kundendaten und gehören zum Contoso Dataset, das sich in der *Demo* Umgebung innerhalb Ihres Customer Insights-Abonnements befindet.

## <a name="scenario"></a>Szenario

Contoso ist ein Unternehmen, das hochwertigen Kaffee und Kaffeemaschinen herstellt, die es über seine Website Contoso Coffee verkauft. Ihr Ziel ist es, zu wissen, welche Kunden, die normalerweise regelmäßig ihre Produkte kaufen, in den nächsten 60 Tagen keine aktiven Kunden mehr sein werden. Zu wissen, welche ihrer Kunden **wahrscheinlich abwandern**, kann ihnen helfen, Marketingaufwand zu sparen, indem sie sich darauf konzentrieren, diese Kunden zu halten.

## <a name="prerequisites"></a>Anforderungen

- Mindestens die [Berechtigung "Mitwirkender"](permissions.md) in Customer Insights.
- Wir empfehlen, dass Sie die folgenden Schritte [in einer neuen Umgebung](manage-environments.md) implementieren.

## <a name="task-1---ingest-data"></a>Aufgabe 1 - Datenerfassung

Lesen Sie insbesondere die Artikel zu [Datenerfassung](data-sources.md) und [Importieren von Datenquellen mit Power Query-Konnektoren](connect-power-query.md). Die folgenden Informationen setzen voraus, dass Sie mit der Datenerfassung im Allgemeinen vertraut sind. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Datenerfassung von Kundendaten aus der eCommerce-Plattform

1. Erstellen Sie eine Datenquelle mit dem Namen **eCommerce**, wählen Sie die Importoption und wählen Sie den **Text/CSV** Konnektor.

1. Geben Sie die URL für eCommerce-Kontakte https://aka.ms/ciadclasscontacts ein.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:

   - **DateOfBirth**: Datum
   - **CreatedOn**: Datum/Uhrzeit/Zone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="DoB in Datum umwandeln.":::

1. Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle von **Abfrage** in **eCommerceContacts** um

1. Speichern Sie die Datenquelle.

### <a name="ingest-online-purchase-data"></a>Datenerfassung von Online-Kaufdaten

1. Fügen Sie einen weiteren Datensatz zur gleichen **eCommerce** Datenquelle hinzu. Wählen Sie erneut den **Text/CSV** Konnektor.

1. Geben Sie die URL für **Online-Einkäufe** Daten https://aka.ms/ciadclassonline ein.

1. Wählen Sie beim Bearbeiten der Daten **Transformieren** und dann **Erste Zeile als Kopfzeile verwenden**.

1. Aktualisieren Sie den Datentyp für die unten aufgeführten Spalten:

   - **Gekauft am**: Datum/Uhrzeit
   - **GesamtPreis**: Währung
   
1. Benennen Sie im Feld **Name** im rechten Fensterbereich Ihre Datenquelle von **Abfrage** in **eCommercePurchases** um.

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

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>Aufgabe 3 - Konfigurieren der Vorhersage der Transaktionsabwanderung

Mit den Unified customer profiles können wir jetzt die Transaktionsabwanderungs-Vorhersage ausführen. Detaillierte Schritte finden Sie im Artikel [Transaktionsabwanderungs-Vorhersage](predict-transactional-churn.md). 

1. Gehen Sie zu **Intelligenz** > **Erkennen** und wählen Sie das Modell **Kundenabwanderung**.

1. Wählen Sie die Option **Transaktional** und wählen Sie **Anfangen**.

1. Benennen Sie das Modell **OOB-E-Commerce-Abonnementsabwanderungsvorhersage** und die Ausgabe-Entität **OOBeCommerceChurnPrediction**.

1. Definieren Sie zwei Bedingungen für das Churn-Modell:

   * **Vorhersagefenster**: **mindestens 60** Tage. Diese Einstellung legt fest, wie weit in die Zukunft wir die Kundenabwanderung vorhersagen wollen.

   * **Abwanderungsdefinition**: **mindestens 60** Tage. Die Dauer ohne Kauf, nach der ein Kunde als abgewandert gilt.

     :::image type="content" source="media/model-levers.PNG" alt-text="Wählen Sie die Modellhebel Vorhersagefenster und Abwanderungsdefinition.":::

1. Wählen Sie **Kaufhistorie (erforderlich)** und wählen Sie **Daten hinzufügen** für die Kaufhistorie.

1. Fügen Sie die Entität **eCommercePurchases : eCommerce** hinzu und ordnen Sie die Felder von eCommerce den entsprechenden vom Modell benötigten Feldern zu.

1. Verbinden Sie die Entität **eCommercePurchases : eCommerce** mit **eCommerceContacts : eCommerce**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Join von eCommerce-Entitäten.":::

1. Wählen Sie **Weiter**, um den Modellplan einzustellen.

   Das Modell muss regelmäßig trainieren, um neue Muster zu lernen, wenn neue Daten erfasst werden. Wählen Sie für dieses Beispiel **Monatlich**.

1. Nachdem Sie alle Details überprüft haben, wählen Sie **Speichern und Ausführen**.

## <a name="task-4---review-model-results-and-explanations"></a>Aufgabe 4 - Überprüfung der Modellergebnisse und Erklärungen

Lassen Sie das Modell das Training und das Scoring der Daten abschließen. Sie können jetzt die Erläuterungen zum Abwanderungsmodell überprüfen. Weitere Informationen finden Sie unter [Überprüfen eines Vorhersagestatus und der Ergebnisse](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Aufgabe 5 - Erzeugen eines Segments von Kunden mit hohem Abwanderungsrisiko

Das Ausführen des Produktionsmodells erstellt eine neue Entität, die Sie in **Daten** > **Entitäten** sehen können.   

Sie können ein neues Segment basierend auf der vom Modell erstellten Entität erstellen.

1.  Gehen Sie zu **Segmente**. Wählen Sie **Neu** aus und wechseln Sie dann zu **Erstellen aus** > **Intelligenz**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Erstellen eines Segments mit der Modellausgabe.":::

1. Wählen Sie den Endpunkt **OOBeCommerceChurnPrediction**, und definieren Sie das Segment: 
   - Feld: ChurnScore
   - Operator: größer als
   - Wert: 0,6

Sie haben jetzt ein dynamisch aktualisiertes Segment, das Kunden mit hohem Abwanderungsrisiko identifiziert.

Weitere Informationen finden Sie unter [Erstellen und Verwalten von Segmenten](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
