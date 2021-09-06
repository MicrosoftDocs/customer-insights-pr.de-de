---
title: Machine Learning Studio (Classic) Experimente
description: Verwenden Sie Machine Learning Studio (Classic) Modelle in Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: ameetj
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b979dd177b7c6de1971c02a69748006d041e4d2c3e49a3639dba03212bd7acf9
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033722"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Verwenden Sie Modelle, die auf Azure Machine Learning Studio (Classic) basieren

Die vereinheitlichten Daten in Dynamics 365 Customer Insights sind eine Quelle für den Aufbau von Machine-Learning-Modellen, die zusätzliche Geschäftseinblicke generieren können. Customer Insights integriert sich mit Machine Learning Studio (Classic), um Ihre eigenen benutzerdefinierten Modelle zu verwenden. Um zu sehen, wie in Azure Machine Learning entwickelte Modelle in Customer Insights integriert werden, siehe [Azure Machine Learning Experimente](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Anforderungen

- Zugriff auf Customer Insights
- Ein aktives Azure-Enterprise-Abonnement
- [Vereinheitlichte Kundenprofile](data-unification.md)
- [Entitätsexport in den Azure Blob-Speicher](export-azure-blob-storage.md) Einrichtung

## <a name="set-up-machine-learning-studio-classic"></a>Machine Learning Studio Classic einrichten

In einem ersten Schritt müssen wir einen Arbeitsbereich für das Machine Learning Studio (Classic) erstellen und öffnen.

1. Wechseln Sie zu [https://www.portal.azure.com](https://www.portal.azure.com/), und melden Sie sich an.

1. Wählen Sie **Ressource erstellen** aus.

1. Suche nach **Machine Learning Studio Arbeitsbereich** und **Erstellen** wählen.

1. Geben Sie die erforderlichen Details ein für [Arbeitsbereich erstellen](/azure/machine-learning/studio/create-workspace). Wählen Sie die **Preisstufe des Webservice-Plans** basierend auf der Datenmenge, die Sie importieren wollen. Für eine optimale Leistung wählen Sie den **Standort**, der Ihnen geografisch am nächsten liegt.

1. Nach dem Erstellen der Ressource wird das Dashboard Machine Learning Studio Arbeitsbereich angezeigt. Wählen Sie **Machine Learning Studio starten**.

   ![Azure Machine Learning Studio-Benutzeroberfläche.](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Arbeiten mit Azure Machine Learning Studio

Sie können jetzt ein neues Experiment erstellen oder eine vorhandene Experimentvorlage aus der Beispielgalerie importieren. Es gibt Beispielexperimente für drei Standardszenarien:

- [Churn Vorhersage](#churn-analysis)

- [Langfristiger Kundenwert](#customer-lifetime-value-prediction)

- [Produktempfehlung oder nächstbeste Aktion](#productrecommendation-or-next-best-action)

1. Wenn Sie ein neues Experiment erstellen oder eine Experimentvorlage aus der Galerie verwenden, müssen Sie die Eigenschaften **Daten importieren** konfigurieren. Verwenden Sie die Anleitung oder geben Sie direkt Details an, um auf den Azure Blob storage zuzugreifen, der Ihre Daten enthält.  

   ![Experiment mit Azure Machine Learning Studio.](media/azure-machine-learning-studio-experiment.png)

1. Jetzt können Sie eine benutzerdefinierte Verarbeitungspipeline erstellen, um die Daten zu bereinigen und vorzuverarbeiten, Features zu extrahieren und ein geeignetes Modell zu trainieren.

1. Modellleistung testen und optimieren.

1. Wenn Sie mit der Qualität eines Modells zufrieden sind, wählen Sie **Richten Sie den Webdienst ein** > **Vorhersage-Webdienst**. Diese Option importiert das trainierte Modell und die Funktions-Pipeline aus dem Trainingsexperiment in einen Vorhersagedienst. Der Vorhersagedienst kann einen anderen Satz von Eingabedaten mit dem im Trainingsexperiment verwendeten Schema verwenden, um Vorhersagen zu treffen.

   ![Richten Sie einen Vorhersage-Webdienst ein.](media/predictive-webservice-control.png)

1. Sobald das Vorhersage-Webdienst-Experiment erfolgreich ist, können Sie es für die automatische Planung bereitstellen. Wählen Sie aus, damit der Webdienst mit Customer Insights funktioniert **Stellen Sie den Webdienst bereit** > **Vorschau Webdienst [Neu] bereitstellen**. [Weitere Informationen zum Bereitstellen eines Webdienstes](/azure/machine-learning/studio/deploy-a-machine-learning-web-service).

   ![Vorhersage-Webdienst bereitstellen.](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Beispielmodelle aus der Galerie

Wir verwenden ein fiktives Szenario von Contoso Hotel für die Modelle in diesem Artikel. Contoso Hotel sammelt die folgenden Daten:

- CRM-Daten, bestehend aus Hotelaufenthaltsaktivität. Das Dataset enthält Informationen zu den Aufenthaltsdaten für jeden registrierten Kunden. Es enthält auch Informationen zur Buchung, Zimmertypen, Details zu den Ausgaben usw. Die Daten erstrecken sich über vier Jahre von Januar 2014 bis Januar 2018.
- Kundenprofile von Hotelgästen. Diese Profile enthalten Informationen zu jedem Kunden, einschließlich Name, Geburtsdatum, Postanschrift, Geschlecht und Telefonnummer.
- Nutzung der vom Hotel angebotenen Dienstleistungen wie Spa, Wäscherei, WLAN oder Kurier. Diese Informationen werden für jeden registrierten Kunden protokolliert. In der Regel ist die Nutzung der Dienste mit dem Aufenthalt verbunden. In einigen Fällen können Dienste von Kunden genutzt werden, ohne im Hotel zu bleiben.

## <a name="churn-analysis"></a>Abwanderungsanalyse

Die Abwanderungsanalyse gilt für verschiedene Geschäftsbereiche. In diesem Beispiel werden wir uns die Service-Abwanderung ansehen, speziell im Zusammenhang mit den oben beschriebenen Hoteldienstleistungen. Es bietet ein funktionierendes Beispiel für eine End-to-End-Modell-Pipeline, die als Ausgangspunkt für jede andere Art von Churn-Modell verwendet werden kann.

### <a name="definition-of-churn"></a>Definition von Abwanderung

Die Definition der Abwanderung kann je nach Szenario unterschiedlich sein. In diesem Beispiel soll ein Gast, der das Hotel im letzten Jahr nicht besucht hat, als abgewandert gekennzeichnet werden.  

Die Experimentvorlage kann aus dem Katalog importiert werden. Stellen Sie zunächst sicher, dass Sie die Daten für **Hotelaufenthaltsaktivität**, **Kundendaten** und **Service-Nutzungsdaten** aus dem Azure Blob storage importieren.

   ![Importieren Sie Daten für das Abwanderungsmodell.](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Funktionenbereitstellung

Basierend auf der Definition von „Churn“ identifizieren wir zunächst die Roh-Features, die das Label beeinflussen werden. Anschließend verarbeiten wir diese Grundfunktionen zu numerischen Funktionen, die mit Machine Learning Modellen verwendet werden können. Die Datenintegration erfolgt in Customer Insights, sodass wir diese Tabellen über die *Kunden-ID* verbinden können.

   ![Importierte Daten verbinden.](media/join-imported-data.png)

Die Funktion zur Erstellung des Modells für die Abwanderungsanalyse kann ein wenig knifflig sein. Die Daten sind eine Funktion der Zeit, wobei täglich neue Hotelaktivitäten aufgezeichnet werden. Während der Anpassung möchten wir statische Funktionen aus den dynamischen Daten generieren. In diesem Fall erzeugen wir mehrere Funktionen aus der Hotelaktivität mit einem gleitenden Fenster von einem Jahr. Wir erweitern auch die kategorialen Funktionen wie Zimmertyp oder Buchungstyp mithilfe der One-Hot-Codierung in separate Funktionen.  

Endgültige Liste der Funktionen:

| **Zahl**  | **Original_Column**          | **Abgeleitete Funktionen**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Zimmertyp                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Buchungstyp                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Reisekategorie              | ReiseKategorieGeschäftsreiseZahl, ReiseKategorieFreizeitZahl                                                                                   |
| 4           | Dollar ausgegeben                | TotalDollarSpent                                                                                                                          |
| 5           | Check-In- und Check-Out-Daten  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Service-Verbrauch                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Modellauswahl

Jetzt müssen wir den optimalen Algorithmus auswählen. In diesem Fall basieren die meisten Funktionen auf kategorialen Funktionen. Typischerweise funktionieren entscheidungsbaumbasierte Modelle gut. Wenn es nur numerische Funktionen gibt, könnten neuronale Netzwerke eine bessere Wahl sein. Support Vector Machine (SVM) ist auch in solchen Situationen ein guter Kandidat. Es ist jedoch einiges an Abstimmung erforderlich, um die beste Leistung zu erzielen. Wir wählen **Zwei-Klassen-Boosted-Entscheidungsbaum** als das erste Modell der Wahl, gefolgt von **Zwei-Klassen-SVM** als zweites Modell. Mit Azure Machine Learning Studio können Sie A/B-Tests durchführen, sodass es von Vorteil ist, mit zwei Modellen statt mit einem zu beginnen.

Das folgende Bild zeigt die Modellschulungs- und Evaluierungspipeline von Azure Machine Learning Studio:

![Abwanderungsmodell in Azure Machine Learning Studio.](media/azure-machine-learning-model.png)

Wir wenden auch eine Technik namens **Wichtigkeit der Permutationsfunktion** an, ein wichtiger Aspekt der Modelloptimierung. Eingebaute Modelle haben wenig bis gar keinen Einblick in die Auswirkungen bestimmter Funktionen auf die endgültige Vorhersage. Der Rechner für die Wichtigkeit der Funktionen verwendet einen benutzerdefinierten Algorithmus, um den Einfluss der einzelnen Funktionen auf das Ergebnis für ein bestimmtes Modell zu berechnen. Die Merkmalsbedeutung wird zwischen +1 und -1 normalisiert. Ein negativer Einfluss bedeutet, dass das entsprechende Merkmal einen kontra-intuitiven Einfluss auf das Ergebnis hat und aus dem Modell entfernt werden sollte. Ein positiver Einfluss zeigt an, dass die Funktion einen großen Beitrag zur Vorhersage leistet. Diese Werte sind keine Korrelationskoeffizienten, da es sich um unterschiedliche Metriken handelt. Weitere Informationen finden Sie unter [Permutation Funktion Wichtigkeit](/azure/machine-learning/studio-module-reference/permutation-feature-importance).

Das gesamte [Kundenabwanderungs-Experiment ist im Azure AI Katalog](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp) verfügbar.

## <a name="customer-lifetime-value-prediction"></a>Benutzerdefinierte Lebensdauer-Wert-Vorhersage

Die Berechnung des Customer Lifetime Value (CLTV) ist eine der wichtigsten Metriken, die ein Unternehmen zur Bewertung und Segmentierung seiner Kunden verwenden kann. Für die Hotellerie ist es wichtig, ihre Kunden zu kennen. Zum Beispiel ist das Verständnis der Faktoren, die gute Kunden ausmachen, eine entscheidende Information. Es hilft dem Hotelmanagement bei der Beurteilung, auf welche Funktionen sie sich konzentrieren und diese verbessern müssen, um ihre hoch zahlenden Kunden zufrieden zu stellen. Diese Entscheidungen können sich direkt auf Umsatz und Ergebnis auswirken.  

### <a name="definition-of-cltv"></a>Definition von CLTV

Für dieses Beispiel definieren wir den CLTV eines Kunden als den gesamten Dollarbetrag, den der Kunde voraussichtlich in den nächsten 365 Tagen ausgeben wird. Wir werden die Daten der letzten drei Jahre für alle Kunden verwenden, um diesen Wert vorherzusagen.

### <a name="featurization"></a>Funktionenbereitstellung

In diesem Fall wird die Funktionenbereitstellung dem Abwanderungsszenario sehr ähnlich sein. Die Labels und vorhergesagten Werte sind jedoch anders als oben definiert.

### <a name="model-selection"></a>Modellauswahl

Die Vorhersage des CLTV ist ein Regressionsproblem, da der vorhergesagte Wert eine kontinuierlich bewertete Variable mit positivem Wert ist. Basierend auf den Funktionseigenschaften wählen wir **Regression mit verstärktem Entscheidungsbaum** als einen Algorithmus und **Regression über neurales Netzwerk** als einen weiteren Algorithmus zum Trainieren des Modells.

## <a name="product-recommendation-or-next-best-action"></a>Produktempfehlung oder nächstbeste Aktion

Die Produktempfehlung in einem Hotelszenario wird als Empfehlung der vom Hotel angebotenen Dienstleistungen an die Kunden interpretiert. Ziel ist es, die geeigneten Services für Kunden auszuwählen, damit deren Nutzung maximiert wird. Es ähnelt den Filmempfehlungen für Benutzer von Video-Streaming-Diensten.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Definition der Produktempfehlung oder nächstbeste Aktion

Wir definieren das Ziel als Maximierung der Service-Nutzung in US-Dollar, indem wir Hotelkunden die am besten passenden Services entsprechend ihren Interessen anbieten.

### <a name="featurization"></a>Funktionenbereitstellung

Wie beim Churn-Modell verbinden wir das Hotel ServiceCustomerID mit CustomerID, um Empfehlungen konsistent pro CustomerID zu erstellen.

![Ausstattung des Empfehlungsmodells.](media/azure-machine-learning-model-featurization.png)

Die Daten stammen von drei verschiedenen Entitäten und Funktionen werden daraus abgeleitet. Die Funktion für das Empfehlungsproblem unterscheidet sich von Abwanderungs- oder CLTV-Szenarien. Das Empfehlungsmodell benötigt Eingabedaten in Form von drei Sätzen von Funktionen.

### <a name="model-selection"></a>Modellauswahl

Wir sagen Produkte oder Dienstleistungen voraus, indem wir den Algorithmus **Übereinstimmungsemfehlung trainieren** verwenden, um das Empfehlungsmodell zu trainieren.

![Produktempfehlungen-Algorithmus.](media/azure-machine-learning-model-recommendation-algorithm.png)

Die drei Eingänge für das Modell **Übereinstimmungsemfehlung trainieren** nehmen die Trainingsdaten der Servicenutzung, die Kundenbeschreibung (optional) und die Servicebeschreibung auf. Es gibt drei verschiedene Arten, das Modell zu bewerten. Eine ist für die Modellbewertung, bei der ein NDCG-Wert (Normalized Discounted Cumulative Gain) berechnet wird, um die bewerteten Elemente in eine Rangfolge zu bringen. In diesem Experiment haben wir den NDCG-Score als 0.97. Die anderen beiden Optionen sind die Bewertung des Modells für den gesamten Katalog empfehlenswerter Dienste oder die Bewertung nur für Elemente, die Benutzer noch nicht verwendet haben.

Wenn wir uns die Verteilung der Empfehlungen auf den gesamten Servicekatalog genauer ansehen, stellen wir fest, dass Telefon, WiFi und Kurier die am häufigsten empfohlenen Services sind. Dies steht im Einklang mit dem, was wir aus den Verteilungen der Dienstverbrauchsdaten herausgefunden haben:

![Empfehlungsmodell-Ausgabe.](media/azure-machine-learning-model-output.png)

Auf das gesamte [Produktempfehlungs-Experiment kann in der Azure AI Gallery zugegriffen werden.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Integrieren Sie benutzerdefinierte Modelle

Um diese Vorhersagen in Customer Insights zu verwenden, müssen Sie die Vorhersagen zusammen mit den Kunden-IDs **exportieren**. [Exportieren Sie sie an denselben Azure Blob-Speicherort](/azure/storage/common/storage-import-export-data-from-blobs), an den Sie die Quelldaten exportieren. Der Predictive Web Service kann so geplant werden, dass er regelmäßig ausgeführt wird und die Ergebnisse aktualisiert werden.

Die vom benutzerdefinierten Modell generierten Daten können verwendet werden, um Ihre Kundendaten weiter anzureichern. Weitere Informationen finden Sie unter [Benutzerdefinierte Machine Learning Modelle](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]