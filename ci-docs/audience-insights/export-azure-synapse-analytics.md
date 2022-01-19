---
title: Exportieren Sie Customer Insights-Daten zu Azure Synapse Analyse
description: Erfahren Sie, wie Sie die Verbindung zu Outlook und Azure Synapse Analyse konfigurieren.
ms.date: 01/05/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 6f630b8fb03bf615ada6d40fe27a91975d0c856e
ms.sourcegitcommit: cb71e39de9b891c24bd5cd9c014eb3eeb537ac24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/10/2022
ms.locfileid: "7951041"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Daten zu Azure Synapse Analyse (Vorschau) exportieren

Azure Synapse ist ein Analysedienst, der die Zeit für Einblicke in Data Warehouses und Big Data-Systeme verkürzt. Sie können Ihre Customer Insights-Daten in [Azure Synapse](/azure/synapse-analytics/overview-what-is) erfassen und verwenden.

## <a name="prerequisites"></a>Anforderungen

Die folgenden Voraussetzungen müssen erfüllt sein, um die Verbindung von Customer Insights zu Azure Synapse zu konfigurieren.

> [!NOTE]
> Stellen Sie sicher, dass Sie alle **Rollenzuweisungen** wie beschrieben festlegen.  

## <a name="prerequisites-in-customer-insights"></a>Voraussetzungen in Customer Insights

* Sie verfügen in Zielgruppenerkenntnissenn über die Benutzerrolle **Administrator**. Erfahren Sie mehr über das [Festlegen von Benutzerberechtigungen in Zielgruppenerkenntnissen](permissions.md#assign-roles-and-permissions)

In Azure: 

- Ein aktives Azure-Abonnement.

- Bei Verwendung eines neuen Azure Data Lake Storage Gen2-Konto benötigt der *Dienstprinzipal für Kundenerkenntnisse* die Berechtigungen **Blob Datenmitwirkender**. Erfahren Sie mehr über [Verbindung zu einem Azure Data Lake Storage Gen2-Konto mit Azure-Dienstprinzipal für Zielgruppenerkenntnisse](connect-service-principal.md). Im Data Lake Storage Gen2 **muss der** [hierarchischer Namespace](/azure/storage/blobs/data-lake-storage-namespace) aktiviert sein.

- In der Ressourcengruppe, in der sich der Azure Synapse Arbeitsbereich befindet, muss dem *Dienstprinzipal* und der *Benutzer für Erkenntniseinblicke* mindestens **Leseberechtigungen** zugewiesen werden. Weitere Informationen finden Sie unter [Weisen Sie Azure-Rollen über das Azure-Portal zu](/azure/role-based-access-control/role-assignments-portal).

- Der *Benutzer* braucht die Berechtigung **Speicher-Blob-Datenmitwirkender** im Azure Data Lake Storage Gen2-Konto, in dem sich die Daten befinden und die mit dem Azure Synapse Arbeitsplatz verknüpft sind. Erfahren Sie mehr über [Verwenden des Azure-Portals zum Zuweisen einer Azure-Rolle für den Zugriff auf Blob- und Warteschlangendaten](/azure/storage/common/storage-auth-aad-rbac-portal) und [Berechtigungen für Speicher-Blob Datenmitwirkender](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Die *[Azure Synapse vom Arbeitsbereich verwaltete Identität](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* benötigt die Berechtigung **Speicher-Blob Datenmitwirkender** im Azure Data Lake Storage Gen2-Konto, in dem sich die Daten befinden und die mit dem Azure Synapse Arbeitsplatz verknüpft sind. Erfahren Sie mehr zur [Verwendung des Azure Portals zum Zuweisen einer Azure Rolle für den Zugriff auf Blob- und Warteschlangendaten](/azure/storage/common/storage-auth-aad-rbac-portal) und [Speichern von Blob-Daten Mitwirkender-Berechtigungen](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Im Azure Synapse Arbeitsbereich benötigt der *Dienstprinzipal für Zielgruppenerkenntnisse* die zugewiesene Rolle **Synapse-Administrator**. Weitere Informationen finden Sie unter [So richten Sie die Zugriffssteuerung für Ihren Synapse-Arbeitsbereich ein](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Richten Sie die Verbindung ein und exportieren Sie diese zu Azure Synapse

### <a name="configure-a-connection"></a>Verbindung konfigurieren

Um eine Verbindung herzustellen, benötigen der Dienstprinzipal und das Benutzerkonto in Customer Insights **Leser**-Berechtigungen für die *Ressourcengruppe*, in der sich der Synapse Analytics-Arbeitsbereich befindet. Darüber hinaus benötigen der Dienstprinzipal und der Benutzer im Synapse Analytics-Arbeitsbereich **Synapse Administrator**-Berechtigungen. 

1. Gehen Sie zu **Administrator** > **Verbindungen**.

1. Wählen Sie **Verbindung hinzufügen** und dann **Azure Synapse Analyse** oder wählen Sie **Einrichten** in der Kachel **Azure Synapse Analyse**, um die Verbindung zu konfigurieren.

1. Geben Sie Ihrer Verbindung einen erkennbaren Namen im Feld Anzeigename. Der Name und der Typ der Verbindung beschreiben die Verbindung. Wir empfehlen, einen Namen zu wählen, der den Zweck und das Ziel der Verbindung erklärt.

1. Wählen Sie aus, wer diese Verbindung verwenden kann. Wenn Sie keine Aktion ausführen, ist die Standardeinstellung Administratoren. Weitere Informationen finden Sie unter [Ermöglichen Sie Mitwirkenden, eine Verbindung für den Export zu verwenden](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Wählen Sie das Abonnement aus oder suchen Sie danach, in dem Sie die Customer Insights-Daten verwenden möchten. Sobald ein Abonnement ausgewählt ist, können Sie auch **Arbeitsbereich**, **Speicherkonto**, und **Container** auswählen.

1. Klicken Sie auf **Speichern**, um die Verbindung zu speichern.

### <a name="configure-an-export"></a>Konfigurieren Sie einen Export

Sie können diesen Export konfigurieren, wenn Sie Zugriff auf eine Verbindung dieses Typs haben. Um den Export mit einer gemeinsamen Verbindung zu konfigurieren, benötigen Sie mindestens **Mitwirkender**-Berechtigungen in Customer Insights. Weitere Informationen finden Sie unter [zum Konfigurieren eines Exports erforderliche Berechtigungen](export-destinations.md#set-up-a-new-export).

1. Gehen Sie zu **Daten** > **Exporte**.

1. Um einen neuen Export zu erstellen, wählen Sie **Export hinzufügen** aus.

1. Wählen Sie im Feld **Verbindung für den Export** eine Verbindung aus dem Bereich **Azure Synapse Analyse** aus. Wenn Sie diesen Abschnittsnamen nicht sehen, stehen Ihnen keine [Verbindungen](connections.md) dieses Typs zur Verfügung.

1. Geben Sie einen erkennbaren **Anzeigename** für Ihren Export und einen **Datenbanknamen** ein.

1. Wählen Sie aus, in welche Entitäten Sie zu Azure Synapse Analyse exportieren möchten.
   > [!NOTE]
   > Datenquellen basierend auf einem [Common Data Model-Ordner](connect-common-data-model.md) werden nicht unterstützt.

2. Wählen Sie **Speichern** aus.

Beim Speichern eines Exports wird der Export nicht sofort ausgeführt.

Der Export wird mit jeder [geplanten Aktualisierung](system.md#schedule-tab) ausgeführt. Sie können auch [Daten bei Bedarf exportieren](export-destinations.md#run-exports-on-demand).

Um Daten abzufragen, die nach Synapse Analytics exportiert wurden, benötigen Sie **Datenleser des Speicher-Blobs**-Zugriff auf den Zielspeicher im Arbeitsbereich der Exporte. 

### <a name="update-an-export"></a>Aktualisieren Sie einen Export

1. Gehen Sie zu **Daten** > **Exporte**.

1. Wählen Sie für den Export, den Sie aktualisieren möchten, **bearbeiten** aus.

   - **Hinzufügen** oder **Entfernen** von Entitäten aus der Auswahl. Wenn Entitäten aus der Auswahl entfernt werden, werden sie nicht aus der Synapse-Analyse-Datenbank gelöscht. Zukünftige Datenaktualisierungen aktualisieren jedoch nicht die entfernten Entitäten in dieser Datenbank.

   - **Ändern des Datenbanknamens** erstellt eine neue Synapse-Analye-Datenbank. Die Datenbank mit dem zuvor konfigurierten Namen erhält bei zukünftigen Aktualisierungen keine Aktualisierungen.
