---
title: Produktempfehlungsvorhersage
description: Sagen Sie voraus, welche Produkte ein Kunde wahrscheinlich kaufen oder mit denen er interagieren wird.
ms.date: 02/15/2021
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a2eb2b4697e51a0abb933b654a9b0b150dfa6a3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270493"
---
# <a name="product-recommendation-prediction-preview"></a>Produktempfehlungsvorhersage (Vorschau)

Das Produktempfehlungsmodell erstellt Sätze von prädiktiven Produktempfehlungen. Empfehlungen basieren auf dem vorherigen Kaufverhalten und Kunden mit ähnlichen Kaufmustern. Sie können neue Produktempfehlungsvorhersagen auf der Seite **Intelligenz** > **Vorhersagen** erstellen. Wählen Sie **Meine Vorhersagen**, um andere Vorhersagen anzuzeigen, die Sie erstellt haben.

Produktempfehlungen können lokalen Gesetzen und Vorschriften sowie Kundenerwartungen unterliegen, die das Modell nicht speziell berücksichtigt.  Als Benutzer dieser Vorhersagefähigkeit **müssen Sie die Empfehlungen überprüfen, bevor Sie sie an Ihre Kunden liefern**, um sicherzustellen, dass Sie alle geltenden Gesetze oder Vorschriften sowie die Kundenerwartungen für das, was Sie empfehlen, einhalten. 

Darüber hinaus gibt Ihnen die Ausgabe dieses Modells Empfehlungen basierend auf der Produkt-ID. Ihr Übermittlungsmechanismus muss vorhergesagte Produkt-IDs verwenden und sie geeigneten Inhalten zuordnen, damit Ihre Kunden Lokalisierung, Bildinhalte und andere geschäftsspezifische Inhalte oder Verhaltensweisen berücksichtigen können.

## <a name="sample-guide"></a>Beispielanleitung

Wenn Sie diese Funktion ausprobieren möchten, aber keine Daten haben, um die folgenden Anforderungen zu erfüllen, können Sie [eine Beispielimplementierung erstellen](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Anforderungen

- Mindestens die [Berechtigung "Mitwirkender"](permissions.md) in Customer Insights.
- Geschäftskenntnisse, um verschiedene Arten von Produkten für Ihr Unternehmen zu verstehen und wie Ihre Kunden mit ihnen interagieren. Wir unterstützen die Empfehlung von Produkten, die zuvor von Ihren Kunden gekauft wurden, oder Empfehlungen für neue Produkte.
- Daten über Transaktionen/Einkäufe und deren Historie:
    - Transaktionskennungen, um Käufe/Transaktionen zu unterscheiden.
    - Kundenidentifikatoren, um Transaktionen Ihren Kunden zuzuordnen.
    - Transaktionsereignisdaten, die das Datum definieren, an dem die Transaktion stattgefunden hat.
    - (Optional) Produkt-ID-Informationen für die Transaktion.
    - (Optional) Wenn eine Transaktion eine Rückgabe ist oder nicht.
    - Das semantische Datenschema benötigt die folgenden Informationen:
        - **Transaktions-ID:** Ein eindeutiger Bezeichner eines Kaufs oder einer Transaktion.
        - **Transaktionsdatum:** Das Datum des Kaufs oder der Transaktion.
        - **Wert der Transaktion:** Der numerische Wert des Kaufs oder der Transaktion.
        - **Eindeutige Produkt-ID:** Die ID des gekauften Produkts oder Dienstes, wenn Ihre Daten auf Einzelpostenebene sind.
        - (Optional) **Kauf oder Rücksendung:** Ein Wahr/Falsch-Feld, das angibt, ob die Transaktion eine Rückgabe war oder nicht. Wenn der **Wert der Transaktion** negativ ist, wird auch diese Information verwendet, um eine Rückgabe abzuleiten.


## <a name="create-a-product-recommendation-prediction"></a>Produktempfehlungsvorhersage erstellen

1. Gehen Sie in Customer Insights zu **Intelligenz** > **Vorhersagen**.

1. Wählen Sie die Kachel **Produktempfehlungsmodell (Vorschau)** und wählen Sie **Dieses Modell verwenden**.
   > [!div class="mx-imgBorder"]
   > ![Produktempfehlungs-Modellkachel mit Schaltfläche „Dieses Modell verwenden“](media/product-recommendation-usethismodel.PNG "Produktempfehlungs-Modellkachel mit Schaltfläche „Dieses Modell verwenden“")

1. Überprüfen Sie die Informationen zu den Modellanforderungen. Wenn Sie die erforderlichen Daten haben, wählen Sie **Erste Schritte**.

### <a name="name-model"></a>Modell benennen

1. Geben Sie einen Namen für das Modell an, um es von anderen Modellen zu unterscheiden.

1. Geben Sie einen Namen für die Ausgabeentität nur mit Buchstaben und Zahlen ohne Leerzeichen ein. Das ist der Name, den die Modell-Entität verwenden wird. Wählen Sie anschließend **Weiter** aus.

### <a name="define-product-recommendation-configuration"></a>Produktempfehlungskonfiguration definieren

1. Legen Sie die **Anzahl der Produkte** fest, die Sie einem Kunden empfehlen möchten. Dieser Wert hängt davon ab, wie Ihre Versandmethode Daten füllt. Wenn Sie drei Produkte empfehlen können, stellen Sie diesen Wert entsprechend ein.
   
   >[!TIP]
   > Sie können jederzeit **Speichern und schließen** wählen, um die Vorhersage als Entwurf zu speichern. Die Entwurfsvorhersage finden Sie auf der **Meine Vorhersagen**-Registerkarte.

1. Wählen Sie, ob Sie **Produkte vorschlagen, die Kunden kürzlich gekauft haben**.

1. Wenn Sie ausgewählt haben, *keine* kürzlich gekauften Produkte zu empfehlen, legen Sie **Fenster für Vergangenheitsdaten** fest. Diese Einstellung gibt den Zeitrahmen an, den das Modell berücksichtigt, bevor das Produkt dem Benutzer erneut empfohlen wird. Geben Sie beispielsweise an, dass ein Kunde alle 2 Jahre einen Laptop kauft. In diesem Fenster wird die Kaufhistorie der letzten 2 Jahre angezeigt. Wenn ein Artikel gefunden wird, wird der Artikel aus den Empfehlungen herausgefiltert.

1. Klicken Sie auf **Weiter**.

### <a name="add-required-data"></a>Erforderliche Daten hinzufügen

1. Wählen Sie **Daten hinzufügen** für **Kundentransaktionsverlauf** und wählen Sie die Entität, die die Informationen zur Transaktion/Kaufhistorie bereitstellt, wie in den [Voraussetzungen](#prerequisites) beschrieben.

1. Ordnen Sie die semantischen Felder den Attributen innerhalb Ihrer Entität „Kaufhistorie“ zu und wählen Sie **Nächste**. Beschreibungen der Felder finden Sie unter [Voraussetzungen](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Definieren der Entitätsbeziehung](media/product-recommendation-purchasehistorymapping.PNG "Seite „Kaufhistorie“ mit semantischen Attributen, die Feldern in der ausgewählten Entität „Kaufhistorie“ zugeordnet sind")

1. Wenn die Felder nicht ausgefüllt sind, konfigurieren Sie die Beziehung von Ihrer Entität „Kaufhistorie“ zur Entität *Kunde*.
    1. Wählen Sie die Entität **Kaufhistorie**.
    1. Wählen Sie das **Feld**, das den Kunden in der Entität Kaufhistorie identifiziert. Es muss sich auf die primäre Kunden-ID Ihrer Entität *Kunde* beziehen.
    1. Wählen Sie das Feld **Kundenentität**, das sich auf Ihre primäre Kundenentität bezieht.
    1. Geben Sie einen Namen ein, der die Beziehung beschreibt.
       > [!div class="mx-imgBorder"]
       > ![Kaufhistorie-Seite, die die Erstellung einer Beziehung zum Kunden anzeigt.](media/model-purchase-join.png "Kaufhistorie-Seite, die die Erstellung einer Beziehung zum Kunden anzeigt.")

1. Wählen Sie **Speichern** aus.

1. Klicken Sie auf **Weiter**.

### <a name="set-schedule-and-review-configuration"></a>Zeitplan festlegen und Konfiguration überprüfen

1. Legen Sie eine Häufigkeit fest, um Ihr Modell neu zu trainieren. Diese Einstellung ist wichtig, um die Genauigkeit der Vorhersagen zu aktualisieren, wenn neue Daten in Customer Insights importiert werden. Die meisten Unternehmen können einmal pro Monat eine Umschulung durchführen und erhalten eine gute Genauigkeit für ihre Vorhersagen.

1. Klicken Sie auf **Weiter**.

1. Überprüfen Sie die Konfiguration. Sie können zu jedem Teil der Vorhersagekonfiguration zurückkehren, indem Sie unter dem angezeigten Wert **Bearbeiten** wählen. Oder Sie können einen Konfigurationsschritt aus der Fortschrittsanzeige auswählen.

1. Wenn alle Werte korrekt konfiguriert sind, wählen Sie **Speichern und ausführen**, um den Vorhersageprozess zu beginnen. Auf der Registerkarte **Meine Vorhersagen** können Sie den Status Ihrer Vorhersagen sehen. Der Prozess kann je nach der Menge der in der Vorhersage verwendeten Daten mehrere Stunden dauern.

## <a name="review-a-prediction-status-and-results"></a>Überprüfen eines Vorhersage-Status und der Ergebnisse

1. Gehen Sie zur Registerkarte **Meine Vorhersagen** auf **Intelligenz** > **Vorhersagen**.
   > [!div class="mx-imgBorder"]
   > ![Ansicht der Seite Meine Vorhersagen](media/product-recommendation-mypredictions.PNG "Ansicht der Seite Meine Vorhersagen")

1. Wählen Sie die Vorhersage aus, die Sie überprüfen möchten.
   - **Name der Vorhersage:** Der Name der Vorhersage, der bei ihrer Erstellung angegeben wurde.
   - **Art der Vorhersage:** Typ des für die Vorhersage verwendeten Modells
   - **Ausgabe-Entität:** Name der Entität, die die Ausgabe der Vorhersage speichern soll. Eine Entität mit diesem Namen finden Sie unter **Daten** > **Entitäten**.
   - **Vorhersagefeld:** Dieses Feld wird nur für einige Arten von Vorhersagen ausgefüllt und wird nicht für die Abwanderungsvorhersage verwendet.
   - **Status:** Der aktuelle Status des Ausführung der Vorhersage.
        - **Warteschleife:** Die Vorhersage wartet derzeit auf die Ausführung anderer Prozesse.
        - **Aktualisierung:** Die Vorhersage durchläuft derzeit die "Bewertung"-Verarbeitungsphase, um Ergebnisse zu erzeugen, die in die Ausgabe-Entität fließen werden.
        - **Fehlgeschlagen:** Die Vorhersage ist fehlgeschlagen. Wählen Sie **Protokolle** für weitere Einzelheiten.
        - **Erfolgreich:** die Vorhersage war erfolgreich. Wählen Sie **Ansicht** unter den vertikalen Auslassungspunkten, um die Vorhersage zu überprüfen.
   - **Bearbeitet:** Das Datum, an dem die Konfiguration für die Vorhersage geändert wurde.
   - **Zuletzt aktualisiert:** Das Datum, an dem die Vorhersage in der Ausgabe-Entität aktualisiert wurde.

1. Markieren Sie die vertikalen Auslassungspunkte neben der Vorhersage, deren Ergebnisse Sie überprüfen möchten, und wählen Sie **Ansicht**.
   > [!div class="mx-imgBorder"]
   > ![Anzeige der Optionen im Menü der vertikalen Auslassungspunkte für eine Vorhersage einschließlich Bearbeiten, Aktualisieren, Anzeigen, Protokolle und Löschen](media/product-recommendation-verticalellipses.PNG "Ansicht der Optionen im Menü der vertikalen Auslassungspunkte für eine Vorhersage einschließlich Bearbeiten, Aktualisieren, Anzeigen, Protokolle und Löschen").

1. Es gibt drei primäre Datenabschnitte innerhalb der Ergebnisseite:
    1. **Leistung des Trainingsmodells:** A, B oder C sind mögliche Bewertungen. Diese Bewertung zeigt die Leistung der Vorhersage an und kann Ihnen bei der Entscheidung helfen, die in der Ausgabe-Entität gespeicherten Ergebnisse zu verwenden.
        - Die Bewertungen werden nach den folgenden Regeln ermittelt:
            - **A** Das Modell wird berücksichtigt **A** Qualität, wenn die Metrik „Success @ K“ mindestens 10 % über der Basislinie liegt. 
            - **B** Das Modell wird berücksichtigt **B** Qualität, wenn die Metrik „Success @ K“ 0 bis 10 % über der Basislinie liegt.
            - **C** Das Modell wird berücksichtigt **C** Qualität, wenn die Metrik „Success @ K“ unter der Basislinie liegt.
               
               > [!div class="mx-imgBorder"]
               > ![Ansicht der Modellleistungsergebnisse](media/product-recommendation-modelperformance.PNG "Ansicht des Leistungsergebnisses des Modells")
            - **Basislinie**: Das Modell verwendet die am häufigsten empfohlenen Produkte nach Kaufanzahl für alle Kunden und verwendet erlernte Regeln, die vom Modell identifiziert wurden, um eine Reihe von Empfehlungen für die Kunden zu erstellen. Die Vorhersagen werden dann mit den Top-Produkten verglichen, berechnet anhand der Anzahl der Kunden, die das Produkt gekauft haben. Wenn ein Kunde mindestens ein Produkt in seinen empfohlenen Produkten hat, das auch in den am häufigsten gekauften Produkten enthalten ist, wird er als Teil der Baseline betrachtet. Wenn 10 dieser Kunden ein empfohlenes Produkt von insgesamt 100 Kunden gekauft hätten, wäre die Basis 10 %.
            - **Success @ K**: Mithilfe eines Validierungssatzes für den Zeitraum von Transaktionen werden Empfehlungen für alle Kunden erstellt und mit dem Validierungssatz für Transaktionen verglichen. Beispielsweise kann in einem Zeitraum von 12 Monaten der 12. Monat als Validierungsdatensatz reserviert werden. Wenn das Modell mindestens eine Sache vorhersagt, die Sie im 12. Monat kaufen würden, basierend auf den Erkenntnissen der letzten 11 Monate, würde der Kunde die Metrik „Success @ K“ erhöhen.
    
    1. **Am häufigsten vorgeschlagene Produkte (mit Tally):** Die Top 5 Produkte, die für Ihre Kunden vorhergesagt wurden.
       > [!div class="mx-imgBorder"]
       > ![Grafik mit den 5 am häufigsten empfohlenen Produkten](media/product-recommendation-topproducts.PNG "Grafik mit den 5 am häufigsten empfohlenen Produkten")
    
    1. **Produktempfehlungen mit hoher Konfidenz:** Eine Auswahl von Empfehlungen an Ihre Kunden, von denen das Modell glaubt, dass sie wahrscheinlich vom Kunden gekauft werden.
       > [!div class="mx-imgBorder"]
       > ![Liste mit Vorschlägen für hohes Vertrauen für eine ausgewählte Gruppe einzelner Kunden](media/product-recommendation-highconfidence.PNG "Liste mit Vorschlägen für hohes Vertrauen für eine ausgewählte Gruppe einzelner Kunden")

## <a name="fix-a-failed-prediction"></a>Korrigieren einer fehlgeschlagenen Vorhersage

1. Gehen Sie zur Registerkarte **Meine Vorhersagen** auf **Intelligenz** > **Vorhersagen**.

1. Markieren Sie die Vorhersage, für die Sie Fehlerprotokolle anzeigen möchten, und wählen Sie **Protokolle**.

1. Überprüfen Sie alle Fehler. Es gibt verschiedene Arten von Fehlern, die auftreten können, und sie beschreiben, welcher Zustand den Fehler verursacht hat. Beispielsweise wird ein Fehler, für den nicht genügend Daten zur genauen Vorhersage vorhanden sind, in der Regel dadurch behoben, dass zusätzliche Daten in Customer Insights geladen werden.

## <a name="refresh-a-prediction"></a>Aktualisieren einer Vorhersage

Vorhersagen werden automatisch nach der gleichen [Planung der Datenaktualisierungen](system.md#schedule-tab) aktualisiert, wie in den Einstellungen konfiguriert.

1. Gehen Sie zur Registerkarte **Meine Vorhersagen** auf **Intelligenz** > **Vorhersagen**.

1. Wählen Sie die vertikalen Auslassungspunkte neben der Vorhersage, die Sie aktualisieren möchten.

1. Wählen Sie **Aktualisieren** aus.

## <a name="delete-a-prediction"></a>Löschen einer Vorhersage

Das Löschen einer Vorhersage entfernt auch deren Ausgabe-Entität.

1. Gehen Sie zur Registerkarte **Meine Vorhersagen** auf **Intelligenz** > **Vorhersagen**.

1. Wählen Sie die vertikalen Auslassungspunkte neben der Vorhersage, die Sie löschen möchten.

1. Klicken Sie auf **Löschen**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]