---
title: Customer Insights-Daten nach Dynamics 365 Marketing exportieren
description: Erfahren Sie, wie Sie die Verbindung konfigurieren und zu Dynamics 365 Marketing exportieren.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 7227f3f9e7699a9b5ad546789de5e568b56da579
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645970"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Segmente in Dynamics 365 Marketing verwenden (Vorschau)



Verwenden Sie [Segmente](segments.md), um mit Dynamics 365 Marketing Kampagnen zu erstellen und bestimmte Kundengruppen zu kontaktieren. Weitere Informationen finden Sie unter [Segmente aus Dynamics 365 Customer Insights mit Dynamics 365 Marketing verwenden](/dynamics365/marketing/customer-insights-segments).

Wenn Sie die neuen Funktionen von Dynamics 365 Marketing für die Echtzeit-Orchestrierung des Kundenkontaktverlauf in einer Dataverse Org. nutzen, müssen Sie keinen Standardexport nach Dynamics 365 Marketing erstellen. Kontakte und Segmente aus Customer Insights sind direkt in Dynamics 365 Marketing verfügbar, nachdem Sie Marketing und Customer Insights miteinander verbunden haben. Bevor Sie bestehende Exporte löschen, lesen Sie die Dokumentation zur [Verbindung von Customer Insights und Dynamics 365 Marketing mit Customer Journey Orchestration](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Voraussetzungen für die Verbindung

- Kontaktdatensätze müssen in Dynamics 365 Marketing vorhanden sein, bevor Sie ein Segment von Customer Insights nach Marketing exportieren können. Lesen Sie mehr darüber, wie Sie Kontakte in [Dynamics 365 Marketing mit Microsoft Dataverse](connect-dataverse-managed-lake.md) erfassen können.

  > [!NOTE]
  > Durch den Export von Segmenten aus Customer Insights nach Marketing werden keine neuen Datensätze in den Marketing-Instanzen erstellt. Die Datensätze aus Marketing müssen in Customer Insights eingebunden und als Datenquelle verwendet werden. Sie müssen auch in die einheitliche Kundenentität aufgenommen werden, um Kunden-IDs Kontakt-IDs zuzuordnen, bevor Segmente exportiert werden können.

## <a name="set-up-connection-to-marketing"></a>Richten Sie die Verbindung mit Marketing ein

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und dann **Dynamics 365 Marketing** aus, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Geben Sie die Marketing URL Ihrer Organisation im Feld **Server-Adresse** ein.

1. In dem Abschnitt **Serveradministratorkonto** wählen Sie **Anmeldung** und ein Dynamics 365 Marketing-Konto.

1. Ordnen Sie das Feld „Kontakt-ID“ in der Entität „Kunde“ der Dynamics 365-Kontakt-ID zu.

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

[!INCLUDE [footer-include](includes/footer-banner.md)]