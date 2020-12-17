---
title: Customer Insights-Daten nach Dynamics 365 Marketing exportieren
description: Erfahren Sie, wie Sie die Verbindung zu Dynamics 365 Marketing konfigurieren.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643772"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Connector für Dynamics 365 Marketing (Vorschau)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Verwenden Sie [Segmente](segments.md), um mit Dynamics 365 Marketing Kampagnen zu erstellen und bestimmte Kundengruppen zu kontaktieren. Weitere Informationen finden Sie unter [Segmente ab Dynamics 365 Customer Insights mit Dynamics 365 Marketing verwenden](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Voraussetzung

Kontaktdatensätze [aus Dynamics 365 Marketing übernommen mit Common Data Service](connect-power-query.md).

## <a name="configure-the-connector-for-marketing"></a>Konfigurieren Sie den Connector für Marketing

1. Gehen Sie in den Zielgruppen-Insights zu **Admin** > **Ziele exportieren**.

1. Unter **Dynamics 365 Marketing**, wählen Sie **Installieren**.

1. Geben Sie Ihrem Exportziel einen erkennbaren Namen im Feld **Anzeigename**.

1. Geben Sie die Marketing URL Ihrer Organisation im Feld **Server-Adresse** ein.

1. In dem Abschnitt **Serveradministratorkonto** wählen Sie **Anmeldung** und ein Dynamics 365 Marketing-Konto.

1. Ordnen Sie ein Kunden-ID-Feld der Dynamics 365 Kontakt-ID zu.

1. Klicken Sie auf **Weiter**.

1. Wählen Sie ein oder mehrere Segmente.

1. Wählen Sie **Speichern** aus.

## <a name="export-the-data"></a>Exportieren der Daten

Sie könenn [Daten nach Bedarf exportieren](export-destinations.md). Der Export wird auch bei jeder [geplanten Aktualisierung](system.md#schedule-tab) durchgeführt.
