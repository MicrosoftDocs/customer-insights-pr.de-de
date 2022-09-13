---
title: Verbinden Sie den Ordner Common Data Model mithilfe einem Azure Data Lake-Konto
description: Arbeiten Sie mit Common Data Model-Daten unter Verwendung von Azure Data Lake Storage.
ms.date: 07/27/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: d79b2d34e425e123224209814fef6e367c77c813
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2022
ms.locfileid: "9396079"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Verbindung mit Daten in Azure Data Lake Storage herstellen

Daten aufnehmen in Dynamics 365 Customer Insights mit Ihrem Azure Data Lake Storage Gen2-Konto. Die Datenaufnahme kann vollständig oder inkrementell erfolgen.

## <a name="prerequisites"></a>Anforderungen

- Datenerfassung unterstützt ausschließlich Azure Data Lake Storage *Gen2* Konten. Sie können keine Data Lake Storage Gen1-Konten für die Datenerfassung verwenden.

- Die Azure Data Lake Storage Konten müssen [hierarchischer Namespace aktiviert haben](/azure/storage/blobs/data-lake-storage-namespace). Die Daten müssen in einem hierarchischen Ordnerformat gespeichert werden, das den Stammordner definiert und Unterordner für jede Entität hat. Die Unterordner können Ordner mit vollständigen Daten oder inkrementellen Daten enthalten.

- Um sich mit einem Azure Service Prinzipal zu authentifizieren, stellen Sie sicher, dass es in Ihrem Mandanten konfiguriert ist. Weitere Informationen finden Sie unter [Verbinden Sie sich mit einem Azure Dienstprinzipal mit einem Azure Data Lake Storage Gen2 Konto](connect-service-principal.md).

- Der Azure Data Lake Storage, zu dem Sie eine Verbindung herstellen und von dem Sie Daten aufnehmen, muss sich in derselben Azure-Region wie die Dynamics 365 Customer Insights-Umgebung befinden. Verbindungen zu einem Common Data Model-Ordner aus einem Data Lake in einer anderen Azure-Region werden nicht unterstützt. Um die Azure-Region der Umgebung zu erfahren, gehen Sie zu **Admin** > **System** > **Über** in Customer Insights.

- Daten, die in Online-Diensten gespeichert sind, können an einem anderen Ort gespeichert werden als dort, wo die Daten verarbeitet oder in Dynamics 365 Customer Insights gespeichert werden. Durch das Importieren von oder Verbinden mit Daten, die in Online-Diensten gespeichert sind, erklären Sie sich damit einverstanden, dass Daten an das Microsoft Trust Center übertragen und dort mit Dynamics 365 Customer Insights gespeichert werden können. [Erfahren Sie mehr im Microsoft Trust Center.](https://www.microsoft.com/trust-center).

- Der Customer Insights-Dienstprinzipal muss sich in einer der folgenden Rollen befinden, um auf das Speicherkonto zugreifen zu können. Weitere Informationen finden Sie unter [Gewähren Sie dem Dienstprinzipal Berechtigungen für den Zugriff auf das Speicherkonto](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Speicher-Blob-Datenleser
  - Speicher-Blob-Datenbesitzer
  - Storage-Blob-Daten-Mitwirkender

- Der Benutzer, der die Datenquellen-Verbindung einrichtet, benötigt die wenigsten Teilnehmer-Berechtigungen für Speicherblobdaten für das Speicherkonto.

- Daten in Ihrem Data Lake Storage sollten dem Common Data Model-Standard für die Speicherung Ihrer Daten folgen und über das Common Data Model-Manifest verfügen, um das Schema der Datendateien (*.csv oder *.parquet) darzustellen. Das Manifest muss die Details der Entitäten wie Entitätsspalten und Datentypen sowie den Speicherort und den Dateityp der Datendatei enthalten. Weitere Informationen unter [Common Data Model-Manifest](/common-data-model/sdk/manifest). Wenn das Manifest nicht vorhanden ist, können Admin-Benutzer mit Zugriff auf Storage Blob Data Owner oder Storage Blob Data Teilnehmer das Schema beim Erfassen der Daten definieren.

## <a name="connect-to-azure-data-lake-storage"></a>Mit Azure Data Lake Storage verbinden

1. Wechseln Sie zu **Daten** > **Datenquellen**.

1. Wählen Sie **Datenquelle hinzufügen**.

1. **Azure Data Lake Storage-Konten** auswählen.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Dialogfeld zum Eingeben von Verbindungsdetails für Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. Geben Sie einen **Namen** und eine optionale **Beschreibung** für die neue Datenquelle ein. Der Name identifiziert eindeutig die Datenquelle und wird in nachgelagerten Prozessen referenziert und kann nicht geändert werden.

1. Wählen Sie eine der folgenden Optionen für **Verbinden Sie Ihren Speicher**. Weitere Informationen finden Sie unter [Verbinden Sie Customer Insights mit einem Azure Data Lake Storage Gen2 Konto mit einem Azure Dienstprinzipal](connect-service-principal.md).

   - **Azure-Ressource**: Geben Sie die **Ressourcen-ID** ein. Wählen Sie optional aus, wenn Sie Daten aus einem Speicherkonto über einen privaten Azure-Link erfassen möchten und wählen Sie **Privaten Link aktivieren**. Weitere Informationen finden Sie unter [Private Links](security-overview.md#set-up-an-azure-private-link).
   - **Azure-Abonnement**: Wählen Sie das **Abonnement** und dann die **Ressourcengruppe** und das **Speicherkonto** aus. Wählen Sie optional aus, wenn Sie Daten aus einem Speicherkonto über einen privaten Azure-Link erfassen möchten und wählen Sie **Privaten Link aktivieren**. Weitere Informationen finden Sie unter [Private Links](security-overview.md#set-up-an-azure-private-link).
  
   > [!NOTE]
   > Sie benötigen entweder eine der folgenden Rollen für den Container oder das Speicherkonto, um die Datenquelle zu erstellen:
   >
   >  - Datenleser des Speicher-Blobs reicht aus, um von einem Speicherkonto zu lesen und die Daten in Customer Insights zu übernehmen.
   >  - Storage Blob-Datenmitwirkender oder Besitzer ist erforderlich, wenn Sie die Manifestdateien direkt in Customer Insights bearbeiten möchten.  
  
1. Wählen Sie den Namen des **Containers**, der die Daten und das Schema (model.json- oder Manifest.json-Datei) enthält, aus denen Daten importiert werden sollen, und wählen Sie **Weiter**.
   > [!NOTE]
   > Jede model.json- oder manifest.json-Datei, die mit einer anderen Datenquelle in der Umgebung verbunden ist, wird nicht in der Liste angezeigt. Allerdings kann dieselbe model.json- oder manifest.json-Datei für Datenquellen in mehreren Umgebungen verwendet werden.

1. Um ein neues Schema zu erstellen, gehen Sie zu [Erstellen Sie eine neue Schemadatei](#create-a-new-schema-file).

1. Um ein vorhandenes Schema zu verwenden, navigieren Sie zu dem Ordner, der die Datei model.json oder Manifest.cdm.json enthält. Sie können innerhalb eines Verzeichnisses suchen, um die Datei zu finden.

1. Wählen Sie die json-Datei und wählen Sie **Weiter** aus. Eine Liste mit verfügbaren Entitäten wird angezeigt.

   :::image type="content" source="media/review-entities.png" alt-text="Dialogfeld mit einer Liste der auszuwählenden Entitäten":::

1. Wählen Sie die Entitäten aus, die Sie einschließen möchten.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialogfeld mit der Anzeige Erforderlich für Primärschlüssel":::

   > [!TIP]
   > Um die Entität in einer JSON-Bearbeitungsschnittstelle zu bearbeiten, wählen Sie die Entität und dann **Schemadatei bearbeiten** aus. Nehmen Sie Ihre Änderungen vor, und **speichern** Sie sie.

1. Für ausgewählte Entitäten, die eine inkrementelle Aufnahme erfordern, wird **Erforderlich** unter **Inkrementelle Aktualisierung** angezeigt. Für jede dieser Entitäten siehe [Konfigurieren Sie eine inkrementelle Aktualisierung für Azure Data Lake-Datenquellen](incremental-refresh-data-sources.md).

1. Für ausgewählte Entitäten, für die kein Primärschlüssel definiert wurde, wird **Erforderlich** unter **Primärschlüssel** angezeigt. Für jede dieser Entitäten:
   1. Wählen Sie **Erforderlich**. Der Bereich **Entität bearbeiten** wird angezeigt.
   1. Wählen Sie den **Primärschlüssel**. Der Primärschlüssel ist ein für die Entität eindeutiges Attribut. Damit ein Attribut ein gültiger Primärschlüssel ist, sollte es keine doppelten Werte, fehlenden Werte oder Nullwerte enthalten. Als Primärschlüssel werden String-, Integer- und GUID-Datentypattribute unterstützt.
   1. Ändern Sie optional das Partitionsmuster.
   1. Wählen Sie **Schließen**, um den Bereich zu speichern und zu schließen.

1. Wählen Sie die Anzahl der **Attribute** für jede enthaltene Entität aus. Die Seite **Attribute verwalten** wird angezeigt.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialogfeld zur Auswahl der Datenprofilerstellung.":::

   1. Erstellen Sie neue Attribute, bearbeiten oder löschen Sie vorhandene Attribute. Sie können den Namen und das Datenformat ändern oder einen semantischen Typ hinzufügen.
   1. Um Analysen und andere Funktionen zu aktivieren, wählen Sie **Datenprofilierung** für die gesamte Entität oder für bestimmte Attribute aus. Standardmäßig ist keine Entität für die Datenprofilierung aktiviert.
   1. Wählen Sie **Fertig** aus.

1. Wählen Sie **Save** (Speichern). Die Seite **Datenquellen** öffnet sich und zeigt die neue Datenquelle im Status **Wird aktualisiert** an.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Das Laden von Daten kann einige Zeit in Anspruch nehmen. Nach einer erfolgreichen Aktualisierung können die aufgenommenen Daten von der Seite [**Entitäten**](entities.md) überprüft werden.

### <a name="create-a-new-schema-file"></a>Erstellen einer neuen Schema-Datei

1. **Neue Schemadatei** auswählen.

1. Geben Sie einen Namen für die Datei ein, und wählen Sie anschließend **Speichern** aus.

1. Wählen Sie **Neue Entität** aus. Der Bereich **Neu Entität** wird angezeigt.

1. Geben Sie den Entitätsnamen ein und wählen Sie den **Speicherort der Datendateien** aus.
   - **Mehrere .csv- oder .parquet-Dateien** : Navigieren Sie zum Stammordner, wählen Sie den Mustertyp aus und geben Sie den Ausdruck ein.
   - **Einzelne .csv- oder .parquet-Dateien**: Navigieren Sie zur .csv- oder .parquet-Datei und wählen Sie sie aus.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Dialogfeld zum Erstellen einer neuen Entität mit hervorgehobenem Speicherort der Datendateien.":::

1. Wählen Sie **Save** (Speichern).

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Dialogfeld zum Definieren oder automatischen Generieren von Attributen.":::

1. Wählen Sie **Definieren Sie die Attribute**, um die Attribute manuell hinzuzufügen, oder wählen **automatisch generieren** aus. Um die Attribute zu definieren, geben Sie einen Namen ein, wählen Sie das Datenformat und optional den semantischen Typ. Für automatisch generierte Attribute:

   1. Nachdem die Attribute automatisch generiert wurden, wählen Sie **Überprüfen Sie die Attribute** aus. Die Seite **Attribute verwalten** wird angezeigt.

   1. Stellen Sie sicher, dass das Datenformat für jedes Attribut korrekt ist.

   1. Um Analysen und andere Funktionen zu aktivieren, wählen Sie **Datenprofilierung** für die gesamte Entität oder für bestimmte Attribute aus. Standardmäßig ist keine Entität für die Datenprofilierung aktiviert.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialogfeld zur Auswahl der Datenprofilerstellung.":::

   1. Wählen Sie **Fertig** aus. Die Seite **Entitäten und Felder auswählen** wird angezeigt.

1. Fahren Sie mit dem Hinzufügen von Entitäten und Attributen fort, falls zutreffend.

1. Nachdem alle Entitäten hinzugefügt wurden, wählen Sie **Einschließen** aus, um die Entitäten in die Aufnahme von Datenquelle aufzunehmen.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialogfeld mit der Anzeige Erforderlich für Primärschlüssel":::

1. Für ausgewählte Entitäten, die eine inkrementelle Aufnahme erfordern, wird **Erforderlich** unter **Inkrementelle Aktualisierung** angezeigt. Für jede dieser Entitäten siehe [Konfigurieren Sie eine inkrementelle Aktualisierung für Azure Data Lake-Datenquellen](incremental-refresh-data-sources.md).

1. Für ausgewählte Entitäten, für die kein Primärschlüssel definiert wurde, wird **Erforderlich** unter **Primärschlüssel** angezeigt. Für jede dieser Entitäten:
   1. Wählen Sie **Erforderlich**. Der Bereich **Entität bearbeiten** wird angezeigt.
   1. Wählen Sie den **Primärschlüssel**. Der Primärschlüssel ist ein für die Entität eindeutiges Attribut. Damit ein Attribut ein gültiger Primärschlüssel ist, sollte es keine doppelten Werte, fehlenden Werte oder Nullwerte enthalten. Als Primärschlüssel werden String-, Integer- und GUID-Datentypattribute unterstützt.
   1. Ändern Sie optional das Partitionsmuster.
   1. Wählen Sie **Schließen**, um den Bereich zu speichern und zu schließen.

1. Wählen Sie **Save** (Speichern). Die Seite **Datenquellen** öffnet sich und zeigt die neue Datenquelle im Status **Wird aktualisiert** an.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Das Laden von Daten kann einige Zeit in Anspruch nehmen. Nach einer erfolgreichen Aktualisierung können die aufgenommenen Daten von der Seite [**Entitäten**](entities.md) überprüft werden.

## <a name="edit-an-azure-data-lake-storage-data-source"></a>Eine Azure Data Lake Storage Datenquelle bearbeiten

Sie können die Option *Stellen Sie eine Verbindung mit dem Speicherkonto her* aktualisieren. Weitere Informationen finden Sie unter [Verbinden Sie Customer Insights mit einem Azure Data Lake Storage Gen2 Konto mit einem Azure Dienstprinzipal](connect-service-principal.md). Um eine Verbindung zu einem anderen Container als Ihrem Speicherkonto herzustellen oder den Kontonamen zu ändern, [erstellen Sie eine neue Datenquellenverbindung](#connect-to-azure-data-lake-storage).

1. Wechseln Sie zu **Daten** > **Datenquellen**.

1. Wählen Sie neben der Datenquelle, die Sie aktualisieren möchten, **Bearbeiten** aus.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Dialogfeld zum Bearbeiten von Azure Data Lake Datenquelle.":::

1. Ändern Sie eine der folgenden Informationen:

   - **Beschreibung des Dataflows**
   - **Verbinden Sie Ihren Speicher** und Verbindungsinformationen. Sie können die **Container**-Informationen beim Aktualisieren der Verbindung nicht ändern.
      > [!NOTE]
      > Dem Speicherkonto oder Container muss eine der folgenden Rollen zugewiesen werden:
        > - Speicher-Blob-Datenleser
        > - Speicher-Blob-Datenbesitzer
        > - Storage-Blob-Daten-Mitwirkender

   - Wählen Sie optional aus, wenn Sie Daten aus einem Speicherkonto über einen privaten Azure-Link erfassen möchten und wählen Sie **Privaten Link aktivieren** aus. Weitere Informationen finden Sie unter [Private Links](security-overview.md#set-up-an-azure-private-link).

1. Wählen Sie **Weiter** aus.
1. Ändern Sie eine der folgenden Informationen:
   - Navigieren Sie zu einer anderen model.json- oder Manifest.json-Datei mit einem anderen Satz von Entitäten aus dem Container.
   - Um weitere Entitäten zur Aufnahme hinzuzufügen, wählen Sie **Neue Entität** aus.
   - Um bereits ausgewählte Entitäten zu entfernen, wenn keine Abhängigkeiten vorhanden sind, wählen Sie die Entität und **Löschen** aus.
      > [!IMPORTANT]
      > Wenn Abhängigkeiten von der vorhandenen model.json- oder manifest.json-Datei und der Gruppe von Entitäten bestehen, wird eine Fehlermeldung angezeigt und Sie können keine andere model.json- oder manifest.json-Datei auswählen. Entfernen Sie diese Abhängigkeiten, bevor Sie die model.json- oder manifest.json-Datei ändern, oder erstellen Sie eine neue Datenquelle mit der model.json- oder manifest.json-Datei, die Sie verwenden möchten, um das Entfernen der Abhängigkeiten zu vermeiden.
   - Um den Speicherort der Datendatei oder den Primärschlüssel zu ändern, wählen Sie **Bearbeiten** aus.
   - Informationen zum Ändern der inkrementellen Aufnahmedaten finden Sie unter [Konfigurieren Sie eine inkrementelle Aktualisierung für Azure Data Lake-Datenquellen](incremental-refresh-data-sources.md)
   - Ändern Sie nur den Entitätsnamen so, dass er mit dem Entitätsnamen in der JSON-Datei übereinstimmt.

     > [!NOTE]
     > Lassen Sie den Entitätsnamen in Customer Insights nach der Aufnahme immer mit dem Entitätsnamen in der Datei „model.json“ oder „Manifest.json“ identisch. Customer Insights validiert bei jeder Systemaktualisierung alle Entitätsnamen mit model.json oder Manifest.json. Wenn ein Entitätsname innerhalb oder außerhalb von Customer Insights geändert wird, tritt ein Fehler auf, da Customer Insights den neuen Entitätsnamen in der JSON-Datei nicht finden kann. Wenn ein aufgenommener Entitätsname versehentlich geändert wurde, bearbeiten Sie den Entitätsnamen in Customer Insights so, dass er mit dem Namen in der JSON-Datei übereinstimmt.

1. Wählen Sie **Attribute** zum Hinzufügen oder Ändern von Attributen oder zum Aktivieren von Datenprofilen. Wählen Sie dann **Fertig**.

1. Klicken Sie auf **Speichern**, um Ihre Änderungen zu übernehmen und zur Seite **Datenquellen** zurückzukehren.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
