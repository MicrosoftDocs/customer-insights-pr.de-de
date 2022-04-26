---
title: Neue Kennzahlen mit dem Kennzahlen-Builder erstellen
description: Erstellen Sie Kennzahlen von Grund auf neu, um wichtige Metriken zu Ihrem Unternehmen zu analysieren.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: 6370df0287362a5512a837cdb588f5d20ef03d3b
ms.sourcegitcommit: e129a1fa8b020b6bfb6efc3c53fa9d89e1614ad1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2022
ms.locfileid: "8561532"
---
# <a name="use-measure-builder-to-create-measures-from-scratch"></a>Kennzahlen-Builder verwenden, um Kennzahlen von Grund auf neu zu erstellen

In diesem Artikel wird erklärt, wie Sie eine neue [Kennzahl](measures.md) von Grund auf neu erstellen. Mit dem Kennzahlen-Builder können Sie Berechnungen mit mathematischen Operatoren, Aggregationsfunktionen und Filtern definieren. Sie können eine Kennzahl mit Attributen von Entitäten erstellen, die sich auf die vereinheitlichte Entität *Kunde* beziehen.

Das Erstellen von Kennzahlen in B2C‑ und B2B-Umgebungen funktioniert auf die gleiche Weise. Wenn Ihre B2B-Umgebung allerdings [Konten mit Hierarchien verwendet](relationships.md#set-up-account-hierarchies), können Sie die Kennzahl über zugehörige Firmen aggregieren.

Sie können auch schnell eine Kennzahl erstellen, indem Sie aus einer Reihe häufig verwendeter und vordefinierter Kennzahlen auswählen. Weitere Informationen finden Sie unter [Vorlage zum Erstellen einer Kennzahl verwenden](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Einzelne Verbraucher (B2C)](#tab/b2c)

Sie können Kennzahlen auf der Ebene einzelner Kunden (Kundenattribut, Kundenkennzahl) oder auf der Ebene des Unternehmens/der Organisation (Geschäftskennzahl) erstellen. Kundenattribut und Kundenkennzahl sind zwei Typen, mit denen Sie die Leistung pro Kunde verfolgen können. Zum Beispiel die Gesamtausgaben jedes Kunden. Geschäftskennzahlen ermöglichen es Ihnen, die Leistung pro Unternehmen zu verfolgen. Beispielsweise der Gesamtumsatz des Unternehmens.

- Kundenattribut: Generiert eine Ausgabe als neues Attribut, das als neue Spalte in der vom System generierten Entität namens *Kunde_Kennzahl* gespeichert wird. Beim Aktualisieren eines Kundenattributs werden alle anderen Kundenattribute in der Entität *Kunde_Kennzahl* gleichzeitig aktualisiert. Darüber hinaus werden Kundenattribute in der Kundenprofilkarte angezeigt. Sobald sie einmal ausgeführt oder gespeichert wurden, können Sie das Kundenattribut nicht in eine Kundenkennzahl ändern.

- Kundenkennzahl: Generiert eine Ausgabe als eigene Entität und Sie können sie nach der Ausführung oder Speicherung nicht mehr in ein Kundenattribut ändern. Kundenkennzahlen werden nicht auf der Kundenprofilkarte angezeigt.

- Geschäftskennzahl: Erzeugt die Ausgabe als eigene Entität und zeigt sie auf der Startseite Ihrer Customer Insights-Umgebung an.

1. Gehen Sie zu **Kennzahlen**.

1. Wählen Sie **Neu** und dann **Eigene erstellen** aus.

   :::image type="content" source="media/measure-b2c.png" alt-text="Leerer Konfigurationsbildschirm für eine B2C-Kennzahl." lightbox="media/measure-b2c.png":::

1. Um die Leistung auf Unternehmensebene zu verfolgen, schalten Sie **Art messen** zu **Geschäftsebene**. **Kundenebene** ist standardmäßig ausgewählt. **Kundenebene** fügt automatisch das *CustomerId* Attribut zu Dimensionen hinzu während **Geschäftsebene** es automatisch entfernt.

1. Wählen Sie im Konfigurationsbereich die Aggregationsfunktion aus dem Dropdown-Menü **Funktion auswählen** aus. Zu den Aggregationsfunktionen gehören:
   - **Sum**
   - **Durchschnitt**
   - **Anzahl**
   - **Anzahl einzigartiger Elemente**
   - **Max.**
   - **Min.**
   - **Zuerst** – verwendet den ersten Wert des Datensatzes
   - **Letzte**: Nimmt den letzten Wert, der dem Datensatz hinzugefügt wurde
   - **ArgMax**: findet den Datensatz, der den Maximalwert einer Zielfunktion angibt
   - **ArgMin**: findet den Datensatz, der den Mindestwert einer Zielfunktion angibt

1. WählenSie **Attribute hinzufügen**, um die Daten auszuwählen, die Sie zum Erstellen dieser Kennzahl benötigen.

   1. Die **Attribute**-Registerkarte auswählen.
   1. Datenentität: Wählen Sie die Entität aus, die das Attribut enthält, das Sie messen möchten.
   1. Datenattribut: Wählen Sie das Attribut aus, das Sie in der Aggregationsfunktion zur Berechnung der Kennzahl verwenden möchten. Sie können jeweils nur ein Attribut auswählen.
   1. Sie können auch ein Datenattribut aus einer vorhandenen Kennzahl auswählen, indem Sie die Registerkarte **Kennzahlen** auswählen oder Sie können auch nach einem Entitäts- oder Kennzahlnamen suchen.
   1. WählenSie **Hinzufügen**, um das ausgewählte Attribut zur Kennzahl hinzuzufügen.

1. Um komplexere Kennzahlen zu erstellen, können Sie weitere Attribute hinzufügen oder mathematische Operatoren für Ihre Kennzahlfunktion verwenden.

1. Um Filter hinzuzufügen, wählen Sie **Filter** im Konfigurationsbereich. Beim Anwenden von Filtern werden nur die Datensätze verwendet, die den Filtern entsprechen, um die Kennzahl zu berechnen.
  
   1. In dem Abschnitt **Attribute hinzufügen** des Bereichs **Filter** wählen Sie im Bereich das Attribut aus, das Sie zum Erstellen von Filtern verwenden möchten.
   1. Legen Sie die Filteroperatoren fest, um den Filter für jedes ausgewählte Attribut zu definieren.
   1. Wählen Sie **Anwenden**, um den Filter zur Kennzahl hinzuzufügen.

1. Wählen Sie **Dimension**, um weitere Felder auszuwählen, die als Spalten zur Kennzahlausgabeentität hinzugefügt werden.

   1. Wählen Sie **Dimensionen bearbeiten** aus, um Datenattribute hinzuzufügen, nach denen Sie die Kennzahlen gruppieren möchten. Zum Beispiel Stadt oder Geschlecht.
   > [!TIP]
   > Wenn Sie **Kundenebene** als **Messungstyp** auswählen, ist das *CustomerId* Attribut bereits hinzugefügt. Wenn Sie das Attribut entfernen, wird **Messungstyp** auf **Geschäftsebene** umgeschaltet.
   1. Wählen Sie **Fertig**, um die Dimensionen zur Kennzahl hinzuzufügen.

1. Wenn Ihre Daten Werte enthalten, die Sie durch eine ganze Zahl ersetzen müssen, wählen Sie **Regeln**. Konfigurieren Sie die Regel und stellen Sie sicher, dass Sie nur ganze Zahlen als Ersatz auswählen. Ersetzen Sie beispielsweise *Null* mit *0*.

1. Wenn zwischen der von Ihnen zugeordneten Datenentität und der *Kunden* Entität mehrere Pfade vorhanden sind, müssen Sie einen der identifizierten [Entitätsbeziehungspfade auswählen](relationships.md). Die Kennzahlenergebnisse können je nach ausgewähltem Pfad variieren.

   1. Wählen Sie **Beziehungspfad** und wählen Sie den Entitätspfad aus, der zum Identifizieren Ihrer Kennzahl verwendet werden soll. Wenn es nur einen einzigen Weg zur Entität *Kunde* gibt, wird dieses Steuerelement nicht angezeigt.
   1. Wählen **Fertig**, um Ihre Auswahl anzuwenden.

1. Wählen Sie aus **Neue Berechnung**, um weitere Berechnungen für die Kennzahl hinzuzufügen. Sie können nur Entitäten im selben Entitätspfad für neue Berechnungen verwenden. Weitere Berechnungen werden als neue Spalten in der Kennzahlausgabeeinheit angezeigt.

1. Wählen Sie **...** für die Berechnung aus, um **Duplikat**, **Umbenennen** oder **Entfernen** zur Berechnung einer Kennzahl auszuwählen.

1. Im Bereich **Vorschau** sehen Sie das Datenschema der Kennzahlausgabeentität, einschließlich Filter und Dimensionen. Die Vorschau reagiert dynamisch auf Änderungen in der Konfiguration.

1. Wählen Sie **Details bearbeiten** neben Takt ohne Titel. Benennen Sie die Messung. Fügen Sie optional [Tags](work-with-tags-columns.md#manage-tags) zur Messung hinzu.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialogfeld „Details bearbeiten“":::

1. Wählen **Ausführen**, um die Ergebnisse für die konfigurierte Messung zu berechnen. Wählen Sie **Speichern und schließen** aus, wenn Sie die aktuelle Konfiguration beibehalten und die Kennzahlmessung später ausführen möchten.

1. Gehen Sie zu **Kennzahlen**, um die neu erstellte Kennzahl in der Liste anzuzeigen.

# <a name="business-accounts-b-to-b"></a>[Unternehmenskonten (B2B)](#tab/b2b)

Sie können Kennzahlen auf der Ebene einzelner Konten (Kundenkennzahl) oder auf der Ebene aller Konten (Geschäftskennzahl) erstellen.

- Kundenkennzahl: Erzeugt die Ausgabe als eigene Entität. Kundenkennzahlen werden nicht auf der Kundenprofilkarte angezeigt.

- Geschäftskennzahl: Erzeugt die Ausgabe als eigene Entität und zeigt sie auf der Startseite Ihrer Customer Insights-Umgebung an.

1. Gehen Sie zu **Kennzahlen**.

1. Wählen Sie **Neu** aus.

   :::image type="content" source="media/measure-b2b.png" alt-text="Leerer Konfigurationsbildschirm für eine B2B-Kennzahl.":::

1. Wählen Sie im Konfigurationsbereich die Aggregationsfunktion aus dem Dropdown-Menü **Funktion auswählen** aus. Zu den Aggregationsfunktionen gehören:
   - **Sum**
   - **Durchschnitt**
   - **Anzahl**
   - **Anzahl einzigartiger Elemente**
   - **Max.**
   - **Min.**
   - **Zuerst** – verwendet den ersten Wert des Datensatzes
   - **Letzte**: Nimmt den letzten Wert, der dem Datensatz hinzugefügt wurde

1. WählenSie **Attribute hinzufügen**, um die Daten auszuwählen, die Sie zum Erstellen dieser Kennzahl benötigen.

   1. Die **Attribute**-Registerkarte auswählen.
   1. Datenentität: Wählen Sie die Entität aus, die das Attribut enthält, das Sie messen möchten.
   1. Datenattribut: Wählen Sie das Attribut aus, das Sie in der Aggregationsfunktion zur Berechnung der Kennzahl verwenden möchten. Sie können jeweils nur ein Attribut auswählen.
   1. Sie können auch ein Datenattribut aus einer vorhandenen Kennzahl auswählen, indem Sie die Registerkarte **Kennzahlen** auswählen oder Sie können auch nach einem Entitäts- oder Kennzahlnamen suchen.
   1. WählenSie **Hinzufügen**, um das ausgewählte Attribut zur Kennzahl hinzuzufügen.

1. Um komplexere Kennzahlen zu erstellen, können Sie weitere Attribute hinzufügen oder mathematische Operatoren für Ihre Kennzahlfunktion verwenden.

1. Um Filter hinzuzufügen, wählen Sie **Filter** im Konfigurationsbereich. Beim Anwenden von Filtern werden nur die Datensätze verwendet, die den Filtern entsprechen, um die Kennzahl zu berechnen.
  
   1. In dem Abschnitt **Attribute hinzufügen** des Bereichs **Filter** wählen Sie im Bereich das Attribut aus, das Sie zum Erstellen von Filtern verwenden möchten.
   1. Legen Sie die Filteroperatoren fest, um den Filter für jedes ausgewählte Attribut zu definieren.
   1. Wählen Sie **Anwenden**, um den Filter zur Kennzahl hinzuzufügen.

1. Wählen Sie **Dimension**, um weitere Felder auszuwählen, die als Spalten zur Kennzahlausgabeentität hinzugefügt werden.

   1. Wählen Sie **Dimensionen bearbeiten** aus, um Datenattribute hinzuzufügen, nach denen Sie die Kennzahlen gruppieren möchten. Zum Beispiel Stadt oder Geschlecht.
      > [!TIP]
      > Wenn Sie **Kundenebene** als **Messungstyp** auswählen, ist das *CustomerId* Attribut bereits hinzugefügt. Wenn Sie das Attribut entfernen, wird **Messungstyp** auf **Geschäftsebene** geändert.
   1. Wählen Sie **Fertig**, um die Dimensionen zur Kennzahl hinzuzufügen.

1. Wenn Ihre Daten Werte enthalten, die Sie durch eine ganze Zahl ersetzen müssen, wählen Sie **Regeln**. Konfigurieren Sie die Regel und stellen Sie sicher, dass Sie nur ganze Zahlen als Ersatz auswählen. Ersetzen Sie beispielsweise *Null* mit *0*.

1. Sie können die Umschaltung **Unterkonten aufrollen** verwenden, um [Konten mit Hierarchien zu verwenden](relationships.md#set-up-account-hierarchies).
   - Wenn auf **Aus** festgelegt, wird die Kennzahl für jedes Konto berechnet. Jedes Konto erhält ein eigenes Ergebnis.
   - Wenn auf **Ein** festgelegt, wählen Sie **Bearbeiten**, um die Kontenhierarchie gemäß den aufgenommenen Hierarchien auszuwählen. Die Kennzahl liefert nur ein Ergebnis, da sie mit Unterkonten aggregiert wird.

1. Wenn zwischen der von Ihnen zugeordneten Datenentität und der *Kunden* Entität mehrere Pfade vorhanden sind, müssen Sie einen der identifizierten [Entitätsbeziehungspfade auswählen](relationships.md). Die Kennzahlenergebnisse können je nach ausgewähltem Pfad variieren.

   1. Wählen Sie **Beziehungspfad** und wählen Sie den Entitätspfad aus, der zum Identifizieren Ihrer Kennzahl verwendet werden soll. Wenn es nur einen einzigen Weg zur Entität *Kunde* gibt, wird dieses Steuerelement nicht angezeigt.
   1. Wählen **Fertig**, um Ihre Auswahl anzuwenden.

1. Wählen Sie **...** für die Berechnung aus, um **Duplikat**, **Umbenennen** oder **Entfernen** zur Berechnung einer Kennzahl auszuwählen.

1. Im Bereich **Vorschau** sehen Sie das Datenschema der Kennzahlausgabeentität, einschließlich Filter und Dimensionen. Die Vorschau reagiert dynamisch auf Änderungen in der Konfiguration.

1. Wählen Sie **Details bearbeiten** neben Takt ohne Titel. Benennen Sie die Messung. Fügen Sie optional [Tags](work-with-tags-columns.md#manage-tags) zur Messung hinzu.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialogfeld „Details bearbeiten“":::

1. Wählen **Ausführen**, um die Ergebnisse für die konfigurierte Messung zu berechnen. Wählen Sie **Speichern und schließen** aus, wenn Sie die aktuelle Konfiguration beibehalten und die Kennzahlmessung später ausführen möchten.

1. Gehen Sie zu **Kennzahlen**, um die neu erstellte Kennzahl in der Liste anzuzeigen.
