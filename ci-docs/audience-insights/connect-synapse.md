---
title: Daten aus Azure Synapse Analytics erfassen
description: Verwenden Sie eine Datenbank in Azure Synapse als Datenquelle in Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356021"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Eine Azure Synapse-Datenquelle verbinden (Vorschauversion)

Azure Synapse Analytics ist ein Analysedienst für Unternehmen, der Erkenntnisse über Data Warehouses und Big-Data-Systeme hinweg verkürzt. Azure Synapse Analytics vereint die besten SQL-Technologien für Data Warehousing in Unternehmen, Spark-Technologien für Big Data, Data Explorer für Protokoll‑ und Zeitreihenanalysen, Pipelines für die Datenintegration und ETL/ELT sowie eine tiefe Integration mit anderen Azure-Diensten wie Power BI, Cosmos DB und AzureML.

Weitere Informationen finden Sie unter [Azure Synapse-Überblick](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Anforderungen

Die folgenden Voraussetzungen müssen erfüllt sein, um die Verbindung von Customer Insights zu Azure Synapse zu konfigurieren.

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie alle **Rollenzuweisungen** wie beschrieben festlegen.  

## <a name="prerequisites-in-customer-insights"></a>Voraussetzungen in Customer Insights

* Sie verfügen über eine **Administrator**-Rolle in Customer Insights. Erfahren Sie mehr über [Benutzerberechtigungen in Zielgruppenerkenntnissen](permissions.md#assign-roles-and-permissions).

In Azure: 

- Ein aktives Azure-Abonnement.

- Bei Verwendung eines neuen Azure Data Lake Storage Gen2-Konto benötigt der *Dienstprinzipal für Kundenerkenntnisse* die Berechtigungen **Blob Datenmitwirkender**. Weitere Informationen zur [Verbindung zu einem mit einem Azure Data Lake Storage mit einem Dienstprinzipal für Zielgruppenerkenntnisse](connect-service-principal.md). Im Data Lake Storage Gen2 **muss der** [hierarchischer Namespace](/azure/storage/blobs/data-lake-storage-namespace) aktiviert sein.

- In der Ressourcengruppe, in der sich der Azure Synapse Arbeitsbereich befindet, muss dem *Dienstprinzipal* und der *Benutzer für Erkenntniseinblicke* mindestens **Leseberechtigungen** zugewiesen werden. Weitere Informationen finden Sie unter [Weisen Sie Azure-Rollen über das Azure-Portal zu](/azure/role-based-access-control/role-assignments-portal).

- Der *Benutzer* braucht die Berechtigung **Speicher-Blob-Datenmitwirkender** im Azure Data Lake Storage Gen2-Konto, in dem sich die Daten befinden und die mit dem Azure Synapse Arbeitsplatz verknüpft sind. Erfahren Sie mehr über [Verwenden des Azure-Portals zum Zuweisen einer Azure-Rolle für den Zugriff auf Blob- und Warteschlangendaten](/azure/storage/common/storage-auth-aad-rbac-portal) und [Berechtigungen für Speicher-Blob Datenmitwirkender](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Die *[Azure Synapse vom Arbeitsbereich verwaltete Identität](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* benötigt die Berechtigung **Speicher-Blob Datenmitwirkender** im Azure Data Lake Storage Gen2-Konto, in dem sich die Daten befinden und die mit dem Azure Synapse Arbeitsplatz verknüpft sind. Erfahren Sie mehr zur [Verwendung des Azure Portals zum Zuweisen einer Azure Rolle für den Zugriff auf Blob- und Warteschlangendaten](/azure/storage/common/storage-auth-aad-rbac-portal) und [Speichern von Blob-Daten Mitwirkender-Berechtigungen](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Im Azure Synapse Arbeitsbereich benötigt der *Dienstprinzipal für Zielgruppenerkenntnisse* die zugewiesene Rolle **Synapse-Administrator**. Weitere Informationen finden Sie unter [So richten Sie die Zugriffssteuerung für Ihren Synapse-Arbeitsbereich ein](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Herstellen einer Verbindung mit Data Lake-Datenbanken in Azure Synapse Analytics

1. Wechseln Sie zu **Daten** > **Datenquellen**.

1. Wählen Sie **Datenquelle hinzufügen**.

1. Wählen Sie die Methode **Azure Synapse Analytics (Vorschauversion)**.

1. Geben Sie einen **Namen** für die Datenquelle und wählen Sie **Weiter**, um die Datenquelle zu erstellen. 

1. Wählen Sie eine [verfügbare Verbindung](connections.md) mit Azure Synapse Analytics aus oder erstellen Sie eine neue.

1. Wählen Sie eine **Lake-Datenbank** aus dem Arbeitsbereich, der in der ausgewählten Azure Synapse Analytics-Verbindung verbunden ist, und Wählen Sie **Weiter**.

1. Wählen Sie die zu erfassenden Entitäten aus der verbundenen Datenbank aus. 

1. Wählen Sie optional die Datenentitäten aus, für die die Datenprofilerstellung zugelassen werden soll. 

1. Wählen Sie **Speichern**, um Ihre Auswahl zu übernehmen und die Erfassung der Daten aus Ihrer neu erstellten Datenquelle zu starten, die mit den Lake-Datenbanktabellen in Azure Synapse Analytics verknüpft ist.
