---
title: Kundenkarten-Add-In für Dynamics 365-Apps (enthält Video)
description: Zeigen Sie mit diesem Add-In Kundenprofildaten aus Customer Insights in Dynamics 365 Apps an.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 2dfa6c643cbe9a8531a085d8ce01b0f64776476f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646031"
---
# <a name="customer-card-add-in-preview"></a>Kundenkarten-Add-in (Vorschau)



Erhalten Sie eine 360-Grad-Sicht auf Ihre Kunden direkt in den Apps von Dynamics 365. Wenn das Kundenkarten-Add-In in einer unterstützten Dynamics 365 App installiert ist, können Sie Kundenprofilfelder, Erkenntnisse und Aktivitätszeitachse anzeigen. Das Add-In ruft Daten aus Customer Insights ab, ohne die Daten in der verbundenen Dynamics 365-App zu beeinflussen.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Anforderungen

- Das Add-In funktioniert nur mit modellgetriebenen Dynamics 365-Apps wie Vertrieb oder Kundenservice, Version 9.0 und höher.
- Damit Ihre Dynamics 365-Daten den Customer Insights-Kundenprofilen zugeordnet werden können, empfehlen wir, sie [über den Konnektor Microsoft Dataverse in die Dynamics 365 App einzubinden](connect-power-query.md). Wenn Sie eine andere Methode zum Erfassen von Dynamics 365-Kontakten (oder -Konten) verwenden, müssen Sie sicherstellen, dass das Feld `contactid` (oder`accountid`) [im Zuordnungsschritt des Datenvereinigungsprozesses als Primärschlüssel für diese Datenquelle](map-entities.md#select-primary-key-and-semantic-type-for-attributes) festgelegt ist. 
- Alle Dynamics 365 Benutzer des Kundenkarten-Add-Ins müssen [als Benutzer](permissions.md) in Customer Insights hinzugefügt werden, um die Daten zu sehen.
- [Konfigurierte Such- und Filter Funktionalitäten](search-filter-index.md) in Customer Insights sind erforderlich, damit das Nachschlagefeld für die Daten funktioniert.
- Jedes Steuerelement des Add-Ins ist auf bestimmte Daten in Customer Insights angewiesen. Einige Daten und Steuerelemente sind nur in Umgebungen bestimmter Typen verfügbar. Die Add-In-Konfiguration informiert Sie, wenn ein Steuerelement aufgrund des ausgewählten Umgebungstyps nicht verfügbar ist. Erhalten Sie weitere Informationen zu [Umgebungen, die Fälle verwenden](work-with-business-accounts.md).
  - **Measure-Steuerelement**: Erfordert [konfigurierte Measures](measures.md) vom Typ Kundenattribute.
  - **Intelligenzsteuerung**: Erfordert Daten, die mit [Vorhersagen oder kundenspezifischen Modellen](predictions-overview.md) generiert wurden.
  - **Kundendetail-Steuerelement**: Alle Felder aus dem Profil sind im vereinheitlichtes Kund*innenprofil verfügbar.
  - **Anreicherungs-Steuerelement**: Erfordert aktive [Anreicherungen](enrichment-hub.md) auf Kundenprofile angewendet. Das Karten-Add-In unterstützt die folgenden Anreicherungen: Von Microsoft bereitgestellte [Marken](enrichment-microsoft.md), [Interessen](enrichment-microsoft.md) und [Office-Bindungsdaten](enrichment-office.md).
  - **Kontakt-Steuerelement**: Erfordert die Definition einer semantischen Entität des Typs Kontakte.
  - **Zeitskala-Steuerelement**: Erfordert [Konfigurierte Aktivitäten](activities.md).

## <a name="install-the-customer-card-add-in"></a>Installieren Sie das Kundenkarten-Add-in

Das Kundenkarten-Add-In ist eine Lösung für Customer Engagement Apps in Dynamics 365. Um die Lösung zu installieren, gehen Sie zu AppSource und suchen Sie nach **Dynamics-Kundenkarte**. Wählen Sie das [Kundenkarten-Add-in in AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) und dann **Jetzt abrufen** aus.

Möglicherweise müssen Sie sich mit Ihren Administratoranmeldeinformationen anmelden, damit die Dynamics 365-App die Lösung installiert. Es kann einige Zeit dauern, bis die Lösung in Ihrer Umgebung installiert ist.

## <a name="configure-the-customer-card-add-in"></a>Konfigurieren des Kundenkarten-Add-ins

1. Als Administrator gehen Sie in modellgesteuerten Anwendungen in Dynamics 365 zum Abschnitt **Einstellungen** und wählen **Lösungen**.

1. Wählen Sie den Link **Anzeigename** für die Lösung **Dynamics 365 Customer Insights-Kundenkarten-Add-in (Vorschau)** aus.

   > [!div class="mx-imgBorder"]
   > ![Anzeigename auswählen.](media/select-display-name.png "Anzeigename auswählen.")

1. Wählen Sie **Anmelden** aus und geben Sie die Anmeldeinformationen für das Administratorkonto ein, mit dem Sie Customer Insights konfiguriert haben.

   > [!NOTE]
   > Stellen Sie sicher, dass der Popupblocker des Browsers das Authentifizierungsfenster nicht blockiert, wenn Sie die Schaltfläche **Anmelden** auswählen.

1. Wählen Sie die Customer Insights Umgebung, von der Sie Daten abrufen möchten.

1. Definieren Sie die Feldzuordnung zu Datensätzen in der Dynamics 365-App. Abhängig von Ihren Daten in Customer Insights können Sie die folgenden Optionen zuordnen:
   - Um mit einem Kontakt zuzuordnen, wählen Sie das Feld in der Entität Kunde, das mit der ID Ihrer Kontakt-Entität übereinstimmt.
   - Um eine Zuordnung zu einem Konto vorzunehmen, wählen Sie das Feld in der Entität „Kunde“, das mit der ID Ihrer Entität „Konto“ übereinstimmt.

   > [!div class="mx-imgBorder"]
   > ![Kontakt-ID-Feld.](media/contact-id-field.png "Kontakt-ID-Feld.")

1. Wählen Sie **Konfiguration speichern**, um die Einstellungen zu speichern.

1. Als Nächstes müssen Sie in Dynamics 365 Sicherheitsrollen zuweisen, damit Benutzer die Kundenkarte anpassen und anzeigen können. Gehen Sie in Dynamics 365 zu **Einstellungen** > **Sicherheit** > **Benutzer**. Wählen Sie die Benutzer aus, um Benutzerrollen zu bearbeiten, und wählen Sie **Rollen verwalten** aus.

1. Weisen Sie die **Customer Insights Kartenanpasser** Rolle Benutzer zu, die den auf der Karte angezeigten Inhalt für die gesamte Organisation anpassen.

## <a name="add-customer-card-controls-to-forms"></a>Fügen Sie Steuerelemente für Kundenkarten zu Formularen hinzu

Abhängig von Ihrem Szenario können Sie entweder Steuerelemente **Kontakt**-Formular oder **Konto**-Formular hinzufügen. Wenn es sich bei Ihrer Customer Insights Umgebung um Geschäftskonten handelt, empfehlen wir, die Steuerelemente zum Formular Konto hinzuzufügen. Ersetzen Sie in diesem Fall Kontakt in den folgenden Schritten durch Konto.

1. Um die Kundenkartensteuerelemente zu Ihrem Kontaktformular hinzuzufügen, gehen Sie zu **Einstellungen** > **Anpassungen** in Dynamics 365.

1. Wählen Sie **System anpassen** aus.

1. Blättern Sie zur Entität **Kontakt**, erweitern Sie sie und wählen Sie dann **Formulare** aus.

1. Wählen Sie das Kontaktformular, dem Sie die Kundenkarten-Steuerelemente hinzufügen möchten.

    > [!div class="mx-imgBorder"]
    > ![Kontaktformular auswählen.](media/contact-active-forms.png "Wählen Sie Kontaktformular.")

1. Um dem Formular-Editor ein Steuerelement hinzuzufügen, ziehen Sie ein beliebiges Feld aus dem **Feld-Explorer** dorthin, wo das Steuerelement angezeigt werden soll.

1. Wählen Sie das Feld im Formular aus, das Sie gerade hinzugefügt haben, und wählen Sie **Eigenschaften ändern** aus.

1. Gehen Sie zur Registerkarte **Steuerelemente** und wählen Sie **Steuerelement hinzufügen**. Wählen Sie eines der verfügbaren benutzerdefinierten Steuerelemente und dann **Hinzufügen** aus.

1. Deaktivieren Sie im Dialogfeld **Feldeigenschaften** das Kontrollkästchen **Anzeigebeschriftung auf dem Formular**.

1. Wählen Sie die Option **Web** für das Steuerelement aus. Wählen Sie für das Anreicherungs-Steuerelement den Anreicherungstyp aus, den Sie anzeigen möchten, indem Sie das Feld **Anreicherungstyp** konfigurieren. Fügen Sie für jeden Anreicherungstyp ein separates Anreicherungssteuerelement hinzu.

1. Wählen Sie **Speichern** und **Veröffentlichen** aus, um das aktualisierte Kontaktformular zu veröffentlichen.

1. Gehen Sie zum veröffentlichten Kontaktformular. Sie sehen das neu hinzugefügte Steuerelement. Möglicherweise müssen Sie sich bei der ersten Verwendung anmelden.

1. Um anzupassen, was Sie auf dem benutzerdefinierten Steuerelement anzeigen möchten, wählen Sie die Schaltfläche „Bearbeiten“ in der oberen rechten Ecke aus.

## <a name="upgrade-customer-card-add-in"></a>Upgrade des Kundenkarten-Add-Ins

Das Kundenkarten-Add-In wird nicht automatisch aktualisiert. Um auf die neueste Version zu aktualisieren, führen Sie diese Schritte in der Dynamics 365-App aus, auf der das Add-In installiert ist.

1. Gehen Sie in der Dynamics 365-App zu **Einstellungen** > **Anpassung** und wählen Sie **Lösungen** aus.

1. Suchen Sie in der Tabelle der Add-Ins nach **CustomerInsightsCustomerCard** und wählen Sie die Zeile aus.

1. Wählen Sie **Upgrade auf Lösung anwenden** in der Aktionsleiste aus.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Aktualisieren Sie die Lösung im Bereich „Anpassung“ von Dynamics 365-Apps.":::

1. Nach dem Start des Upgradevorgangs wird eine Ladeanzeige angezeigt, bis das Upgrade abgeschlossen ist. Wenn es keine neuere Version gibt, wird beim Upgrade eine Fehlermeldung angezeigt.

## <a name="troubleshooting"></a>Problembehandlung

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Steuerelemente aus dem Kundenkarten-Add-In finden keine Daten

**Problem:**

Selbst mit korrekt konfigurierten ID-Feldern können die Steuerelemente keine Daten für jeden Kunden finden.  

**Lösung:**

1. Stellen Sie sicher, dass Sie das Karten-Add-In gemäß den Anweisungen konfiguriert haben: [Konfigurieren des Kundenkarten-Add-Ins](#configure-the-customer-card-add-in) 

1. Überprüfen Sie die Datenerfassungskonfiguration. Bearbeiten Sie die Datenquelle für das Dynamics 365-System, das die Kontakt-ID-GUID enthält. Wenn die GUID der Kontakt-ID in Großbuchstaben im Power Query-Editor angezeigt wird, versuchen Sie Folgendes: 
    1. Bearbeiten Sie Datenquelle, um die Datenquelle im Power Query-Editor zu öffnen.
    1. Wählen Sie die Spalte Kontakt-ID aus.
    1. Wählen Sie **Transformieren** in der Kopfleiste, um verfügbare Aktionen anzuzeigen.
    1. Wählen Sie **Kleinbuchstaben**. Überprüfen Sie, ob die GUIDs in der Tabelle jetzt in Kleinbuchstaben geschrieben sind.
    1. Speichern Sie die Datenquelle.
    1. Führen Sie Datenerfassung, Vereinheitlichung und nachgelagerte Prozesse aus, um die Änderungen an der GUID weiterzugeben. 

Nach Abschluss der vollständigen Aktualisierung sollten die Steuerelemente des Kundenkarten-Add-Ins die erwarteten Daten anzeigen. 

[!INCLUDE [footer-include](includes/footer-banner.md)]
