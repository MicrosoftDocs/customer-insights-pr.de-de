---
title: Verbindungsübersicht (Vorschauversion)
description: Verbindungen zu anderen Diensten von Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245510"
---
# <a name="connections-preview-overview"></a>Verbindungsübersicht (Vorschauversion)

Verbindungen sind der Schlüssel, um die gemeinsame Nutzung von Daten zu und von Customer Insights zu ermöglichen. Jede Verbindung stellt die gemeinsame Nutzung von Daten mit einem bestimmten Dienst her. Verwenden Sie Verbindungen zum [Konfigurieren von Anreicherungen von Drittanbietern](enrichment-hub.md) und [Konfigurieren von Exporten](export-destinations.md). Dieselbe Verbindung kann mehrfach verwendet werden. Beispielsweise funktioniert eine Verbindung zu Dynamics 365 Marketing für mehrere Exporte, und eine Leadspace-Verbindung kann für mehrere Anreicherungen verwendet werden.

## <a name="export-connections"></a>Exportverbindungen

Nur Administratoren können neue Verbindungen konfigurieren, sie können jedoch [Mitwirkenden Zugriff gewähren](#allow-contributors-to-use-a-connection-for-exports), um vorhandene Verbindungen zu verwenden. Administratoren steuern, wohin Daten gehen können, und die Mitwirkenden definieren die Nutzlast und Häufigkeit, die ihren Anforderungen entsprechen.

## <a name="enrichment-connections"></a>Anreicherungsverbindungen

Nur Administratoren können neue Verbindungen konfigurieren, aber die erstellten Verbindungen stehen sowohl Administratoren als auch Mitwirkenden immer zur Verfügung. Administratoren verwalten Anmeldeinformationen und stimmen der Datenübertragung zu. Die Verbindungen können dann sowohl von Administratoren als auch von Mitwirkenden zur Bereicherung verwendet werden.

## <a name="add-a-new-connection"></a>Eine neue Verbindung hinzufügen

### <a name="prerequisites"></a>Anforderungen

- [Administratorberechtigungen](permissions.md)
- Andere Microsoft-Dienste, falls vorhanden, befinden sich in derselben Organisation

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und dann den Verbindungstyp aus, den Sie erstellen möchten. Sie können auch auf einer Kachel **Einrichten** in der Registerkarte **Entdecken** auswählen.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Geben Sie die erforderlichen Details ein. Die genauen Felder hängen davon ab, mit welchem Dienst Sie sich verbinden. Details zu einem bestimmten Verbindungstyp finden Sie im Artikel über den Zieldienst.

1. Wenn Sie [Ihren eigenen Key Vault verwenden](use-azure-key-vault.md), um Geheimnisse zu speichern, aktivieren Sie **Key Vault verwenden** und wählen Sie das Geheimnis aus der Liste aus.

1. Überprüfen Sie Datenschutz und Konformität und wählen **Ich stimme zu** aus.

1. Wählen Sie zum Erstellen der Verbindung **Speichern** aus.

### <a name="data-privacy-and-compliance"></a>Datenschutz und Konformität

Wenn Sie Dynamics 365 Customer Insights aktivieren, um Daten an Drittparteien oder andere Microsoft-Produkte zu übertragen, erlauben Sie die Übertragung von Daten außerhalb der Compliance-Grenze für Dynamics 365 Customer Insights, einschließlich potenziell sensibler Daten wie personenbezogener Daten. Microsoft wird solche Daten auf Ihre Anweisung hin übertragen, aber Sie sind dafür verantwortlich, dass die Drittpartei alle Datenschutz- oder Sicherheitsverpflichtungen erfüllt, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=396732).

Ihr Dynamics 365 Customer Insights Administrator kann diese Verbindung jederzeit entfernen, um die Nutzung der Funktionalität einzustellen.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden

Beim Einrichten oder Bearbeiten einer Exportverbindung legen Sie fest, welche Benutzer diese bestimmte Verbindung zum Definieren von [Exporten](export-destinations.md) verwenden dürfen. Standardmäßig steht Benutzern mit der Rolle „Administrator“ eine Verbindung zur Verfügung. Ändern Sie diese Einstellung unter **Wählen Sie aus, wer diese Verbindung verwenden kann**, um den Benutzern mit der Rolle „Mitwirkender“ erlauben, diese Verbindung zu verwenden.

- Mitwirkende können die Verbindung nicht anzeigen oder bearbeiten. Sie sehen nur den Anzeigename und den Typ, wenn sie einen Export erstellen.
- Durch die Freigabe einer Verbindung können Mitwirkende eine Verbindung verwenden. Mitwirkende sehen gemeinsame Verbindungen, wenn sie Exporte einrichten. Sie können jeden Export verwalten, der diese bestimmte Verbindung verwendet.
- Sie können diese Einstellung ändern, während Sie die Exporte beibehalten, die bereits von Mitwirkenden definiert wurden.

## <a name="manage-existing-connections"></a>Vorhandene Verbindungen verwalten

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Anreicherung** oder **Exporte** Registerkarte aus, um eine Liste der Anreicherungs- oder Exportverbindungen, den Verbindungstyp, das Erstellungsdatum und die Zugriffsberechtigten anzuzeigen. Sie können die Liste der Verbindungen nach jeder Spalte sortieren.

1. Wählen Sie die Verbindung aus, um verfügbare Aktionen anzuzeigen.

   - **Bearbeiten** Sie die Verbindung.
   - [**Verbindung entfernen**](#remove-a-connection).

### <a name="remove-a-connection"></a>Verbindung entfernen

Wenn die Verbindung, die Sie entfernen, von Anreicherungen oder Exporten verwendet wird, müssen Sie sie zuerst trennen oder entfernen. Das Dialogfeld „Entfernen“ führt Sie zu den relevanten Anreicherungen oder Exporten.

> [!TIP]
> Deaktivierte Anreicherungen und getrennte Exporte werden inaktiv. Sie reaktivieren sie, indem Sie ihnen eine weitere Verbindung auf den Seiten [Anreicherungen](enrichment-hub.md) oder [Exporte](export-destinations.md) hinzufügen.

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Anreicherung** oder **Exporte** aus.

1. Wählen Sie die Verbindung aus, die Sie entfernen möchten.

1. Klicken Sie im Dropdown-Menü auf **Entfernen**. Ein Bestätigungsdialogfeld wird angezeigt.

   1. Wenn über diese Verbindung Anreicherungen oder Exporte erfolgen, klicken Sie auf die Schaltfläche, um zu sehen, was die Verbindung verwendet.
      - **Exporte:** Wählen Sie entweder Export **Entfernen** oder **Trennen Sie die Verbindung**. Wenn Sie die Verbindung trennen, behalten Sie die Exportkonfiguration bei, sie wird jedoch erst ausgeführt, wenn eine weitere Verbindung hinzugefügt wird.
      - **Anreicherungen:** Wählen Sie entweder **Löschen** oder **Deaktivieren** der Bereicherungen.
   1. Wenn die Verbindung keine Abhängigkeiten mehr aufweist, kehren Sie zu **Administrator** > **Verbindungen** zurück, und versuchen Sie erneut, die Verbindung zu entfernen.

1. Um den Löschvorgang zu bestätigen, wählen Sie **Entfernen**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Stellen Sie Verbindungen mit Geheimnissen her, die von Ihrem eigenen Key Vault verwaltet werden

Einige Verbindungen benötigen Geheimnisse wie API-Schlüssel oder Passwörter. Einige Verbindungen unterstützen Geheimnisse, die in Ihrem eigenen Key Vault gespeichert sind. Erfahren Sie mehr über unterstützte Verbindungen und wie Sie [Ihren eigenen Key Vault für Customer Insights](use-azure-key-vault.md) festlegen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
