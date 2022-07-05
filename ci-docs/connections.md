---
title: Verbindungsübersicht (Vorschauversion)
description: Verbindungen zu anderen Diensten von Customer Insights.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: a8b4b8a9bdcf7cf43c47a67d547405dd20dad60d
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080972"
---
# <a name="connections-preview-overview"></a>Verbindungsübersicht (Vorschauversion)

Verbindungen sind der Schlüssel, um die gemeinsame Nutzung von Daten zu und von Customer Insights zu ermöglichen. Jede Verbindung stellt die gemeinsame Nutzung von Daten mit einem bestimmten Dienst her. Verbindungen sind das Fundament zum [Konfigurieren von Anreicherungen von Drittanbietern](enrichment-hub.md) und [Konfigurieren von Exporten](export-destinations.md). Dieselbe Verbindung kann mehrfach verwendet werden. Beispielsweise funktioniert eine Verbindung zu Dynamics 365 Marketing für mehrere Exporte, und eine Leadspace-Verbindung kann für mehrere Anreicherungen verwendet werden.

Gehen Sie zu **Administrator** > **Verbindungen**, um Verbindungen zu erstellen und anzuzeigen.

Die Registerkarte **Verbindungen** zeigt Ihnen alle aktiven Verbindungen. Die Liste zeigt eine Zeile für jede Verbindung.

Verschaffen Sie sich einen schnellen Überblick, erhalten Sie eine Beschreibung, und finden Sie heraus, was Sie mit den einzelnen Erweiterungsoptionen auf der Registerkarte **Entdecken** tun können.

## <a name="exports"></a>Exporte

Nur Administratoren können neue Verbindungen konfigurieren, sie können jedoch Mitwirkenden Zugriff gewähren, um vorhandene Verbindungen zu verwenden. Administratoren steuern, wohin Daten gehen können, und die Mitwirkenden definieren die Nutzlast und Häufigkeit, die ihren Anforderungen entsprechen. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](#allow-contributors-to-use-a-connection-for-exports).

## <a name="enrichments"></a>Anreicherungen

Nur Administratoren können neue Verbindungen konfigurieren, aber die erstellten Verbindungen stehen sowohl Administratoren als auch Mitwirkenden immer zur Verfügung. Administratoren verwalten Anmeldeinformationen und stimmen der Datenübertragung zu. Die Verbindungen können dann sowohl von Administratoren als auch von Mitwirkenden zur Bereicherung verwendet werden.

## <a name="add-a-new-connection"></a>Eine neue Verbindung hinzufügen

Um Verbindungen hinzuzufügen, müssen Sie [Administratorberechtigungen](permissions.md) haben. Wenn Sie eine Verbindung zu anderen Microsoft-Diensten herstellen, gehen wir davon aus, dass sich beide Dienste in derselben Organisation befinden.

1. Gehen Sie zu **Administrator** > **Verbindungen (Vorschauversion)**.

1. Zur Registerkarte **Verbindungen** wechseln.

1. Wählen Sie zu **Verbindung hinzufügen**, um eine neue Verbindung zu erstellen. Wählen Sie aus dem Dropdown-Menü aus, welche Art von Verbindung Sie erstellen möchten.

1. Im Bereich **Verbindung herstellen** geben Sie die erforderlichen Details an.
   1. Der **Anzeigename** und der Typ der Verbindung beschreiben eine Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel dieser Verbindung erklärt.
   1. Die genauen Felder hängen davon ab, mit welchem Dienst Sie sich verbinden. Einzelheiten zu einem bestimmten Verbindungstyp finden Sie im Artikel über den Zieldienst.
   1. Wenn Sie [Ihren eigenen Key Vault verwenden](use-azure-key-vault.md), um Geheimnisse zu speichern, aktivieren Sie **Key Vault verwenden** und wählen Sie das Geheimnis aus der Liste aus.

1. Wählen Sie zum Erstellen der Verbindung **Speichern** aus.

Sie können auch auf einer Kachel **Installieren** in der Registerkarte **Entdecken** auswählen.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden

Beim Einrichten oder Bearbeiten einer Exportverbindung legen Sie fest, welche Benutzer diese bestimmte Verbindung zum Definieren von [Exporten](export-destinations.md) verwenden dürfen. Standardmäßig steht Benutzern mit der Rolle „Administrator“ eine Verbindung zur Verfügung. Sie können diese Einstellung unter **Wählen Sie aus, wer diese Verbindung verwenden kann** ändern und Benutzern mit der Rolle „Mitwirkender“ erlauben, diese Verbindung zu verwenden.

- Mitwirkende können die Verbindung nicht anzeigen oder bearbeiten. Sie sehen nur den Anzeigename und den Typ, wenn sie einen Export erstellen.
- Durch die Freigabe einer Verbindung können Mitwirkende eine Verbindung verwenden. Mitwirkende sehen gemeinsame Verbindungen, wenn sie Exporte einrichten. Sie können jeden Export verwalten, der diese bestimmte Verbindung verwendet.
- Sie können diese Einstellung ändern, während Sie die Exporte beibehalten, die bereits von Mitwirkenden definiert wurden.

## <a name="edit-a-connection"></a>Eine Verbindung bearbeiten

1. Gehen Sie zu **Administrator** > **Verbindungen (Vorschauversion)**.

1. Zur Registerkarte **Verbindungen** wechseln.

1. Wählen Sie die vertikalen Auslassungspunkte (&vellip;) für die Verbindung aus, die Sie bearbeiten möchten.

1. Wählen Sie **Bearbeiten**.

1. Ändern Sie die gewünschten Werte zur Aktualisierung und wählen **Speichern** aus.

## <a name="remove-a-connection"></a>Verbindung entfernen

Wenn die Verbindung, die Sie entfernen, von Anreicherungen oder Exporten verwendet wird, müssen Sie sie zuerst trennen oder entfernen. Das Dialogfeld „Entfernen“ führt Sie zu den relevanten Anreicherungen oder Exporten.

Abgelöste Anreicherungen und Exporte werden inaktiv. Sie reaktivieren sie, indem Sie ihnen eine weitere Verbindung auf den Seiten [Anreicherungen](enrichment-hub.md) oder [Exporte](export-destinations.md) hinzufügen.

1. Gehen Sie zu **Administrator** > **Verbindungen (Vorschauversion)**.

1. Zur Registerkarte **Verbindungen** wechseln.

1. Wählen Sie die vertikalen Auslassungspunkte (&vellip;) für die Verbindung aus, die Sie entfernen möchten.

1. Klicken Sie im Dropdown-Menü auf **Entfernen**. Ein Bestätigungsdialogfeld wird angezeigt.

   1. Wenn über diese Verbindung Anreicherungen oder Exporte erfolgen, klicken Sie auf die Schaltfläche, um zu sehen, was die Verbindung verwendet.
      - **Exporte:** Sie können die Exporte entweder entfernen oder trennen, um die Verbindung zu entfernen. Um einen Export zu trennen, können Administratoren die **Trennen**-Aktion verwenden. Diese Aktion ist für einzelne und mehrere ausgewählte Exporte verfügbar. Wenn Sie die Verbindung trennen, behalten Sie die Exportkonfiguration bei, sie wird jedoch erst ausgeführt, wenn eine weitere Verbindung hinzugefügt wird.
      - **Anreicherungen:** Sie können die Anreicherungen entweder entfernen oder deaktivieren, um die Verbindung zu entfernen.
   1. Wenn die Verbindung keine Abhängigkeiten mehr aufweist, kehren Sie zu **Administrator** > **Verbindungen** zurück, und versuchen Sie erneut, die Verbindung zu entfernen.

1. Um den Löschvorgang zu bestätigen, wählen Sie **Entfernen**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Stellen Sie Verbindungen mit Geheimnissen her, die von Ihrem eigenen Key Vault verwaltet werden

Einige Verbindungen benötigen Geheimnisse wie API-Schlüssel oder Passwörter. Einige Verbindungen unterstützen Geheimnisse, die in Ihrem eigenen Key Vault gespeichert sind. Erfahren Sie mehr über unterstützte Verbindungen und wie Sie [Ihren eigenen Key Vault für Customer Insights](use-azure-key-vault.md) festlegen.
