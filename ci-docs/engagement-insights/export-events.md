---
title: Exportieren verfeinerter Ereignisse
description: So exportieren Sie verfeinerte Ereignisse und Basisereignisse.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: d062e2982c1041454b083630404f2b68f0da9669
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232887"
---
# <a name="export-events"></a>Ereignisse exportieren

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ein Ereignis repräsentiert das Benutzerverhalten. Es zeichnet auf, wann ein Benutzer eine Seite anzeigt (Anzeigeereignis) oder mit Inhalten interagiert (Aktionsereignis). Wenn Sie entscheiden können, welche Eigenschaften der Daten in einem Bericht angezeigt werden sollen, wird diese virtuelle Ansicht der Daten als *verfeinertes Ereignis* bezeichnet. Weitere Informationen finden Sie unter [Ereignisse erstellen und bearbeiten](refined-events.md).

- Sie können Ereignisse und verfeinerte Ereignisse in einen externen Speicher exportieren. 
- Die Exporte sind ein Forward-Datenstrom. Sie können den Stream nicht nachfüllen. 
- Exporte haben feste Schemata. Wenn Sie einem Ereignis benutzerdefinierte Eigenschaften hinzufügen, werden diese nicht berücksichtigt. Sie müssen einen neuen Export erstellen.

## <a name="prerequisites"></a>Anforderungen

Vor dem Einrichten eines Exports benötigen Sie Zugriff auf und ein aktives Abonnement für das Azure-Portal. Sie benötigen die Speicherkontoinformationen während des Exportvorgangs. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Erstellen eines Azure Data Lake Storage Gen 2-Kontos

1. Melden Sie sich beim Azure-Portal an und [erstellen Sie ein neues Speicherkonto](/azure/storage/common/storage-account-create). 

1. Stellen Sie sicher, dass Sie auf der Registerkarte **Erweitert** die Option **Hierarchischer Namespace** aktivieren. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Aktivieren der Option „Hierarchischer Namespace“ auf der Registerkarte „Erweitert“.":::

1. Wechseln Sie nach der Bereitstellung zum neu erstellten Speicherkonto. Wählen Sie im Navigationsbereich **Einstellungen** > **Zugriffsschlüssel** aus. 

1. Kopieren Sie den **Kontonamen** und den **Schlüssel**, um sie beim Erstellen eines neuen Exports zu verwenden.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Zugriffsschlüssel in einem Speicherkonto.":::

## <a name="export-events"></a>Ereignisse exportieren

Es gibt zwei Möglichkeiten, den Dialog **Ereignisse exportieren** anzuzeigen: 
- Wechseln Sie zu **Daten** > **Exporte** und wählen Sie **Neuer Export** aus.
- Gehen Sie zu **Daten** > **Ereignisse**, wählen Sie **Mehr [...]** neben dem Ereignis, das Sie exportieren möchten und wählen Sie **Export** aus dem Dropdown-Menü. 

:::image type="content" source="media/new-export.png" alt-text="Einen neuen Export erstellen.":::

Sie werden durch die Schritte zum Erstellen eines Exports geführt:

1. Geben Sie einen **Exportnamen** ein und wählen Sie dann **Weiter**.

1. In der Dropdown-Liste **Veranstaltungsauswahl** wählen Sie die Basisereignisse und die verfeinerten Ereignisse aus, die in den Export aufgenommen werden sollen. 

1. In dem Abschnitt **Dateistruktur** wählen Sie die Frequenz aus (stündlich oder täglich), um neue Dateien im Zielspeicher zu erstellen, und wählen Sie dann **Weiter**. Ereignisse werden kontinuierlich exportiert, sobald sie eintreffen.

1. In dem Dialog **Format wählen** wählen Sie das Format für Ihren Export aus. Wählen Sie zwischen **Gemeinsames Datenmodell**, **CSV**, und **JSON** Formaten. Um den Export mit anderen Dynamics 365 Anwendungen zu verwenden, empfehlen wir das **Common Data Model** Format.

1. In dem Dialog **Ziel auswählen** spezifizieren Sie den Azure Data Lake Storage Gen 2-Standort.
    1. **ADLS Gen 2-Kontoname** ist der Name des Speicherkontos, in dem Sie den Export speichern möchten. 
    1. **Ordnerpfad** definiert, wo der Export im Dateisystem und in der Verzeichnisstruktur des Speicherkontos gespeichert werden soll.
    1. **Freigegebener Schlüssel** ist im Azure-Portal für das Speicherkonto verfügbar.

1. Überprüfen und bestätigen Sie die Auswahl, und klicken Sie dann auf Fertig stellen.

## <a name="view-and-manage-exports"></a>Anzeigen und Verwalten von Exporten

Sobald Sie einen Export eingerichtet haben, wechseln Sie zu **Daten** > **Exporte**, um es anzuzeigen. Wählen Sie für jeden vorhandenen Export **Mehr [...]** aus, um ihn zu bearbeiten oder zu löschen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
