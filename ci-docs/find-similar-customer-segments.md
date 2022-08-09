---
title: Ähnliche Kunden mit KI finden (Vorschauversion) (enthält Video)
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
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170726"
---
# <a name="find-similar-customers-with-ai-preview"></a>Ähnliche Kunden mit KI finden (Vorschauversion)

Finden Sie mithilfe künstlicher Intelligenz ähnliche Kunden in Ihrem Kundenstamm. Sie müssen mindestens ein Segment erstellt haben, um diese Funktion nutzen zu können. Durch Erweitern der Kriterien eines vorhandenen Segments können Sie Kunden finden, die diesem Segment ähnlich sind.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Finden Sie ähnliche Kunden* verwendet automatisierte Mittel, um Daten auszuwerten und auf der Grundlage dieser Daten Vorhersagen zu treffen. Daher kann es als Methode zur Profilerstellung verwendet werden, wie dieser Begriff in der allgemeinen Datenschutzverordnung („DSGVO“) definiert ist. Die Nutzung dieser Funktion durch den Kunden zur Datenverarbeitung kann der DSGVO oder anderen Gesetzen oder Vorschriften unterliegen. Sie sind dafür verantwortlich, dass Ihre Dynamics 365 Customer Insights-Nutzung, einschließlich der Vorhersagen, allen geltenden Gesetzen und Vorschriften entspricht, einschließlich Gesetzen in Bezug auf Privatsphäre, personenbezogene Daten, biometrische Daten, Datenschutz und Vertraulichkeit der Kommunikation.

## <a name="find-similar-customers"></a>Ähnliche Kunden finden

1. Gehen Sie zu **Segmente** und wählen Sie das Segment aus, auf das Sie Ihr neues Segment stützen möchten. Das ist Ihr *Quellensegment*.

1. **Ähnliche Kunden finden** auswählen

1. Überprüfen Sie den vorgeschlagenen Namen für Ihr neues Segment und ändern Sie ihn gegebenenfalls.

1. Fügen Sie optional [Tags](work-with-tags-columns.md#manage-tags) zum neuen Segment hinzu.

1. Überprüfen Sie die Felder, die Ihr neues Segment definieren. Diese Felder definieren die Basis, auf der das System versucht, ähnliche Kunden wie Ihr Quellsegment zu finden. Das System wählt standardmäßig empfohlene Felder aus. Fügen Sie bei Bedarf weitere Felder hinzu.
  Felder, die die Modellleistung erheblich reduzieren können, werden automatisch ausgeschlossen:
  
   - Felder mit den folgenden Datentypen: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Felder mit einer Kardinalität (Anzahl der Elemente in einem Feld) von weniger als 2 oder mehr als 30

1. Wählen Sie aus, ob Sie **Alle Kunden** einschließen möchten ausschließlich der Quellsegmente oder nur Kunden in einem **Anderes Segment** in Ihrem neuen Segment.

1. Standardmäßig schlägt das System vor, nur 20 % der Zielgruppe in Ihre Ausgabe aufzunehmen. Bearbeiten Sie diesen Schwellenwert nach Bedarf. Durch Erhöhen des Schwellenwerts wird die Genauigkeit verringert.

1. Beziehen Sie Kunden in Ihr Quellensegment ein, indem Sie das Kontrollkästchen **Mitglieder aus dem Quellsegment zusätzlich zu Kunden mit ähnlichen Attributen einbeziehen** auswählen.

1. Wählen Sie **Ausführen** am Ende der Seite, um eine [binäre Klassifizierungsaufgabe](#about-similarity-scores) (eine Methode von Maschinellem Lernen) zu starten, die das Datenset analysiert.

## <a name="view-the-similar-segment"></a>Sehen Sie sich das ähnliche Segment an

Nach der Verarbeitung des ähnlichen Segments finden Sie das neue Segment auf der Seite **Segmente** mit dem Typ **Erweiterung**.

Wählen Sie **Ansicht** aus. um die Ergebnisverteilung über [Ähnlichkeitsbewertung](#about-similarity-scores) und Ähnlichkeitswert unter **Vorschau der Segmentmitglieder** anzuzeigen.

:::image type="content" source="media/expanded-segment.png" alt-text="Ähnliche Kundensegmente.":::

## <a name="manage-a-similar-segment"></a>Ein ähnliches Segment verwalten

[Mit der Ausgabe eines ähnlichen Segments arbeiten und dieses verwalten](segments.md#manage-existing-segments), wie Sie es mit anderen Segmenten tun. Exportieren Sie beispielsweise das Segment oder erstellen Sie eine Kennzahl.

Bearbeiten, aktualisieren, umbenennen, herunterladen und löschen eines ähnlichen Segments. Durch Bearbeiten eines ähnlichen Segments werden Ihre Daten erneut verarbeitet. Das zuvor erstellte Segment wird mit aktualisierten Daten aktualisiert.

## <a name="about-similarity-scores"></a>Über die Ähnlichkeitsbewertung

Das Modell der binären Klassifizierung Maschinelles Lernen weist Kunden im ähnlichen Segment eine Bewertung zu. Die Bewertung basiert auf der Ähnlichkeit mit Kunden im Quellensegment.

- Ähnlichkeitswerte unter 0,55 sind Kunden, die das System klassifiziert als *nicht ähnlich* an Kunden im Quellensegment
- Ähnlichkeitswerte zwischen 0,55 und 0,7 werden klassifiziert als *etwas ähnlich*
- Ähnlichkeitswerte zwischen 0,7 und 0,85 werden klassifiziert als *ähnlich*
- Ähnlichkeitswerte zwischen 0,85 – 1 sind Kunden, die das System klassifiziert als *sehr ähnlich*

Kunden mit Ähnlichkeitswerten unter 0,4 werden nicht in die Modellausgabe einbezogen. Das System betrachtet sie nicht als ähnlich genug für das Quellensegment.

[!INCLUDE [footer-include](includes/footer-banner.md)]
