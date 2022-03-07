---
title: Exportieren verfeinerter Ereignisse
description: So exportieren Sie verfeinerte Ereignisse und Basisereignisse.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032384"
---
# <a name="export-events"></a>Ereignisse exportieren

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ein Ereignis repräsentiert das Benutzerverhalten. Es zeichnet auf, wann ein Benutzer eine Seite anzeigt (Anzeigeereignis) oder mit Inhalten interagiert (Aktionsereignis). Wenn Sie entscheiden können, welche Eigenschaften der Daten in einem Bericht angezeigt werden sollen, wird diese virtuelle Ansicht der Daten als *verfeinertes Ereignis* bezeichnet. 

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

Zum Exportieren von Ereignissen stehen zwei Möglichkeiten zur Verfügung: 
- Wechseln Sie zu **Daten** > **Exporte** und wählen Sie **Neuer Export** aus.
- Gehen Sie zu **Daten** > **Ereignisse**, wählen Sie **Mehr [...]** neben dem Ereignis, das Sie exportieren möchten und wählen Sie **Export** aus dem Dropdown-Menü. 

Sie werden durch die Schritte zum Erstellen eines Exports geführt:

1. Geben Sie einen **Exportnamen** an.

1. In der Dropdown-Liste **Veranstaltungsauswahl** wählen Sie die Basisereignisse und die verfeinerten Ereignisse aus, die in den Export aufgenommen werden sollen. 

1. Wählen Sie unter **Dateistruktur** die Kadenz aus, um neue Dateien im Zielspeicher zu erstellen. Ereignisse werden kontinuierlich exportiert, sobald sie eintreffen.

1. Wählen Sie das Format für Ihren Export aus. Sie können zwischen den Formaten **Common Data Model**, **CSV** und **JSON** wählen. Um den Export mit anderen Dynamics 365-Anwendungen zu verwenden, empfehlen wir das Common Data Model-Format.

1. Geben Sie im Schritt **Ziel auswählen** den Speicherort des Azure Data Lake Storage Gen 2-Kontos an.
    1. **ADLS Gen 2-Kontoname** ist der Name des Speicherkontos, in dem Sie den Export speichern möchten. 
    1. **Ordnerpfad** definiert, wo der Export im Dateisystem und in der Verzeichnisstruktur des Speicherkontos gespeichert werden soll.
    1. **Freigegebener Schlüssel** ist im Azure-Portal für das Speicherkonto verfügbar.

1. Überprüfen und bestätigen Sie Ihre Auswahl.

## <a name="view-and-manage-exports"></a>Anzeigen und Verwalten von Exporten

Sobald Sie einen Export eingerichtet haben, wechseln Sie zu **Daten** > **Exporte**, um es anzuzeigen. Wählen Sie für jeden vorhandenen Export **Mehr [...]** aus, um ihn zu bearbeiten oder zu löschen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]