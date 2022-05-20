---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755543"
---
Beginnen Sie nach der Aufnahme der Daten mit dem Datenvereinheitlichungsprozess, um ein Unified customer profile zu erstellen. Weitere Informationen finden Sie unter [Datenvereinheitlichung](../data-unification.md).

### <a name="select-source-fields"></a>Auswählen von Quellfeldern

1. Nach der Datenerfassung ordnen Sie die Kontakte aus den eCommerce- und Loyalty-Daten den gemeinsamen Datentypen zu. Gehen Sie zu **Daten** > **Vereinheitlichen**.

1. Wählen Sie die Entitäten, die das Kundenprofil darstellen - **eCommerceContacts** und **loyCustomers**.

   ![Vereinheitlichen Sie E-Commerce- und Treue-Datenquellen.](../media/unify-ecommerce-loyalty.png)

1. Wählen Sie **KontaktId** als Primärschlüssel für **eCommerceKontakte** und **LoyaltyID** als Primärschlüssel für **loyCustomers**.

1. Wählen Sie **Weiter** aus. Überspringen Sie doppelte Datensätze überspringen und wählen Sie **Weiter**.

### <a name="match-conditions"></a>Abgleich-Bedingungen

1. Wählen Sie **eCommerceContacts: eCommerce** als primäre Entität und schließen Sie alle Datensätze ein.

1. Wählen Sie **loyCustomers : LoyaltyScheme**, und nehmen Sie alle Datensätze auf.

1. Fügen Sie eine Regel hinzu:
   - Wählen Sie **FullName** sowohl für eCommerceContacts als auch für loyCustomers.
   - Wählen Sie **Typ (Telefon, Name, Adresse ...)** für **Normalisieren**.
   - Setzen Sie **Präzisionsstufe**: **Basis** und **Wert**: **Hoch**.
   - Geben Sie für den Namen **FullName, Email** ein.

1. Fügen Sie eine zweite Bedingung für die E-Mail-Adresse hinzu:
   - Wählen Sie **E-Mail** sowohl für eCommerceContacts als auch für loyCustomers.
   - Lassen Sie Normalisieren leer.
   - Setzen Sie **Präzisionsstufe**: **Basis** und **Wert**: **Hoch**.

   ![Übereinstimmungsregel für Name und E-Mail vereinheitlichen.](../media/unify-match-rule.png)

1. Wählen Sie **Fertig** aus.

1. Wählen Sie **Weiter** aus.

### <a name="unify-fields"></a>Vereinheitlichen von Feldern

1. Benennen Sie die **ContactId** für **loyCustomers** in **ContactIdLOYALTY** um, um sie von den anderen aufgenommenen IDs zu unterscheiden.

1. Wählen Sie **Weiter**, um zu prüfen, und wählen Sie dann **Kundenprofile erstellen**.
