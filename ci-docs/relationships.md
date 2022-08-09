---
title: Beziehungen zwischen Entitäten und Entitätspfaden
description: Erstellen und verwalten Sie Beziehungen zwischen Entitäten aus mehreren Datenquellen.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: e622e5fa0b5738e31db1c668d95312adbc4f7d36
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183557"
---
# <a name="relationships-between-entities-and-entity-paths"></a>Beziehungen zwischen Entitäten und Entitätspfaden

Beziehungen verbinden Entitäten und definieren einen Graphen Ihrer Daten, wenn Entitäten einen gemeinsamen Bezeichner, einen Fremdschlüssel, teilen. Dieser Fremdschlüssel kann von einer Entität zu einer anderen referenziert werden. Verbundene Entitäten ermöglichen die Definition von Segmenten und Kennzahlen auf der Grundlage mehrerer Datenquellen.

Es gibt drei Arten von Beziehungen: 
- Nicht bearbeitbare Systembeziehungen, die vom System im Rahmen der Datenvereinheitlichung erstellt werden
- Nicht bearbeitbare, geerbte Beziehungen, die automatisch aus der Erfassung von Datenquellen erstellt werden
- Bearbeitbare benutzerdefinierte Beziehungen, die von Benutzern erstellt und konfiguriert werden

## <a name="non-editable-system-relationships"></a>Nicht bearbeitbare Systembeziehungen

Während der Datenvereinheitlichung werden basierend auf intelligenten Abgleichen automatisch Systembeziehungen erstellt. Diese Beziehungen helfen dabei, die Datensätze zum Kundenprofil mit entsprechenden Datensätzen in Beziehung zu setzen. Das folgende Diagramm veranschaulicht die Erstellung von drei systembasierten Beziehungen. Die Kundenentität wird mit anderen Entitäten abgeglichen, um die vereinheitlichte Entität *Kunde* zu erhalten.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagramm mit Beziehungspfaden für die Kundenentität mit drei 1-n-Beziehungen.":::

- Die ***CustomerToContact*-Beziehung** wurde zwischen der Entität *Kunde* und der Entität *Kontakt* erstellt. Die Entität *Kunde* erhält das Schlüsselfeld **Contact_contactID**, das sich auf das Schlüsselfeld **contactID** der Entität *Contact* bezieht.
- Die ***CustomerToAccount*-Beziehung** wurde zwischen der Entität *Kunde* und der Entität *Konto* erstellt. Die Entität *Kunde* erhält das Schlüsselfeld **Account_accountID**, das sich auf das Schlüsselfeld **accountID** der Entität *Konto* bezieht.
- Die ***CustomerToWebAccount*-Beziehung** wurde zwischen der Entität *Kunde* und der Entität *WebAccount* erstellt. Die Entität *Kunde* erhält das Schlüsselfeld **WebAccount_webaccountID**, das sich auf das Schlüsselfeld **webaccountID** der Entität *WebAccount* bezieht.

## <a name="non-editable-inherited-relationships"></a>Nicht bearbeitbare, geerbte Beziehungen

Während der Datenerfassung überprüft das System Datenquellen auf vorhandene Beziehungen. Wenn keine Beziehung besteht, legt sie das System automatisch an. Diese Beziehungen werden auch in nachgeschalteten Prozessen verwendet.

## <a name="create-a-custom-relationship"></a>Erstellen einer benutzerdefinierten Beziehung

Die Beziehung besteht aus einer *Quellentität* mit dem Fremdschlüssel und einer *Zielentität*, auf die der Fremdschlüssel der Quellentität verweist. 

1. Gehen Sie zu **Daten** > **Beziehungen**.

2. Wählen Sie **Neue Beziehung**.

3. Im Bereich **Neue Beziehung** geben Sie die folgenden Informationen ein:

   :::image type="content" source="media/relationship-add.png" alt-text="Seitenbereich der neuen Beziehung mit leeren Eingabefeldern.":::

   - **Beziehungsname**: Der Name, der den Zweck der Beziehung widerspiegelt. Beispiel: CustomerToSupportCase.
   - **Beschreibung:**: Beschreibung der Beziehung.
   - **Quellentität**: Die Entität, die in der Beziehung als Quelle verwendet wird. Beispiel: SupportCase.
   - **Zielentität**: Die Entität, die in der Beziehung als Ziel verwendet wird. Beispiel: Customer.
   - **Quellkardinalität**: Kardinalität der Quellentität an. Die Kardinalität beschreibt die Anzahl der möglichen Elemente in einer Menge. Sie bezieht sich immer auf die Zielkardinalität. Sie können zwischen **Einer** und **Viele** wählen. Es werden nur Viele-zu-Eins und Eins-zu-Eins-Beziehungen unterstützt.  
     - n:1: Mehrere Quelldatensätze können sich auf einen Zieldatensatz beziehen. Beispiel: Mehrere Supportfälle eines einzigen Kunden.
     - 1:1: Ein einzelner Quelldatensatz bezieht sich auf einen einzelnen Zieldatensatz. Beispiel: Eine Treue-ID für einen einzelnen Kunden.

     > [!NOTE]
     > m:n-Beziehungen können erstellt werden, indem Sie zwei n:1-Beziehungen verwenden und dann eine verknüpfende Entität erstellen, die die Quellentität und die Zielentität verbindet.

   - **Zielkardinalität**: Kardinalität der Zielentitätsdatensätze.
   - **Quellschlüsselfeld**: Fremdschlüsselfeld in der Quellentität Beispiel: SupportCase verwendet  **CaseID** als Fremdschlüsselfeld verwenden.
   - **Zielschlüsselfeld**: Schlüsselfeld der Zielentität. Beispiel: Customer verwendet das Schlüsselfeld **CustomerID**.

4. Wählen Sie **Speichern** aus, um die benutzerdefinierte Beziehung zu erstellen.

## <a name="set-up-account-hierarchies"></a>Kontohierarchien einrichten

Umgebungen, die für die Verwendung von Geschäftskonten als primäre Zielgruppe konfiguriert sind, können Kontohierarchien für zugehörige Geschäftskonten konfigurieren. Beispiel: ein Unternehmen mit separaten Geschäftsbereichen.

Organisationen erstellen Kontohierarchien, um Konten und ihre Beziehungen untereinander besser zu verwalten. Customer Insights unterstützt untergeordnete Kontenhierarchien, die bereits in den eingebundenen Kundendaten vorhanden sind. Zum Beispiel Konten von Dynamics 365 Sales. Diese Hierarchien können auf der Seite **Beziehungen** konfiguriert werden.

1. Gehen Sie zu **Daten** > **Beziehungen**.
1. Wählen Sie die Registerkarte **Kontohierarchie** aus.
1. **Neue Kontohierarchie** auswählen.
1. In dem Bereich **Kontohierarchie** geben Sie einen Namen für die Hierarchie ein. Das System erstellt einen Namen für die Ausgabeentität, aber Sie können ihn ändern.
1. Wählen Sie die Entität aus, die Ihre Kontohierarchie enthält. Es befindet sich normalerweise in derselben Entität, die die Konten enthält.
1. Wählen Sie **Konto-UID** und **Übergeordnete UID** von der ausgewählten Entität aus
1. Wählen Sie **Speichern**, um die Kontohierarchie abzuschließen.

## <a name="manage-existing-relationships"></a>Verwalten bestehender Beziehungen

Gehen Sie zur Seite **Beziehungen**, um alle erstellten Beziehungen, ihre Quellentität, die Zielentität und die Kardinalität anzuzeigen.

:::image type="content" source="media/relationships-list.png" alt-text="Liste von Beziehungen und Optionen in der Aktionsleiste der Seite „Beziehungen“.":::

Verwenden Sie die Optionen **Filtern nach** oder **Beziehungen suchen** aus, um eine bestimmte Beziehung zu finden. Wählen Sie [**Visualizer**](#explore-the-relationship-visualizer) aus, um ein Netzwerkdiagramm der bestehenden Beziehungen und ihrer Kardinalität anzuzeigen.

Wählen Sie eine Beziehung aus, um verfügbare Aktionen anzuzeigen:
- **Bearbeiten**: Aktualisieren Sie die Eigenschaften von benutzerdefinierten Beziehungen im Bearbeitungsbereich und speichern Sie die Änderungen.
- **Löschen**: Löschen Sie benutzerdefinierte Beziehungen.
- **Anzeigen**: Zeigen Sie vom System erstellte und geerbte Beziehungen an.

### <a name="explore-the-relationship-visualizer"></a>Der Beziehungsvisualisierer

Der Beziehungsvisualisierer zeigt ein Netzwerkdiagramm der bestehenden Beziehungen zwischen verbundenen Entitäten und ihrer Kardinalität an. Es visualisiert auch den Beziehungspfad.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Screenshot des Netzwerkdiagramms des Beziehungsvisualisierers mit Verbindungen zwischen verwandten Entitäten.":::

Um die Ansicht anzupassen, können Sie die Position der Felder ändern, indem Sie sie auf das Canvas ziehen. Folgende weitere Optionen stehen zur Verfügung: 
- **Als Bild exportieren**: Speichern Sie die aktuelle Ansicht als Bilddatei.
- **Zum horizontalen/vertikalen Layout wechseln**: Ändern Sie die Ausrichtung der Entitäten und Beziehungen.
- **Bearbeiten**: Aktualisieren Sie die Eigenschaften von benutzerdefinierten Beziehungen im Bearbeitungsbereich und speichern Sie die Änderungen.

## <a name="relationship-paths"></a>Beziehungspfade

Ein Beziehungspfad beschreibt die Entitäten, die mit Beziehungen zwischen einer Quell-Entität und einer Ziel-Entität verbunden sind. Es wird verwendet, wenn ein Segment oder eine Kennzahl erstellt wird, die andere Entitäten als die einheitliche Profilentität enthält, und es gibt mehrere Optionen, um die einheitliche Profilentität zu erreichen. Unterschiedliche Beziehungspfade können zu unterschiedlichen Ergebnissen führen.

Zum Beispiel hat die Entität *eCommerce_eCommerceEinkäufe* die folgenden Beziehungen zum einheitlichen Profil *benutzerdefinierte* Entität:

- eCommerce_eCommercePurchases > Kunde
- eCommerce_eCommercePurchases > eCommerce_eCommerceKontakte > POS_posPurchases > Kunde
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Kunde

Ein Beziehungspfad bestimmt, welche Entitäten Sie beim Erstellen von Regeln für Kennzahlen oder Segmente verwenden können. Die Auswahl der Option mit dem längsten Beziehungspfad führt wahrscheinlich zu weniger Ergebnissen, da die übereinstimmenden Datensätze Teil aller Entitäten sein müssen. In diesem Beispiel muss ein Kunde Waren über E-Commerce (eCommerce_eCommercePurchases) an einer Verkaufsstelle (POS_posPurchases) gekauft haben und an unserem Treueprogramm (loyaltyScheme_loyCustomers) teilnehmen. Wenn Sie sich für die erste Option entscheiden, erhalten Sie wahrscheinlich mehr Ergebnisse, da Kunden nur in einer weiteren Entität vorhanden sein müssen.

### <a name="direct-relationship"></a>Direkte Beziehung

Eine Beziehung wird als eine **direkte Beziehung** klassifiziert, wenn sich eine Quellentität auf eine Zielentität mit nur einer Beziehung bezieht.

Wenn beispielsweise eine Aktivitätsentität namens *eCommerce_eCommercePurchases* mit einer Zielentität *eCommerce_eCommerceContacts* nur durch *ContactId* verbunden ist, ist das eine direkte Beziehung.

:::image type="content" source="media/direct_Relationship.png" alt-text="Die Quellentität verbindet sich direkt mit der Zielentität.":::

#### <a name="multi-path-relationship"></a>Multipfadbeziehung

Eine **Multipfadbeziehung** ist eine spezielle Art von direkter Beziehung, die eine Quellentität mit mehr als einer Zielentität verbindet.

Wenn sich beispielsweise eine Aktivitätsentität namens *eCommerce_eCommercePurchases* auf zwei Zielentitäten bezieht, *eCommerce_eCommerceContacts* und *loyaltyScheme_loyCustomers*, ist das eine Multipfadbeziehung.

:::image type="content" source="media/multi-path_relationship.png" alt-text="Die Quellentität verbindet sich über eine Multi-Hop-Beziehung direkt mit mehr als einer Zielentität.":::

### <a name="indirect-relationship"></a>Indirekte Beziehung

Eine Beziehung wird als eine **indirekte Beziehung** klassifiziert, wenn sich eine Quellentität auf eine oder mehrere zusätzliche Entitäten bezieht, bevor sie sich auf eine Zielentität bezieht.

#### <a name="multi-hop-relationship"></a>Multi-Hop-Beziehung

Eine **Multi-Hop-Beziehung** ist eine *indirekte Beziehung*, die es Ihnen ermöglicht, eine Quell-Entität mit einer Ziel-Entität über eine oder mehrere andere zwischengeschaltete Entitäten zu verbinden.

Wenn sich beispielsweise eine Aktivitätsentität namens *eCommerce_eCommercePurchasesWest* mit einer Zwischenentität namens *eCommerce_eCommercePurchasesEast* verbindet und sich dann mit einer Zielentität namens *eCommerce_eCommerceContacts* verbindet, ist dies eine Multi-Hop-Beziehung.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="Die Quellentität verbindet sich direkt mit einer Zielentität mit einer Zwischenentität.":::

### <a name="multi-hop-multi-path-relationship"></a>Multi-Hop-Multipfadbeziehung

Multi-Hop- und Multipfadbeziehungen können zusammen verwendet werden, um **Multi-Hop-Multipfadbeziehungen** zu erstellen. Dieser spezielle Typ vereint die Funktionen von **Multi-Hop-** und **Multipfadbeziehungen**. Sie können eine Verbindung zu mehr als einer Zielentität herstellen, während Sie Zwischenentitäten verwenden.

Wenn sich beispielsweise eine Aktivitätsentität namens *eCommerce_eCommercePurchasesWest* mit einer Zwischenentität namens *eCommerce_eCommercePurchasesEast* verbindet und sich dann mit zwei Zielentitäten namens *eCommerce_eCommerceContacts* und *loyaltyScheme_loyCustomers* verbindet, ist dies eine Multi-Hop-Multipfadbeziehung.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="Die Quellentität stellt eine direkte Verbindung zu einer Zielentität und über eine Zwischenentität eine Verbindung zu einer anderen Zielentität her.":::

## <a name="next-step"></a>Nächster Schritt

System und benutzerdefinierte Beziehungen werden verwendet, um [Segmente zu erstellen](segments.md) und [Maße](measures.md) basierend auf mehreren Datenquellen, die nicht mehr isoliert sind.

[!INCLUDE [footer-include](includes/footer-banner.md)]
