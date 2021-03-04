---
title: Installieren und konfigurieren Sie das Customer Card Add-in
description: Installieren und konfigurieren Sie das Kundenkarten-Add-in für Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268043"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="df631-103">Kundenkarten-Add-in (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="df631-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="df631-104">Erhalten Sie eine 360-Grad-Sicht auf Ihre Kunden direkt in den Apps von Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="df631-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="df631-105">Zeigen Sie demografische Daten, Einblicke und Aktivitätszeitpläne mit dem Kundenkarten-Add-in an.</span><span class="sxs-lookup"><span data-stu-id="df631-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="df631-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="df631-106">Prerequisites</span></span>

- <span data-ttu-id="df631-107">Dynamics 365-App (z. B. Vertriebshub oder Kundenservicehub), Version 9.0 und höher mit aktivierter Einheitlicher Oberfläche.</span><span class="sxs-lookup"><span data-stu-id="df631-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="df631-108">Kundenprofile [werden aus der Dynamics 365 App über Common Data Service abgerufen](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="df631-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="df631-109">Benutzer des Customer Card Add-Ins müssen [als Benutzer](permissions.md) in Zielgruppen-Insights hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="df631-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="df631-110">[Konfigurierte Such- und Filter-Funktionalitäten](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="df631-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="df631-111">Demografische Kontrolle: Demografische Felder, wie z.B. Alter oder Geschlecht, sind im einheitlichen Kundenprofil verfügbar.</span><span class="sxs-lookup"><span data-stu-id="df631-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="df631-112">Anreicherungskontrolle: Erfordert aktive [Anreicherungen](enrichment-hub.md) auf Kundenprofile angewendet.</span><span class="sxs-lookup"><span data-stu-id="df631-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="df631-113">Steuerung der Intelligenz: Erfordert Daten, die mit Azure Machine Learning generiert wurden ([Vorhersagen](predictions.md) oder [Benutzerdefinierte Modelle](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="df631-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="df631-114">Kennzahlen-Kontrolle: Erfordert [Konfigurierte Kennzahlen](measures.md).</span><span class="sxs-lookup"><span data-stu-id="df631-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="df631-115">Zeitleistensteuerung: Erfordert [Konfigurierte Aktivitäten](activities.md).</span><span class="sxs-lookup"><span data-stu-id="df631-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="df631-116">Installieren Sie das Kundenkarten-Add-in</span><span class="sxs-lookup"><span data-stu-id="df631-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="df631-117">Das Kundenkarten-Add-In ist eine Lösung für Customer Engagement Apps in Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="df631-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="df631-118">Um die Lösung zu installieren, gehen Sie zu AppSource und suchen Sie nach **Dynamics-Kundenkarte**.</span><span class="sxs-lookup"><span data-stu-id="df631-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="df631-119">Wählen Sie das [Kundenkarten-Add-in in AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) und dann **Jetzt abrufen** aus.</span><span class="sxs-lookup"><span data-stu-id="df631-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="df631-120">Möglicherweise müssen Sie sich mit Ihren Administratoranmeldeinformationen anmelden, damit die Dynamics 365-App die Lösung installiert.</span><span class="sxs-lookup"><span data-stu-id="df631-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="df631-121">Es kann einige Zeit dauern, bis die Lösung in Ihrer Umgebung installiert ist.</span><span class="sxs-lookup"><span data-stu-id="df631-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="df631-122">Konfigurieren des Kundenkarten-Add-ins</span><span class="sxs-lookup"><span data-stu-id="df631-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="df631-123">Als Administrator gehen Sie in modellgesteuerten Anwendungen in Dynamics 365 zum Abschnitt **Einstellungen** und wählen **Lösungen**.</span><span class="sxs-lookup"><span data-stu-id="df631-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="df631-124">Wählen Sie den Link **Anzeigename** für die Lösung **Dynamics 365 Customer Insights-Kundenkarten-Add-in (Vorschau)** aus.</span><span class="sxs-lookup"><span data-stu-id="df631-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="df631-125">![Anzeigename auswählen](media/select-display-name.png "Anzeigename auswählen")</span><span class="sxs-lookup"><span data-stu-id="df631-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="df631-126">Wählen Sie **Anmelden** aus und geben Sie die Anmeldeinformationen für das Administratorkonto ein, mit dem Sie Customer Insights konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="df631-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="df631-127">Stellen Sie sicher, dass der Popupblocker des Browsers das Authentifizierungsfenster nicht blockiert, wenn Sie die Schaltfläche **Anmelden** auswählen.</span><span class="sxs-lookup"><span data-stu-id="df631-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="df631-128">Wählen Sie die Umgebung, aus der Sie Daten abrufen wollen.</span><span class="sxs-lookup"><span data-stu-id="df631-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="df631-129">Definieren Sie, welche die Zuordnung der Felder zu Datensätzen in der Dynamics 365 App.</span><span class="sxs-lookup"><span data-stu-id="df631-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="df631-130">Um mit einem Kontakt zuzuordnen, wählen Sie das Feld in der Entität Kunde, das mit der ID Ihrer Kontakt-Entität übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="df631-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="df631-131">Um eine Zuordnung zu einem Konto vorzunehmen, wählen Sie das Feld in der Entität „Kunde“, das mit der ID Ihrer Entität „Konto“ übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="df631-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="df631-132">![Kontakt-ID-Feld](media/contact-id-field.png "Kontakt-ID-Feld")</span><span class="sxs-lookup"><span data-stu-id="df631-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="df631-133">Wählen Sie **Konfiguration speichern**, um die Einstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="df631-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="df631-134">Als Nächstes müssen Sie in Dynamics 365 Sicherheitsrollen zuweisen, damit Benutzer die Kundenkarte anpassen und anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="df631-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="df631-135">Gehen Sie in Dynamics 365 zu **Einstellungen** > **Sicherheit** > **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="df631-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="df631-136">Wählen Sie die Benutzer aus, um Benutzerrollen zu bearbeiten, und wählen Sie **Rollen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="df631-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="df631-137">Weisen Sie die **Customer Insights Kartenanpasser** Rolle Benutzer zu, die den auf der Karte angezeigten Inhalt für die gesamte Organisation anpassen.</span><span class="sxs-lookup"><span data-stu-id="df631-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="df631-138">Fügen Sie Steuerelemente für Kundenkarten zu Formularen hinzu</span><span class="sxs-lookup"><span data-stu-id="df631-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="df631-139">Um die Kundenkartensteuerelemente zu Ihrem Kontaktformular hinzuzufügen, gehen Sie zu **Einstellungen** > **Anpassungen** in Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="df631-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="df631-140">Wählen Sie **System anpassen** aus.</span><span class="sxs-lookup"><span data-stu-id="df631-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="df631-141">Blättern Sie zur Entität **Kontakt**, erweitern Sie sie und wählen Sie **Formulare** aus.</span><span class="sxs-lookup"><span data-stu-id="df631-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="df631-142">Wählen Sie das Kontaktformular aus, dem Sie die Kundenkartensteuerelemente hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="df631-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="df631-143">![Auswählen von Kontaktformular](media/contact-active-forms.png "Wählen Sie Kontaktformular")</span><span class="sxs-lookup"><span data-stu-id="df631-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="df631-144">Um dem Formular-Editor ein Steuerelement hinzuzufügen, ziehen Sie ein beliebiges Feld aus dem **Feld-Explorer** dorthin, wo das Steuerelement angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="df631-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="df631-145">Wählen Sie das Feld im Formular aus, das Sie gerade hinzugefügt haben, und wählen Sie **Eigenschaften ändern** aus.</span><span class="sxs-lookup"><span data-stu-id="df631-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="df631-146">Gehen Sie zur Registerkarte **Steuerelemente** und wählen Sie **Steuerelement hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="df631-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="df631-147">Wählen Sie eines der verfügbaren benutzerdefinierten Steuerelemente und dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="df631-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="df631-148">Deaktivieren Sie im Dialogfeld **Feldeigenschaften** das Kontrollkästchen **Anzeigebeschriftung auf dem Formular**.</span><span class="sxs-lookup"><span data-stu-id="df631-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="df631-149">Wählen Sie die Option **Web** für das Steuerelement aus.</span><span class="sxs-lookup"><span data-stu-id="df631-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="df631-150">Wählen Sie für das Anreicherungs-Steuerelement den Anreicherungstyp aus, den Sie anzeigen möchten, indem Sie das Feld **Anreicherungstyp** konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="df631-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="df631-151">Fügen Sie für jeden Anreicherungstyp ein separates Anreicherungssteuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="df631-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="df631-152">Wählen Sie **Speichern** und **Veröffentlichen** aus, um das aktualisierte Kontaktformular zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="df631-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="df631-153">Gehen Sie zum veröffentlichten Kontaktformular.</span><span class="sxs-lookup"><span data-stu-id="df631-153">Go to the published contact form.</span></span> <span data-ttu-id="df631-154">Sie sehen das neu hinzugefügte Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="df631-154">You'll see the newly added control.</span></span> <span data-ttu-id="df631-155">Möglicherweise müssen Sie sich bei der ersten Verwendung anmelden.</span><span class="sxs-lookup"><span data-stu-id="df631-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="df631-156">Um anzupassen, was Sie auf dem benutzerdefinierten Steuerelement anzeigen möchten, wählen Sie die Schaltfläche „Bearbeiten“ in der oberen rechten Ecke aus.</span><span class="sxs-lookup"><span data-stu-id="df631-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="df631-157">Upgrade des Kundenkarten-Add-Ins</span><span class="sxs-lookup"><span data-stu-id="df631-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="df631-158">Das Kundenkarten-Add-In wird nicht automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="df631-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="df631-159">Befolgen Sie dieses Verfahren in der Dynamics 365-App, in der das Add-In installiert ist, um ein Upgrade auf die neueste Version durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="df631-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="df631-160">Gehen Sie in der Dynamics 365-App zu **Einstellungen** > **Anpassung** und wählen Sie **Lösungen** aus.</span><span class="sxs-lookup"><span data-stu-id="df631-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="df631-161">Suchen Sie in der Tabelle der Add-Ins nach **CustomerInsightsCustomerCard** und wählen Sie die Zeile aus.</span><span class="sxs-lookup"><span data-stu-id="df631-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="df631-162">Wählen Sie **Upgrade auf Lösung anwenden** in der Aktionsleiste aus.</span><span class="sxs-lookup"><span data-stu-id="df631-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Aktualisieren Sie die Lösung im Bereich „Anpassung“ von Dynamics 365-Apps":::

1. <span data-ttu-id="df631-164">Nach dem Start des Upgradevorgangs wird eine Ladeanzeige angezeigt, bis das Upgrade abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="df631-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="df631-165">Wenn es keine neuere Version gibt, wird beim Upgrade eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="df631-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]