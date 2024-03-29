---
title: 'Schritt 1: Vorbereiten des Quellservers für die Migration zu Windows Server Essentials'
description: Beschreibt, wie Windows Server Essentials
ms.custom: na
ms.date: 10/03/2016
ms.prod: windows-server-2016-essentials
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 244c8a06-04c6-4863-8b52-974786455373
author: nnamuhcs
ms.author: coreyp
manager: dongill
ms.openlocfilehash: 23dd4cb7513619382df55d674d5c4ee876c41d18
ms.sourcegitcommit: eaf071249b6eb6b1a758b38579a2d87710abfb54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66432591"
---
# <a name="step-1-prepare-your-source-server-for-windows-server-essentials-migration"></a>Schritt 1: Vorbereiten des Quellservers für die Migration zu Windows Server Essentials

>Gilt für: Windows Server 2016 Essentials, Windows Server 2012 R2 Essentials, Windows Server 2012 Essentials

In diesem Thema wird erläutert, wie Sie den Quellserver sichern, die Systemintegrität des Quellservers prüfen, die aktuellen Service Packs und Fixes installieren und die Netzwerkkonfiguration überprüfen.  

## <a name="to-prepare-for-migration"></a>So bereiten Sie die Migration vor  
 Führen Sie vorab folgende Schritte aus, um sicherzustellen, dass eine erfolgreiche Migration der Einstellungen und Daten vom Quellserver zum Zielserver möglich ist.  

1.  [Sichern des Quellservers](Step-1--Prepare-your-Source-Server-for-Windows-Server-Essentials-migration.md#BKMK_BackUpYourSourceServerToPrepareForMigration)  

2.  [Installieren Sie die neuesten Servicepacks](Step-1--Prepare-your-Source-Server-for-Windows-Server-Essentials-migration.md#BKMK_InstallTheMostRecentServicePacksToPrepareForMigration)  

3.  [Löschen Sie das Protokoll auf eine diensteinstellung für das Konto](Step-1--Prepare-your-Source-Server-for-Windows-Server-Essentials-migration.md#BKMK_DeleteSvcAcctSetting)  

4.  [Bewerten Sie die Integrität des Quellservers](Step-1--Prepare-your-Source-Server-for-Windows-Server-Essentials-migration.md#BKMK_EvaluateHealth)  

5.  [Erstellen Sie einen Plan zum Migrieren von Line-of-Business-Anwendungen](Step-1--Prepare-your-Source-Server-for-Windows-Server-Essentials-migration.md#BKMK_MigrateLOB)  

###  <a name="BKMK_BackUpYourSourceServerToPrepareForMigration"></a> Sichern des Quellservers  
 Sichern Sie den Quellserver, bevor Sie mit dem Migrationsprozess beginnen. Durch diese Sicherung schützen Sie sich vor Datenverlusten, wenn während der Migration ein nicht behebbarer Fehler auftritt.  

##### <a name="to-back-up-the-source-server"></a>So sichern Sie den Zielserver  

1. Verwenden Sie eine der Ressourcen in der folgenden Tabelle, um eine vollständige Sicherung des Quellservers auszuführen.  

2. Überprüfen Sie, ob die Sicherung erfolgreich ausgeführt wurde. Zum Prüfen der Integrität der Sicherung wählen Sie beliebige Dateien der Sicherung aus und stellen diese an einem anderen Speicherort wieder her. Überprüfen Sie dann, ob die wiederhergestellten Dateien mit den Originaldateien identisch sind.  

   |Produkt|Ressource|
   |---|---|
   |Windows Small Business Server 2003|[Sichern und Wiederherstellen von Windows Small Business Server 2003](https://msdn.microsoft.com/library/cc875809.aspx) 
   |Windows Small Business Server 2008|[Sichern und Wiederherstellen von Daten in Windows Small Business Server 2008](https://technet.microsoft.com/library/cc527505\(WS.10\).aspx)
   |Windows Server 2008 Foundation|[Sicherung und Wiederherstellung](https://technet.microsoft.com/library/cc754097\(WS.10\).aspx)  
   |Windows Small Business Server 2011 Essentials|[Erfahren Sie mehr über das Einrichten der serversicherung](https://technet.microsoft.com/library/server-backup-support-1.aspx)
   |Windows Small Business Server 2011 Standard|[Verwalten der Serversicherung](https://technet.microsoft.com/library/cc527488.aspx)  
   |Windows Server Essentials|[Verwalten der Sicherung und Wiederherstellung in Windows Server Essentials](https://technet.microsoft.com/library/jj713536.aspx)

###  <a name="BKMK_InstallTheMostRecentServicePacksToPrepareForMigration"></a> Installieren Sie die neuesten Servicepacks  
 Sie müssen vor der Migration die neuesten Updates und Service Packs auf dem Quellserver installieren.  

###  <a name="BKMK_DeleteSvcAcctSetting"></a> Löschen Sie das Protokoll auf eine diensteinstellung für das Konto  
 Wenn Sie von Windows Small Business Server 2003 oder Windows Server 2003 migrieren, löschen Sie die Kontoeinstellung **Anmelden als Dienst** aus der Gruppenrichtlinie.  

##### <a name="to-delete-the-log-on-as-a-service-account-setting"></a>Das Protokoll als diensteinstellung Konto löschen  

1.  Klicken Sie zum Öffnen des Tools **Gruppenrichtlinienverwaltung** auf **Start**, klicken Sie auf **Systemsteuerung**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **Gruppenrichtlinienverwaltung**.  

2.  Klicken Sie mit der rechten Maustaste auf **Standard-Domänencontrollerrichtlinie**, und klicken Sie dann auf **Bearbeiten**.  

3.  Navigieren Sie zu **Computerkonfigurationen\Windows-Einstellungen\Sicherheitseinstellungen\Lokale Richtlinien\Zuweisen von Benutzerrechten**.  

4.  Doppelklicken Sie im Detailbereich auf **Anmelden als Dienst**.  

5.  Deaktivieren Sie das Kontrollkästchen **Diese Richtlinieneinstellungen definieren** .  

6.  Löschen Sie \\\localhost\SYSVOL\\< Domainname\>\scripts\SBS_LOGIN_SCRIPT.bat.  

###  <a name="BKMK_EvaluateHealth"></a> Bewerten Sie die Integrität des Quellservers  
 Es ist wichtig, dass Sie die Integrität des Quellservers auswerten, bevor Sie mit der Migration beginnen. Verwenden Sie die folgenden Verfahren, um sicherzustellen, dass die Updates aktuell sind, um einen Systemintegritätsbericht zu generieren und das Windows Server Solutions Best Practice Analyzer (BPA) auszuführen.  

#### <a name="download-and-install-critical-and-security-updates"></a>Laden Sie kritische und Sicherheits-Updates herunter und installieren sie sie.  
 Durch das Installieren von kritischen und Sicherheits-Updates auf dem Quellserver wird sichergestellt, dass Ihre Migration erfolgreich wird und hilft dabei, Ihr Netzwerk während der Migration zu schützen.  

###### <a name="to-check-for-the-latest-updates"></a>So überprüfen Sie die neuesten Updates  

1.  Klicken Sie auf dem Quellserver auf **Start**, klicken Sie auf **Programme** und klicken Sie dann auf **Windows Update**.  

2.  Klicken Sie auf **Nach Updates suchen**.  

3.  Wenn entsprechende Updates ermittelt werden, klicken Sie auf **Updates installieren**.  

#### <a name="run-the-best-practices-analyzer"></a>Ausführen des Best Practices Analyzer  
 Sie können den Best Practices Analyzer (BPA) ausführen, um sicherzustellen, dass vor Beginn des Migrationsvorgangs keine Probleme auf dem Server, im Netzwerk, oder in der Domäne vorliegen. Das BPA erfasst Konfigurationsinformationen aus den folgenden Quellen:  

-   Active Directory Windows Management Instrumentation (WMI)  

-   Registrierung  

-   Internetinformationsdienste (IIS)  

###### <a name="to-use-the-bpa-to-analyze-your-source-server"></a>So verwenden Sie den BPA zum Analysieren des Quellservers  

1. Die folgende Tabelle enthält Links zum Microsoft Download Center, wo Sie den Best Practices Analyzer (BPA) für den Quellserver herunterladen und installieren können.  


   |             Wenn auf dem Quellserver ausgeführt wird             |                                                     Sie können die BPA-Tools von abrufen.                                                      |
   |----------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
   |                     Windows SBS 2003                     | [Microsoft Windows Small Business Server 2003 Best Practices Analyzer-website](https://www.microsoft.com/download/details.aspx?id=5334) |
   |                     Windows SBS 2008                     | [Microsoft Windows Small Business Server 2008 Best Practices Analyzer-website](https://www.microsoft.com/download/details.aspx?id=6231) |
   | Windows SBS 2011 Essentials oder Windows SBS 2011 Standard |          [Windows Server Solutions Best Practices Analyzer-website](https://www.microsoft.com/download/details.aspx?id=15556)           |
   |     Windows Server Essentials oder WindowsServer 2012     |                                                          Das Server-Dashboard                                                           |


2. Gehen Sie nach dem Abschluss des Downloads auf **Start**, **Alle Programme** und dann auf **SBS Best Practices Analyzer Tool**.  

   > [!NOTE]
   >  Suchen Sie vor dem Überprüfen des Servers nach Updates.  

3. Klicken Sie im Navigationsbereich auf **Überprüfung starten**.  

    Wenn Sie den Quellserver Windows Server Essentials ausgeführt wird, führen Sie folgende Schritte aus:  

   1.  Melden Sie sich auf dem Zielserver als Administrator an und öffnen Sie das Dashboard.  

   2.  Klicken Sie im Dashboard auf die Registerkarte **Geräte**.  

   3.  In der <**Server** >**Aufgaben** Bereich, klicken Sie auf **Best Practices Analyzer**.  

4. Geben Sie im Detailbereich die Überprüfungsbezeichnung ein und klicken Sie dann auf **Überprüfung starten**. Die Überprüfungsbezeichnung ist der Name des Überprüfungsberichts, z. B. **SBS BPA Scan 1Jul2013**.  

5. Nachdem die Überprüfung abgeschlossen ist, klicken Sie auf **Bericht für diese Bewährte Methoden-Überprüfung anzeigen**.  

   Nachdem das BPA-Tool Informationen zur Serverkonfiguration gesammelt hat, überprüft es, ob die Informationen korrekt sind, und legt dann den Administratoren eine Liste der Informationen und Probleme nach Schweregrad sortiert vor. Die Liste beschreibt jedes Problem und bietet eine Empfehlung oder eine mögliche Lösung. Folgende drei Berichtstypen sind verfügbar:  

|Berichttyp|Beschreibung
|-----------------|----------------- 
|Listenberichte|Zeigt Berichte in einer eindimensionalen Liste an. 
|Strukturberichte|Zeigt Berichte in einer hierarchischen Liste an.

Wenn Sie die Beschreibung und Lösungen für ein Problem anzeigen möchten, klicken Sie im Bericht auf das betreffende Problem. Nicht alle vom BPA-Tool erfassten Probleme wirken sich auf die Migration aus, Sie sollten jedoch möglichst viele der Probleme beheben, um eine erfolgreiche Migration sicherzustellen.  

####  <a name="BKMK_SynchronizeTheSourceServerTimeWithAnExternalTimeSource"></a> Synchronisieren der quellserveruhrzeit mit einer externen Zeitquelle  
 Die Uhrzeit auf dem Quellserver darf maximal fünf Minuten von der Uhrzeit auf dem Zielserver abweichen, und die Datums- und Zeitzone muss auf beiden Servern gleich sein. Wenn der Quellserver einen virtuellen Computer ausführt, müssen das Datum, die Uhrzeit und die Zeitzone auf dem Hostserver diesen Angaben auf dem Quell- und dem Zielserver entsprechen. Um sicherzustellen, dass Windows Server Essentials erfolgreich installiert wurde, müssen Sie die Uhrzeit des Quellservers mit dem Network Time Protocol (NTP)-Server im Internet synchronisieren.  

###### <a name="to-synchronize-the-source-server-time-with-the-ntp-server"></a>So synchronisieren Sie die Uhrzeit des Quellservers mit dem NTP-Server  

1.  Melden Sie sich mit einem Domänenadministratorkonto und -kennwort am Quellserver an.  

2.  Klicken Sie auf **Start**, dann auf **Ausführen**, geben Sie im Textfeld **cmd** ein, und drücken Sie dann die EINGABETASTE.  

3.  Geben Sie an der Eingabeaufforderung den Befehl w32tm/config / DOMHIER / reliable: keine/Update, und drücken Sie dann die EINGABETASTE.  

4.  Geben Sie an der Eingabeaufforderung net Stop w32time, und drücken Sie dann die EINGABETASTE.  

5.  Geben Sie an der Eingabeaufforderung net Start w32time, und drücken Sie dann die EINGABETASTE.  

> [!IMPORTANT]
>  Während der Installation von Windows Server Essentials müssen Sie die Gelegenheit, überprüfen die Zeit auf dem Zielserver, und ändern Sie ihn bei Bedarf. Stellen Sie sicher, dass die Uhrzeit höchstens fünf Minuten von der Uhrzeit auf dem Quellserver abweicht. Nachdem die Installation abgeschlossen ist, wird der Zielserver mit dem NTP-Server synchronisiert. Alle Computer, die Mitglied der Domäne sind (einschließlich des Quellservers) werden mit dem Zielserver synchronisiert, der die Rolle des Betriebsmasters für den PDC-Emulator (Primary Domain Controller, primärer Domänencontroller) ausübt.  

###  <a name="BKMK_MigrateLOB"></a> Erstellen Sie einen Plan zum Migrieren von Line-of-Business-Anwendungen  
 Eine Branchenanwendung ist eine wichtige Computeranwendung, die für den Geschäftsbetrieb unabdingbar ist. Dabei kann es sich z. B. um Buchhaltungs-, Supply Chain Management- oder Ressourcenplanungsanwendungen handeln.  

 Wenn Sie die Migration Ihrer Branchenanwendungen planen, beraten Sie sich mit dem Branchenanwendungsanbieter, um die geeignete Methode zum Migrieren der einzelnen Anwendungen zu ermitteln. Außerdem müssen Sie das Medium ermitteln, das zum Installieren der Branchenanwendungen auf dem Zielserver verwendet wird.  

> [!NOTE]
>  Wenn Sie zum Entwickeln von Windows Small Business Server 2011 Essentials SDK verwendet ein angepasstes Systemintegritäts- oder Warnungs-Add-In, und Sie weiterhin das Add-in in Windows Server Essentials verwenden möchten, müssen Sie auch das Add-in aktualisieren und auf dem Zielserver bereitstellen.  


### <a name="create-a-plan-to-migrate-email-hosted-on-windows-sbs-2011-windows-sbs-2008-and-windows-sbs-2003"></a>Erstellen eines Plans zum Migrieren von auf Windows SBS 2011, Windows SBS 2008 und Windows SBS 2003 gehosteten E-Mails  
 In Windows SBS 2011, Windows SBS 2008 und Windows SBS 2003 wird der E-Mail-Dienst über den Microsoft Exchange Server bereitgestellt. Windows Server Essentials bietet jedoch keine e-Mail-posteingangsdienst. Wenn Sie derzeit einen Server mit Windows SBS 2011, Windows SBS 2008 oder Windows SBS 2003 zum Hosten Ihrer Unternehmens-s-e-Mail verwenden, Sie müssen zum Migrieren zu einer alternativen lokalen oder gehosteten Lösung.  

> [!NOTE]
>  Nachdem Sie den Quellserver aktualisiert und für die Migration vorbereitet haben, ist es empfehlenswert, eine Sicherung des aktualisierten Servers zu erstellen, bevor Sie mit der Migration fortfahren.  

#### <a name="migrate-email-to-microsoft-office-365"></a>Migrieren von E-Mails zu Microsoft Office 365  
 Wenn Sie sich für Microsoft Office 365 als E-Mail-Lösung für Ihre Domäne entschieden haben, folgen Sie den Anweisungen unter [Migrieren aller Postfächer zur Cloud mit einer Exchange-Übernahmemigration](http://help.outlook.com/140/ms.exch.ecp.emailmigrationwizardexchangelearnmore.aspx) , um die E-Mail-Migration zu Office 365 zu starten. Es wird empfohlen, die e-Mail-Migration abzuschließen, bevor Sie Windows Server Essentials installieren.  

> [!NOTE]
>  Der Schritt zum Entfernen der lokalen Exchange-Server auf dem Quellserver ist erforderlich, wenn Sie beabsichtigen, Windows Server Essentials in Office 365 integrieren. Informationen zum Migrieren der öffentlichen Ordner von Exchange Server zu Office 365 finden Sie im Blogbeitrag [Microsoft Exchange 2013 Public Folders Migration Scripts for Office 365](http://blogs.technet.com/b/fmustafa/archive/2013/04/11/microsoft-exchange-2013-public-folders-migration-scripts-for-office-365.aspx).  
>   
>  Nach Abschluss die Installation sollten aktivieren Sie das Office 365-Integration Feature in Windows Server Essentials mit dem **in Microsoft Office 365 integrieren** Aufgabe.  

> [!IMPORTANT]
>  Um eine Verbindung des Office 365-Migrationstools mit Exchange Server auf dem Quellserver zu ermöglichen, müssen Sie auf dem Quellserver RPC über HTTP aktivieren. Informationen zum Aktivieren von RPC über HTTP finden Sie unter [Erstmaliges Bereitstellen von RPC über HTTP in Small Business Server 2003 (Standard oder Premium)](https://technet.microsoft.com/library/bb123622%28EXCHG.65%29.aspx). Wenn das Office 365-Migrationstool nach dem Aktivieren von RPC über HTTP nicht ordnungsgemäß ausgeführt werden kann, zeigen Sie die Einstellung **ValidPorts** in der Registrierung unter HKEY_LOCAL_MACHINE\Software\Microsoft\Rpc\RpcProxy an, und stellen sicher, dass der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) für den Quellserver dort aufgeführt ist. Wenn der FQDN nicht aufgeführt ist, fügen Sie ihn anhand des folgenden Beispiels manuell hinzu:  
>   
>  remote. *contoso*.com:6001-6002;remote. *contoso*.com:6004 (ersetzen Sie *contoso* durch den Namen Ihrer Domäne).  

#### <a name="migrate-email-to-another-on-premises-exchange-server"></a>Migrieren von E-Mail zu einem anderen lokalen Exchange-Server  
 Weitere Informationen zum Migrieren von e-Mail-Adresse zu einem anderen Exchange-Server lokal, finden Sie unter [Integrieren eines lokalen Exchange-Servers mit Windows Server Essentials](https://technet.microsoft.com/library/jj200172.aspx). Es wird empfohlen, dass Sie den neuen lokalen Exchange-Server einrichten, nach der Installation von Windows Server Essentials, und schließen Sie dann die e-Mail-Migration, bevor Sie den Quellserver herabstufen.  

> [!NOTE]
>  Der Windows Small Business Server-POP3-Connector ist nicht in Exchange Server enthalten. Nach der Migration von Daten zu einem anderen Exchange-Server kann POP3-Connector-Funktion nicht mehr genutzt werden.  

> [!NOTE]
>  Nachdem Sie den Quellserver aktualisiert und für die Migration vorbereitet haben, sollten Sie eine Sicherung des aktualisierten Servers erstellen, bevor Sie mit der Migration fortfahren.  

## <a name="next-steps"></a>Nächste Schritte  
 Sie haben den Quellserver für die Migration zu Windows Server Essentials vorbereitet.  Wechseln Sie nun zur [Schritt2: Installieren von Windows Server Essentials als ein neuer replikatsdomänencontroller](Step-2--Install-Windows-Server-Essentials-as-a-new-replica-domain-controller.md).  

Alle Schritte finden Sie unter [Migrieren zu Windows Server Essentials](Migrate-from-Previous-Versions-to-Windows-Server-Essentials-or-Windows-Server-Essentials-Experience.md).

