---
title: Segmente zu Dynamics 365 Marketing exportieren (Vorschauversion)
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu Dynamics 365 Marketing exportieren.
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
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196623"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Segmente zu Dynamics 365 Marketing exportieren (Vorschauversion)

Verwenden Sie [Segmente](segments.md), um mit [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments) Kampagnen zu erstellen und bestimmte Kundengruppen zu kontaktieren.

Wenn Sie die neuen Funktionen von Dynamics 365 Marketing für die Echtzeit-Orchestrierung des Kundenkontaktverlauf in einer Dataverse Org. nutzen, müssen Sie keinen Standardexport nach Dynamics 365 Marketing erstellen. Kontakte und Segmente aus Customer Insights sind direkt in Dynamics 365 Marketing verfügbar, nachdem Sie Marketing und Customer Insights miteinander verbunden haben. Bevor Sie bestehende Exporte löschen, lesen Sie die Dokumentation zur [Verbindung von Customer Insights und Dynamics 365 Marketing mit Customer Journey Orchestration](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Voraussetzung

Kontaktdatensätze müssen in Dynamics 365 Marketing vorhanden sein, bevor Sie ein Segment von Customer Insights nach Marketing exportieren können. Lesen Sie mehr darüber, wie Sie Kontakte in [Dynamics 365 Marketing mit Microsoft Dataverse](connect-dataverse-managed-lake.md) erfassen können.

> [!NOTE]
> Durch den Export von Segmenten aus Customer Insights nach Marketing werden keine neuen Datensätze in den Marketing-Instanzen erstellt. Die Datensätze aus Marketing müssen in Customer Insights eingebunden und als Datenquelle verwendet werden. Sie müssen auch in die einheitliche Kundenentität aufgenommen werden, um Kunden-IDs Kontakt-IDs zuzuordnen, bevor Segmente exportiert werden können.

## <a name="set-up-connection-to-marketing"></a>Richten Sie die Verbindung mit Marketing ein

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Dynamics 365 Marketing**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie die Marketing URL Ihrer Organisation im Feld **Server-Adresse** ein.

1. In dem Abschnitt **Serveradministratorkonto** wählen Sie **Anmeldung** und ein Dynamics 365 Marketing-Konto.

1. Ordnen Sie das Feld „Kontakt-ID“ in der Entität „Kunde“ der Dynamics 365-Kontakt-ID zu.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Dynamics 365 Marketing-Abschnitt aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen Namen für den Export ein.

1. Wählen Sie das Feld „Kontakt-ID“ in der Entität „Kunde“, das zur Dynamics 365-Kontakt-ID gehört.

1. Wählen Sie die Segemente aus, die Sie exportieren möchten.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
