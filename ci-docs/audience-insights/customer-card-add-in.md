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
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059587"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="51ddc-103">Kundenkarten-Add-in (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="51ddc-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="51ddc-104">Erhalten Sie eine 360-Grad-Sicht auf Ihre Kunden direkt in den Apps von Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="51ddc-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="51ddc-105">Wenn das Kundenkarten-Add-In in einer unterstützten Dynamics 365-App installiert ist, können Sie Demografien, Einblicke und Aktivitätszeitpläne anzeigen.</span><span class="sxs-lookup"><span data-stu-id="51ddc-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="51ddc-106">Das Add-In ruft Daten aus Customer Insights ab, ohne die Daten in der verbundenen Dynamics 365-App zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="51ddc-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="51ddc-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="51ddc-107">Prerequisites</span></span>

- <span data-ttu-id="51ddc-108">Das Add-In funktioniert nur mit modellgetriebenen Dynamics 365-Apps wie Vertrieb oder Kundenservice, Version 9.0 und höher.</span><span class="sxs-lookup"><span data-stu-id="51ddc-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="51ddc-109">Damit Ihre Dynamics 365-Daten den Kundenprofilen der Zielgruppenerkenntnissen zugeordnet werden können, müssen sie [von der Dynamics 365-App mit dem Common Data Service Konnektor](connect-power-query.md) eingebunden werden.</span><span class="sxs-lookup"><span data-stu-id="51ddc-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="51ddc-110">Alle Dynamics 365-Benutzer des Kundenkarten-Add-Ins müssen in Zielgruppenerkenntnissen [als Benutzer hinzugefügt](permissions.md) sein, um die Daten zu sehen.</span><span class="sxs-lookup"><span data-stu-id="51ddc-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="51ddc-111">[Konfigurierte Such- und Filterfunktionen](search-filter-index.md) In Zielgruppenerkenntnissen sind erforderlich, damit die Suche nach Daten funktioniert.</span><span class="sxs-lookup"><span data-stu-id="51ddc-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="51ddc-112">Jedes Add-In-Steuerelement basiert auf bestimmten Daten in Zielgruppenerkenntnissen:</span><span class="sxs-lookup"><span data-stu-id="51ddc-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="51ddc-113">Kennzahlen-Kontrolle: Erfordert [Konfigurierte Kennzahlen](measures.md).</span><span class="sxs-lookup"><span data-stu-id="51ddc-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="51ddc-114">Intelligenzsteuerung: Erfordert Daten, die mit [Vorhersagen](predictions.md) oder [kundenspezifischen Modellen](custom-models.md) generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="51ddc-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="51ddc-115">Demografische Kontrolle: Demografische Felder, wie z.B. Alter oder Geschlecht, sind im einheitlichen Kundenprofil verfügbar.</span><span class="sxs-lookup"><span data-stu-id="51ddc-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="51ddc-116">Anreicherungskontrolle: Erfordert aktive [Anreicherungen](enrichment-hub.md) auf Kundenprofile angewendet.</span><span class="sxs-lookup"><span data-stu-id="51ddc-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="51ddc-117">Zeitleistensteuerung: Erfordert [Konfigurierte Aktivitäten](activities.md).</span><span class="sxs-lookup"><span data-stu-id="51ddc-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="51ddc-118">Installieren Sie das Kundenkarten-Add-in</span><span class="sxs-lookup"><span data-stu-id="51ddc-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="51ddc-119">Das Kundenkarten-Add-In ist eine Lösung für Customer Engagement Apps in Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="51ddc-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="51ddc-120">Um die Lösung zu installieren, gehen Sie zu AppSource und suchen Sie nach **Dynamics-Kundenkarte**.</span><span class="sxs-lookup"><span data-stu-id="51ddc-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="51ddc-121">Wählen Sie das [Kundenkarten-Add-in in AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) und dann **Jetzt abrufen** aus.</span><span class="sxs-lookup"><span data-stu-id="51ddc-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="51ddc-122">Möglicherweise müssen Sie sich mit Ihren Administratoranmeldeinformationen anmelden, damit die Dynamics 365-App die Lösung installiert.</span><span class="sxs-lookup"><span data-stu-id="51ddc-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="51ddc-123">Es kann einige Zeit dauern, bis die Lösung in Ihrer Umgebung installiert ist.</span><span class="sxs-lookup"><span data-stu-id="51ddc-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="51ddc-124">Konfigurieren des Kundenkarten-Add-ins</span><span class="sxs-lookup"><span data-stu-id="51ddc-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="51ddc-125">Als Administrator gehen Sie in modellgesteuerten Anwendungen in Dynamics 365 zum Abschnitt **Einstellungen** und wählen **Lösungen**.</span><span class="sxs-lookup"><span data-stu-id="51ddc-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="51ddc-126">Wählen Sie den Link **Anzeigename** für die Lösung **Dynamics 365 Customer Insights-Kundenkarten-Add-in (Vorschau)** aus.</span><span class="sxs-lookup"><span data-stu-id="51ddc-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="51ddc-127">![Anzeigename auswählen](media/select-display-name.png "Anzeigename auswählen")</span><span class="sxs-lookup"><span data-stu-id="51ddc-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="51ddc-128">Wählen Sie **Anmelden** aus und geben Sie die Anmeldeinformationen für das Administratorkonto ein, mit dem Sie Customer Insights konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="51ddc-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="51ddc-129">Stellen Sie sicher, dass der Popupblocker des Browsers das Authentifizierungsfenster nicht blockiert, wenn Sie die Schaltfläche **Anmelden** auswählen.</span><span class="sxs-lookup"><span data-stu-id="51ddc-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="51ddc-130">Wählen Sie die Customer Insights Umgebung, von der Sie Daten abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="51ddc-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="51ddc-131">Definieren Sie die Feldzuordnung zu Datensätzen in der Dynamics 365-App.</span><span class="sxs-lookup"><span data-stu-id="51ddc-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="51ddc-132">Abhängig von Ihren Daten in Customer Insights können Sie die folgenden Optionen zuordnen:</span><span class="sxs-lookup"><span data-stu-id="51ddc-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="51ddc-133">Um mit einem Kontakt zuzuordnen, wählen Sie das Feld in der Entität Kunde, das mit der ID Ihrer Kontakt-Entität übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="51ddc-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="51ddc-134">Um eine Zuordnung zu einem Konto vorzunehmen, wählen Sie das Feld in der Entität „Kunde“, das mit der ID Ihrer Entität „Konto“ übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="51ddc-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="51ddc-135">![Kontakt-ID-Feld](media/contact-id-field.png "Kontakt-ID-Feld")</span><span class="sxs-lookup"><span data-stu-id="51ddc-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="51ddc-136">Wählen Sie **Konfiguration speichern**, um die Einstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="51ddc-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="51ddc-137">Als Nächstes müssen Sie in Dynamics 365 Sicherheitsrollen zuweisen, damit Benutzer die Kundenkarte anpassen und anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="51ddc-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="51ddc-138">Gehen Sie in Dynamics 365 zu **Einstellungen** > **Sicherheit** > **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="51ddc-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="51ddc-139">Wählen Sie die Benutzer aus, um Benutzerrollen zu bearbeiten, und wählen Sie **Rollen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="51ddc-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="51ddc-140">Weisen Sie die **Customer Insights Kartenanpasser** Rolle Benutzer zu, die den auf der Karte angezeigten Inhalt für die gesamte Organisation anpassen.</span><span class="sxs-lookup"><span data-stu-id="51ddc-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="51ddc-141">Fügen Sie Steuerelemente für Kundenkarten zu Formularen hinzu</span><span class="sxs-lookup"><span data-stu-id="51ddc-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="51ddc-142">Um die Kundenkartensteuerelemente zu Ihrem Kontaktformular hinzuzufügen, gehen Sie zu **Einstellungen** > **Anpassungen** in Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="51ddc-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="51ddc-143">Wählen Sie **System anpassen** aus.</span><span class="sxs-lookup"><span data-stu-id="51ddc-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="51ddc-144">Blättern Sie zur Entität **Kontakt**, erweitern Sie sie und wählen Sie **Formulare** aus.</span><span class="sxs-lookup"><span data-stu-id="51ddc-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="51ddc-145">Wählen Sie das Kontaktformular aus, dem Sie die Kundenkartensteuerelemente hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="51ddc-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="51ddc-146">![Auswählen von Kontaktformular](media/contact-active-forms.png "Wählen Sie Kontaktformular")</span><span class="sxs-lookup"><span data-stu-id="51ddc-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="51ddc-147">Um dem Formular-Editor ein Steuerelement hinzuzufügen, ziehen Sie ein beliebiges Feld aus dem **Feld-Explorer** dorthin, wo das Steuerelement angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="51ddc-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="51ddc-148">Wählen Sie das Feld im Formular aus, das Sie gerade hinzugefügt haben, und wählen Sie **Eigenschaften ändern** aus.</span><span class="sxs-lookup"><span data-stu-id="51ddc-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="51ddc-149">Gehen Sie zur Registerkarte **Steuerelemente** und wählen Sie **Steuerelement hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="51ddc-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="51ddc-150">Wählen Sie eines der verfügbaren benutzerdefinierten Steuerelemente und dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="51ddc-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="51ddc-151">Deaktivieren Sie im Dialogfeld **Feldeigenschaften** das Kontrollkästchen **Anzeigebeschriftung auf dem Formular**.</span><span class="sxs-lookup"><span data-stu-id="51ddc-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="51ddc-152">Wählen Sie die Option **Web** für das Steuerelement aus.</span><span class="sxs-lookup"><span data-stu-id="51ddc-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="51ddc-153">Wählen Sie für das Anreicherungs-Steuerelement den Anreicherungstyp aus, den Sie anzeigen möchten, indem Sie das Feld **Anreicherungstyp** konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="51ddc-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="51ddc-154">Fügen Sie für jeden Anreicherungstyp ein separates Anreicherungssteuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="51ddc-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="51ddc-155">Wählen Sie **Speichern** und **Veröffentlichen** aus, um das aktualisierte Kontaktformular zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="51ddc-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="51ddc-156">Gehen Sie zum veröffentlichten Kontaktformular.</span><span class="sxs-lookup"><span data-stu-id="51ddc-156">Go to the published contact form.</span></span> <span data-ttu-id="51ddc-157">Sie sehen das neu hinzugefügte Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="51ddc-157">You'll see the newly added control.</span></span> <span data-ttu-id="51ddc-158">Möglicherweise müssen Sie sich bei der ersten Verwendung anmelden.</span><span class="sxs-lookup"><span data-stu-id="51ddc-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="51ddc-159">Um anzupassen, was Sie auf dem benutzerdefinierten Steuerelement anzeigen möchten, wählen Sie die Schaltfläche „Bearbeiten“ in der oberen rechten Ecke aus.</span><span class="sxs-lookup"><span data-stu-id="51ddc-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="51ddc-160">Upgrade des Kundenkarten-Add-Ins</span><span class="sxs-lookup"><span data-stu-id="51ddc-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="51ddc-161">Das Kundenkarten-Add-In wird nicht automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="51ddc-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="51ddc-162">Befolgen Sie dieses Verfahren in der Dynamics 365-App, in der das Add-In installiert ist, um ein Upgrade auf die neueste Version durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="51ddc-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="51ddc-163">Gehen Sie in der Dynamics 365-App zu **Einstellungen** > **Anpassung** und wählen Sie **Lösungen** aus.</span><span class="sxs-lookup"><span data-stu-id="51ddc-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="51ddc-164">Suchen Sie in der Tabelle der Add-Ins nach **CustomerInsightsCustomerCard** und wählen Sie die Zeile aus.</span><span class="sxs-lookup"><span data-stu-id="51ddc-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="51ddc-165">Wählen Sie **Upgrade auf Lösung anwenden** in der Aktionsleiste aus.</span><span class="sxs-lookup"><span data-stu-id="51ddc-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Aktualisieren Sie die Lösung im Bereich „Anpassung“ von Dynamics 365-Apps":::

1. <span data-ttu-id="51ddc-167">Nach dem Start des Upgradevorgangs wird eine Ladeanzeige angezeigt, bis das Upgrade abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="51ddc-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="51ddc-168">Wenn es keine neuere Version gibt, wird beim Upgrade eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="51ddc-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
