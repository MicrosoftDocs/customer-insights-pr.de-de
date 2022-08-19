---
title: Konfigurieren von Sicherheitseinstellungen
description: Erfahren Sie mehr über die Sicherheitseinstellungen in Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ea21163d7dd05370de28ca8340ae9583846adb26
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246061"
---
# <a name="configure-security-settings"></a>Konfigurieren von Sicherheitseinstellungen

Verwalten Sie API-Schlüssel, greifen Sie auf Kundendaten zu und richten Sie einen Azure Private Link ein.

## <a name="manage-api-keys"></a>API-Schlüssel verwalten

Hier können Sie die Schlüssel zur Verwendung der [Customer Insights APIs](apis.md) mit den Daten in Ihrer Umgebung anzeigen und verwalten.

1. Gehen Sie zu **System** > **Sicherheit** und wählen Sie die Registerkarte **APIs**.

1. Wenn kein API-Zugriff auf die Umgebung eingerichtet wurde, wählen Sie **Aktivieren**. Oder, um den API-Zugriff auf die Umgebung zu blockieren, wählen Sie **Deaktivieren** und bestätigen Sie.

1. Verwalten Sie die primären und sekundären API-Schlüssel:

   1. Um den primären oder sekundären API-Schlüssel anzuzeigen, wählen Sie das **Anzeigen** Symbol.

   1. Um den primären oder sekundären API-Schlüssel zu kopieren, wählen Sie das **Kopieren** Symbol.

   1. Sie können neue Primär- und Sekundär-API-Schlüssel erstellen, indem Sie **Primärschlüssel neu generieren** oder **Sekundärschlüssel neu generieren** wählen.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Sicherer Zugriff auf Kunddaten mit Kunden-Lockbox (Vorschauversion)

Customer Insights verwendet die Power Platform Kunden-Lockbox-Funktion. Kunden-Lockbox bietet eine Schnittstelle zum Überprüfen und Genehmigen (oder Ablehnen) von Datenzugriffsanfragen. Diese Anfragen treten auf, wenn Datenzugriff auf Kundendaten erforderlich ist, um einen Supportfall zu lösen. Um diese Funktion verwenden zu können, muss Customer Insights eine bestehende Verbindung zu einem Microsoft Dataverse Umfeld in Ihrem Mandanten haben.

Weitere Informationen zur Kunden-Lockbox finden Sie unter [Zusammenfassung](/power-platform/admin/about-lockbox#summary) von Power Platform Kunden-Lockbox. Der Artikel beschreibt auch den [Arbeitsablauf](/power-platform/admin/about-lockbox#workflow) und die erforderliche [Einrichtung](/power-platform/admin/about-lockbox#enable-the-lockbox-policy), um die Kunden-Lockbox zu aktivieren.

> [!IMPORTANT]
> Globale Administratoren für Power Platform oder Power Platform Administratoren können Kunden-Lockbox-Anforderungen genehmigen, die für Customer Insights ausgestellt wurden.

## <a name="set-up-an-azure-private-link"></a>Richten Sie einen Azure Private Link ein

Mit [Azure Private Link](/azure/private-link/private-link-overview) können Sie uns Customer Insights mit Ihrem Azure Data Lake Storage Konto über ein privates Endpunkt in Ihrem virtuellen Netzwerk verbinden. Für Daten in einem Speicherkonto, das nicht dem öffentlichen Internet ausgesetzt ist, ermöglicht Private Link die Verbindung mit diesem eingeschränkten Netzwerk.

> [!IMPORTANT]
> Minimale Rollenanforderung zum Einrichten einer Private Link-Verbindung:
>
> - Customer Insights Administrator
> - Integrierte Azure-Rolle: [Speicherkonto Teilnehmer](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Berechtigungen für benutzerdefinierte Azure-Rolle: [Microsoft.Storage/storageAccounts/read und Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. Gehen Sie in Customer Insights zu **Admin** > **Sicherheit** und wählen Sie das Register **Private Links**.

1. Wählen Sie **Private Link hinzufügen**.

   Der Bereich **Privaten Link hinzufügen** führt Speicherkonten Ihres Mandanten auf, für die Sie Berechtigungen zum Anzeigen haben.

1. Wählen Sie das Abonnement, die Ressourcengruppe, und das Speicherkonto.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie **Save** (Speichern).

1. Gehen Sie zu Ihrem Data Lake Storage-Konto und öffnen Sie den auf dem Bildschirm angezeigten Link.

1. Private Link genehmigen.


[!INCLUDE [footer-include](includes/footer-banner.md)]
