---
title: Semantische Zuordnungen (Vorschau)
description: Überblick über semantische Zuordnungen und deren Verwendung.
ms.date: 12/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: 08b257b97704b219bb3277042516e00deb886a49
ms.sourcegitcommit: 58651d33e0a7d438a2587c9ceeaf7ff58ae3b648
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2021
ms.locfileid: "7881829"
---
# <a name="semantic-mappings-preview"></a>Semantische Zuordnungen (Vorschau)

Mit semantischen Zuordnungen können Sie Ihre Nicht-Aktivitätsdaten vordefinierten Schemata zuordnen. Diese Schemas helfen Zielgruppenerkenntnissen, Ihre Datenattribute besser zu verstehen. Semantische Zuordnungen und die bereitgestellten Daten ermöglichen neue Erkenntnisse und Funktionen in Zielgruppenerkenntnissen. Um Ihre Aktivitätsdaten den Schemata zuzuordnen, lesen Sie die [Aktivitäten](activities.md) Dokumentation.

**Semantische Zuordnungen sind derzeit für Umgebungen aktiviert, die auf Geschäftskonten basieren**. *KontaktProfil* ist die einzige Art der semantischen Zuordnung, die derzeit in Zielgruppenerkenntnissen verfügbar ist.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definieren Sie eine semantische Entitätszuordnung von ContactProfile

1. Gehen Sie in Zielgruppenerkenntnissen zu **Daten** > **Semantische Zuordnungen (Vorschau)**.

1. Wählen Sie **Semantische Zuordnung hinzufügen** um das geführte Erlebnis zu starten.

1. In dem **Entitätsdaten** Schritt legen Sie die Werte für die folgenden Felder fest:

   - **Name der semantischen Entitätszuordnung**: Geben Sie einen Namen für Ihre semantische Entitätszuordnung an.
   - **Quell-Entität**: Wählen Sie eine Entität aus, die Kontaktdaten enthält.
   - **Primärschlüssel**: Wählen Sie das Feld aus, mit dem ein Kontaktdatensatz eindeutig identifiziert wird. Sie sollte keine doppelten Werte, leere Werte oder fehlende Werte enthalten.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Richten Sie die semantische Entitätszuordnung mit Name, Quellentität und Primärschlüssel ein.":::

1. Wählen Sie **Weiter** aus, um den Vorgang fortzusetzen.

1. Konfigurieren Sie im Schritt **Beziehung** die Details, die zum Verbinden Ihrer Kontaktdaten mit den entsprechenden Kundendaten verwendet werden. Dieser Schritt visualisiert die Verbindung zwischen Entitäten.  

   Es gibt zwei Arten von Beziehungspfaden, die implementiert werden können: **Direkt Beziehungen** und **Indirekt Beziehungen**. Weitere Informationen finden Sie unter [direkte und indirekte Beziehungswege](relationships.md#relationship-paths).

   1. Wählen Sie **Beziehung hinzufügen** und konfigurieren Sie die Beziehung.
   1. Wählen Sie das Attribut aus Ihrer Quellentität aus, das Ihre Kontaktentität mit einer anderen Entität verbindet.
   1. Wählen Sie die Entität aus, mit der Sie Ihre Kontaktentität verbinden möchten. Sie können eine Entität aus dem Bereich **Kontoentitäten** oder **Zwischenentität** wählen. Wenn Sie eine Zwischenentität auswählen, müssen Sie eine zweite Beziehung definieren, um eine Verbindung zu Ihrer Zielkontoentität herzustellen.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Wählen Sie entweder eine Kontoentität oder eine Zwischenentität aus.":::

   1. **Beziehungsname** angeben. Wenn bereits eine Beziehung zwischen Ihren Entitäten besteht, ist der Beziehungsname schreibgeschützt. Wenn keine Beziehung besteht, wird eine neue Beziehung mit dem von Ihnen angegebenen Namen erstellt.
   1. Wählen Sie **Anwenden**, um die Beziehungskonfiguration abzuschließen.

   > [!NOTE]
   > Sie können mehr Beziehungen zwischen der Kontaktentität und anderen Kontoentitäten mit Zwischenentitäten konfigurieren.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualisierung verschiedener Beziehungen, die Kontaktentitäten mit Kontoentitäten verbinden.":::

1. Wählen Sie **Weiter**, wenn Sie mit der Beziehungskonfiguration fertig sind.

1. In dem Schritt **Semantiktyp einstellen** wählen Sie einen **Semantischen Typ**. Aktuell gibt es einen **Semantischen Typ** namens *KontaktProfil*.

1. Ordnen Sie Ihre Daten jetzt den angezeigten Feldern *KontaktProfil* **Semantischer Typ** zu.
   - Erforderliches Feld: Kontakt-ID
   - Optionale Felder: Vorname, Nachname, Geburtsdatum, Geschlecht, primäre E-Mail-Adresse und primäre Telefonnummer

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Ordnen Sie Ihre Kontaktdatenattribute den bereitgestellten erforderlichen und optionalen Feldern zu.":::

1. Wählen Sie **Weiter** aus, um den Vorgang fortzusetzen.

1. In dem Schritt **Überprüfen** werfen Sie einen Blick auf die Konfiguration der semantischen Zuordnung. Wählen Sie **Bearbeiten** für den entsprechenden Abschnitt, um Änderungen vorzunehmen.

1. Wählen Sie **Speichern**, um Ihre neue **Semantische Zuordnung** zu speichern.

1. Nach dem Speichern können Sie den Prozess **Ausführen** auswählen, um die semantische Zuordnung zu verarbeiten oder **Schließen** wählen, um Ihre semantische Zuordnung zu speichern, ohne sie zu verarbeiten.

1. Um eine semantische Zuordnung zu einem späteren Zeitpunkt auszuführen, wählen Sie die semantische Zuordnung aus und wählen Sie **Aktualisierung**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Verwalten Sie vorhandene semantische Zuordnungen

Unter **Daten** > **Semantische Zuordnungen (Vorschau)**, können Sie alle Ihre gespeicherten semantischen Zuordnungen anzeigen und verwalten. Jede semantische Zuordnung wird durch eine separate Zeile dargestellt. Sie finden Details über die Quellentität, den semantischen Typ, den Zuordnungs-Typ und seinen Status.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Optionen zum Verwalten von semantischen Zuordnungen.":::

- **Bearbeiten**: Öffnet die Konfiguration der semantischen Zuordnungseinrichtung für den Schritt Überprüfung. Sie können die aktuelle Konfiguration ändern. Klicken Sie auf **Speichern** und **Ausführen**, um die Änderungen zu verarbeiten.

- **Aktualisierung**: Aktualisiert die ausgewählte semantische Zuordnung mit den aktuellsten Daten der Entitäten, die Teil ihrer Konfiguration sind. Das Aktualisieren einer bestimmten semantischen Zuordnung aktualisiert alle semantischen Zuordnungen desselben Typs.

- **Umbenennen**: Öffnet einen Dialog, in dem Sie einen anderen Namen für die ausgewählte semantische Zuordnung eingeben können. Wählen Sie **Speichern**, um Ihre Änderungen zu übernehmen.

- **Löschen**: Öffnet einen Dialog, um das Löschen der ausgewählten semantischen Zuordnung zu bestätigen. Sie können auch mehrere semantische Zuordnungen gleichzeitig löschen, indem Sie die semantischen Zuordnungen und das Löschsymbol auswählen. Um den Löschvorgang zu bestätigen, wählen Sie **Löschen**.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Eine semantische Entitätszuordnung von ContactProfile zum Erstellen von Aktivitäten auf Kontaktebene verwenden

Nach dem Erstellen einer semantischen Entitätszuordnung von *ContactProfile* können Sie Aktivitäten von Kontakten erfassen. Dadurch können Sie in der Aktivitätszeitleiste für ein Konto anzeigen, welcher Kontakt für jede Aktivität verantwortlich war. Die meisten Schritte folgen der typischen Aktivitätszuordnungskonfiguration.

   > [!NOTE]
   > Damit Aktivitäten auf Kontaktebene funktionieren, müssen sowohl das Attribut **AccountID** als auch das Attribut **ContactID** in Ihren Aktivitätsdaten enthalten sein.

1. [Eine semantische Entitätszuordnung von *ContactProfile* definieren](#define-a-contactprofile-semantic-entity-mapping) Führen Sie außerdem die semantische Zuordnung aus.

1. Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Aktivitäten**.

1. Wählen Sie **Aktivität hinzufügen** aus, um eine neue Aktivität zu erstellen.

1. Benennen Sie die Aktivität, wählen Sie die Quellaktivitätsentität und dann den Primärschlüssel der Aktivitätsentität aus.

1. Erstellen Sie im Schritt **Beziehungen** eine indirekte Beziehung zwischen Ihren Aktivitätsquellendaten und Konten, indem Sie Ihre Kontaktdaten als vermittelnde Entität verwenden. Weitere Informationen finden Sie unter [direkte und indirekte Beziehungspfade](relationships.md#relationship-paths).
   - Beispielbeziehung für eine Aktivität namens *Einkäufe*:
      - **Aktivitätsdaten der Einkaufsquelle** > **Kontaktdaten** auf das Attribut **ContactID**
      - **Kontaktdaten** > **Kontodaten** im Attribut **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Beispiel für die Einrichtung einer Beziehung":::

1. Wählen Sie nach dem Einrichten der Beziehung(en) **Weiter** aus, und vervollständigen Sie Ihre Aktivitätszuordnungskonfiguration. Detaillierte Schritte zum Erstellen von Aktivitäten finden Sie unter [Eine Aktivität definieren](activities.md).

1. Führen Sie Ihre Aktivitätszuordnungen aus.

1. Ihre Aktivitäten auf Kontaktebene werden jetzt auf Ihrer Kundenzeitskala angezeigt.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Endergebnis nach der Konfiguration der Kontaktaktivitäten":::

### <a name="contact-level-activity-timeline-filtering"></a>Filterung der Aktivitätszeitskala auf Kontaktebene

Nachdem Sie eine Aktivitätszuordnung auf Kontaktebene konfiguriert und ausgeführt haben, wird die Aktivitätszeitskala für Ihre Kunden aktualisiert. Je nach Ihrer *ContactProfile*-Konfiguration enthält sie die IDs oder Namen dieser Personen für die Aktivitäten, an denen sie beteiligt waren. Sie können Aktivitäten in der Zeitskala nach Kontakten filtern, um bestimmte Kontakte anzuzeigen, die Sie interessieren. Darüber hinaus können Sie alle Aktivitäten anzeigen, die keinem bestimmten Kontakt zugeordnet sind, indem Sie **Aktivitäten, die keinem Kontakt zugeordnet sind** auswählen.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Filteroptionen, die für Aktivitäten auf Kontaktebene verfügbar sind":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
