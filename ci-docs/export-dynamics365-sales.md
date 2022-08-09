---
title: Segmente zu Dynamics 365 Sales exportieren (Vorschauversion)
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu Dynamics 365 Sales exportieren.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195980"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Segmente zu Dynamics 365 Sales exportieren (Vorschauversion)

Verwenden Sie Ihre Kundendaten, um Marketinglisten zu erstellen, Workflows zu verfolgen und Werbeaktionen mit Dynamics 365 Sales zu senden.

## <a name="prerequisites"></a>Anforderungen

Kontaktdatensätze müssen in Dynamics 365 Sales vorhanden sein, bevor Sie ein Segment von Customer Insights nach Sales exportieren können. Lesen Sie mehr darüber, wie Sie Kontakte von [Dynamics 365 Sales mithilfe von Microsoft Dataverse](connect-dataverse-managed-lake.md) erfassen können.

   > [!NOTE]
   > Durch den Export von Segmenten aus Customer Insights in den Vertrieb werden keine neuen Datensätze in den Vertriebsinstanzen erstellt. Die Kontaktdatensätze aus dem Vertrieb müssen in Customer Insights eingebunden und als Datenquelle verwendet werden. Sie müssen auch in die einheitliche Kundenentität aufgenommen werden, um Kunden-IDs Kontakt-IDs zuzuordnen, bevor Segmente exportiert werden können.

## <a name="known-limitations"></a>Bekannte Einschränkungen

Exporte nach Dynamics 365 Sales sind auf 100.000 pro Segment limitiert, dies kann bis zu 3 Stunden dauern.

## <a name="set-up-connection-to-sales"></a>Verbindung mit Sales einrichten

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Dynamics 365 Sales**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie die Vertriebs URL Ihrer Organisation im Feld **Server-Adresse** ein.

1. In dem Abschnitt **Serveradministratorkonto** wählen Sie **Anmeldung** und ein Dynamics 365 Sales Konto.

1. Ordnen Sie ein Kunden-ID-Feld der Dynamics 365 Kontakt-ID zu.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Dynamics 365 Sales-Abschnitt aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. Wählen Sie das Feld „Kontakt-ID“ in der Entität „Kunde“, das zur Dynamics 365-Kontakt-ID gehört.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten.

1. Wählen Sie **Speichern** aus

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
