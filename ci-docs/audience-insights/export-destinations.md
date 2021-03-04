---
title: Exportziele
description: Daten exportieren und Exportziele verwalten.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 63caa2ebdd7d637d14ac9c9cc7972095803aee2f
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477132"
---
# <a name="export-destinations-preview-overview"></a>Exportziele (Vorschau) – Übersicht

Die Seite **Exportziele** zeigt Ihnen die Orte, die Sie für den Export von Daten eingerichtet haben. Sie können auch neue Ziele für den Export hinzufügen. Zusätzlich zeigt es die aktuell verfügbaren Exportoptionen an. Verschaffen Sie sich einen schnellen Überblick und eine Beschreibung und finden Sie heraus, was Sie mit den einzelnen Erweiterungsoptionen tun können. Exportieren Sie vereinheitlichte Profile, Messgrößen und Segmente in unterstützte Anwendungen, die für Ihr Unternehmen relevant sind.

Gehen Sie zu **Admin** > **Exportziele**, um die folgenden Erweiterungsoptionen zu finden:

- [Dynamics 365 Customer Card Add-in](customer-card-add-in.md)
- [Facebook Ads Manager-Connector](export-facebook.md)
- [Power AutomateConnector](export-power-automate.md)
- [Power AppsConnector](export-power-apps.md)
- [Power BIConnector](export-power-bi.md)
- [Autopilot](export-autopilot.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Azure Blob Storage](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [SendGrid](export-sendgrid.md)
- [LiveRamp&reg; Connector](export-liveramp.md)
- [Bot für Microsoft Teams](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [Customer Insights API](apis.md)

## <a name="add-a-new-export-destination"></a>Neues Exportziel hinzufügen

Um Exportziele hinzuzufügen, haben Sie [Administrator-Berechtigungen](permissions.md). Wenn Sie zu Microsoft-Diensten exportieren, gehen wir davon aus, dass sich beide Dienste in derselben Organisation befinden.

1. Gehen Sie zu **Administrator** > **Exportziele**.

1. Wechseln Sie zur Registerkarte **Meine Exportziele**.

1. Wählen **Ziel hinzufügen**, um ein neues Exportziel zu erstellen.

1. In dem Bereich **Ziel hinzufügen** wählen Sie den **Typ** des Exportziels in der Dropdown-Liste.

1. Geben Sie die erforderlichen Details ein und wählen Sie **Weiter**, um das Exportziel zu erstellen.

Sie können auch auf einer Kachel **Installieren** in der Registerkarte **Entdecken** auswählen.

## <a name="view-export-destinations"></a>Exportziele anzeigen

Nachdem Sie Exportziele erstellt haben, finden Sie diese in einer Tabelle auf der Registerkarte **Meine Exportziele**. Diese Tabelle enthält drei Spalten:

- **Anzeigename**: Der Name, den Sie beim Erstellen des Ziels eingegeben haben.
- **Typ**:  Der Exportzieltyp, den Sie beim Erstellen des Ziels festgelegt haben.
- **Erstellt am**: Das Datum, an dem das Ziel erstellt wurde.

## <a name="edit-an-export-destination"></a>Ein Exportziel bearbeiten

1. Wählen Sie die vertikale Auslassung für das Exportziel aus, das Sie bearbeiten möchten.

   > [!div class="mx-imgBorder"]
   > ![Vertikale Ellipsen](media/export-destinations-page-ellipsis.png "Vertikale Ellipsen")

1. Wählen Sie **Bearbeiten** aus dem Dropdown-Menü aus.

1. Ändern Sie die zu aktualisierenden Werte und wählen Sie **speichern**.

## <a name="export-data-on-demand"></a>Daten nach Bedarf exportieren

Nach dem Konfigurieren eines Connectors für ein Exportziel werden die Exporte mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt.

Um Daten zu exportieren, ohne auf eine geplante Aktualisierung zu warten, gehen Sie zur Regisgerkarte **Meine Exportziele** unter **Administrator** > **Ziele exportieren**.

> [!div class="mx-imgBorder"]
> ![Vertikale Ellipsen](media/export-destinations-page-ellipsis.png "Vertikale Ellipsen")

- Wählen Sie **Exportieren** oben in der Liste aus, um den Export zu allen Exportzielen gleichzeitig auszuführen.
- Wählen Sie die Auslassungspunkte (...) nach einem Listenelement aus und wählen Sie dann die Option **Exportieren** zum Ausführen des Exports für ein einzelnes Exportziel.

## <a name="remove-an-export-destination"></a>Ein Exportziel entfernen

Um ein Exportziel zu entfernen, beginnen Sie auf der Hauptseite **Exportziele**.

1. Wählen Sie die vertikale Auslassung für das Exportziel aus, das Sie entfernen möchten.

   > [!div class="mx-imgBorder"]
   > ![Vertikale Ellipsen](media/export-destinations-page-ellipsis.png "Vertikale Ellipsen")

2. Klicken Sie im Dropdown-Menü auf **Entfernen**.

3. Bestätigen Sie das Entfernen, indem Sie **Entfernen** auf dem Bestätigungsbildschirm wählen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]