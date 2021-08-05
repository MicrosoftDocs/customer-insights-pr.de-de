---
title: Zuordnen von Entitäten zur Datenvereinheitlichung
description: Ordnen Sie Daten zu, um einheitliche Kundenprofile zu erstellen.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7fc05aca61d1136f620019ee82dc6937ea39d8e5
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555122"
---
# <a name="map-entities-and-attributes"></a>Entitäten und Attribute zuordnen

**Zuordnen** ist die erste Stufe im Datenvereinheitlichungsprozess von Zielgruppen-Insights. Das Mapping besteht aus drei Phasen:

- *Entitätsauswahl*: Identifizieren Sie die kombinierbaren Entitäten, die zu einem Datensatz mit vollständigeren Informationen über Ihre Kunden führen.
- *Attributauswahl*: Identifizieren Sie für jede Entität die Spalten, die Sie in den Phasen *Abgleich* und *Zusammenführung* kombinieren und abstimmen möchten. Diese Spalten werden *Attribute* genannt.
- *Auswahl des Primärschlüssels und des semantischen Typs*: Identifizieren Sie für jede Entität ein Attribut, das Sie als Primärschlüssel für diese Entität definieren möchten, und identifizieren Sie für jedes Attribut einen semantischen Typ, der dieses Attribut am besten beschreibt.

Weitere Informationen über den allgemeinen Flow der Datenvereinheitlichung finden Sie unter [Vereinheitlichung](data-unification.md).

## <a name="select-the-first-entities"></a>Wählen Sie die ersten Entitäten

1. Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Vereinheitlichen** > **Karte**.

2. Beginnen Sie die Mappingphase, indem Sie **Entitäten auswählen** wählen.

3. Wählen Sie die Entitäten und Attribute aus, die Sie in den Phasen *Abgleichen* und *Zusammenführen* verwenden wollen. Sie können die erforderlichen Attribute einzeln aus einer Entität auswählen oder alle Attribute aus einer Entität einschließen, indem Sie das Kontrollkästchen **Alle Felder einschließen** auf Entitätsebene auswählen. Wir empfehlen die Auswahl von mindestens zwei Entitäten, die von dem Datenvereinheitlichungsprozess profitieren.

   > [!div class="mx-imgBorder"]
   > ![Beispiel für das Hinzufügen von Entitäten.](media/data-manager-configure-map-add-entities-example.png "Beispiel für das Hinzufügen von Entitäten")

   In diesem Beispiel fügen wir die Entitäten **eCommerceContacts** und **loyCustomers** hinzu. Durch Auswahl dieser Entitäten können Sie Erkenntnisse darüber gewinnen, welche der Online-Geschäftskunden Mitglieder des Treueprogramms sind.
   
   Sie können nach Schlüsselwörtern in allen Attributen und Entitäten suchen, um die erforderlichen Attribute auszuwählen, die Sie zuordnen möchten.
   
     > [!div class="mx-imgBorder"]
   > ![Beispiel für Suchfelder.](media/data-manager-configure-map-search-fields-example.png "Beispiel für Suchfelder")

4. Wählen Sie **Anwenden**, um Ihre Auswahl zu bestätigen.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Wählen Sie den Primärschlüssel und den semantischen Typ für Attribute aus

Nach Auswahl Ihrer Entitäten wird die Seite **Karte** die ausgewählten Entitäten zu Ihrer Überprüfung auflisten. Definieren Sie den Primärschlüssel für eine Entität und identifizieren Sie den semantischen Typ für ein Attribut in der Entität.

- **Primärschlüssel**: Wählen Sie ein Attribut als Primärschlüssel für jede Ihrer Entitäten aus. Damit ein Attribut ein gültiger Primärschlüssel ist, sollte es keine doppelten Werte, fehlenden Werte oder Nullwerte enthalten. Zeichenfolgen-, Integer- und GUID-Datentypattribute werden als Primärschlüssel unterstützt und in einem Feld angezeigt, aus dem Sie auswählen können.

- **Semantischer Attributtyp**: Kategorien Ihrer Attribute, wie z. B. E-Mail-Adresse oder Name. Um KI-Modelle für intelligente Vorhersage der Semantik zu verwenden, Zeit zu sparen und die Genauigkeit zu verbessern, stellen Sie **Intelligentes Mapping** auf **AN**. Intelligentes Mapping hebt die KI-basierte Semantikempfehlung im **Typ**-Feld hervor. Wenn Sie es auf **AUS** stellen, sehen Sie unsere regulären Mappingempfehlungen. Sie können einen beliebigen semantischen Typ aus der Liste verfügbarer Optionen auswählen und die vorgeschlagene Auswahl außer Kraft setzen.

> [!div class="mx-imgBorder"]
> ![Attributtyp und Semantikvorhersage.](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attributtyp und Semantikvorhersage")

Das Hinzufügen eines benutzerdefinierten semantischen Typs ist ebenfalls möglich. Wählen Sie das Typ-Feld für dieses Attribut und geben Sie Ihren benutzerdefinierten Namen des semantischen Typs ein. Auf diese Weise können Sie auch die Attributtypen ändern, die vom System identifiziert wurden.

Alle Attribute, für die ein semantischer Typ automatisch identifiziert wird, sind im Abschnitt **Überprüfen zugeordneter Felder** zusammengefasst. Überprüfen Sie diese Attribute und ihre semantischen Typen, da sie verwendet werden, um Ihre Entitäten im Zusammenführungsschritt der Datenvereinigung zu kombinieren.

Attribute, die nicht automatisch einem semantischen Typ zugeordnet werden, werden im Abschnitt **Definieren der Daten in den nicht zugeordneten Feldern** zusammengefasst. Wählen Sie das Feld für den semantischen Typ für die nicht zugeordneten Attribute aus, oder geben Sie Ihren benutzerdefinierten Attributtypnamen ein.

> [!div class="mx-imgBorder"]
> ![Primärschlüssel und Attributtyp.](media/data-manager-configure-map-add-attributes.png "Primärschlüssel und Attributtyp")

> [!NOTE]
> Ein Feld sollte dem semantischen Typ Person.FullName zugeordnet sein, um den Kundennamen auf der Kundenkarte auszufüllen. Andernfalls erscheinen die Kundenkarten namenlos. 

## <a name="add-and-remove-attributes-and-entities"></a>Hinzufügen und Entfernen von Attributen und Entitäten

1. Wählen -Sie auf **Vereinheitlichen** > **Karte** **Felder bearbeiten**.

2. In dem Bereich **Felder bearbeiten** fügen Sie Attribute oder Entitäten hinzu oder entfernen sie diese. Verwenden Sie die Suche oder den Bildlauf, um Ihre Attribute und Objekte von Interesse zu finden und auszuwählen. Sie können ein Attribut oder eine Entität nicht entfernen, wenn sie bereits übereinstimmen.

   > [!div class="mx-imgBorder"]
   > ![Hinzufügen oder Entfernen von Attributen.](media/configure-data-map-edit.png "Attribute hinzufügen oder entfernen")

3. Wählen Sie **Übernehmen** aus.

## <a name="add-images-to-profiles"></a>Hinzufügen von Bildern zu Profilen

Wenn eine Entität URLs zu öffentlich verfügbaren Profilbildern oder Logos enthält, können Sie diese dem einheitlichen Kundenprofil hinzufügen.

Wählen Sie die Entität aus und suchen Sie das Feld, das die URL zum Profilbild enthält. Geben Sie im Eingabefeld **Typ** manuell den folgenden Wert ein: 
- Für eine Person: Person.ProfileImage
- Für eine Organisation: Organization.LogoImage

Fahren Sie mit den Vereinigungsschritten fort und stellen Sie sicher, dass das Attribut, das die Bild-URL enthält, auch im Schritt [Zusammenführen](merge-entities.md) zusammengeführt wird.

## <a name="set-attributes-for-organizations"></a>Setzen Sie Attribute für Organisationen

Bei Organisationen (Vorschau) sollte der Attributtyp auf „Organization.Name“ abgebildet werden
> [!div class="mx-imgBorder"]
> ![Primärschlüssel und Attributtyp B2B](media/configure-data-map-edit-b2b.png "Primärschlüssel und Attributtyp B2B")

## <a name="next-step"></a>Nächster Schritt

Als Teil des Datenvereinheitlichungsprozesses gehen Sie auf die Seite **Abgleich**. Besuchen Sie [**Abgleichen**](match-entities.md) um mehr über diese Phase zu erfahren.

> [!TIP]
> Sehen Sie sich das folgende Video an: [Einstieg: Erstellen eines einheitlichen Kundenprofils](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]