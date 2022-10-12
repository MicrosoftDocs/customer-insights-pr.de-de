---
title: Übersicht über Vorhersagen
description: Vorhersageszenarien und Optionen, die von der Anwendung Dynamics 365 Customer Insights abgedeckt werden.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610189"
---
# <a name="predictions-overview"></a>Übersicht über Vorhersagen

Dynamics 365 Customer Insights ist mit einer Vielzahl von Optionen ausgestattet, die KI und Machine Learning nutzen, um Daten vorherzusagen.

## <a name="out-of-box-models"></a>Sofort einsatzbereite Modelle

Der einfachste Weg, um mit der Vorhersage von Daten zu beginnen, sind vordefinierte Modelle, die auch als sofort einsatzbereite Modelle bezeichnet werden. Sie benötigen nur bestimmte Daten und Strukturen, um schnell Erkenntnisse zu gewinnen. Die folgenden Modelle sind verfügbar:

# <a name="individual-consumers-b-to-c"></a>[Einzelne Verbraucher (B2C)](#tab/b2c)

- [Langfristiger Kundenwert](predict-customer-lifetime-value.md) : Prognostiziert den potenziellen Umsatz eines Kunden während der gesamten Interaktion mit einem Unternehmen.
- [Produktempfehlung](predict-product-recommendation.md) : Schlägt prädiktive Produktempfehlungen basierend auf dem Kaufverhalten und Kunden mit ähnlichen Kaufmustern vor.
- [Abonnementabwanderung](predict-subscription-churn.md): Sagt vorher, ob das Risiko besteht, dass ein Kunde die Abonnementprodukte oder Services Ihres Unternehmens nicht länger verwendet.
- [Transaktionsabwanderung](predict-transactional-churn.md): Sagt vorher, ob ein einzelner Kunde Ihre Produkte oder Dienstleistungen in einem bestimmten Zeitrahmen nicht mehr kaufen wird.
- [Stimmungsanalyse](sentiment-analysis.md) : Analysiert die Stimmung des Kundenfeedbacks und identifiziert häufig erwähnte Geschäftsaspekte.

# <a name="business-accounts-b-to-b"></a>[Unternehmenskonten (B2B)](#tab/b2b)

- [Transaktionsabwanderung](predict-transactional-churn.md) : Sagt vorher, ob ein Kundenkonto Ihre Produkte oder Dienstleistungen in einem bestimmten Zeitrahmen nicht mehr kaufen wird.

---

> [!TIP]
> Wir empfehlen, dass Sie Standardmodelle regelmäßig mit aktualisierten Daten aktualisieren, um sicherzustellen, dass sie Ihren geschäftlichen Anwendungsfall genau darstellen. Daten werden ad hoc aktualisiert, wenn das System neue oder aktualisierte Datenquellen aufnimmt. Modelle werden jedoch nur in diesem Fall neu bewertet und verwenden weiterhin die vorhandenen Trainingsdaten.
>
> Konfigurieren Sie **Zeitplan aktualisieren**, indem Sie während der Konfiguration den Zeitplan zur erneuten Training des Modells einstellen. Das Modell wird nach diesem Zeitplan, den Sie jederzeit ändern können, erneut trainiert und neu bewertet.

## <a name="azure-machine-learning-integration"></a>Azure Machine Learning-Integration

Wenn eine Organisation bereits Machine Learning-Szenarien basierend auf Azure Machine Learning-Experimenten verwendet, hilft das Feature für benutzerdefinierte Modelle in Customer Insights, alles zu verbinden. Erstellen Sie Workflows, die Ihnen bei der Auswahl der Daten helfen, aus denen Sie Erkenntnisse generieren möchten, und bei der Zuordnung der Ergebnisse zu Ihren vereinheitlichten Kundenprofilen. Weitere Informationen finden Sie unter [Benutzerdefinierte Machine Learning Modelle](custom-models.md).

## <a name="manage-existing-predictions"></a>Vorhandene Vorhersagen verwalten

Gehen Sie zur Seite **Intelligenz** > **Vorhersagen**. Sehen Sie sich auf der Seite **Meine Vorhersagen** die erstellten Vorhersagen, den Vorhersagetyp, den Namen der Ausgabeentität, den Status, die letzte Bearbeitung der Vorhersage und die letzte Aktualisierung der Daten an. Sie können die Liste der Vorhersagen nach jeder Spalte sortieren.

Wählen Sie eine Vorhersage aus, um verfügbare Aktionen anzuzeigen.

:::image type="content" source="media/predictions.png" alt-text="Seite „Meine Vorhersagen“.":::

- **Bearbeiten** Sie die Vorhersage, um seine Eigenschaften zu ändern.
- [**Aktualisieren**](#refresh-a-prediction) Sie die Vorhersage, um die neuesten Daten einzuschließen.
- Lassen Sie sich die Vorhersagedetails **anzeigen**.
- [**Eingabedaten-Nutzungsbericht**](#view-the-input-data-usability-report), um Fehler, Warnungen und Empfehlungen anzuzeigen.
- **Löschen** Sie die Vorhersage.

### <a name="refresh-a-prediction"></a>Aktualisieren einer Vorhersage

Vorhersagen können nach einem automatischen Zeitplan oder manuell bei Bedarf aufgefrischt werden. Um alle Vorhersagen manuell zu aktualisieren, wählen Sie **Alle aktualisieren**. Um eine Vorhersage manuell zu aktualisieren, wählen Sie die Vorhersage und dann **Aktualisieren** aus. Zum [Planen einer automatischen Aktualisierung](schedule-refresh.md) wechseln Sie zu **Administrator** > **System** > **Zeitplan**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Anzeigen des Eingabedaten-Nutzungsberichts

Der Eingabedaten-Nutzungsbericht bietet eine konsolidierte Ansicht der Fehler und Warnungen, die Ihre sofort einsatzbereiten Vorhersagen generieren. Er gibt auch Empfehlungen zur Verbesserung der Modellleistung.

Der Bericht ist verfügbar, nachdem ein Modell seinen Trainingsprozess abgeschlossen hat. Er wird für jedes Modell separat erstellt, unabhängig davon, ob das Training erfolgreich abgeschlossen wurde oder nicht.

Wählen Sie auf der Registerkarte **Meine Vorhersagen** die Vorhersage und dann **Eingabedaten-Nutzungsbericht** aus. Oder wählen Sie in der Detailansicht „Vorhersage“ **Eingabedaten-Nutzungsbericht** aus.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Beispiel für einen Eingabedaten-Nutzungsbericht mit einer Tabelle mit Fehlern, Warnungen und Empfehlungen.":::

Der Bericht enthält Folgendes:

- **Name:** Ein beschreibender Name des Fehlers, der Warnung oder der Empfehlung.
- **Schritt:** Modellphase, Training oder Bewertung, auf die sich die Informationen beziehen.
- **Status:** Der Schweregrad der Information (Fehler, Warnung, Empfehlung).
- **Spaltenname:** Eine Spalte in einer Entität, die geändert werden muss, um die Modellleistung zu verbessern.
- **Entitätsname:** Der Name der Entität, die geändert werden muss, um die Modellleistung zu verbessern.
- **Details:** Details zu Fehlern, Warnungen oder Empfehlungen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
