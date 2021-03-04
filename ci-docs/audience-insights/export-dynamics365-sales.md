---
title: Customer Insights-Daten nach Dynamics 365 Sales exportieren
description: Erfahren Sie, wie Sie die Verbindung zu Dynamics 365 Sales konfigurieren.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269007"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Connector für Dynamics 365 Sales (Vorschau)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Verwenden Sie Ihre Kundendaten, um Marketinglisten zu erstellen, Workflows zu verfolgen und Werbeaktionen mit Dynamics 365 Sales zu senden.

## <a name="prerequisite"></a>Voraussetzung

1. Kontaktdatensätze müssen in Dynamics 365 Sales vorhanden sein, bevor Sie ein Segment von Customer Insights nach Sales exportieren können. Lesen Sie mehr darüber, wie Sie Kontakte in [Dynamics 365 Sales mit Common Data Services](connect-power-query.md) erfassen können.

   > [!NOTE]
   > Durch das Exportieren von Segmenten aus Zielgruppenerkenntnissen nach Sales werden keine neuen Kontaktdatensätze in den Sales-Instanzen erstellt. Die Kontaktdatensätze von Sales müssen in Zielgruppenerkenntnissen aufgenommen und als Datenquelle verwendet werden. Sie müssen auch in die einheitliche Kundenentität aufgenommen werden, um Kunden-IDs Kontakt-IDs zuzuordnen, bevor Segmente exportiert werden können.

## <a name="configure-the-connector-for-sales"></a>Konfigurieren Sie den Connector für Vertrieb

1. Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Ziele exportieren**.

1. Unter **Dynamics 365 Sales**, wählen Sie **Installieren**.

1. Geben Sie Ihrem Exportziel einen erkennbaren Namen im Feld **Anzeigename**.

1. Geben Sie die Vertriebs URL Ihrer Organisation im Feld **Server-Adresse** ein.

1. In dem Abschnitt **Serveradministratorkonto** wählen Sie **Anmeldung** und ein Dynamics 365 Sales Konto.

1. Ordnen Sie ein Kunden-ID-Feld der Dynamics 365 Kontakt-ID zu.

1. Klicken Sie auf **Weiter**.

1. Wählen Sie ein oder mehrere Segmente.

1. Wählen Sie **Speichern** aus.

## <a name="export-the-data"></a>Exportieren der Daten

Sie könenn [Daten nach Bedarf exportieren](export-destinations.md). Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.


[!INCLUDE[footer-include](../includes/footer-banner.md)]