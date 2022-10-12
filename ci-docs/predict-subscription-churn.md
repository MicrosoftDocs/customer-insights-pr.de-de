---
title: Abonnementabwanderung vorhersagen (enthält Video)
description: Sagen Sie voraus, ob für einen Kunden das Risiko besteht, dass er die Abonnementprodukte oder -dienste Ihres Unternehmens nicht mehr nutzt.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610235"
---
# <a name="predict-subscription-churn"></a>Abonnementabwanderung vorhersagen

Sagen Sie voraus, ob für einen Kunden das Risiko besteht, dass er die Abonnementprodukte oder -dienste Ihres Unternehmens nicht mehr nutzt. Abonnementdaten enthalten aktive und inaktive Abonnements für jeden Kunden, sodass pro Kunden-ID mehrere Einträge vorhanden sind.

Sie benötigen Geschäftswissen, um zu verstehen, was Abwanderung für Ihr Unternehmen bedeutet. Wir unterstützen zeitbasierte Abwanderungsbedingungen, d. h. ein Kunde gilt eine gewisse Zeit nach Ablauf seines Abonnements als abgewandert.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Probieren Sie die Vorhersage der Abonnementabwanderung mit Beispieldaten aus: [Beispielanleitung für die Vorhersage der Abonnementabwanderung](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Anforderungen

- Mindestens [Beteiligungsberechtigungen](permissions.md).
- Mindestens 10 Kundenprofile, vorzugsweise mehr als 1.000 eindeutigen Kunden.
- Kundenbezeichner, ein eindeutiger Bezeichner zur Zuordnung von Abonnements zu Ihren Kunden.
- Abonnementdaten für mindestens das Doppelte des ausgewählten Zeitfensters. Vorzugsweise zwei bis drei Jahre Abonnementdaten. Der Abonnementverlauf muss Folgendes enthalten:
  - **Abonnement-ID:** Eindeutiger Bezeichner eines Abonnements.
  - **Abonnement-Enddatum:** Datum, an dem das Abonnement für den Kunden abläuft.
  - **Abonnement-Startdatum:** Datum, an dem das Abonnement für den Kunden beginnt.
  - **Transaktionsdatum:** Datum, an dem eine Abonnementänderung stattgefunden hat. Zum Beispiel ein Kunde, der ein Abonnement kauft oder kündigt.
  - **Ist es ein wiederkehrendes Abonnement:** Boolesches Wahr-/Falsch-Feld, das festlegt, ob das Abonnement ohne Eingreifen des Kunden mit derselben Abonnement-ID erneuert wird.
  - **Häufigkeit der Serie (in Monaten):** Bei wiederkehrenden Abonnements ist dies der Monat, in dem das Abonnement erneuert wird. Zum Beispiel hat ein Jahresabonnement, das sich für einen Kunden jedes Jahr automatisch um ein weiteres Jahr verlängert, den Wert 12.
  - **Abonnementbetrag:** Währungsbetrag, den ein Kunde für die Abonnementverlängerung bezahlt. Sie kann helfen, Muster für verschiedene Abonnementstufen zu erkennen.
- Mindestens zwei Aktivitätsdatensätze für 50 % der Kunden, für die Sie die Abwanderung berechnen möchten. Kundenaktivitäten müssen Folgendes miteinbeziehen:
  - **Primärschlüssel:** Eindeutiger Bezeichner für eine Aktivität. Zum Beispiel ein Website-Besuch oder ein Datensatz, der zeigt, dass der Kunde eine TV-Show-Episode angesehen hat.
  - **Zeitstempel:** Datum und die Uhrzeit des Ereignisses, identifiziert durch den Primärschlüssel.
  - **Ereignis:** Name des Ereignisses, das Sie verwenden möchten. Beispielsweise könnte ein Feld mit dem Namen "UserAction" in einem Streaming-Video-Dienst den Wert "Viewed" haben.
  - **Details:** Detaillierte Informationen über das Ereignis. Beispielsweise könnte ein Feld namens "ShowTitle" in einem Streaming-Video-Dienst den Wert eines Videos haben, das ein Kunde angesehen hat.
- Weniger als 20 % der fehlenden Werte im Datenfeld der angegebenen Entität.

## <a name="create-a-subscription-churn-prediction"></a>Erstellen Sie eine Vorhersage zur Abonnementabwanderung.

Wählen Sie **Entwurf speichern** aus, um die Vorhersage als Entwurf zu speichern. Die Entwurfsvorhersage wird in der Registerkarte **Meine Vorhersagen** angezeigt.

1. Gehen Sie zu **Intelligenz** > **Vorhersagen**.

1. Wählen Sie auf der Registerkarte **Erstellen** auf der Kachel **Kundenabwanderungsmodell** **Modell verwenden** aus.

1. Wählen Sie **Abonnement** für die Art der Abwanderung und dann **Erste Schritte** aus.

1. **Dieses Modell benennen** und **Ausgabeentitätsname**, um sie von anderen Modellen oder Entitäten zu unterscheiden.

1. Wählen Sie **Weiter** aus.

### <a name="define-customer-churn"></a>Kundenabwanderung definieren

1. Geben Sie die Anzahl von **Tagen seit Ende des Abonnements** ein, die Ihr Unternehmen einen Kunden in einem abgewanderten Zustand betrachtet. Dieser Zeitraum wird in der Regel für Geschäftsaktivitäten wie Angebote oder andere Marketingmaßnahmen genutzt, um den Verlust des Kunden zu verhindern.

1. Geben Sie die Anzahl der **Tage in der Zukunft für die Abwanderungsvorhersage** an. Sagen Sie z. B. das Abwanderungsrisiko für Ihre Kunden in den nächsten 90 Tagen voraus, um Ihre Marketing-Bindungsmaßnahmen darauf abzustimmen. Die Vorhersage des Abwanderungsrisikos für längere oder kürzere Zeiträume könnte es schwieriger machen, die Faktoren in Ihrem Abwanderungsrisikoprofil zu berücksichtigen, je nach spezifischen Unternehmensanforderungen.

1. Wählen Sie **Weiter** aus.

### <a name="add-required-data"></a>Erforderliche Daten hinzufügen

1. Wählen Sie **Daten hinzufügen** für **Abonnementverlauf** aus.

1. Wählen Sie den semantischen Aktivitätstyp **Abonnement** aus, der die erforderlichen Abonnementverlaufsinformationen enthält. Wenn die Aktivität nicht eingerichtet wurde, wählen Sie sie **hier** aus und erstellen Sie sie.

1. Wählen Sie unter **Aktivitäten**, wenn die Aktivitätsattribute der Aktivität semantisch zugeordnet wurden, die spezifischen Attribute oder Entitäten aus, auf die sich die Berechnung konzentrieren soll. Wenn keine semantische Zuordnung erfolgt ist, wählen Sie **Bearbeiten** aus und ordnen Sie Ihre Daten aus.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Erforderliche Daten für das Abonnementabwanderungsmodell hinzufügen":::

1. Wählen Sie **Nächste** und überprüfen Sie die für dieses Modell erforderlichen Attribute.

1. Wählen Sie **Save** (Speichern).

1. Wählen Sie **Daten hinzufügen** für **Kundenaktivitäten** aus.

1. Wählen Sie den semantischen Aktivitätstyp aus, der die Kundenaktivitätsinformationen bereitstellt. Wenn die Aktivität nicht eingerichtet wurde, wählen Sie sie **hier** aus und erstellen Sie sie.

1. Wählen Sie unter **Aktivitäten**, wenn die Aktivitätsattribute der Aktivität semantisch zugeordnet wurden, die spezifischen Attribute oder Entitäten aus, auf die sich die Berechnung konzentrieren soll. Wenn keine semantische Zuordnung erfolgt ist, wählen Sie **Bearbeiten** aus und ordnen Sie Ihre Daten aus.

1. Wählen Sie **Nächste** und überprüfen Sie die für dieses Modell erforderlichen Attribute.

1. Wählen Sie **Save** (Speichern).

1. Fügen Sie weitere Aktivitäten hinzu oder wählen Sie **Weiter** aus.

### <a name="set-update-schedule"></a>Zeitplanaktualisierung festlegen

1. Wählen Sie die Häufigkeit aus, um Ihr Modell erneut zu trainieren. Diese Einstellung ist wichtig, um die Genauigkeit der Vorhersagen zu aktualisieren, wenn neue Daten in Customer Insights eingebunden werden. Die meisten Unternehmen können einmal pro Monat eine Umschulung durchführen und erhalten eine gute Genauigkeit für ihre Vorhersagen.

1. Wählen Sie **Weiter** aus.

### <a name="review-and-run-the-model-configuration"></a>Überprüfen Sie die Modellkonfiguration und führen Sie sie aus

Der Schritt **Überprüfen und ausführen** zeigt eine Zusammenfassung der Konfiguration und bietet die Möglichkeit, Änderungen vorzunehmen, bevor Sie die Datei Vorhersage erstellen.

1. Wählen Sie **Bearbeiten** bei einem der Schritte, um sie zu überprüfen und Änderungen vorzunehmen.

1. Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **Speichern und ausführen** aus, um das Modell ausführen zu lassen. Wählen Sie **Fertig** aus. Die Registerkarte **Meine Vorhersagen** wird angezeigt, während Vorhersage erstellt wird. Der Prozess kann je nach der Menge der in der Vorhersage verwendeten Daten mehrere Stunden dauern.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Vorhersageergebnisse anzeigen

1. Gehen Sie zu **Intelligenz** > **Vorhersagen**.

1. Wählen Sie in der Registerkarte **Meine Vorhersagen** die Vorhersage aus, die Sie ansehen möchten.

Es gibt drei primäre Datenabschnitte innerhalb der Ergebnisseite:

- **Leistung des Trainingsmodells**: Die Stufen A, B oder C geben die Leistung der Vorhersage an und können Ihnen bei der Entscheidung helfen, die in der Ausgabeentität gespeicherten Ergebnisse zu verwenden.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Bild des Informationsfelds für die Modellbewertung mit der Stufe A.":::

  Die Stufen werden nach den folgenden Regeln ermittelt:
  - **A**, wenn das Modell mindestens 50 % der gesamten Vorhersagen richtig vorhergesagt hat und wenn der Prozentsatz der richtigen Vorhersagen für Kunden, die abgewandert sind, um mindestens 10 % größer ist als die historische durchschnittliche Abwanderung.
  - **B**, wenn das Modell mindestens 50 % der gesamten Vorhersagen richtig vorhergesagt hat und wenn der Prozentsatz der richtigen Vorhersagen für Kunden, die abgewandert sind, um bis zu 10 % größer ist als die historische durchschnittliche Abwanderung.
  - **C** wenn das Modell weniger als 50% der Gesamtvorhersagen genau vorhergesagt hat oder wenn der Prozentsatz der genauen Vorhersagen für abgewanderte Kunden, geringer ist als die historische durchschnittliche Abwanderungsrate.
  
- **Wahrscheinlichkeit der Abwanderung (Anzahl der Kunden)**: Kundengruppen auf der Grundlage ihres vorhergesagten Abwanderungsrisikos. Optional können Sie [Kundensegmente erstellen](prediction-based-segment.md), bei denen ein hohes Abwanderungsrisiko besteht. Solche Segmente helfen Ihnen zu verstehen, wo Ihr Grenzwert für die Segmentmitgliedschaft liegen sollte.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Grafik zur Verteilung der Abwanderungsergebnisse, unterteilt in Bereiche von 0-100%":::

- **Die wichtigsten Einflussfaktoren:** Es gibt viele Faktoren, die bei der Erstellung Ihrer Vorhersage berücksichtigt werden. Für jeden der Faktoren wird seine Wichtigkeit für die aggregierten Vorhersagen, die ein Modell erstellt, berechnet. Verwenden Sie diese Faktoren, um Ihre Vorhersageergebnisse zu validieren. Oder verwenden Sie diese Informationen später, um [Segmente](.//prediction-based-segment.md) zu erstellen, die dazu beitragen könnten, das Abwanderungsrisiko für Kunden zu beeinflussen.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Liste, die die Einflussfaktoren und ihre Bedeutung bei der Vorhersage des Abwanderungsergebnisses zeigt.":::

> [!NOTE]
> In der Ausgabeentität für dieses Modell ist *ChurnScore* die vorhergesagte Abwanderungswahrscheinlichkeit und *IsChurn* eine binäre Bezeichnung basierend auf *ChurnScore* mit Grenzwert 0,5. Wenn dieser Standardgrenzwert für Ihr Szenario nicht funktioniert, [erstellen Sie ein neues Segment](segments.md) mit Ihrem bevorzugten Grenzwert. Um das Abwanderungsergebnis anzuzeigen, gehen Sie zu **Daten** > **Entitäten** und zeigen Sie die Registerkarte „Daten“ für die Ausgabeentität an, die Sie für dieses Modell festgelegt haben.

[!INCLUDE [footer-include](includes/footer-banner.md)]
