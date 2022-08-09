---
title: Daten zu Azure Synapse Analytics exportieren (Vorschauversion)
description: Erfahren Sie, wie Sie die Verbindung zu Azure Synapse Analytics konfigurieren.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196393"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Daten zu Azure Synapse Analytics exportieren (Vorschauversion)

Azure Synapse ist ein Analysedienst, der die Zeit für Einblicke in Data Warehouses und Big Data-Systeme verkürzt. Sie können Ihre Customer Insights-Daten in [Azure Synapse](/azure/synapse-analytics/overview-what-is) erfassen und verwenden.

## <a name="prerequisites"></a>Anforderungen

> [!NOTE]
> Stellen Sie sicher, dass Sie alle **Rollenzuweisungen** wie beschrieben festlegen.

- In Customer Insights muss Ihr Azure Active Directory (AD) Benutzerkonto hat eine [Administrator](permissions.md#assign-roles-and-permissions) Rolle haben.

In Azure:

- Ein aktives Azure-Abonnement.

- Bei Verwendung eines neuen Azure Data Lake Storage Gen2-Kontos, hat das [Dienstprinzipal für Customer Insights](connect-service-principal.md) **Speicherblobdaten-Teilnehmer** Berechtigungen. Im Data Lake Storage Gen2 **muss der** [hierarchischer Namespace](/azure/storage/blobs/data-lake-storage-namespace) aktiviert sein.

- In der Ressourcengruppe, in der sich der Azure Synapse Workspace befindet, müssen dem *Dienstprinzipal* und dem *Azure AD Benutzer mit Administratorberechtigungen in Customer Insights* mindestens eine **Leser** [Berechtigung](/azure/role-based-access-control/role-assignments-portal) zugewiesen sein.

- Der *Azure AD Benutzer mit Administratorberechtigungen in Customer Insights* hat **Speicherblobdaten-Teilnehmer** Berechtigungen im Azure Data Lake Storage Gen2-Konto, in dem sich die Daten befinden und mit dem Azure Synapse Workspace verknüpft sind. Erfahren Sie mehr über [Verwenden des Azure-Portals zum Zuweisen einer Azure-Rolle für den Zugriff auf Blob- und Warteschlangendaten](/azure/storage/common/storage-auth-aad-rbac-portal) und [Berechtigungen für Speicher-Blob Datenmitwirkender](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Die *[Azure Synapse Workspace verwaltete Identität](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* hat die Berechtigung **Speicher-Blob Datenmitwirkender** im Azure Data Lake Storage Gen2-Konto, in dem sich die Daten befinden und die mit dem Azure Synapse Arbeitsplatz verknüpft sind. Erfahren Sie mehr zur [Verwendung des Azure Portals zum Zuweisen einer Azure Rolle für den Zugriff auf Blob- und Warteschlangendaten](/azure/storage/common/storage-auth-aad-rbac-portal) und [Speichern von Blob-Daten Mitwirkender-Berechtigungen](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Im Azure Synapse Workspace, braucht der *Dienstprinzipal für Customer Insights* hat die Zuweisung einer **Synapse Administrator** [Rolle](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-connection-to-azure-synapse"></a>Verbindungen mit Azure Synapse einrichten

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** aus, und klicken Sie dann auf **Azure Synapse Analytics**.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld **Anzeigename**. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Standardmäßig sind es nur Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wählen Sie das Abonnement aus oder suchen Sie danach, in dem Sie die Customer Insights-Daten verwenden möchten. Sobald ein Abonnement ausgewählt ist, können Sie auch **Arbeitsbereich**, **Speicherkonto**, und **Container** auswählen.

1. Überprüfen Sie [Datenschutz und Konformität](connections.md#data-privacy-and-compliance) und wählen **Ich stimme zu** aus.

1. Wählen Sie zum Abschließen der Verbindung **Speichern** aus.

## <a name="configure-an-export"></a>Konfigurieren Sie einen Export

[!INCLUDE [export-permission-include](includes/export-permission.md)] Um den Export mit einer gemeinsamen Verbindung zu konfigurieren, benötigen Sie mindestens **Mitwirkender**-Berechtigungen in Customer Insights.

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie **Export hinzufügen**.

1. Wählen Sie unter **Verbindung für den Export** eine Verbindung aus dem Abschnitt Azure Synapse Analytics aus. Wenden Sie sich an einen Administrator, wenn keine Verbindung verfügbar ist.

1. Geben Sie einen erkennbaren **Anzeigename** für Ihren Export und einen **Datenbanknamen** ein. Der Export erstellt eine neue [Azure Synapse Lake-Datenbank](/azure/synapse-analytics/database-designer/concepts-lake-database) in dem in der Verbindung definierten Arbeitsbereich.

1. Wählen Sie die Entitäten aus, die Sie zu Azure Synapse Analytics exportieren möchten.
   > [!NOTE]
   > Datenquellen basierend auf einem [Common Data Model-Ordner](connect-common-data-model.md) werden nicht unterstützt.

1. Wählen Sie **Save** (Speichern).

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Um Daten abzufragen, die nach Synapse Analytics exportiert wurden, benötigen Sie **Datenleser des Speicher-Blobs**-Zugriff auf den Zielspeicher im Arbeitsbereich der Exporte.

## <a name="update-an-export"></a>Aktualisieren Sie einen Export

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie für den Export, den Sie aktualisieren möchten, **bearbeiten** aus.

   - **Hinzufügen** oder **Entfernen** von Entitäten aus der Auswahl. Wenn Entitäten aus der Auswahl entfernt werden, werden sie nicht aus der Synapse-Analyse-Datenbank gelöscht. Zukünftige Datenaktualisierungen aktualisieren jedoch nicht die entfernten Entitäten in dieser Datenbank.

   - **Ändern des Datenbanknamens** erstellt eine neue Synapse-Analye-Datenbank. Die Datenbank mit dem zuvor konfigurierten Namen erhält bei zukünftigen Aktualisierungen keine Aktualisierungen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
