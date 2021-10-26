---
title: Testversion FAQ - Dynamics 365 Customer Insights
description: Lösungen für häufig gestellte Fragen im Zusammenhang mit der Einrichtung und Verwaltung der Testversion von Customer Insights. Erfahren Sie, wie Sie plattform- und app-spezifische Probleme lösen können.
author: m-hartmann
ms.author: mhart
ms.date: 09/30/2021
ms.topic: get-started
ms.service: customer-insights
ms.custom: template-trial-faq
ms.reviewer: jeffhar
manager: shellyha
ms.openlocfilehash: 2837ae13b4150310193a2d09d59aed66b4a69c69
ms.sourcegitcommit: e6020c178a61beb0ee31a031c11ded914d10d995
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2021
ms.locfileid: "7642870"
---
# <a name="dynamics-365-customer-insights-trial-faq"></a>Häufig gestellte Fragen zur Testversion von Dynamics 365 Customer Insights

## <a name="sign-up"></a>Services

### <a name="what-are-the-system-requirements-for-the-trial"></a>Was sind die Systemanforderungen für den Test?

Diese App ist ein cloudbasierter Dienst, für den keine spezielle Software auf den Computern der Benutzer ausgeführt werden muss. Es ist nur ein aktueller Webbrowser erforderlich, obwohl gewisse Einschränkungen gelten. Um das beste Testerlebnis zu erzielen, vermeiden Sie es, im Inkognito-Modus auf die Testversion zuzugreifen, und wählen Sie den Teststandort in Ihrer Nähe. [Erfahren Sie mehr über die Anforderungen für Webanwendungen.](/power-platform/admin/web-application-requirements)

### <a name="how-do-i-sign-up-for-the-trial-without-a-microsoft-365-tenant"></a>Wie melde ich mich für den Test an, ohne einen Microsoft 365-Mandanten zu haben?

Sie können eine nicht beruflich genutzte E-Mail-Adresse eingeben und wir erstellen ein Konto und einen Mandanten für Sie.

### <a name="can-i-sign-up-for-multiple-dynamics-365-apps-such-as-sales-marketing-and-customer-service"></a>Kann ich mich für mehrere Dynamics 365 Apps wie Sales, Marketing und Customer Service anmelden?

Ja, das können Sie. Um alle verfügbaren Tests zu sehen, [besuchen Sie die Seite des Trial Hubs](https://dynamics.microsoft.com/dynamics-365-free-trial). Sie können dasselbe E-Mail-Konto verwenden, um sich für verschiedene Tests anzumelden. Es ist jedoch nicht möglich, mehrere Apps auf der gleichen Testseite zu verwenden. Jeder Test wird unter einer anderen Organisation und URL durchgeführt. Die Daten des Tests werden nicht zwischen den Apps ausgetauscht.

## <a name="trial-app"></a>Test-App

### <a name="i-didnt-receive-the-trial-details-email-after-signing-up-what-should-i-do"></a>Ich habe nach der Anmeldung keine E-Mail mit den Details zum Test erhalten. Was soll ich tun?

Wenn Sie sich für den Test anmelden, erhalten Sie eine E-Mail mit den Einzelheiten zum Test. Wenn Sie die E-Mail nicht in Ihrem Posteingang sehen, überprüfen Sie Ihren Spam-Ordner. Alternativ können Sie auch wie folgt auf Ihre App zugreifen:

1. Gehen Sie zur Testseite und wählen Sie **kostenlos testen** aus.
1. Geben Sie die E-Mail-ID ein, mit der Sie sich für den Test angemeldet haben. Sie werden zu Ihrer App zum Testen weitergeleitet.

### <a name="how-do-i-add-more-users-to-a-trial"></a>Wie füge ich weitere Benutzer zu einem Test hinzu?

Um Benutzer hinzuzufügen, gehen Sie zum [Microsoft 365 Admin Center](https://admin.microsoft.com) und verwenden Sie das Test-Administratorkonto. Folgen Sie der [Anleitung des Admin Centers](/microsoft-365/admin/add-users/add-users), um Benutzer bis zum Limit der Testlizenz hinzuzufügen. Wenn der Benutzer, den Sie hinzufügen, bereits über ein Microsoft 365-Konto verfügt, weisen Sie ihm eine geeignete Sicherheitsrolle in der Test-Org zu. Weitere Informationen finden Sie unter [Zuweisen einer Sicherheitsrolle zu einem Benutzer](/power-platform/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user).

### <a name="how-many-users-can-i-add-to-my-trial-environment"></a>Wie viele Benutzer kann ich zu meiner Testumgebung hinzufügen?

Sie können der Testumgebung eine unbegrenzte Anzahl von Benutzern hinzufügen.

### <a name="how-do-i-reset-the-trial-environment"></a>Wie kann ich die Testumgebung zurücksetzen?

Sie können die Testumgebung nicht zurücksetzen. Sie können jedoch das Ende des Testzeitraums abwarten und sich dann erneut für eine Testversion anmelden.

## <a name="trial-expiration-and-extension"></a>Ablauf der Testversion und Verlängerung

### <a name="how-do-i-extend-the-trial"></a>Wie kann ich den Test verlängern?

Sie können die Testversion direkt in der App verlängern. Sie können Ihre Testversion einmal verlängern.

### <a name="can-i-convert-the-trial-to-a-paid-license"></a>Kann ich die Testversion in eine kostenpflichtige Lizenz umwandeln?

Wir empfehlen grundsätzlich, beim Upgrade auf die kostenpflichtige Version von Customer Insights mit Ihren eigenen Daten neu zu beginnen. 

Wenn Sie nur Publikum Insights verwenden, können Sie optional Ihre Daten aus einer Testumgebung kopieren, wenn Sie Customer Insights erwerben. Sie müssen Administrator der Customer Insights-Testversion und der globale Administrator Ihres Microsoft 365-Mandanten oder Dynamics 365-Administrator in Ihrer Organisation sein, um die Einstellungen von einer Testumgebung in eine kostenpflichtige Umgebung zu migrieren. 

Nachdem Sie sich zum ersten Mal bei Ihrer kostenpflichtigen Instanz von Customer Insights angemeldet haben, werden Sie aufgefordert, eine neue Umgebung zu erstellen. In diesem Prozess können Sie die Konfiguration aus einer vorhandenen Umgebung kopieren und die meisten Einstellungen migrieren. Wenn Sie über die oben genannten Berechtigungen verfügen, wird die Testumgebung in dieser Liste angezeigt. Weitere Informationen finden Sie unter [Die Umgebungskonfiguration kopieren](audience-insights/manage-environments.md#copy-the-environment-configuration).

### <a name="what-are-the-trial-limits-and-quotas"></a>Welche Beschränkungen und Kontingente gelten für den Test?

- Sie können Ihr eigenes Azure Data Lake Storage Konto nicht verwenden, um Ausgabedaten während einer Testversion von Zielgruppenerkenntnissen zu speichern. Sie können jedoch Daten aus einem Data Lake Storage-Konto erfassen.
- Sie können bis zu 3 GB Daten in der Dataverse Umgebung speichern, die automatisch bereitgestellt wird, wenn Sie eine Customer Insights Testversion starten.

## <a name="customer-insights-specific-questions"></a>Customer Insights spezifische Fragen

### <a name="how-do-i-start-using-the-trial"></a>Wie beginne ich mit der Nutzung der Testversion?

Nachdem Sie sich für die Testversion angemeldet haben, gelangen Sie zum Hauptbildschirm der App. Der Hauptbildschirm enthält Links zu Benutzerhandbüchern und Tutorials. Um mehr zu erfahren, besuchen Sie die Links auf der Seite [Zusätzliche Ressourcen](trial-signup.md#additional-resources) zum Einrichten der Testversion auf der Anmeldeseite.

### <a name="what-features-are-available-in-the-trial"></a>Welche Funktionen stehen in der Testversion zur Verfügung?

Die meisten Funktionen der Customer Insights-Funktionen sind in der Testversion verfügbar.

Die folgende Funktion ist nicht verfügbar: 
- Sie können keine neuen Umgebungen erstellen, die Ihr eigenes Azure Data Lake Storage Konto verwenden.

### <a name="how-long-does-the-trial-last"></a>Wie lange ist die Testversion gültig?

Die Customer Insights-Testversion dauert 30 Tage. Sie können die Testversion einmalig nach 23 Tagen verlängern, wenn Sie sich bei Ihrer Testumgebung anmelden.

### <a name="how-do-i-remove-sample-data-from-the-trial"></a>Wie kann ich Beispieldaten aus dem Test entfernen?

Sie können die Beispieldaten aus der Testinstanz nicht entfernen.
