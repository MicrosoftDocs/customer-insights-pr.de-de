---
title: Beziehungen zwischen Entitäten und Entitätspfaden
description: Erstellen und verwalten Sie Beziehungen zwischen Entitäten aus mehreren Datenquellen.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405796"
---
# <a name="relationships-between-entities"></a>Beziehungen zwischen Entitäten

Beziehungen helfen Ihnen, Entitäten zu verbinden und ein Diagramm Ihrer Daten zu erstellen, wenn Entitäten einen gemeinsamen Identifikator (Fremdschlüssel) haben, auf den von einer Entität zu einer anderen verwiesen werden kann. Verbundene Entitäten ermöglichen Ihnen die Definition von Segmenten und Maßen auf der Grundlage mehrerer Datenquellen.

Es gibt zwei Arten von Beziehungen. Nicht editierbare Systembeziehungen, die automatisch erstellt werden, und benutzerdefinierte Beziehungen, die von Benutzern erstellt und konfiguriert werden.

Während der Abgleich- und Zusammenführungsprozesse werden hinter den Kulissen Systembeziehungen auf der Grundlage eines intelligenten Abgleichs erstellt. Diese Beziehungen helfen dabei, die Kundenprofilsätze mit den Datensätzen anderer entsprechender Entitäten in Beziehung zu setzen. Das folgende Diagramm veranschaulicht die Erstellung von drei Systembeziehungen, wenn die Kundenentität mit zusätzlichen Entitäten abgeglichen wird, um die endgültige Entität Kundenprofil zu erzeugen.

> [!div class="mx-imgBorder"]
> ![Beziehungserstellung](media/relationships-entities-merge.png "Erstellung von Beziehungen")

- ***CustomerToContact*-Beziehung** wurde zwischen der Entität Kunde und der Entität Kontakt erstellt. Die Entität Kunde erhält das Schlüsselfeld **Contact_contactId**, das sich auf das Schlüsselfeld Kontakt-Entität **contactId** bezieht.
- **_CustomerToAccount_-Beziehung** wurde zwischen der Entität Kunde und der Entität Konto erstellt. Die Entität Kunde erhält das Schlüsselfeld **Account_accountId**, das sich auf das Schlüsselfeld Kontoentität **AccountId** bezieht.
- **_CustomerToWebAccount_-Beziehung** wurde zwischen der Entität Kunde und der Entität WebAccount angelegt. Die Entität Kunde erhält das Schlüsselfeld **WebAccount_webaccountId**, das sich auf das Schlüsselfeld der Entität WebAccount **webaccountId** bezieht.

## <a name="create-a-relationship"></a>Erstellen einer Beziehung

Definieren Sie benutzerdefinierte Beziehungen auf der Seite **Beziehungen**. Jede Beziehung besteht aus einer Quell-Entität (die Entität, die den Fremdschlüssel enthält) und einer Ziel-Entität (die Entität, auf die der Fremdschlüssel der Quell-Entität zeigt).

1. Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Beziehungen**.

2. Wählen Sie **Neue Beziehung**.

3. Geben Sie im Fensterbereich **Beziehung hinzufügen** die folgenden Informationen an:

   > [!div class="mx-imgBorder"]
   > ![Beziehungsdetails eingeben](media/relationships-add.png "Beziehungsdetails eingeben")

   - **Beziehungsname**: Name, der den Zweck der Beziehung widerspiegelt (z. B. **AccountWebLogs**).
   - **Beschreibung:**: Beschreibung der Beziehung.
   - **Quellentität**: Wählen Sie die Entität aus, die als Quelle in der Beziehung verwendet wird (z. B. WebLog).
   - **Kardinalität**: Wählen Sie die Kardinalität der Quell-Entitätsdatensätze aus. Beispielsweise bedeutet „viele“, dass mehrere Weblog-Einträge mit einem WebAccount verbunden sind.
   - **Quellschlüsselfeld**: Dies stellt das Fremdschlüsselfeld in der Quellentität dar. Beispielsweise hat WebLog das Schlüsselfeld **KontoId**-Fremdschlüssel.
   - **Zielentität**: Wählen Sie die Entität, die als Ziel in der Beziehung verwendet wird (z. B. WebAccount).
   - **Zielkardinalität**: Wählen Sie die Kardinalität der Zielentitätsdatensätze aus. Beispielsweise bedeutet „einer“, dass mehrere Weblog-Einträge mit einem WebAccount verbunden sind.
   - **Zielschlüsselfeld**: Dieses Feld stellt das Schlüsselfeld der Zielentität dar. Beispielsweise hat WebAccount das Schlüsselfeld **KontoId**.

> [!NOTE]
> Es werden nur Viele-zu-Eins und Eins-zu-Eins-Beziehungen unterstützt. Many-to-Many-Beziehungen können mit Hilfe von zwei Many-to-One-Beziehungen und einer Link-Entität (eine Entität, die zur Verbindung zwischen der Quell- und der Ziel-Entität verwendet wird) erstellt werden.

## <a name="delete-a-relationship"></a>Beziehung löschen

1. Gehen Sie in den Zielgruppen-Insights zu **Daten** > **Beziehungen**.

2. Markieren Sie die Ankreuzfelder für die Beziehungen, die Sie löschen möchten.

3. Wählen Sie **Löschen** oben in der Tabelle **Beziehungen**.

4. Bestätigen Sie den Löschvorgang.

## <a name="next-step"></a>Nächster Schritt

System- und benutzerdefinierte Beziehungen werden verwendet, um Segmente auf der Grundlage mehrerer Datenquellen zu erstellen, die nicht mehr in einem Silo gespeichert sind. Weitere Informationen finden Sie unter [Segmente](segments.md).
