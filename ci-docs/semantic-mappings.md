---
title: Semantische Zuordnungen (Vorschauversion)
description: Überblick über semantische Zuordnungen und deren Verwendung.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183630"
---
# <a name="semantic-mappings-preview"></a>Semantische Zuordnungen (Vorschauversion)

Mit semantischen Zuordnungen können Sie Ihre Nicht-Aktivitätsdaten vordefinierten Schemata zuordnen. Diese Schemata helfen Customer Insights, Ihre Datenattribute besser zu verstehen. Semantische Zuordnungen und die bereitgestellten Daten ermöglichen neue Einblicke und Funktionen in Customer Insights. Um Ihre Aktivitätsdaten den Schemata zuzuordnen, lesen Sie die [Aktivitäten](activities.md) Dokumentation.

**Semantische Zuordnungen sind derzeit für Umgebungen aktiviert, die auf Geschäftskonten basieren**. *ContactProfile* ist die einzige Art der semantischen Zuordnung, die derzeit in Customer Insights verfügbar ist.

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

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Eine semantische Entitätszuordnung von ContactProfile zum Erstellen von Aktivitäten auf Kontaktebene verwenden

Nach dem Erstellen einer semantischen Entitätszuordnung von *ContactProfile* können Sie Aktivitäten von Kontakten erfassen. Dadurch können Sie in der Aktivitätszeitleiste für ein Konto anzeigen, welcher Kontakt für jede Aktivität verantwortlich war. Die meisten Schritte folgen der typischen Aktivitätszuordnungskonfiguration.

   > [!NOTE]
   > Damit Aktivitäten auf Kontaktebene funktionieren, müssen sowohl das Attribut **AccountID** als auch das Attribut **ContactID** in Ihren Aktivitätsdaten enthalten sein.

1. [Definieren Sie ein *ContactProfile* Semantische Entitätszuordnung](#define-a-contactprofile-semantic-entity-mapping) und führen Sie die semantische Zuordnung aus.

1. Gehen Sie zu **Daten** > **Aktivitäten**.

1. Wählen Sie **Aktivität hinzufügen** aus, um eine neue Aktivität zu erstellen.

1. Benennen Sie die Aktivität, wählen Sie die Quellaktivitätsentität und dann den Primärschlüssel der Aktivitätsentität aus.

1. Erstellen Sie im Schritt **Beziehungen** eine indirekte Beziehung zwischen Ihren Aktivitätsquellendaten und Konten, indem Sie Ihre Kontaktdaten als vermittelnde Entität verwenden. Weitere Informationen finden Sie unter [direkte und indirekte Beziehungspfade](relationships.md#relationship-paths).
   - Beispielbeziehung für eine Aktivität namens *Einkäufe*:
      - **Aktivitätsdaten der Einkaufsquelle** > **Kontaktdaten** auf das Attribut **ContactID**
      - **Kontaktdaten** > **Kontodaten** im Attribut **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Beispiel für die Einrichtung einer Beziehung":::

1. Wählen Sie nach dem Einrichten der Beziehung(en) **Weiter** aus, und vervollständigen Sie Ihre Aktivitätszuordnungskonfiguration. Detaillierte Schritte zum Erstellen von Aktivitäten finden Sie unter [Eine Aktivität definieren](activities.md).

1. Führen Sie Ihre Aktivitätszuordnungen aus.

1. Nachdem eine Aktivitätszuordnung auf Kontaktebene ausgeführt wurde, wählen Sie **Kunden** aus. Ihre Aktivitäten auf Kontaktebene werden auf Ihrer Kundenzeitskala angezeigt.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Endergebnis nach der Konfiguration der Kontaktaktivitäten":::

### <a name="contact-level-activity-timeline-filtering"></a>Filterung der Aktivitätszeitskala auf Kontaktebene

Je nach Ihrer *ContactProfile*-Konfiguration enthält die Aktivitätszeitleiste für Kunden die IDs oder Namen dieser Personen für die Aktivitäten, an denen sie beteiligt waren. Filtern Sie Aktivitäten in der Zeitskala nach Kontakten, um bestimmte Kontakte anzuzeigen, die Sie interessieren. Sie können alle Aktivitäten anzeigen, die keinem bestimmten Kontakt zugeordnet sind, indem Sie **Aktivitäten, die keinem Kontakt zugeordnet sind** auswählen.

:::image type="content" source="media/Contact_Activities3.png" alt-text="Filteroptionen, die für Aktivitäten auf Kontaktebene verfügbar sind":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
