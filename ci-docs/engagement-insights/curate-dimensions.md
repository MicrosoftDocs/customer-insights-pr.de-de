---
title: Verwenden Sie demografische Dimensionen zum Aufteilen von Verhaltensdaten (kuratierte Dimensionen)
description: Verwenden Sie einheitliche profilkuratierte Dimensionen, um Zielgruppenerkenntnisse-Kundenprofileigenschaften zu ermöglichen.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8a3d7f9276330a6daacbe9428d84a371b81bbefe
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466347"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Verwenden Sie demografische Dimensionen zum Aufteilen von Verhaltensdaten

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Durch die Verwendung einheitlicher demografischer Profildimensionen können Nutzer von Interaktionsinformationen auf die Profileigenschaften von Zielgruppenerkenntnissen zugreifen. Sie können diese Eigenschaften dann in interaktiven Analysen von Verhaltensdaten verwenden, einschließlich Daten, die durch Bindungserkenntnissen auf Ihrer Website oder mobilen App erfasst wurden.

>[!NOTE]
> Erkenntnisse zur Kundenbindung umfassen sofort einsatzbereite Dimensionen für Ereigniseigenschaften. Weitere Informationen: [Erstellen und Anzeigen von Dimensionen](dimensions.md)

## <a name="prerequisite"></a>Voraussetzung

- Eine Umgebung mit Bindungserkenntnissen, in der Kundenprofildaten mit der Umgebung mit Zielgruppenerkenntnissen verknüpft sind, in der die Kundenprofile erstellt werden. Weitere Informationen: [Erstellen Sie eine Verknüpfung zwischen Zielgruppenerkenntnissen und Kundenbindungserkenntnissen](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Nachdem Sie eine Verknüpfung zwischen den Umgebungen Zielgruppenerkenntnissen und Bindungserkenntnissen erstellt haben, möchten Sie möglicherweise nur Daten speziell für Kundenprofileigenschaften, die als Dimensionen in Bindungserkenntnissen nützlich sein können. Weitere Informationen unter [Aktivieren Sie vereinheitlichte Profilattribute und -segmente für Zielgruppenerkenntnisse](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>Einen neuen benutzerdefinierten Bericht erstellen

1. Wählen Sie im linken Bereich **Benutzerdefiniert** > **Neuer Bericht**, und wählen Sie dann die gewünschte Metrik aus. (Für dieses Beispiel haben wir **Seitenaufrufe nach Stunde** gewählt.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Metrik auswählen.":::

2. Wählen Sie im Visualisierungseditor **Dimensionen**, und wählen Sie dann **Demografisch** in dem **Dimensionstyp** Dropdown-Menü.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Demografisch wählen.":::

3. Wählen Sie eine **Signal.Kunde.*xxx*** Dimension. (Dieses Beispiel zeigt Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Dimension auswählen.":::
  
## <a name="limitations"></a>Einschränkungen

Zurzeit können Sie nur demografische Dimensionen zum Aufteilen von Verhaltensdaten verwenden.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
