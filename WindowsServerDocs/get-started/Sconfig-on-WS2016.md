---
title: Konfigurieren einer Server Core-Installation von Windows Server mit „Sconfig.cmd“
description: Erläutert die Verwendung von „Sconfig.cmd“
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.date: 10/17/2017
ms.technology: server-general
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: e6cac074-c6fc-46dd-9664-fa0342c0a5e8
author: jaimeo
ms.author: jaimeo
manager: dongill
ms.localizationpriority: medium
ms.openlocfilehash: 617005fd2d4e63c3cfc11bed28404656b2a81d6e
ms.sourcegitcommit: 0948a1abff1c1be506216eeb51ffc6f752a9fe7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2019
ms.locfileid: "66749578"
---
# <a name="configure-a-server-core-installation-of-windows-server-2016-or-windows-server-version-1709-with-sconfigcmd"></a>Konfigurieren einer Server Core-Installation von Windows Server mit „Sconfig.cmd“

> Gilt für: WindowsServer (Halbjährlicher Kanal) und WindowsServer 2016

In der Version 1709 von Windows Server 2016 können Sie das Server-Konfigurationstool (Sconfig.cmd) zum Konfigurieren und Verwalten verschiedener allgemeiner Aspekte von Server Core-Installationen verwenden. Sie müssen Mitglied der Gruppe %%amp;quot;Administratoren%%amp;quot; sein, um das Tool verwenden zu können.

Sie können „Sconfig.cmd“ in Installationen von Server Core und Server mit Desktopdarstellung (nur Windows Server 2016) verwenden.

## <a name="start-the-server-configuration-tool"></a>Starten Sie das Serverkonfigurationstool

1. Wechseln Sie zum Systemlaufwerk.

2. Geben Sie `Sconfig.cmd` ein, und drücken Sie dann die EINGABETASTE. Die Benutzeroberfläche des Serverkonfigurationstools wird geöffnet:

    ![Screenshot der Benutzeroberfläche von %%amp;quot;Sconfig.cmd%%amp;quot;](media/mainsconfigpage.png)

## <a name="domainworkgroup-settings"></a>Domänen-/Arbeitsgruppeneinstellungen

Die aktuellen Domänen-/Arbeitsgruppeneinstellungen werden auf dem Standardbildschirm des Serverkonfigurationstools angezeigt. Sie können die einer Domäne oder Arbeitsgruppe beitreten, indem Sie den Zugriff auf die **Domäne/Arbeitsgruppe** Seite "Einstellungen" im Hauptmenü und den Anweisungen, die Eingabe erforderlichen Informationen.

Wenn ein Domänenbenutzer nicht der lokalen Administratorgruppe hinzugefügt wurde, nicht Sie systemänderungen, z. B. den Namen des Computers ändern, mit der Domäne herstellen. Zum Hinzufügen eines Benutzers zur Gruppe der lokalen Administratoren sollten Sie den Computer neu starten lassen. Als Nächstes als lokaler Administrator am Computer anmelden, und führen Sie die Schritte in der [lokale administratoreinstellungen](#local-administrator-settings) weiter unten in diesem Artikel.

> [!NOTE]
> Sie müssen den Server zum Anwenden von Änderungen auf Domänen-oder Arbeitsgruppenmitgliedschaft neu starten. Sie können jedoch weitere Änderungen vornehmen und den Server nach der Durchführung aller Änderungen neu starten, um einen mehrfachen Neustart zu umgehen. Standardmäßig wird die Ausführung virtueller Computer vor dem Neustart des Hyper-V-Servers automatisch gespeichert.

## <a name="computer-name-settings"></a>Computernamenseinstellungen

Der aktuelle Computername wird auf dem Standardbildschirm des Serverkonfigurationstools angezeigt. Sie können den Namen des Computers ändern, indem Sie den Zugriff auf die **Computername** Seite "Einstellungen" im Hauptmenü und den Anweisungen.

> [!NOTE]
> Sie müssen den Server zum Anwenden von Änderungen auf Domänen-oder Arbeitsgruppenmitgliedschaft neu starten. Sie können jedoch weitere Änderungen vornehmen und den Server nach der Durchführung aller Änderungen neu starten, um einen mehrfachen Neustart zu umgehen. Standardmäßig wird die Ausführung virtueller Computer vor dem Neustart des Hyper-V-Servers automatisch gespeichert.

## <a name="local-administrator-settings"></a>Lokale Administratoreinstellungen

Verwenden Sie zum Hinzufügen weiterer Benutzer zur Gruppe der lokalen Administratoren die Option **Lokalen Administrator hinzufügen** im Hauptmenü. Geben Sie auf einem Computer, der zur Domäne gehört, den Benutzer im Format "Domäne\Benutzername" ein. Geben Sie auf einem Computer, der nicht zur Domäne gehört (Arbeitsgruppencomputer), nur den Benutzernamen ein. Die Änderungen werden sofort wirksam.

## <a name="network-settings"></a>Netzwerkeinstellungen

Sie können die IP-Adresse so konfigurieren, dass sie automatisch von einem DHCP-Server zugewiesen wird, oder Sie weisen manuell eine statische Adresse zu. Mit dieser Option können Sie auch DNS-Server-Einstellungen für den Server konfigurieren.

> [!NOTE]
> Diese und viele weitere Optionen sind jetzt über die Windows PowerShell-Cmdlets für Netzwerke verfügbar. Weitere Informationen finden Sie unter [Netzwerkadapter-Cmdlets](https://docs.microsoft.com/powershell/module/netadapter/?view=win10-ps) in der Windows Server-Bibliothek.

## <a name="windows-update-settings"></a>Windows Update-Server

Die aktuellen Windows Update-Einstellungen werden auf dem Standardbildschirm des Serverkonfigurationstools angezeigt. Über die Konfigurationsoption **Windows Update-Einstellungen** im Hauptmenü können Sie automatische oder manuelle Updates für den Server konfigurieren.

Ist **Automatische Updates** aktiviert, prüft das System täglich um 15:00 Uhr, ob Updates vorliegen, und installiert diese. Die Einstellungen werden sofort wirksam. Wenn **Manuelle Updates** aktiviert ist, prüft das System nicht automatisch, ob Updates vorhanden sind.

Sie können erforderlich Updates jederzeit über die Option **Updates herunterladen und Installieren** im Hauptmenü herunterladen und installieren.

Mit der Option **Nur herunterladen** werden verfügbare Updates gesucht und herunterladen, und Sie werden im Info-Center benachrichtigt, dass sie bereit für die Installation sind. Dies ist die Standardoption.

## <a name="remote-desktop-settings"></a>Remotedesktopeinstellungen

Der aktuelle Status der Remotedesktopeinstellungen wird auf dem Standardbildschirm des Serverkonfigurationstools angezeigt. Sie können die folgenden Remotedesktopeinstellungen konfigurieren, indem Sie im Hauptmenü auf die Option **Remotedesktop** zugreifen und den Anweisungen auf dem Bildschirm folgen.

- Remotedesktop für Clients aktivieren, auf denen Remotedesktop mit Authentifizierung auf Netzwerkebene ausgeführt wird

- Remotedesktop für Clients mit einer beliebigen Remotedesktopversion aktivieren

- Remotedesktop deaktivieren

## <a name="date-and-time-settings"></a>Datums- und Uhrzeiteinstellungen

Sie können Zugriff auf und ändern Sie Datum und Uhrzeiteinstellungen über die **Datums- /** Hauptmenü-Option.

## <a name="telemetry-settings"></a>Telemetrieeinstellungen

Sie können mit dieser Option konfigurieren, welche Daten an Microsoft gesendet werden.

## <a name="windows-activation-settings"></a>Einstellungen für die Aktivierung von Windows

Sie können mit dieser Option die Aktivierung von Windows konfigurieren.

## <a name="to-enable-remote-management"></a>So aktivieren Sie die Remoteverwaltung

Sie können verschiedene Remoteverwaltungsszenarien über die Option **Remoteverwaltung konfigurieren** im Hauptmenü aktivieren:

- MMC-Remoteverwaltung (Microsoft Management Console)

- Windows PowerShell

- Server-Manager  

## <a name="to-log-off-restart-or-shut-down-the-server"></a>So können Sie den Server abmelden, neu starten oder herunterfahren

Greifen Sie zum Abmelden, Neustarten oder Herunterfahren des Servers auf das entsprechende Menüelement im Hauptmenü zu. Diese Optionen stehen auch über die **Windows Security** Menü, die von jeder Anwendung jederzeit durch Drücken von STRG + ALT + ENTF zugegriffen werden kann.  

## <a name="to-exit-to-the-command-line"></a>So wechseln Sie zur Befehlszeile
  
Wählen Sie die Option **Zur Befehlszeile wechseln** aus, und drücken Sie die EINGABETASTE, um zur Befehlszeile zu wechseln. Um zum Serverkonfigurationstool zurückzukehren, geben Sie **Sconfig.cmd**, und drücken Sie dann die EINGABETASTE.