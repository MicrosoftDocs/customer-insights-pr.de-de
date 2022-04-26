---
title: Ähnliche Kunden mit KI finden (enthält Video)
description: Finden Sie ähnliche Kundensegmente mit künstlicher Intelligenz.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 851ea2c3388de603c1beef4a58e359aa989c9c46
ms.sourcegitcommit: e129a1fa8b020b6bfb6efc3c53fa9d89e1614ad1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2022
ms.locfileid: "8561569"
---
# <a name="similar-customers-preview"></a>Ähnliche Kunden (Vorschau)

Mit dieser Funktion können Sie mithilfe künstlicher Intelligenz ähnliche Kunden in Ihrem Kundenstamm finden. Sie müssen mindestens ein Segment erstellt haben, um diese Funktion nutzen zu können. Durch Erweitern der Kriterien eines vorhandenen Segments können Sie Kunden finden, die diesem Segment ähnlich sind.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Finden Sie ähnliche Kunden* verwendet automatisierte Mittel, um Daten auszuwerten und Vorhersagen auf der Grundlage dieser Daten zu treffen, und kann daher als Methode zur Profilerstellung verwendet werden, wie dieser Begriff in der allgemeinen Datenschutzverordnung (DSGVO) definiert ist. Die Nutzung dieser Funktion durch den Kunden zur Datenverarbeitung kann der DSGVO oder anderen Gesetzen oder Vorschriften unterliegen. Sie sind dafür verantwortlich, dass Ihre Dynamics 365 Customer Insights-Nutzung, einschließlich der Vorhersagen, allen geltenden Gesetzen und Vorschriften entspricht, einschließlich Gesetzen in Bezug auf Privatsphäre, personenbezogene Daten, biometrische Daten, Datenschutz und Vertraulichkeit der Kommunikation.

## <a name="finding-similar-customers"></a>Ähnliche Kunden finden

1. Gehen Sie in Zielgruppen-Insights zu **Segmente** und wählen Sie das Segment, auf dem Ihr neues Segment basieren soll. Das ist Ihr *Quellensegment*.

1. Wählen Sie in der Aktionsleiste aus **Finden Sie ähnliche Kunden**.

1. Überprüfen Sie den vorgeschlagenen Namen für Ihr neues Segment und ändern Sie ihn gegebenenfalls.

1. Fügen Sie optional [Tags](work-with-tags-columns.md#manage-tags) zum neuen Segment hinzu.

1. Überprüfen Sie die Felder, die Ihr neues Segment definieren. Diese Felder definieren die Basis, auf der das System versucht, ähnliche Kunden wie Ihr Quellsegment zu finden. Das System wählt standardmäßig empfohlene Felder aus.
  Felder, die die Modellleistung erheblich reduzieren können, werden automatisch ausgeschlossen:
  
   - Felder mit den folgenden Datentypen: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Felder mit einer Kardinalität (Anzahl der Elemente in einem Feld) von weniger als 2 oder mehr als 30

1. Wählen Sie aus, ob Sie **Alle Kunden** einschließen möchten oder nur Kunden in einem **Spezifisch vorhandenen Segment** in Ihrem neuen Segment.

1. Standardmäßig schlägt das System vor, nur 20 % der Zielgruppe in Ihre Ausgabe aufzunehmen. Bearbeiten Sie diesen Schwellenwert nach Bedarf. Durch Erhöhen des Schwellenwerts wird die Genauigkeit verringert.

1. Beziehen Sie Kunden in Ihr Quellensegment ein, indem Sie das Kontrollkästchen **Mitglieder aus dem Quellsegment zusätzlich zu Kunden mit ähnlichen Attributen einbeziehen** auswählen.

1. Wählen Sie **Ausführen** am Ende der Seite, um eine binäre Klassifizierungsaufgabe (eine Methode von Maschinellem Lernen) zu starten, die das DataSet analysiert.

## <a name="view-the-similar-segment"></a>Sehen Sie sich das ähnliche Segment an

Nach der Verarbeitung des ähnlichen Segments finden Sie das neue Segment auf der Seite **Segmente**.

> [!div class="mx-imgBorder"]
> ![Ähnliche Kundensegmente.](media/expanded-segment.png "Ähnliche Kundensegmente")

Wählen Sie **Ansicht** in der Aktionsleiste, um das Segmentdetail zu öffnen. Diese Ansicht enthält Informationen zur Ergebnisverteilung über [Ähnlichkeitswerte](#about-similarity-scores). Die Ähnlichkeitswerte finden Sie auch in der **Vorschau der Segmentmitglieder**.

## <a name="use-the-output-of-a-similar-segment"></a>Verwenden Sie die Ausgabe eines ähnlichen Segments

Sie können [mit der Ausgabe eines ähnlichen Segments arbeiten](segments.md), wie Sie es mit anderen Segmenten tun. Exportieren Sie beispielsweise das Segment oder erstellen Sie eine Kennzahl.

## <a name="refresh-and-edit-a-similar-segment"></a>Aktualisieren und bearbeiten Sie ein ähnliches Segment

Um ein ähnliches Segment zu aktualisieren, wählen Sie es auf der Seite **Segmente** aus und wählen Sie **Aktualisierung** in der Aktionsleiste.

Durch Bearbeiten eines ähnlichen Segments werden Ihre Daten erneut verarbeitet. Das zuvor erstellte Segment wird mit aktualisierten Daten aktualisiert.
Um ein ähnliches Segment zu bearbeiten, wählen Sie es auf der Seite **Segmente** aus und wählen Sie **Bearbeitung** in der Aktionsleiste. Übernehmen Sie Ihre Änderungen und wählen Sie **Ausführen**, um die Verarbeitung zu starten.

## <a name="delete-a-similar-segment"></a>Löschen Sie ein ähnliches Segment

Wählen Sie das Segment auf der Seite **Segmente** aus und wählen Sie **Löschen** in der Aktionsleiste. Bestätigen Sie dann den Löschvorgang.

## <a name="about-similarity-scores"></a>Über die Ähnlichkeitsbewertung

Das Modell der binären Klassifizierung Maschinelles Lernen weist Kunden im ähnlichen Segment eine Bewertung zu. Die Bewertung basiert auf der Ähnlichkeit mit Kunden im Quellensegment.

- Ähnlichkeitswerte unter 0,55 sind Kunden, die das System klassifiziert als *nicht ähnlich* an Kunden im Quellensegment
- Ähnlichkeitswerte zwischen 0,55 und 0,7 werden klassifiziert als *etwas ähnlich*
- Ähnlichkeitswerte zwischen 0,7 und 0,85 werden klassifiziert als *ähnlich*
- Ähnlichkeitswerte zwischen 0,85 – 1 sind Kunden, die das System klassifiziert als *sehr ähnlich*

Kunden mit Ähnlichkeitswerten unter 0,4 werden nicht in die Modellausgabe einbezogen. Das System betrachtet sie nicht als ähnlich genug für das Quellensegment.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
