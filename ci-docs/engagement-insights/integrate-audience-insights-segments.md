---
title: Verwenden Sie Zielgruppenerkenntnis-Segmente um Bindungserkenntnisse in Berichten zu filtern
description: Verwenden Sie Zielgruppenerkenntnis-Segmente in interaktiven Analysen von Verhaltensdaten, die durch Bindungserkenntnisse auf der Website eines Kunden erfasst wurden.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bdd5641bb17384725491f22f70ae967ad90b1696
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461057"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Verwenden Sie Zielgruppenerkenntnis-Segmente um Bindungserkenntnisse in Berichten zu filtern

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Mit Bindungserkenntnissen können Sie Zielgruppenerkenntnis-Segmente in interaktiven Analysen von Verhaltensdaten verwenden, die durch Bindungserkenntnisse auf Ihrer Website erfasst wurden.

## <a name="prerequisite"></a>Voraussetzung

- Eine Umgebung mit Bindungserkenntnissen, in der Sie Zielgruppenerkenntnis-Segmente haben, die mit der Umgebung von Zielgruppenerkenntnissen verknüpft sind, in der die Segmente und Kundenprofile erstellt werden. Weitere Informationen: [Erstellen Sie eine Verknüpfung zwischen Zielgruppenerkenntnissen und Kundenbindungserkenntnissen](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Zielgruppenerkenntnisse erstellen 

> [!IMPORTANT]
> Damit Zielgruppenerkenntnis-Segmente in den Bindungserkenntnissen angezeigt werden, müssen Sie zuerst [Merge -und Downstream-Prozesse ausführen](../audience-insights/merge-entities.md). Nachgelagerte Prozesse sind wichtig, weil sie eine einzigartige Tabelle generieren, die Zielgruppenerkenntnis-Segmente für die gemeinsame Nutzung mit Bindungserkenntnissen vorbereitet. (Wenn eine Systemaktualisierung geplant ist, umfasst sie automatisch nachgelagerte Prozesse.)

Sie können Zielgruppenerkenntnis-Segmente in vorkonfigurierten Bindungserkenntnis-Berichten oder benutzerdefinierten Berichten verwenden, die von Ihnen erstellt wurden. Weitere Informationen finden Sie unter [Vorkonfigurierte Profilberichte](profile-reports.md) und [Benutzerdefinierte Berichte erstellen und bearbeiten](custom-reports.md).

**Verwendung von Zielgruppenerkenntnis-Segmenten in Berichten zu Bindungserkenntnissen**

1. Wählen Sie auf der Seite **Arbeitsplatz** **Daten**, und wählen Sie dann die Registerkarte **Segmente**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Auswahl der Registerkarte Segmente.":::

   >[!NOTE]
   > Wenn Sie ein Zielgruppenerkenntnis-Segment auswählen, gelangen Sie zu Zielgruppenerkenntnis, wo Sie herausfinden können, wie dieses Segment in Bezug auf Regeln und Logik erstellt wurde. Weitere Informationen über Zielgruppenerkenntnis-Segmente finden Sie unter [Segmente anzeigen und erstellen](../audience-insights/segments.md).

2. Wählen Sie einen vorkonfigurierten Bericht oder [erstellen Sie einen benutzerdefinierten Bericht](custom-reports.md), und wählen Sie dann **Bedingung hinzufügen**. (Für dieses Beispiel haben wir den **Bericht Seitenansicht** gewählt.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Eine Bedingung hinzufügen.":::

3. **Nach Segment filtern** auswählen und die Liste **Segmenttyp** erweitern, und wählen Sie dann **Demografisch**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Wählen Sie den Segmenttyp Demografisch aus.":::

4. Erweitere die Liste **Segmentname** und wählen Sie dann ein Zielgruppenerkenntnis-Segment aus.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Segment auswählen.":::

5. Sie können ein oder mehrere Segmente anwenden, darunter verhaltensbezogene (Bindungserkenntni) und demografische (Zielgruppenerkenntnis) Segmente. 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Der Bericht zu Seitenaufrufen ist auf die US-Kunden und die Startseitensegmente beschränkt.":::

Im vorherigen Bild sind die Segmente **USA-Kunden** und **Startseite** ausgewählt, was den Bericht **Seitenansicht** einschränkt; es werden nur diese zwei Segmente angezeigt. 


>[!NOTE]
> Sie können Zielgruppenerkenntnis-Segmente verwenden um vorkonfigurierte Berichte, benutzerdefinierte und Trichter in Bindungserkenntnissen zu filtern. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]