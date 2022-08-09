---
title: Wählen von Quellfeldern für die Datenvereinheitlichung
description: Der erste Schritt im Vereinheitlichungsprozess ist die Auswahl von Entitäten, Attributen, Primärschlüsseln und semantischen Typen, um Daten dem Unified customer profile zuzuordnen.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a75218c996b277e00924f2b7b38ea686a1f4dc38
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139781"
---
# <a name="select-source-fields-for-data-unification"></a>Wählen von Quellfeldern für die Datenvereinheitlichung

Der erste Schritt bei der Vereinheitlichung ist die Auswahl der Entitäten und Felder in Ihren DataSets, die Sie vereinheitlichen möchten. Wählen Sie Entitäten aus, die kundenbezogene Details wie Name, Adresse, Telefonnummer und E-Mail enthalten. Sie können eine oder mehrere Entitäten auswählen.

## <a name="select-entities-and-fields"></a>Entitäten und Felder auswählen

1. Gehen Sie zu **Daten** > **Vereinheitlichen**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Screenshot der Unify-Angebotsseite für die erste Ausführung, wobei „Erste Schritte“ hervorgehoben ist.":::

1. Wählen Sie **Erste Schritte** aus.

1. Auf der Seite **Quellfelder** wählen Sie **Entitäten und Felder auswählen**. Der Bereich **Entitäten und Felder auswählen** wird angezeigt.

1. Wählen Sie mindestens eine Entität.

1. Identifizieren Sie für jede ausgewählte Entität die Felder, die Sie verwenden möchten, um Kundendatensätze und Felder abzugleichen, die in das einheitliche Profil aufgenommen werden sollen. Diese Felder werden *Attribute* genannt. Sie können die erforderlichen Attribute einzeln aus einer Entität auswählen oder alle Attribute einer Entität einbeziehen, indem Sie das Kontrollkästchen auf Entitätsebene aktivieren. Sie können nach Schlüsselwörtern in allen Attributen und Entitäten suchen, um die erforderlichen Attribute auszuwählen, die Sie zuordnen möchten.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Screenshot der ausgewählten Entitäten und Attribute":::

   In diesem Beispiel fügen wir die Entitäten **Contacts** und **CustomerLoyalty** hinzu. Durch Auswahl dieser Entitäten können Sie Erkenntnisse darüber gewinnen, welche der Online-Geschäftskunden Mitglieder des Treueprogramms sind.

1. Wählen Sie **Anwenden**, um Ihre Auswahl zu bestätigen. Die ausgewählten Entitäten und Attribute werden angezeigt.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Wählen Sie den Primärschlüssel und den semantischen Typ für Attribute aus

   :::image type="content" source="media/m3_select_primary.png" alt-text="Screenshot ausgewählter Entitäten mit nicht ausgewähltem Primärschlüssel." lightbox="media/m3_select_primary.png":::

Führen Sie für jede Entität die folgenden Schritte aus.

1. Wählen Sie den **Primärschlüssel**. Der Primärschlüssel ist ein für die Entität eindeutiges Attribut. Damit ein Attribut ein gültiger Primärschlüssel ist, sollte es keine doppelten Werte, fehlenden Werte oder Nullwerte enthalten. Als Primärschlüssel werden String-, Integer- und GUID-Datentypattribute unterstützt.

1. Stellen Sie sicher, dass **Intelligente Zuordnung** aktiviert ist, damit Sie KI-Modelle für eine intelligente Vorhersage der Semantik verwenden, Zeit sparen und die Genauigkeit verbessern können. Intelligentes Mapping hebt die KI-basierte Semantikempfehlung im **Typ**-Feld hervor. Sie können die vorgeschlagene Auswahl überschreiben, indem Sie einen beliebigen Semantiktyp aus der Liste der verfügbaren Optionen auswählen.

1. Wählen Sie für jedes Attribut einen semantischen **Typ** aus, der dieses Attribut am besten beschreibt, z. B. Name, Stadt oder E-Mail-Adresse.

   > [!NOTE]
   > Ein Feld sollte dem semantischen Typ *Person.FullName* zugeordnet werden, um den Kundennamen in die Kundenkarte einzutragen. Andernfalls erscheinen die Kundenkarten namenlos.

   1. Um den Attributtyp zu ändern, der vom System identifiziert wurde, wählen Sie einen anderen Typ. Wenn der Typ nicht vorhanden ist, erstellen Sie einen benutzerdefinierten semantischen Typ, indem Sie das Feld **Typ** für das Attribut auswählen und den Namen Ihres benutzerdefinierten semantischen Typs eingeben.

   1. Um öffentlich zugänglichen Profilbildern oder Logos ein Attribut hinzuzufügen, das eine URL enthält, wählen Sie die Entität und das Feld aus, das die URL enthält. Geben Sie im Feld **Typ** Folgendes ein:
      - Für eine Person: Person.ProfileImage
      - Für eine Organisation: Organization.LogoImage

   1. Geben Sie für ein Kontonamensattribut „Organization.Name“ in das Feld **Typ** ein.

1. Überprüfen Sie die Attribute, bei denen ein semantischer Typ automatisch identifiziert wird. Diese Attribute sind unter **Zugeordnete Felder überprüfen** aufgelistet. Im Schritt **Vereinheitlichte Kundenfelder** können nur Attribute des gleichen Typs kombiniert werden. Semantische Typen werden verwendet, um Erkenntnisse automatisch vorzuschlagen. Stellen Sie sicher, dass die ausgewählten Typen für alle ausgewählten Entitäten konsistent sind.

1. Wählen Sie für Attribute, die nicht automatisch einem Semantiktyp zugeordnet werden, ein Semantiktypfeld aus, geben Sie Ihren benutzerdefinierten Attributtypnamen ein, oder lassen Sie sie nicht zugeordnet. Diese Attribute sind unter **Daten in nicht zugeordneten Feldern definieren** aufgelistet.

1. Nachdem Sie die Schritte für jede Entität abgeschlossen haben, wählen Sie **Quellfelder speichern**.

1. Wählen Sie **Weiter** aus.

> [!div class="nextstepaction"]
> [Nächster Schritt: Duplikate entfernen](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
