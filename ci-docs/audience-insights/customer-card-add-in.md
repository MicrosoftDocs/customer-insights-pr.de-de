---
title: Kundenkarten-Add-In für Dynamics 365 Apps
description: Zeigen Sie mit diesem Add-In Daten aus Zielgruppenerkenntnissen in Dynamics 365-Apps an.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6a7137730ab8cc43bc93daf647d9d55d02d96cd8
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692204"
---
# <a name="customer-card-add-in-preview"></a>Kundenkarten-Add-in (Vorschau)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Erhalten Sie eine 360-Grad-Sicht auf Ihre Kunden direkt in den Apps von Dynamics 365. Wenn das Kundenkarten-Add-In in einer unterstützten Dynamics 365-App installiert ist, können Sie Demografien, Einblicke und Aktivitätszeitpläne anzeigen. Das Add-In ruft Daten aus Customer Insights ab, ohne die Daten in der verbundenen Dynamics 365-App zu beeinflussen. 

## <a name="prerequisites"></a>Anforderungen

- Das Add-In funktioniert nur mit modellgetriebenen Dynamics 365-Apps wie Vertrieb oder Kundenservice, Version 9.0 und höher.
- Damit Ihre Dynamics 365-Daten den Kundenprofilen der Zielgruppenerkenntnissen zugeordnet werden können, müssen sie [von der Dynamics 365-App mit dem Microsoft Dataverse Konnektor](connect-power-query.md) eingebunden werden.
- Alle Dynamics 365-Benutzer des Kundenkarten-Add-Ins müssen in Zielgruppenerkenntnissen [als Benutzer hinzugefügt](permissions.md) sein, um die Daten zu sehen.
- [Konfigurierte Such- und Filterfunktionen](search-filter-index.md) In Zielgruppenerkenntnissen sind erforderlich, damit die Suche nach Daten funktioniert.
- Jedes Add-In-Steuerelement basiert auf bestimmten Daten in Zielgruppenerkenntnissen:
  - Kennzahlen-Kontrolle: Erfordert [Konfigurierte Kennzahlen](measures.md).
  - Intelligenzsteuerung: Erfordert Daten, die mit [Vorhersagen](predictions.md) oder [kundenspezifischen Modellen](custom-models.md) generiert wurden.
  - Demografische Kontrolle: Demografische Felder, wie z.B. Alter oder Geschlecht, sind im einheitlichen Kundenprofil verfügbar.
  - Anreicherungskontrolle: Erfordert aktive [Anreicherungen](enrichment-hub.md) auf Kundenprofile angewendet.
  - Zeitleistensteuerung: Erfordert [Konfigurierte Aktivitäten](activities.md).

## <a name="install-the-customer-card-add-in"></a>Installieren Sie das Kundenkarten-Add-in

Das Kundenkarten-Add-In ist eine Lösung für Customer Engagement Apps in Dynamics 365. Um die Lösung zu installieren, gehen Sie zu AppSource und suchen Sie nach **Dynamics-Kundenkarte**. Wählen Sie das [Kundenkarten-Add-in in AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) und dann **Jetzt abrufen** aus.

Möglicherweise müssen Sie sich mit Ihren Administratoranmeldeinformationen anmelden, damit die Dynamics 365-App die Lösung installiert.

Es kann einige Zeit dauern, bis die Lösung in Ihrer Umgebung installiert ist.

## <a name="configure-the-customer-card-add-in"></a>Konfigurieren des Kundenkarten-Add-ins

1. Als Administrator gehen Sie in modellgesteuerten Anwendungen in Dynamics 365 zum Abschnitt **Einstellungen** und wählen **Lösungen**.

1. Wählen Sie den Link **Anzeigename** für die Lösung **Dynamics 365 Customer Insights-Kundenkarten-Add-in (Vorschau)** aus.

   > [!div class="mx-imgBorder"]
   > ![Anzeigename auswählen.](media/select-display-name.png "Anzeigename auswählen")

1. Wählen Sie **Anmelden** aus und geben Sie die Anmeldeinformationen für das Administratorkonto ein, mit dem Sie Customer Insights konfiguriert haben.

   > [!NOTE]
   > Stellen Sie sicher, dass der Popupblocker des Browsers das Authentifizierungsfenster nicht blockiert, wenn Sie die Schaltfläche **Anmelden** auswählen.

1. Wählen Sie die Customer Insights Umgebung, von der Sie Daten abrufen möchten.

1. Definieren Sie die Feldzuordnung zu Datensätzen in der Dynamics 365-App. Abhängig von Ihren Daten in Customer Insights können Sie die folgenden Optionen zuordnen:
   - Um mit einem Kontakt zuzuordnen, wählen Sie das Feld in der Entität Kunde, das mit der ID Ihrer Kontakt-Entität übereinstimmt.
   - Um eine Zuordnung zu einem Konto vorzunehmen, wählen Sie das Feld in der Entität „Kunde“, das mit der ID Ihrer Entität „Konto“ übereinstimmt.

   > [!div class="mx-imgBorder"]
   > ![Kontakt-ID-Feld.](media/contact-id-field.png "Kontakt-ID-Feld")

1. Wählen Sie **Konfiguration speichern**, um die Einstellungen zu speichern.

1. Als Nächstes müssen Sie in Dynamics 365 Sicherheitsrollen zuweisen, damit Benutzer die Kundenkarte anpassen und anzeigen können. Gehen Sie in Dynamics 365 zu **Einstellungen** > **Sicherheit** > **Benutzer**. Wählen Sie die Benutzer aus, um Benutzerrollen zu bearbeiten, und wählen Sie **Rollen verwalten** aus.

1. Weisen Sie die **Customer Insights Kartenanpasser** Rolle Benutzer zu, die den auf der Karte angezeigten Inhalt für die gesamte Organisation anpassen.

## <a name="add-customer-card-controls-to-forms"></a>Fügen Sie Steuerelemente für Kundenkarten zu Formularen hinzu
  
1. Um die Kundenkartensteuerelemente zu Ihrem Kontaktformular hinzuzufügen, gehen Sie zu **Einstellungen** > **Anpassungen** in Dynamics 365.

1. Wählen Sie **System anpassen** aus.

1. Blättern Sie zur Entität **Kontakt**, erweitern Sie sie und wählen Sie **Formulare** aus.

1. Wählen Sie das Kontaktformular aus, dem Sie die Kundenkartensteuerelemente hinzufügen möchten.

    > [!div class="mx-imgBorder"]
    > ![Kontaktformular auswählen.](media/contact-active-forms.png "Wählen Sie Kontaktformular")

1. Um dem Formular-Editor ein Steuerelement hinzuzufügen, ziehen Sie ein beliebiges Feld aus dem **Feld-Explorer** dorthin, wo das Steuerelement angezeigt werden soll.

1. Wählen Sie das Feld im Formular aus, das Sie gerade hinzugefügt haben, und wählen Sie **Eigenschaften ändern** aus.

1. Gehen Sie zur Registerkarte **Steuerelemente** und wählen Sie **Steuerelement hinzufügen**. Wählen Sie eines der verfügbaren benutzerdefinierten Steuerelemente und dann **Hinzufügen** aus.

1. Deaktivieren Sie im Dialogfeld **Feldeigenschaften** das Kontrollkästchen **Anzeigebeschriftung auf dem Formular**.

1. Wählen Sie die Option **Web** für das Steuerelement aus. Wählen Sie für das Anreicherungs-Steuerelement den Anreicherungstyp aus, den Sie anzeigen möchten, indem Sie das Feld **Anreicherungstyp** konfigurieren. Fügen Sie für jeden Anreicherungstyp ein separates Anreicherungssteuerelement hinzu.

1. Wählen Sie **Speichern** und **Veröffentlichen** aus, um das aktualisierte Kontaktformular zu veröffentlichen.

1. Gehen Sie zum veröffentlichten Kontaktformular. Sie sehen das neu hinzugefügte Steuerelement. Möglicherweise müssen Sie sich bei der ersten Verwendung anmelden.

1. Um anzupassen, was Sie auf dem benutzerdefinierten Steuerelement anzeigen möchten, wählen Sie die Schaltfläche „Bearbeiten“ in der oberen rechten Ecke aus.

## <a name="upgrade-customer-card-add-in"></a>Upgrade des Kundenkarten-Add-Ins
Das Kundenkarten-Add-In wird nicht automatisch aktualisiert. Befolgen Sie dieses Verfahren in der Dynamics 365-App, in der das Add-In installiert ist, um ein Upgrade auf die neueste Version durchzuführen.

1. Gehen Sie in der Dynamics 365-App zu **Einstellungen** > **Anpassung** und wählen Sie **Lösungen** aus.

1. Suchen Sie in der Tabelle der Add-Ins nach **CustomerInsightsCustomerCard** und wählen Sie die Zeile aus.

1. Wählen Sie **Upgrade auf Lösung anwenden** in der Aktionsleiste aus.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Aktualisieren Sie die Lösung im Bereich „Anpassung“ von Dynamics 365-Apps.":::

1. Nach dem Start des Upgradevorgangs wird eine Ladeanzeige angezeigt, bis das Upgrade abgeschlossen ist. Wenn es keine neuere Version gibt, wird beim Upgrade eine Fehlermeldung angezeigt.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
