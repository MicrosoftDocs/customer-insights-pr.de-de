---
title: Semantische Zuordnungen (Vorschauversion)
description: Überblick über semantische Zuordnungen und deren Verwendung.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 8780c11c8b091717349f0fd75a36b99c3a63ab49
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303875"
---
# <a name="semantic-mappings-preview"></a>Semantische Zuordnungen (Vorschauversion)

> [!NOTE]
> Die Seite **Semantische Abbildungen** ist nur für Geschäftsumgebungen (B-to-B) verfügbar, in denen Kontaktprofile bereits mit dieser Seite erstellt wurden. Die einzelnen Kontaktprofile können Sie weiterhin über die Seite **Semantische Abbildungen** verwalten und erstellen. Oder [Vereinheitlichen Sie Ihre Kontaktdaten](data-unification-contacts.md),  um Duplikate zu entfernen, Übereinstimmungen zwischen Entitäten zu identifizieren und ein einheitliches Kontaktprofil zu erstellen. Sie können dann die einheitlichen Kontaktprofile verwenden, um Aktivitäten auf Kontaktebene zu erstellen.

Mit semantischen Zuordnungen können Sie Ihre Nicht-Aktivitätsdaten vordefinierten Schemata zuordnen. Diese Schemata helfen Customer Insights, Ihre Datenattribute besser zu verstehen. Semantische Zuordnungen und die bereitgestellten Daten ermöglichen neue Einblicke und Funktionen in Customer Insights. Um Ihre Aktivitätsdaten den Schemata zuzuordnen, lesen Sie die [Aktivitäten](activities.md) Dokumentation.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definieren Sie eine semantische Entitätszuordnung von ContactProfile

1. Gehen Sie zu **Daten** > **Semantische Zuordnungen (Vorschauversion)**.

1. Wählen Sie **Semantische Zuordnung hinzufügen** um das geführte Erlebnis zu starten.

1. In dem **Entitätsdaten** Schritt legen Sie die Werte für die folgenden Felder fest:

   - **Name der semantischen Entitätszuordnung**: Geben Sie einen Namen für Ihre semantische Entitätszuordnung an.
   - **Quell-Entität**: Eine Entität, die Kontaktdaten enthält.
   - **Primärschlüssel**: Feld, mit dem ein Kontaktdatensatz eindeutig identifiziert wird. Sie sollte keine doppelten Werte, leere Werte oder fehlende Werte enthalten.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Richten Sie die semantische Entitätszuordnung mit Name, Quellentität und Primärschlüssel ein.":::

1. Wählen Sie **Weiter** aus.

1. Konfigurieren Sie im Schritt **Beziehung** die Details, die zum Verbinden Ihrer Kontaktdaten mit den entsprechenden Kundendaten verwendet werden. Dieser Schritt visualisiert die Verbindung zwischen Entitäten.  

   Es gibt zwei Arten von Beziehungspfaden, die implementiert werden können: **Direkt Beziehungen** und **Indirekt Beziehungen**. Weitere Informationen finden Sie unter [direkte und indirekte Beziehungswege](relationships.md#relationship-paths).

   1. Wählen Sie **Beziehung hinzufügen** und konfigurieren Sie die Beziehung.
   1. Wählen Sie das Attribut aus Ihrer Quellentität aus, das Ihre Kontaktentität mit einer anderen Entität verbindet.
   1. Wählen Sie die Entität aus, mit der Sie Ihre Kontaktentität verbinden möchten. Wählen Sie eine Entität aus dem Bereich **Kontoentitäten** oder **Zwischenentität** aus. Wenn Sie eine Zwischenentität auswählen, definieren Sie eine zweite Beziehung, um eine Verbindung zu Ihrer Zielkontoentität herzustellen.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Wählen Sie entweder eine Kontoentität oder eine Zwischenentität aus.":::

   1. **Beziehungsname** angeben. Wenn bereits eine Beziehung zwischen Ihren Entitäten besteht, ist der Beziehungsname schreibgeschützt. Wenn keine Beziehung besteht, wird eine neue Beziehung mit dem von Ihnen angegebenen Namen erstellt.
   1. Wählen Sie **Anwenden**, um die Beziehungskonfiguration abzuschließen.

   > [!NOTE]
   > Sie können mehr Beziehungen zwischen der Kontaktentität und anderen Kontoentitäten mit Zwischenentitäten konfigurieren.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualisierung verschiedener Beziehungen, die Kontaktentitäten mit Kontoentitäten verbinden.":::

1. Wählen Sie **Weiter** aus.

1. In dem Schritt **Semantiktyp einstellen** wählen Sie einen **Semantischen Typ**. Aktuell gibt es einen **Semantischen Typ** namens *KontaktProfil*.

1. Ordnen Sie Ihre Kontakt-ID dem zu *ContactProfile* semantischer Typ **Kontakt-ID**. Ordnen Sie optional andere Felder wie Vorname, Nachname, Gender oder E-Mail zu.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Ordnen Sie Ihre Kontaktdatenattribute den bereitgestellten erforderlichen und optionalen Feldern zu.":::

1. Wählen Sie **Weiter** aus.

1. In dem Schritt **Überprüfen** überprüfen Sie die Konfiguration der semantischen Zuordnung. Wählen Sie **Bearbeiten** für den entsprechenden Abschnitt, um Änderungen vorzunehmen.

1. Wählen Sie **Save** (Speichern).

1. Wählen Sie **Ausführen** aus, um die semantische Zuordnung zu verarbeiten. Oder wählen Sie **Schließen** aus, um Ihre semantische Zuordnung zu speichern, ohne sie zu verarbeiten. Für die spätere Ausführung wählen Sie die semantische Zuordnung aus und wählen Sie **Aktualisierung**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Verwalten Sie vorhandene semantische Zuordnungen

Gehen Sie zu **Daten** > **Semantische Zuordnungen (Vorschau)**, um Ihre gespeicherten semantischen Zuordnungen, deren Quellentität, Semantiktyp, Zuordnungstyp und Status anzuzeigen.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Optionen zum Verwalten von semantischen Zuordnungen.":::

Wählen Sie die semantische Zuordnung aus, um verfügbare Aktionen anzuzeigen.
- **Bearbeiten** Sie die aktuelle Konfiguration. Klicken Sie auf **Speichern** und **Ausführen**, um die Änderungen zu verarbeiten.
- **Aktualisieren** Sie die semantische Zuordnung, um die neuesten Daten einzuschließen. Das Aktualisieren einer bestimmten semantischen Zuordnung aktualisiert alle semantischen Zuordnungen desselben Typs.
- **Umbenennen** Sie die semantische Zuordnung. Wählen Sie **Save** (Speichern).
- **Löschen** Sie die semantische Zuordnung. Sie können auch mehrere semantische Zuordnungen gleichzeitig löschen, indem Sie die semantischen Zuordnungen und das Löschsymbol auswählen. Um den Löschvorgang zu bestätigen, wählen Sie **Löschen**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
