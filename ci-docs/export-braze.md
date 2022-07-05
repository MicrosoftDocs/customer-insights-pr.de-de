---
title: Segmente nach Braze exportieren (Vorschauversion)
description: Weitere Informationen zum Konfigurieren der Verbindung und zum Exportieren nach Braze.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 314a61f82c4040a8dbd6dff1dd5d92e20464f82a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081489"
---
# <a name="export-segments-to-braze-preview"></a>Segmente nach Braze exportieren (Vorschauversion)

Exportieren Sie Segmente von Unified customer Profiles nach Braze und verwenden Sie sie für Marketingaktivitäten.

## <a name="prerequisites"></a>Anforderungen

- Ein [Braze-Konto](https://www.braze.com/) und die entsprechenden Administrator-Anmeldeinformationen.
- Vorhandenene [Segmente in Braze](https://www.braze.com/docs/user_guide/engagement_tools/segments/creating_a_segment/).
- [Konfigurierte Segmente](segments.md) in Customer Insights.
- Einheitliche Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse und eine Braze-Kunden-ID darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Der Export nach Braze ist auf Segmente beschränkt.
- Der Export von Segmenten mit bis zu 1 Millionen Kundenprofilen nach Braze kann bis zu 40 Minuten dauern.
- Die Anzahl der Kundenprofile, die Sie nach Braze exportieren können, hängt von Ihrem Vertrag mit Braze ab.

## <a name="set-up-connection-to-braze"></a>Richten Sie die Verbindung mit Braze ein

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Braze**, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Stellen Sie Ihren [Braze API-Schlüssel](https://www.braze.com/docs/api/basics/) bereit, um sich weiterhin anzumelden.

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Wählen Sie **Verbinden**, um die Verbindung zu Braze zu initialisieren.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.

1. Wählen Sie im Feld **Verbindung für Export** eine Verbindung aus dem Braze-Abschnitt aus. Wenn Sie diesen Abschnitt nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.  

1. Fügen Sie einen **Anzeigenamen** für Ihren Export hinzu.

1. Fügen Sie die API-ID des Braze-Segments hinzu, in das Sie exportieren möchten, im Feld **Braze-Segment-API-Bezeichner**. Sie finden den Bezeichner in den Segmentdetails auf der Braze-Plattform.

1. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt. Wählen Sie das Feld für die Kunden-Braze-ID im Feld **Kunden-ID** aus. Es ist erforderlich, um Segmente nach Braze zu exportieren. Sie können optional weitere Felder auswählen.

1. Wählen Sie **Save** (Speichern).

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt. Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Braze aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Konformitätsgrenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird solche Daten auf Ihre Anweisung übertragen, aber Sie sind dafür verantwortlich, sicherzustellen, dass Braze alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).

Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.
