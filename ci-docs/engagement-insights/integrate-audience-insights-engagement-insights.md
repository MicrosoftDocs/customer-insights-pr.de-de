---
title: Erstellen Sie eine Verknüpfung zwischen Zielgruppenerkenntnissen und Kundenbindungserkenntnissen
description: Erstellen Sie eine aktive Verknüpfung zwischen Zielgruppenerkenntnissen und Bindungserkenntnissen, um den bidirektionalen Datenaustausch zu ermöglichen.
ms.date: 09/08/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0fdbc93292291814b2e1a62fee2c5ff796ae14e2
ms.sourcegitcommit: 4e5b7ec50c7612765a9ec2c8673e0cc43b357abb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2021
ms.locfileid: "7487106"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Erstellen Sie eine Verknüpfung zwischen Zielgruppenerkenntnissen und Kundenbindungserkenntnissen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Die Integration zwischen Bindungserkenntnissen und Zielgruppenerkenntnissen verknüpft Umgebungen aus beiden Funktionen und ermöglicht den bidirektionalen Datenaustausch zwischen ihnen.

Verwenden Sie einheitliche Profile und Segmente aus Zielgruppenerkenntnissen für mehr Analyseoptionen in Bindungserkenntnissen. Exportieren Sie Ereignisse mit hohem geschäftlichem Wert aus Bindungserkenntnissen. Verwenden Sie diese Ereignisse, um Daten zu einheitlichen Profilen in Zielgruppenerkenntnissen hinzuzufügen.

## <a name="prerequisites"></a>Anforderungen

- Zielgruppenerkenntnis-Profile müssen in einem Azure Data Lake Storage Konto, das Sie besitzen, oder in einem [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md)&ndash; verwalteten Data Lake gespeichert werden. 
- Ihre Zielgruppenerkenntnis-Umgebung sollte eine zugeordnete Dataverse-Umgebung haben. Und wenn diese Umgebung Dataverse auch für die Datenspeicherung verwendet, aktivieren Sie unbedingt die Option **Datenfreigabe aktivieren** in den Zielgruppenerkenntnissen. Weitere Informationen finden Sie unter [Erstellen und Konfigurieren einer kostenpflichtigen Umgebung in Zielgruppenerkenntnissen](../audience-insights/get-started-paid.md).
- Sie benötigen Administrator-Berechtigungen sowohl für die Umgebungen mit Bindungserkenntnissen als auch für Zielgruppenerkenntnissen.
- Verknüpfte Umgebungen müssen sich in derselben geografischen Region befinden.

> [!NOTE]
> - Wenn es sich bei Ihrem Zielgruppenerkenntnis-Abonnement um eine Testversion handelt, die einen Zielgruppenerkenntnis intern verwalteten Data Lake verwendet, wenden Sie sich an [pirequest@microsoft.com](mailto:pirequest@microsoft.com) für Unterstützung. 
> - Wenn Ihre Zielgruppenerkenntnis-Umgebung Ihren eigenen Azure Data Lake Storage verwendet, um Daten zu speichern, müssen Sie Ihrem Speicherkonto einen Azure-Dienstprinzipal für Bindungserkenntnisse hinzufügen. Weitere Informationen finden Sie unter [Verbinden Sie sich mit einem Azure Data Lake Storage Konto mit einem Azure-Dienstprinzipal für Zielgruppenerkenntnisse](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Eine Umgebungsverknüpfung erstellen

Sie können eine Umgebungsverknüpfung erstellen, indem Sie die Einstellungen **Administrator** > **Umgebung** in Bindungserkenntnissen aktualisieren.

**Um eine aktive Verknüpfung zwischen Zielgruppenerkenntnissen und Kundenbindungserkenntnissen zu erstellen**

1. Auf der **Umgebungsadministrator** Seite, wählen Sie die Registerkarte **Umgebungen verknüpfen**.

    :::image type="content" source="media/integrate1.png" alt-text="Umgebung einrichten.":::

1. **Umgebungen einrichten** in der oberen linken Ecke oder am unteren Bildschirmrand auswählen.

     :::image type="content" source="media/integrate2.png" alt-text="Eine Umgebung für Zielgruppenerkenntnisse auswählen":::

1. Wählen Sie Zielgruppenerkenntnis-Umgebung und dann ***Weiter** aus zum Beenden. Jetzt können Sie optionale Funktionen für die verknüpften Umgebungen auswählen.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Aktivieren Sie vereinheitlichte Profilattribute und -segmente für Zielgruppenerkenntnisse

Nach der verknüpfung von Umgebungen können Sie optionale Funktionen für die verknüpften Umgebungen auswählen. Diese Funktionen ermöglichen einheitliche Profilattribute und Segmente aus Zielgruppenerkenntnissen für die interaktive Analyse von Kundendaten.

**Um Webdaten in Bindungserkenntnissen zu analysieren**

1. Auf der **Umgebungsadministrator** Seite, schalten Sie die **Daten aus Zielgruppenerkenntnis mit Bindungserkenntnissen teilen** um und wählen Sie dann **Weiter**.

    :::image type="content" source="media/integrate4.png" alt-text="Funktionen auswählen.":::

1. Wählen Sie die Attribute der einheitlichen Profile aus, die zu Dimensionen in den Bindungserkenntnissen werden. (Nicht alle Attribute sind nützliche Dimensionen. Zum Beispiel ist es unwahrscheinlich, dass Sie **Vorname** oder **Nachname** als Attribut zur Analyse Ihrer Website-Ereignisse benötigen.)

    :::image type="content" source="media/integrate5.png" alt-text="Dimensionen zusammenstellen.":::

   >[!NOTE]
   > Alle Zielgruppenerkenntnis-Profilattribute, die Bezeichner darstellen (wie **ID** und **alternative ID**) werden aus den verfügbaren Attributen herausgefiltert und werden zu Dimensionen in den Bindungserkenntnissen.

1. Wenn Sie mit der Auswahl der Attribute fertig sind, wählen Sie **Weiter**.
1. Fügen Sie Nutzer hinzu, die die Profildimensionen und Segmente der Zielgruppenerkenntnis-Profile in Interaktions-Statistiken anzeigen können.

    :::image type="content" source="media/integrate6.png" alt-text="Zugriff auf Kundendaten verwalten.":::

   > [!IMPORTANT]
   > Wenn Sie in diesem Schritt keine Nutzer explizit hinzufügen, werden die Daten für Nutzer in Bindungserkenntnissen ausgeblendet.
   > Damit Zielgruppenerkenntnis-Segmente in den Bindungserkenntnissen angezeigt werden, müssen Sie zuerst [Merge -und Downstream-Prozesse ausführen](../audience-insights/merge-entities.md). Nachgelagerte Prozesse sind wichtig, weil sie eine einzigartige Tabelle generieren, die Zielgruppenerkenntnis-Segmente für die gemeinsame Nutzung mit Bindungserkenntnissen vorbereitet. (Wenn eine Systemaktualisierung geplant ist, umfasst sie automatisch nachgelagerte Prozesse.)

1. Überprüfen Sie Ihren Abschnitt und wählen Sie **Fertig**.

    :::image type="content" source="media/integrate7.png" alt-text="Dateneinstellungen von Kunden überprüfen.":::

## <a name="export-refined-events-to-audience-insights"></a>Verfeinertes Ereignis für Zielgruppenerkenntnisse freigeben exportieren

Nachdem Sie eine Verknüpfung zwischen Umgebungen erstellt haben, können Sie verfeinerte Ereignisse aus Bindungserkenntnissen in Zielgruppenerkenntnisse exportieren und als neue Datenquelle aufnehmen. 

Weitere Informationen finden Sie unter [Integrieren Sie Webdaten aus Bindungserkenntnissen mit Zielgruppenerkenntnissen](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
