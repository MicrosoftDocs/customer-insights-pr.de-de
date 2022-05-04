---
title: Customer Insights-Daten nach Iterable exportieren
description: Weitere Informationen zum Konfigurieren der Verbindung und zum Exportieren nach Iterable.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 714a1323521be7d2f29ccaacd7799b2174e2937d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647420"
---
# <a name="export-segment-lists-to-iterable-preview"></a>Segmentlisten nach Iterable exportieren (Vorschau)

Exportieren Sie Segmente von Unified customer Profiles nach Iterable und verwenden Sie sie für Marketingaktivitäten.

## <a name="prerequisites"></a>Anforderungen

-   Sie haben ein [Iterable-Konto](https://iterable.com/) und die entsprechenden Administrator-Anmeldeinformationen.
-   Sie haben [Konfigurierte Segmente](segments.md) in Customer Insights.
-   Unified-Kundenprofile in den exportierten Segmenten enthalten ein Feld, das eine E-Mail-Adresse darstellt.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Der Export nach Iterable ist auf Segmente beschränkt.
- Der Export von Segmenten mit bis zu 1 Millionen Kundenprofilen nach Itrable kann bis zu 30 Minuten dauern. 
- Die Anzahl der Kundenprofile, die Sie nach Iterable exportieren können, hängt von Ihrem Vertrag mit Iterable ab.

## <a name="set-up-connection-to-iterable"></a>Richten Sie die Verbindung mit Iterable ein

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und wählen Sie **Iterable**, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Stellen Sie Ihren [Iterable API-Schlüssel](https://support.iterable.com/hc/en-us/articles/360043464871) bereit, um sich weiterhin anzumelden. 

1. Wählen Sie **einverstanden**, um **Datenschutz und Compliance** zu bestätigen.

1. Wählen Sie **Verbinden**, um die Verbindung zu Iterable zu initialisieren.

1. Wählen Sie **Sich selbst als Exportbenutzer hinzufügen** und geben Sie Ihre Customer Insights Anmeldeinformationen an.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Weitere Informationen finden Sie unter [Zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Ziel hinzufügen**, um einen neuen Export zu erstellen.

1. Wählen Sie im Feld **Verbindung für Export** eine Verbindung aus dem Iterable-Abschnitt aus. Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine Verbindungen dieses Typs zur Verfügung.

3. In dem Bereich **Datenabgleich** im Feld **E-Mail** wählen Sie das Feld, das eine Mail-Adresse eines Kunden darstellt. Es ist erforderlich, Segmente nach Iterable zu exportieren. Die in Iterable erstellte Liste erhält genau denselben Namen wie Ihr Segmentname in Dynamics 365 Customer Insights.

1. Wählen Sie **Speichern**.

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt. Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights für die Übertragung von Daten an Iterable aktivieren, erlauben Sie die Übertragung von Daten außerhalb der Konformitätsgrenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird solche Daten auf Ihre Anweisung übertragen, aber Sie sind dafür verantwortlich, sicherzustellen, dass Iterable alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).

Ihr Dynamics 365 Customer Insights-Administrator kann dieses Exportziel jederzeit entfernen, um die Verwendung dieser Funktionalität einzustellen.
