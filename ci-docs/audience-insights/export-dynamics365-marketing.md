---
title: Customer Insights-Daten nach Dynamics 365 Marketing exportieren
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu Dynamics 365 Marketing exportieren.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bd8189f8daee1a6aea75e75e116186f62a360ba4
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692480"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Segmente in Dynamics 365 Marketing verwenden (Vorschau)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Verwenden Sie [Segmente](segments.md), um mit Dynamics 365 Marketing Kampagnen zu erstellen und bestimmte Kundengruppen zu kontaktieren. Weitere Informationen finden Sie unter [Segmente ab Dynamics 365 Customer Insights mit Dynamics 365 Marketing verwenden](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite-for-a-connection"></a>Voraussetzungen für die Verbindung

- Kontaktdatensätze müssen in Dynamics 365 Marketing vorhanden sein, bevor Sie ein Segment von Customer Insights nach Marketing exportieren können. Lesen Sie mehr darüber, wie Sie Kontakte in [Dynamics 365 Marketing mit Microsoft Dataverse](connect-power-query.md) erfassen können.

  > [!NOTE]
  > Durch das Exportieren von Segmenten aus Zielgruppenerkenntnissen nach Marketing werden keine neuen Kontaktdatensätze in den Marketinginstanzen erstellt. Die Kontaktdatensätze von Marketing müssen in Zielgruppenerkenntnissen aufgenommen und als Datenquelle verwendet werden. Sie müssen auch in die einheitliche Kundenentität aufgenommen werden, um Kunden-IDs Kontakt-IDs zuzuordnen, bevor Segmente exportiert werden können.

## <a name="set-up-connection-to-marketing"></a>Richten Sie die Verbindung mit Marketing ein

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und dann **Dynamics 365 Marketing** aus, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie die Marketing URL Ihrer Organisation im Feld **Server-Adresse** ein.

1. In dem Abschnitt **Serveradministratorkonto** wählen Sie **Anmeldung** und ein Dynamics 365 Marketing-Konto.

1. Ordnen Sie ein Kunden-ID-Feld der Dynamics 365 Kontakt-ID zu.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus. 

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Dynamics 365 Marketing-Abschnitt aus. Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

1. Wählen Sie ein oder mehrere Segmente.

1. Wählen Sie **Speichern** aus.

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt. Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
