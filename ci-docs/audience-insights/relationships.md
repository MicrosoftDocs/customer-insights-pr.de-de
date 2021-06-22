---
title: Beziehungen zwischen Entitäten und Entitätspfaden
description: Erstellen und verwalten Sie Beziehungen zwischen Entitäten aus mehreren Datenquellen.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171163"
---
# <a name="relationships-between-entities"></a>Beziehungen zwischen Entitäten

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

1. Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Beziehungen**.

2. Wählen Sie **Neue Beziehung**.

3. Im Bereich **Neue Beziehung** geben Sie die folgenden Informationen ein:

   :::image type="content" source="media/relationship-add.png" alt-text="Seitenbereich der neuen Beziehung mit leeren Eingabefeldern.":::

   - **Beziehungsname**: Der Name, der den Zweck der Beziehung widerspiegelt. Beispiel: CustomerToSupportCase.
   - **Beschreibung:**: Beschreibung der Beziehung.
   - **Quellentität**: Die Entität, die in der Beziehung als Quelle verwendet wird. Beispiel: SupportCase.
   - **Zielentität**: Die Entität, die in der Beziehung als Ziel verwendet wird. Beispiel: Customer.
   - **Quellkardinalität**: Geben Sie die Kardinalität der Quellentität an. Die Kardinalität beschreibt die Anzahl der möglichen Elemente in einer Menge. Sie bezieht sich immer auf die Zielkardinalität. Sie können zwischen **Einer** und **Viele** wählen. Es werden nur Viele-zu-Eins und Eins-zu-Eins-Beziehungen unterstützt.  
     - n:1: Mehrere Quelldatensätze können sich auf einen Zieldatensatz beziehen. Beispiel: Mehrere Supportfälle eines einzigen Kunden.
     - 1:1: Ein einzelner Quelldatensatz bezieht sich auf einen einzelnen Zieldatensatz. Beispiel: Eine Treue-ID für einen einzelnen Kunden.

     > [!NOTE]
     > m:n-Beziehungen können erstellt werden, indem Sie zwei n:1-Beziehungen verwenden und dann eine verknüpfende Entität erstellen, die die Quellentität und die Zielentität verbindet.

   - **Zielkardinalität**: Wählen Sie die Kardinalität der Zielentitätsdatensätze aus. 
   - **Quellschlüsselfeld**: Das Fremdschlüsselfeld in der Quellentität. Beispiel: SupportCase könnte CaseID als Fremdschlüsselfeld verwenden.
   - **Zielschlüsselfeld**: Das Schlüsselfeld der Zielentität. Beispiel: Customer könnte das Schlüsselfeld **CustomerID** verwenden.

4. Wählen Sie **Speichern** aus, um die benutzerdefinierte Beziehung zu erstellen.

## <a name="view-relationships"></a>Anzeigen von Beziehungen

Die Seite „Beziehungen“ listet alle erstellten Beziehungen auf. Jede Zeile steht für eine Beziehung, die auch Details zur Quellentität, Zielentität und Kardinalität enthält. 

:::image type="content" source="media/relationships-list.png" alt-text="Liste von Beziehungen und Optionen in der Aktionsleiste der Seite „Beziehungen“.":::

Diese Seite bietet eine Reihe von Optionen für bestehende und neue Beziehungen: 
- **Neue Beziehung**: [Erstellen Sie eine neue Beziehung](#create-a-custom-relationship).
- **Visualisierer**: [Entdecken Sie den Beziehungsvisualisierer](#explore-the-relationship-visualizer), um ein Netzwerkdiagramm der bestehenden Beziehungen und ihrer Kardinalität anzuzeigen.
- **Filtern nach**: Wählen Sie den Typ von Beziehungen aus, der in der Liste angezeigt werden soll.
- **Beziehungen durchsuchen**: Verwenden Sie eine textbasierte Suche nach Eigenschaften von Beziehungen.

### <a name="explore-the-relationship-visualizer"></a>Der Beziehungsvisualisierer

Der Beziehungsvisualisierer zeigt ein Netzwerkdiagramm der bestehenden Beziehungen zwischen verbundenen Entitäten und ihrer Kardinalität an.

Um die Ansicht anzupassen, können Sie die Position der Felder ändern, indem Sie sie auf das Canvas ziehen.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Screenshot des Netzwerkdiagramms des Beziehungsvisualisierers mit Verbindungen zwischen verwandten Entitäten.":::

Verfügbare Optionen: 
- **Als Bild exportieren**: Speichern Sie die aktuelle Ansicht als Bilddatei.
- **Zum horizontalen/vertikalen Layout wechseln**: Ändern Sie die Ausrichtung der Entitäten und Beziehungen.
- **Bearbeiten**: Aktualisieren Sie die Eigenschaften von benutzerdefinierten Beziehungen im Bearbeitungsbereich und speichern Sie die Änderungen.

## <a name="manage-existing-relationships"></a>Verwalten bestehender Beziehungen 

Auf der Seite „Beziehungen“ wird jede Beziehung durch eine Zeile dargestellt. 

Wählen Sie eine Beziehung aus und wählen Sie dann eine der folgenden Optionen aus: 
 
- **Bearbeiten**: Aktualisieren Sie die Eigenschaften von benutzerdefinierten Beziehungen im Bearbeitungsbereich und speichern Sie die Änderungen.
- **Löschen**: Löschen Sie benutzerdefinierte Beziehungen.
- **Anzeigen**: Zeigen Sie vom System erstellte und geerbte Beziehungen an. 

## <a name="next-step"></a>Nächster Schritt

System- und benutzerdefinierte Beziehungen werden zur [Erstellung von Segmenten](segments.md) auf der Grundlage mehrerer Datenquellen verwendet, die nicht mehr in einem Silo gespeichert sind.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
