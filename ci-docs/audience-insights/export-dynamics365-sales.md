---
title: Customer Insights-Daten nach Dynamics 365 Sales exportieren
description: Erfahren Sie, wie Sie die Verbindung zu Dynamics 365 Sales konfigurieren.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643817"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Connector für Dynamics 365 Sales (Vorschau)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Verwenden Sie Ihre Kundendaten, um Marketinglisten zu erstellen, Workflows zu verfolgen und Werbeaktionen mit Dynamics 365 Sales zu senden.

## <a name="prerequisite"></a>Voraussetzung

Kontaktdatensätze [aus Dynamics 365 Sales übernommen mit Common Data Service](connect-power-query.md).

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
