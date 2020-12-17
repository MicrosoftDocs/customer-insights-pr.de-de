---
title: Datenvereinigung
description: Erfahren Sie, wie Sie aufgenommene Daten vereinheitlichen können.
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405758"
---
# <a name="data-unification"></a>Datenvereinigung

Nachdem [Sie die Datenquellen eingerichtet haben](data-sources.md), können Sie die Daten vereinheitlichen. Die Datenvereinheitlichung umfasst drei Schritte: **Karte**, **Übereinstimmung**, und **Zusammenführung**.

Der Datenvereinheitlichungsprozess ermöglicht es Ihnen, einmal disparate Datenquellen in einem einzigen Stammdatensatz zu vereinheitlichen, der eine einheitliche Sicht auf Ihre Kunden bietet. Die Vereinheitlichungsphasen sind obligatorisch und werden in der folgenden Reihenfolge durchgeführt:

1. [Zuordnen](map-entities.md)
2. [Übereinstimmung](match-entities.md)
3. [Zusammenführen](merge-entities.md)

Nachdem Sie die Datenvereinigung abgeschlossen haben, können Sie optional

- [Beziehungen zwischen Entitäten einrichten](relationships.md), um anspruchsvolle Segmente zu erstellen
- [Ihre Daten anreichern](enrichment-hub.md), um eine breitere Palette von Einblicken über Ihre Kunden zu erhalten
- [Aktivitäten definieren](activities.md) aus einigen der eingelesenen Attribute
