---
title: Sicherheitseinstellungen in Dynamics 365 Customer Insights festgelegt
description: Erfahren Sie mehr über die Sicherheitseinstellungen in Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653710"
---
# <a name="security-overview-page"></a>Übersichtsseite Sicherheit

Auf der Seite **Sicherheit** finden Sie Optionen zur Konfiguration von Benutzerberechtigungen und Funktionen, die dazu beitragen, Dynamics 365 Customer Insights sicherer zu machen. Nur Administratoren können auf diese Seite zugreifen. 

Gehen Sie auf **Admin** > **Sicherheit**, um die Einstellungen festzulegen.

Die Seite **Sicherheit** enthält die folgenden Registerkarten:
- [Benutzer](#users-tab)
- [APIs](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>Registerkarte Benutzer

Der Zugriff auf Customer Insights ist auf Benutzer in Ihrem Unternehmen beschränkt, die von einem Admin zu der Anwendung hinzugefügt wurden. Auf der Registerkarte **Benutzer** können Sie den Zugriff der Benutzer und ihre Berechtigungen verwalten. Weitere Informationen finden Sie unter [Benutzerberechtigungen](permissions.md).

## <a name="apis-tab"></a>Registerkarte APIs

Hier können Sie die Schlüssel zur Verwendung der [Customer Insights APIs](apis.md) mit den Daten Ihrer Umgebung anzeigen und verwalten.

Sie können neue Primär- und Sekundärschlüssel erstellen, indem Sie **Primärschlüssel neu generieren** oder **Sekundärschlüssel neu generieren** wählen. 

Um den API-Zugriff auf die Umgebung zu blockieren, wählen Sie **Deaktivieren**. Wenn APIs deaktiviert sind, können Sie **Einschalten** wählen, um den Zugriff wieder zuzulassen.

## <a name="key-vault-tab"></a>Registerkarte Key Vault

Auf der Registerkarte **Key Vault** können Sie Ihren eigenen [Azure Key Vault](/azure/key-vault/general/basic-concepts) mit der Umgebung verknüpfen und verwalten.
Der dedizierte Schlüsseltresor kann verwendet werden, um Geheimnisse innerhalb der Compliance-Grenze einer Organisation bereitzustellen und zu verwenden. Customer Insights kann die Geheimnisse im Azure Key Vault nutzen, um [Verbindungen](connections.md) zu Systemen von Drittanbietern festzulegen.

Weitere Informationen finden Sie unter [Bring Your Own Azure Key Vault](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
