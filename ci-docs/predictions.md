---
title: Vervollständigen Sie Teildaten mithilfe von Vorhersagen
description: Verwenden Sie Vorhersagen, um unvollständige Kundendaten aufzufüllen.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-predictions
- ci-custom-models
- customerInsights
ms.openlocfilehash: e2cace3547a0b584dbf26ae5eecf86f3b256649f
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740718"
---
# <a name="complete-your-partial-data-with-predictions-deprecated"></a>Teildaten mit Vorhersagen ergänzen (eingestellt)

> [!IMPORTANT]
> Diese Funktion gilt als **veraltet** ab dem **5. November 2021**. Aktuelle Implementierungen funktionieren weiterhin, bis die Funktion entfernt wird, Sie können jedoch keine neuen Integrationen mithilfe der folgenden Anweisungen erstellen.

Mit Vorhersagen können Sie auf einfache Weise Werte vorhersagen, die Ihr Verständnis für einen Kunden verbessern können. Auf der Seite **Intelligenz** > **Vorhersagen** können Sie **Meine Vorhersagen** auswälen, um Vorhersagen anzuzeigen, die Sie in anderen Teilen von Customer Insights konfiguriert haben, und um sie weiter anzupassen.

> [!NOTE]
> Sie können diese Funktion nicht verwenden, wenn Ihre Umgebung Azure Data Lake Gen 2-Speicher verwendet.
>
> Die Vorhersagenfunktion verwendet automatisierte Mittel zur Auswertung von Daten und zur Erstellung von Vorhersagen auf der Grundlage dieser Daten und kann daher als Methode zur Erstellung von Profilen verwendet werden, da dieser Begriff in der Datenschutz-Grundverordnung („DSGVO“) definiert ist. Die Nutzung dieser Funktion durch den Kunden zur Datenverarbeitung kann der DSGVO oder anderen Gesetzen oder Vorschriften unterliegen. Sie sind dafür verantwortlich, dass Ihre Dynamics 365 Customer Insights-Nutzung, einschließlich der Vorhersagen, allen geltenden Gesetzen und Vorschriften entspricht, einschließlich Gesetzen in Bezug auf Privatsphäre, personenbezogene Daten, biometrische Daten, Datenschutz und Vertraulichkeit der Kommunikation.

## <a name="prerequisites"></a>Voraussetzungen

Bevor Ihre Organisation die Vorhersagefunktion verwenden kann, müssen die folgenden Voraussetzungen erfüllt sein:

1. Ihre Organisation hat eine Instanz [in Microsoft Dataverse eingerichtet](/ai-builder/build-model#prerequisites) und sie befindet sich in derselben Organisation wie Customer Insights.

2. Ihre Customer Insights-Umgebung wird an Ihre Dataverse-Instanz angehängt.

Weitere Informationen finden Sie unter [Eine neue Umgebung erstellen](create-environment.md).

## <a name="create-a-prediction-in-the-customer-entity"></a>Erstellen Sie eine Vorhersage in der Kunde-Entität

1. Gehen Sie zu **Daten** > **Entitäten**.

2. Wählen Sie die Entität **Kunde** aus.

3. Im Bereich **Kunde: CustomerInsights**-Entität, wählen Sie auf dem Register **Felder**.

4. Suchen Sie den Attributnamen, für den Sie Werte vorhersagen möchten, und wählen Sie dann das Symbol **Übersicht** in der Spalte **Zusammenfassung**.
   > [!div class="mx-imgBorder"]
   > ![Übersichtssymbol.](media/intelligence-overviewicon.png "Übersicht über das Symbol")

5. Wenn es eine hohe Rate fehlender Werte für Ihr Attribut gibt, wählen Sie **Fehlende Werte vorhersagen** aus, um mit Ihrer Vorhersage fortzufahren.
   > [!div class="mx-imgBorder"]
   > ![Übersichtsstatus mit angezeigter Schaltfläche zur Vorhersage fehlender Werte.](media/intelligence-overviewpredictmissingvalues.png "Überblicksstatus mit angezeigter Schaltfläche zur Vorhersage fehlender Werte")

6. Stellen Sie einen **Anzeigename** und einen **Name der Ausgabeentität** für die Ergebnisse der Vorhersage bereit.

7. Eine vorbelegte Liste von Optionen zeigt an, wo Sie die Werte einer vorhergesagten Kategorie zuordnen können. In diesem Fall sind Ihre einzigen Kategorie-Optionen 0 oder 1, da sie der Wahr/Falsch- oder Binär-Natur der Vorhersage entsprechen. Ordnen Sie in der Kategorie-Spalte die Feldwerte, die in der endgültigen Vorhersage als 0 klassifiziert werden sollen, als 0 und die Elemente, die Sie in der endgültigen Vorhersage als 1 klassifizieren möchten, als 1 zu.
   > [!div class="mx-imgBorder"]
   > ![Beispiel mit zugeordneten Feldwerten zu Kategorien.](media/intelligence-categorymapping.png "Beispiel für die Zuordnung von Feldwerten zu Kategorien")

8. Wählen Sie **Abgeschlossen**, und die Vorhersage wird verarbeitet. Die Bearbeitung wird je nach Umfang und Komplexität der Daten einige Zeit in Anspruch nehmen. Die Ergebnisse werden in einer neuen Entität basierend auf dem **Name der Ausgabeentität** der Vorhersage bereitgestellt, die Sie erstellt haben.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="create-a-prediction-while-creating-a-segment"></a>Erstellen einer Vorhersage beim Erstellen eines Segments

Die Vorhersage fehlender Werte für ein bestimmtes Attribut der Wahl ist auch bei der Erstellung eines Segments möglich. Insbesondere, wenn Sie schnell ein Segment erstellen, das entweder auf Ihrer vereinheitlichten Kunden-Entität oder Ihrer Customer_Measure-Entität basiert.

Als Teil dieses Ablaufs wählen Sie ein bestimmtes Attribut aus, auf dem Ihr Segment basiert, z. B. Kundenzufriedenheit oder Kaufbetrag. Bei der Segmenterstellung schlägt das System eine Methode zur Vorhersage fehlender Werte für dieses Attribut vor.

1. Gehen Sie zu **Segmente** und wählen Sie die Kachel **Profile**.

2. Wählen Sie ein **Feld**, um ein Segment zu erstellen, und wählen Sie ein **Bediener**, dann wählen Sie **Überprüfen**.

3. Geben Sie einen **Name** und einen **Anzeigename** für das Segment an.

4. Wählen Sie **Speichern** aus.

5. Wenn das von Ihnen erstellte Segment unvollständige Daten im Quellfeld enthält, können Sie die fehlenden Werte vorhersagen.
   > [!div class="mx-imgBorder"]
   > ![Schaltfläche „Vorhersage“.](media/segments-predictoption.png "Schaltfläche Vorhersage")

6. Stellen Sie einen **Anzeigename** und einen **Name der Ausgabeentität** für die Ergebnisse der Vorhersage bereit.

7. **Fertig** auswählen Ihre Vorhersage wird in Kürze in einer neuen Entität mit dem Namen generiert, den Sie für den **Namen der Ausgabeentität** angegeben haben.

## <a name="view-a-prediction"></a>Eine Vorhersage anzeigen

1. Gehen Sie zu **Intelligenz** > **Vorhersagen** > **Meine Vorhersagen**.

2. Wählen Sie die Vorhersage aus, die Sie überprüfen möchten.

3. Markieren Sie die Auslassungspunkte in der Spalte **Aktionen** und wählen Sie **Ansicht**.

4. Sie sehen eine Reihe von Datenpunkten in der Ansicht Ihrer Vorhersage.
   > [!div class="mx-imgBorder"]
   > ![Seite „Vorhersagen“.](media/intelligence-predictionsviewpage.png "Seite Vorhersagen")

   - **Vorhergesagte Werte** zeigt die Zuordnung, die Sie während der Zuordnungsphase von Feldwert zu Kategorie erstellt haben. Dies sind die Werte in Ihrem DataSet, die einer bestimmten Kategorie zugeordnet wurden.
   -**Top-Einflussfaktoren** sind die Faktoren innerhalb Ihres Datensatzes, die am ehesten die Zuverlässigkeit der Vorhersage bezüglich der Zuordnung Ihres Feldwertes zu einer bestimmten Kategorie beeinflussen.
   - **Leistung** zeigt an, wie sich die Vorhersagen entwickeln. Wählen Sie den Link, um mehr zu erfahren.
   - **Vorschau** zeigt Beispiele des Ausgabedatensatzes Ihrer Vorhersage und die Wahrscheinlichkeit oder unser Vertrauen in den vorhergesagten Wert, wobei 0 unsicher und 1 sicher ist.

## <a name="update-a-prediction"></a>Aktualisieren einer Vorhersage

1. Gehen Sie zu **Intelligenz** > **Vorhersagen** > **Meine Vorhersagen**.

2. Wählen Sie die Vorhersage, die Sie aktualisieren möchten, und wählen Sie das Symbol **Aktualisierung**.

3. Die Vorhersage wird für die Verarbeitung geplant. Sie können den Zeitpunkt der letzten Aktualisierung in der Spalte **Aktualisiert** auf der Seite **Vorhersagen** sehen.

## <a name="edit-a-prediction"></a>Bearbeiten einer Vorhersage

Nachdem Sie ein Vorhersage erstellt haben, können Sie das Modell in AI Builder anpassen, um die Effektivität Ihres Modells zu steigern.  

1. Gehen Sie zu **Intelligenz** > **Vorhersagen** > **Meine Vorhersagen**.

2. Wählen Sie die Vorhersage aus, die Sie bearbeiten möchten.

3. Markieren Sie die Auslassungspunkte in der Spalte **Aktionen** und wählen Sie **Ansicht**.

4. Klicken Sie auf **In AI Builder anpassen**.

5. Aktualisieren Sie Ihr Modell im AI Builder. [Lernen Sie mehr über die Verwaltung von Modellen im AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).

Der nächste Lauf Ihrer Vorhersage wird das von Ihnen erstellte aktualisierte Modell verwenden.

> [!NOTE]
> Neue Modelle, die unter AI Builder erstellt werden, werden in Customer Insights nicht angezeigt, es sei denn, das Modell wurde aus den oben aufgeführten Erfahrungen erstellt.

## <a name="remove-a-prediction"></a>Eine Vorhersage entfernen

1. Gehen Sie zu **Intelligenz** > **Vorhersagen** > **Meine Vorhersagen**.

2. Wählen Sie die Vorhersage aus, die Sie löschen möchten.

3. Markieren Sie die Auslassungspunkte in der Spalte **Aktionen** und wählen Sie **Löschen**.

4. Bestätigen Sie den Löschvorgang.

## <a name="troubleshooting"></a>Problembehandlung

Wenn Sie den Dataverse-Anfügevorgang aufgrund eines Fehlers nicht abschließen können, können Sie versuchen, den Vorgang manuell abzuschließen. Es gibt zwei bekannte Probleme, die beim Anfügevorgang auftreten können:

- Die Lösung Customer Card Add-in ist nicht installiert.
    1. Vervollständigen Sie die Anweisungen in Bezug auf [Installieren und Konfigurieren der Lösung](customer-card-add-in.md).

- App-Berechtigungen werden nicht gewährt.
    1. Wechseln Sie zu [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. **Umgebungen** auswählen.
    1. Wählen Sie die Auslassungspunkte neben der Umgebung aus, zu der Sie die Berechtigung hinzufügen möchten, und wählen Sie **Einstellungen** aus.
    1. Erweitern Sie **Benutzer + Berechtigungen** und wählen Sie **Benutzer** aus.
    1. Wählen Sie **+ Neu** und **Benutzer** aus.
    1. Wenn es noch nicht ausgewählt ist, wählen Sie **Anwendungsbenutzer** aus, und geben Sie die folgenden Informationen ein:
        - **Benutzername:** cihelp@microsoft.com
        - **Anwendungs-ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Vorname:** Kunde
        - **Nachname:** Insights
        - **Primäre E-Mail-Adresse:** cihelp@microsoft.com
    1. Klicken Sie auf **Speichern und Schließen**.
    1. Wählen Sie den gerade erstellten Benutzer aus.
    1. Wählen Sie in der oberen Menüleiste **Rollen verwalten** aus.
    1. Wählen Sie **Systemadministrator** und dann **OK** aus.


[!INCLUDE [footer-include](includes/footer-banner.md)]