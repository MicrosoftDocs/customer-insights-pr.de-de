---
title: Verwenden Sie Ihr eigenes Azure Data Lake Storage Gen2-Konto
author: mukeshpo
description: Informieren Sie sich über die Voraussetzungen für die Verwendung Ihres eigenen Azure Data Lake Storage Kontos zum Speichern von Customer Insights-Daten.
ms.author: mukeshpo
ms.date: 08/15/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5e4b9348f06d4e5e10b4499ad86b38c9d52da1f5
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304380"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Verwenden Sie Ihr eigenes Azure Data Lake Storage Gen2-Konto

Dynamics 365 Customer Insights bietet Ihnen die Möglichkeit, alle Ihre Daten in [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction) zu speichern. Durch das Speichern von Daten in Data Lake Storage stimmen Sie zu, dass Daten an den entsprechenden geografischen Standort für dieses Azure-Speicherkonto übertragen und dort gespeichert werden. Weitere Informationen dazu, finden Sie unter [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Administratoren in Customer Insights können [Umgebungen erstellen](create-environment.md) und [die Datenspeicherungsoption angeben](create-environment.md#step-2-configure-data-storage).

## <a name="prerequisites"></a>Anforderungen

- Azure Data Lake Storage Konten müssen in derselben Azure-Region sein, die Sie beim Erstellen der Customer Insights Umgebung ausgewählt haben. Um die Azure-Region der Umgebung zu erfahren, gehen Sie zu **Admin** > **System** > **Über** in Customer Insights.
- Das Data Lake Storage Konto muss Gen2 sein. Azure Data Lake Gen1-Speicherkonten werden nicht unterstützt.
- Das Data Lake Storage Konto muss [hierarchischer Namespace aktiviert](/azure/storage/blobs/data-lake-storage-namespace) haben.
- Auf dem Speicherkonto muss ein Container mit dem Namen `customerinsights` vorhanden sein. Sie müssen es erstellen, bevor Sie Ihren eigenen Data Lake Storage in Customer Insights verwenden.
- Der Administrator, der die Customer Insights-Umgebung einrichtet, benötigt die Rolle „Storage Blob-Datenmitwirkender“ oder „Datenbesitzer des Speicher-Blobs“ für das Speicherkonto oder den `customerinsights`-Container. Weitere Informationen zum Zuweisen von Berechtigungen in einem Speicherkonto finden Sie unter [Erstellen Sie ein Speicherkonto](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Verbinden Sie Customer Insights mit Ihrem Speicherkonto

Stellen Sie beim Erstellen einer neuen Umgebung sicher, dass das Data Lake Storage-Konto vorhanden ist und alle Voraussetzungen erfüllt sind.

1. Im **Datenspeicher**-Schritt legen Sie während der Umgebungserstellung **Ausgabedaten speichern** auf **Azure Data Lake Storage Gen2** fest.
1. Wählen Sie aus, wie Sie mit dem **Speicherkonto verbinden** möchten. Sie können zwischen einer ressourcenbasierten Option und einer abonnementbasierten Option für die Authentifizierung wählen. Weitere Informationen finden Sie unter [Stellen Sie eine Verbindung mit einem Azure Data Lake Storage-Konto mithilfe eines Azure-Dienstprinzipals her](connect-service-principal.md).
   - Wählen Sie für **Azure-Abonnement** das **Abonnement**, **Ressourcengruppe** und **Speicherkonto** aus, das den `customerinsights`-Container enthält.
   - Geben Sie für **Kontoschlüssel** den **Kontonamen** und den **Kontoschlüssel** für das Data Lake Storage-Konto an. Die Verwendung dieser Authentifizierungsmethode impliziert, dass Sie informiert werden, wenn Ihre Organisation die Schlüssel rotiert. Sie müssen [die Umgebungskonfiguration mit dem neuen Schlüssel aktualisieren](manage-environments.md#edit-an-existing-environment), wenn dieser rotiert wird.
1. Wählen Sie aus, ob Sie Azure Private Link verwenden möchten, um eine Verbindung mit dem Speicherkonto herzustellen und mit einem zweistufigen Verfahren [die Verbindung zu Private Link herstellen](security-overview.md#set-up-an-azure-private-link).

Wenn Systemprozesse wie die Datenaufnahme abgeschlossen sind, erstellt das System entsprechende Ordner im Speicherkonto. Datendateien und model.json-Dateien werden erstellt und Ordnern basierend auf dem Prozessnamen hinzugefügt.

Wenn Sie mehrere Umgebungen von Customer Insights erstellen und die Ausgabeentitäten aus diesen Umgebungen in Ihrem Speicherkonto speichern, erstellt Customer Insights separate Ordner für jede Umgebung mit `ci_environmentID` im Behältnis.
