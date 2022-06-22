---
title: Daten aus Azure Synapse Analytics erfassen
description: Verwenden Sie eine Datenbank in Azure Synapse als Datenquelle in Dynamics 365 Customer Insights.
ms.date: 03/25/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 6f94cdbcc203fc4518544f7a945bd80e871b36c1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011426"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Eine Azure Synapse Analytics-Datenquelle verbinden (Vorschauversion)

Azure Synapse Analytics ist ein Analysedienst für Unternehmen, der Erkenntnisse über Data Warehouses und Big-Data-Systeme hinweg verkürzt. Azure Synapse Analytics vereint die besten SQL-Technologien für Data Warehousing in Unternehmen, Spark-Technologien für Big Data, Data Explorer für Protokoll‑ und Zeitreihenanalysen, Pipelines für die Datenintegration und ETL/ELT sowie eine tiefe Integration mit anderen Azure-Diensten wie Power BI, Cosmos DB und AzureML.

Weitere Informationen finden Sie unter [Azure Synapse-Überblick](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Anforderungen

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie alle **Rollenzuweisungen** wie beschrieben festlegen.  

**In Customer Insights**:

* Sie verfügen über eine **Administrator**-Rolle in Customer Insights. Erfahren Sie mehr über [Benutzerberechtigungen in Customer Insights](permissions.md#assign-roles-and-permissions).

**In Azure**:

- Ein aktives Azure-Abonnement.

- Bei Verwendung eines neuen Azure Data Lake Storage Gen2-Kontos, benötigt das *Dienstprinzipal für Customer Insights* **Speicherblobdaten-Teilnehmer** Berechtigungen. Erfahren Sie mehr über [Verbindungen zu einer Azure Data Lake Storage mit einem Dienstprinzipal für Customer Insights](connect-service-principal.md). Im Data Lake Storage Gen2 **muss der** [hierarchischer Namespace](/azure/storage/blobs/data-lake-storage-namespace) aktiviert sein.

- In der Ressourcengruppe, in der sich der Azure Synapse workspace befindet, müssen dem *Dienstprinzipal* und dem *Benutzer für Customer Insights* mindestens die Berechtigung **Leser** zugewiesen werden. Weitere Informationen finden Sie unter [Weisen Sie Azure-Rollen über das Azure-Portal zu](/azure/role-based-access-control/role-assignments-portal).

- Der *Benutzer* braucht die Berechtigung **Speicher-Blob-Datenmitwirkender** im Azure Data Lake Storage Gen2-Konto, in dem sich die Daten befinden und die mit dem Azure Synapse Arbeitsplatz verknüpft sind. Erfahren Sie mehr über [Verwenden des Azure-Portals zum Zuweisen einer Azure-Rolle für den Zugriff auf Blob- und Warteschlangendaten](/azure/storage/common/storage-auth-aad-rbac-portal) und [Berechtigungen für Speicher-Blob Datenmitwirkender](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Die *[Azure Synapse vom Arbeitsbereich verwaltete Identität](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* benötigt die Berechtigung **Speicher-Blob Datenmitwirkender** im Azure Data Lake Storage Gen2-Konto, in dem sich die Daten befinden und die mit dem Azure Synapse Arbeitsplatz verknüpft sind. Erfahren Sie mehr zur [Verwendung des Azure Portals zum Zuweisen einer Azure Rolle für den Zugriff auf Blob- und Warteschlangendaten](/azure/storage/common/storage-auth-aad-rbac-portal) und [Speichern von Blob-Daten Mitwirkender-Berechtigungen](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Im Azure Synapse Workspace, braucht der *Dienstprinzipal für Customer Insights* die Zuweisung einer **Synapse Administrator** Rolle. Weitere Informationen finden Sie unter [So richten Sie die Zugriffssteuerung für Ihren Synapse-Arbeitsbereich ein](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Herstellen einer Verbindung mit Data Lake-Datenbanken in Azure Synapse Analytics

1. Wechseln Sie zu **Daten** > **Datenquellen**.

1. Wählen Sie **Datenquelle hinzufügen**.

1. Wählen Sie die Methode **Azure Synapse Analytics (Vorschauversion)**.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Dialogfeld zum Herstellen einer Verbindung mit Synapse Analytics-Daten":::
  
1. Geben Sie einen **Namen** und eine optionale **Beschreibung** für die neue Datenquelle ein.

1. Wählen Sie eine [verfügbare Verbindung](connections.md) mit Azure Synapse Analytics aus oder erstellen Sie eine neue.

1. Wählen Sie eine **Datenbank** aus dem Arbeitsbereich, der in der ausgewählten Azure Synapse Analytics-Verbindung verbunden ist, und wählen Sie **Weiter**.

1. Wählen Sie die zu erfassenden Entitäten aus der verbundenen Datenbank aus und wählen Sie **Weiter**.

1. Wählen Sie optional die Datenentitäten aus, für die die Datenprofilerstellung zugelassen werden soll.

1. Wählen Sie **Speichern**, um Ihre Auswahl zu übernehmen und die Erfassung der Daten aus Ihrer neu erstellten Datenquelle zu starten, die mit den Lake-Datenbanktabellen in Azure Synapse Analytics verknüpft ist. Die Seite **Datenquellen** öffnet sich und zeigt die neue Datenquelle im Status **Wird aktualisiert** an.
