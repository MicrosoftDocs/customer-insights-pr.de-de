---
title: Sicherheitseinstellungen in Customer Insights
description: Erfahren Sie mehr über die Sicherheitseinstellungen in Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947414"
---
# <a name="security-settings-in-customer-insights"></a>Sicherheitseinstellungen in Customer Insights

Auf der Seite **Sicherheit** finden Sie Optionen zur Konfiguration von Benutzerberechtigungen und Funktionen, die dazu beitragen, Dynamics 365 Customer Insights sicherer zu machen. Nur Administratoren können auf diese Seite zugreifen.

Gehen Sie auf **Admin** > **Sicherheit**, um die Einstellungen festzulegen.

Die Seite **Sicherheit** enthält die folgenden Registerkarten:

- [Benutzer](#users-tab)
- [APIs](#apis-tab)
- [Private Links](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [Sicherer Zugriff auf Kunddaten mit Kunden-Lockbox (Vorschauversion)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Registerkarte Benutzer

Der Zugriff auf Customer Insights ist auf Benutzer in Ihrem Unternehmen beschränkt, die von einem Admin zu der Anwendung hinzugefügt wurden. Auf der Registerkarte **Benutzer** können Sie den Zugriff der Benutzer und ihre Berechtigungen verwalten. Weitere Informationen finden Sie unter [Benutzerberechtigungen](permissions.md).

## <a name="apis-tab"></a>Registerkarte APIs

Hier können Sie die Schlüssel zur Verwendung der [Customer Insights APIs](apis.md) mit den Daten Ihrer Umgebung anzeigen und verwalten.

Sie können neue Primär- und Sekundärschlüssel erstellen, indem Sie **Primärschlüssel neu generieren** oder **Sekundärschlüssel neu generieren** wählen. 

Um den API-Zugriff auf die Umgebung zu blockieren, wählen Sie **Deaktivieren**. Wenn APIs deaktiviert sind, können Sie **Einschalten** wählen, um den Zugriff wieder zuzulassen.

## <a name="private-links-tab"></a>Registerkarte Private Links

Mit [Azure Private Link](/azure/private-link/private-link-overview) können Sie uns Customer Insights mit Ihrem Azure Data Lake Storage Konto über ein privates Endpunkt in Ihrem virtuellen Netzwerk verbinden. Für Daten in einem Speicherkonto, das nicht dem öffentlichen Internet ausgesetzt ist, ermöglicht Private Link die Verbindung mit diesem eingeschränkten Netzwerk.

> [!IMPORTANT]
> Minimale Rollenanforderung zum Einrichten einer Private Link-Verbindung:
>
> - Customer Insights Administrator
> - Integrierte Azure-Rolle: [Speicherkonto Teilnehmer](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Berechtigungen für benutzerdefinierte Azure-Rolle: [Microsoft.Storage/storageAccounts/read und Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Das Einrichten von Private Link in Customer Insights ist ein zweistufiger Prozess. Zunächst leiten Sie die Erstellung eines privaten Links von **Administrator** > **Sicherheit** > **Private Links** in Customer Insights ein. Der Bereich **Privaten Link hinzufügen** führt Speicherkonten Ihres Mandanten auf, für die Sie Berechtigungen zum Anzeigen haben. Wählen Sie das Speicherkonto aus und stimmen Sie der Erstellung des privaten Links zu.

Als Nächstes müssen Sie den privaten Link auf der Seite des Data Lake Storage-Kontos genehmigen. Öffnen Sie den auf dem Bildschirm angezeigten Link, um den neuen privaten Link zu genehmigen.

## <a name="key-vault-tab"></a>Registerkarte Key Vault

Auf der Registerkarte **Key Vault** können Sie Ihren eigenen [Azure Key Vault](/azure/key-vault/general/basic-concepts) mit der Umgebung verknüpfen und verwalten.
Der dedizierte Schlüsseltresor kann verwendet werden, um Geheimnisse innerhalb der Compliance-Grenze einer Organisation bereitzustellen und zu verwenden. Customer Insights kann die Geheimnisse im Azure Key Vault nutzen, um [Verbindungen](connections.md) zu Systemen von Drittanbietern festzulegen.

Weitere Informationen finden Sie unter [Bring Your Own Azure Key Vault](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Sicherer Zugriff auf Kunddaten mit Kunden-Lockbox (Vorschauversion)

Customer Insights verwendet die Power Platform Kunden-Lockbox-Funktion. Kunden-Lockbox bietet eine Schnittstelle zum Überprüfen und Genehmigen (oder Ablehnen) von Datenzugriffsanfragen. Diese Anfragen treten auf, wenn Datenzugriff auf Kundendaten erforderlich ist, um einen Supportfall zu lösen. Um diese Funktion verwenden zu können, muss Customer Insights eine bestehende Verbindung zu einem Microsoft Dataverse Umfeld in Ihrem Mandanten haben.

Weitere Informationen zur Kunden-Lockbox finden Sie unter [Zusammenfassung](/power-platform/admin/about-lockbox#summary) von Power Platform Kunden-Lockbox. Der Artikel beschreibt auch den [Arbeitsablauf](/power-platform/admin/about-lockbox#workflow) und die erforderliche [Einrichtung](/power-platform/admin/about-lockbox#enable-the-lockbox-policy), um die Kunden-Lockbox zu aktivieren.

> [!IMPORTANT]
> Globale Administratoren für Power Platform oder Power Platform Administratoren können Kunden-Lockbox-Anforderungen genehmigen, die für Customer Insights ausgestellt wurden.

[!INCLUDE [footer-include](includes/footer-banner.md)]
