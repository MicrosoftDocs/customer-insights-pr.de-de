---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611101"
---
- **Leistung des Trainingsmodells**: Die Stufen A, B oder C geben die Leistung der Vorhersage an und können Ihnen bei der Entscheidung helfen, die in der Ausgabeentität gespeicherten Ergebnisse zu verwenden.

  Die Stufen werden nach den folgenden Regeln ermittelt:
  - **A**, wenn das Modell mindestens 50 % der gesamten Vorhersagen richtig vorhergesagt hat und wenn der Prozentsatz der richtigen Vorhersagen für Kunden, die abgewandert sind, um mindestens 10 % größer ist als die Basisrate.
  - **B**, wenn das Modell mindestens 50 % der gesamten Vorhersagen richtig vorhergesagt hat und wenn der Prozentsatz der richtigen Vorhersagen für Kunden, die abgewandert sind, bis zu 10 % höher ist als die Basislinie.
  - **C**, wenn das Modell weniger als 50 % der gesamten Vorhersagen richtig vorhergesagt hat, oder wenn der Prozentsatz der richtigen Vorhersagen für Kunden, die abgewandert sind, kleiner ist als die Baseline.
  - Die **Basislinie** nimmt das für das Modell eingegebene Vorhersagezeitfenster (z. B. ein Jahr) und erstellt verschiedene Zeitbruchteile, indem es durch 2 geteilt wird, bis es einen Monat oder weniger erreicht. Es verwendet diese Anteile, um eine Geschäftsregel für Kunden zu erstellen, die in diesem Zeitrahmen nicht gekauft haben. Diese Kunden werden als abgewandert betrachtet. Die zeitbasierte Geschäftsregel mit der höchsten Fähigkeit zur Vorhersage der Abwanderungswahrscheinlichkeit wird als Baselinemodell gewählt.

- **Wahrscheinlichkeit der Abwanderung (Anzahl der Kunden)**: Kundengruppen auf der Grundlage ihres vorhergesagten Abwanderungsrisikos. Optional können Sie [Kundensegmente erstellen](../prediction-based-segment.md), bei denen ein hohes Abwanderungsrisiko besteht. Solche Segmente helfen Ihnen zu verstehen, wo Ihr Grenzwert für die Segmentmitgliedschaft liegen sollte.

- **Die wichtigsten Einflussfaktoren**: Es gibt viele Faktoren, die bei der Erstellung Ihrer Vorhersage berücksichtigt werden. Für jeden der Faktoren wird seine Wichtigkeit für die aggregierten Vorhersagen, die ein Modell erstellt, berechnet. Verwenden Sie diese Faktoren, um Ihre Vorhersageergebnisse zu validieren. Oder verwenden Sie diese Informationen später, um [Segmente](../prediction-based-segment.md) zu erstellen, die dazu beitragen könnten, das Abwanderungsrisiko für Kunden zu beeinflussen.