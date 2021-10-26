---
title: Bringen Sie Ihren eigenen Azure-Schlüsseltresor mit, um Geheimnisse zu verwalten
description: Erfahren Sie, wie Sie Customer Insights für die Verwendung Ihres eigenen Azure-Schlüsseltresors konfigurieren.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: 6f521dfce3e0922238d16beee3be8e1bbcfc63a5
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606072"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Bring Your Own Azure Key Vault (Vorschau)

Verknüpfen eines dedizierten [Azure Key Vault](/azure/key-vault/general/basic-concepts) zu einer Zielgruppenerkenntnis-Umgebung hilft Unternehmen dabei, Compliance-Anforderungen zu erfüllen.
Der dedizierte Schlüsseltresor kann verwendet werden, um Geheimnisse innerhalb der Compliance-Grenze einer Organisation bereitzustellen und zu verwenden. Zielgruppenerkenntnisse können die Geheimnisse in Azure Key Vault verwenden, um [Verbindungen einzurichten](connections.md) zu Drittsystemen.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>Verknüpfen Sie den Schlüsseltresor mit der Zielgruppenerkenntnis-Umgebung

### <a name="prerequisites"></a>Voraussetzungen

Um den Schlüsseltresor in Zielgruppenerkenntnissen zu konfigurieren, müssen die folgenden Voraussetzungen erfüllt sein:

- Sie müssen ein aktives Azure Abonnement haben.

- Sie verfügen in Zielgruppenerkenntnissenn über die Benutzerrolle [Administrator](permissions.md#administrator). Erfahren Sie mehr über [Benutzerberechtigungen in Zielgruppenerkenntnissen](permissions.md#assign-roles-and-permissions).

- Sie haben [Mitwirkenden](/azure/role-based-access-control/built-in-roles#contributor) und [Benutzerzugriff-Administrator](/azure/role-based-access-control/built-in-roles#user-access-administrator)-Rollen im Schlüsseltresor oder der Ressourcengruppe, zu der der Schlüsseltresor gehört. Weitere Informationen finden Sie unter [Hinzufügen oder Entfernen von Azure-Rollenzuweisungen über das Azure-Portal](/azure/role-based-access-control/role-assignments-portal). Wenn Sie nicht über die Rolle Benutzerzugriff Administrator für den Schlüsseltresor verfügen, müssen Sie die rollenbasierten Zugriffssteuerungsberechtigungen für den Azure-Dienstprinzipal für Dynamics 365 Customer Insights separat einrichten. Folgen Sie den Schritten, um einen [Azure-Dienstprinzipals](connect-service-principal.md) für den zu verknüpfenden Schlüsseltresor zu verwenden.

- Im Schlüsseltresor muss die Key Vault-Firewall **deaktiviert** sein.

- Der Schlüsseltresor ist im selben [Azure-Standort](https://azure.microsoft.com/global-infrastructure/geographies/#overview) wie die Zielgruppenerkenntnis-Umgebung. Die Region der Umgebung in Zielgruppenerkenntnissen ist unter **Administrator** > **System** > **Über** > **Region** aufgeführt.

### <a name="link-a-key-vault-to-the-environment"></a>Verknüpfen Sie einen Schlüsseltresor mit der Umgebung

1. Gehen Sie zu **Admin** > **System** und wählen Sie dann die Registerkarte **Sicherheit**.
1. Auf der **Key Vault** Kachel wählen Sie **Einrichten**.
1. **Abonnement** auswählen.
1. Wählen Sie einen Schlüsseltresor aus der **Key Vault** Dropdown-Liste aus. Wenn zu viele Schlüsseltresore angezeigt werden, wählen Sie eine Ressourcengruppe aus, um die Suchergebnisse einzuschränken.
1. Akzeptieren Sie die **Datenschutz und Compliance** Anweisung.
1. Wählen Sie **Speichern** aus.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Schritte zum Einrichten eines verknüpften Schlüsseltresors in Zielgruppenerkenntnissen":::

Die **Key Vault** Kachel zeigt jetzt den verknüpften Schlüsseltresornamen, die Ressourcengruppe und das Abonnement an. Es ist bereit für den Verbindungsaufbau.
Einzelheiten dazu, welche Berechtigungen für den Schlüsseltresor den Zielgruppenerkenntnissen gewährt werden, finden Sie unter [Berechtigungen für den Schlüsseltresor für Zielgruppenerkenntnisse](#permissions-granted-on-the-key-vault-to-audience-insights) weiter unten in diesem Artikel.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Verwenden Sie den Schlüsseltresor im Verbindungsaufbau

Beim [Einrichten von Verbindungen](connections.md) zu Drittsystemen können die Geheimnisse aus dem verknüpften Key Vault verwendet werden, um die Verbindungen zu konfigurieren.

1. Gehen Sie zu **Administrator** > **Verbindungen**.
1. Wählen Sie **Verbindung hinzufügen** aus.
1. Für die unterstützten Verbindungstypen ist eine Umschaltung **Key Vault** verfügbar, wenn Sie einen Schlüsseltresor verknüpft haben.
1. Anstatt das Geheimnis manuell einzugeben, können Sie den geheimen Namen wählen, der auf den geheimen Wert im Schlüsseltresor verweist.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Verbindungsbereich mit einer SFTP-Verbindung, die ein Key Vault-Geheimnis verwendet.":::

## <a name="supported-connection-types"></a>Unterstützte Verbindungstypen

Folgende [Export](export-destinations.md)-Verbindungen werden unterstützt:

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [SendGrid](export-sendgrid.md)
* [SendInBlue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>Berechtigungen für den Schlüsseltresor für Zielgruppenerkenntnisse

Die folgenden Berechtigungen werden Zielgruppenerkenntnissen in einem verknüpften Schlüsseltresor gewährt, wenn entweder [Key Vault-Zugriffsrichtlinie](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) oder [Rollenbasierte Zugriffssteuerung in Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) aktiviert ist.

### <a name="key-vault-access-policy"></a>Key Vault-Zugriffsrichtlinien

| Art        | Berechtigungen          |
| ----------- | -------------------- |
| Schlüssel         | [Schlüssel erhalten](/rest/api/keyvault/get-keys), [Schlüssel abrufen](/rest/api/keyvault/get-key)                                 |
| Geheimnis      | [Geheimnisse abrufen](/rest/api/keyvault/get-secrets), [Geheimnis abrufen](/rest/api/keyvault/get-secret)                     |
| Zertifikat | [Zertifikate abrufen](/rest/api/keyvault/get-certificates), [Zertifikat abrufen](/rest/api/keyvault/get-certificate) |

Die vorstehenden Werte sind die Mindestwerte, die während der Ausführung aufgelistet und gelesen werden müssen.

### <a name="azure-role-based-access-control"></a>Rollenbasierte Zugriffssteuerung in Azure

Die Rollen Key Vault Leser und Key Vault Secrets-Benutzer werden für Zielgruppenerkenntnisse hinzugefügt. Weitere Informationen zu diesen Rollen finden Sie unter [Integrierte Azure-Rollen für Key Vault-Datenebenenvorgänge](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Empfehlungen

- Verwenden Sie einen separaten oder dedizierten Schlüsseltresor, der nur die Geheimnisse enthält, die für Zielgruppenerkenntnisse erforderlich sind. Lesen Sie mehr darüber, warum [separate Schlüsseltresore empfohlen werden](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Folgen Sie den [Best Practices für die Verwendung von Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) für Steuerungszugriff, Datensicherung, Überwachung und Wiederherstellungs-Optionen.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Können Zielgruppenerkenntnisse Geheimnisse in den Schlüsseltresor schreiben oder Geheimnisse überschreiben?

Nr. Nur die Lese- und Listenberechtigungen, die im Abschnitt [erteilte Berechtigungen](#permissions-granted-on-the-key-vault-to-audience-insights) weiter oben in diesem Artikeld dargestellt sind, werden Zielgruppenerkenntnissen gewährt. Das System kann keine Geheimnisse im Schlüsseltresor hinzufügen, löschen oder überschreiben. Dies ist auch der Grund, warum Sie keine Anmeldeinformationen eingeben können, wenn eine Verbindung Key Vault verwendet.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Kann ich eine Verbindung von der Verwendung von Key Vault-Geheimnissen in die Standardauthentifizierung ändern?

Nr. Sie können nicht wieder zu einer Standardverbindung wechseln, nachdem Sie sie mithilfe eines Geheimnisses aus einem verknüpften Schlüsseltresor konfiguriert haben. Erstellen Sie eine separate Verbindung und löschen Sie die alte, wenn Sie sie nicht mehr benötigen.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>Wie kann ich den Zugriff auf einen Schlüsseltresor für Zielgruppenerkenntnisse widerrufen?

Je nachdem, ob [Key Vault-Zugriffsrichtlinie](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) oder [Rollenbasierte Zugriffssteuerung in Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) aktiviert ist, müssen Sie die Berechtigungen für den Dienstprinzipal `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` mit dem Namen `Dynamics 365 AI for Customer Insights` entfernen. Alle Verbindungen, die den Schlüsseltresor verwenden, funktionieren nicht mehr.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Ein Geheimnis, das in einer Verbindung verwendet wird, wurde aus dem Schlüsseltresor entfernt. Was kann ich tun?

In Zielgruppenerkenntnissen wird eine Benachrichtigung angezeigt, wenn auf ein konfiguriertes Geheimnis aus dem Schlüsseltresor nicht mehr zugegriffen werden kann. Aktivieren Sie [Vorläufiges Löschen](/azure/key-vault/general/soft-delete-overview) im Schlüsseltresor, um Geheimnisse wiederherzustellen, wenn sie versehentlich entfernt wurden.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Eine Verbindung funktioniert nicht, aber mein Geheimnis liegt im Schlüsseltresor. Was könnte die Ursache sein?

In Zielgruppenerkenntnissen wird eine Benachrichtigung angezeigt, wenn kein Zugriff auf den Schlüsseltresor möglich ist. Die Ursache könnte sein:

- Die Berechtigungen für den Dienstprinzipal Zielgruppenerkenntnisse wurden entfernt. Sie müssen manuell wiederhergestellt werden.

- Die Firewall des Schlüsseltresors ist aktiviert. Die Firewall muss deaktiviert werden, damit der Schlüsseltresor wieder für Zielgruppenerkenntnisse zugänglich ist.
