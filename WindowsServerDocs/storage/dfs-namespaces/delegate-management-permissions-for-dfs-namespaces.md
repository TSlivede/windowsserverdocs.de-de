---
title: Delegieren von Verwaltungsberechtigungen für DFS-Namespaces
description: In diesem Artikel wird beschrieben, wie Sie Verwaltungsberechtigungen für DFS-Namespaces delegieren und welche Gruppen standardmäßig Namespaceaufgaben ausführen können
ms.date: 6/5/2017
ms.prod: windows-server-threshold
ms.technology: storage
ms.topic: article
author: JasonGerend
manager: brianlic
ms.author: jgerend
ms.openlocfilehash: 7895432ca16dd13c6425d966f99104fc03db100d
ms.sourcegitcommit: 0d0b32c8986ba7db9536e0b8648d4ddf9b03e452
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2019
ms.locfileid: "59829491"
---
# <a name="delegate-management-permissions-for-dfs-namespaces"></a>Delegieren von Verwaltungsberechtigungen für DFS-Namespaces

> Gilt für: WindowsServer 2019, WindowsServer (Halbjährlicher Kanal), WindowsServer 2016, Windows Server 2012 R2, WindowsServer 2012, Windows Server 2008 R2, WindowsServer 2008

Die folgende Tabelle beschreibt die Gruppen, die grundlegende Namespaceaufgaben standardmäßig ausführen können, und die Methode für das Delegieren der Fähigkeit zum Ausführen dieser Aufgaben:

|Aufgabe | Gruppen, die diese Aufgabe standardmäßig ausführen können | Delegierungsmethoden |
|---|---|---|
|Erstellen eines domänenbasierten Namespaces|Domänen-Admins werden in der Domäne gruppiert, in der der Namespace konfiguriert ist|Klicken Sie mit der rechten Maustaste in der Konsolenstruktur unter dem Knoten **Namespaces** auf **Delegieren von Verwaltungsberechtigungen**. Oder verwenden Sie [Set-DfsnRoot GrantAdminAccounts](https://technet.microsoft.com/itpro/powershell/windows/dfsn/set-dfsnroot) und [Set-DfsnRoot RevokeAdminAccounts](https://technet.microsoft.com/itpro/powershell/windows/dfsn/set-dfsnroot). Windows PowerShell Cmdlets (wurden in Windows Server 2012 eingeführt). Außerdem müssen Sie der lokalen Gruppe Administratoren auf dem Namespaceserver den Benutzer hinzufügen.|
|Fügen Sie einen Namespaceserver zu einem domänenbasierten Namespace hinzu|Domänen-Admins werden in der Domäne gruppiert, in der der Namespace konfiguriert ist| Klicken Sie mit der rechten Maustaste in der Konsolenstruktur auf den domänenbasierten Namespaces und dann auf **Delegieren von Verwaltungsberechtigungen**. Oder verwenden Sie [Set-DfsnRoot GrantAdminAccounts](https://technet.microsoft.com/itpro/powershell/windows/dfsn/set-dfsnroot) und [Set-DfsnRoot RevokeAdminAccounts](https://technet.microsoft.com/itpro/powershell/windows/dfsn/set-dfsnroot). Windows PowerShell Cmdlets (wurden in Windows Server 2012 eingeführt). Außerdem müssen Sie der lokalen Gruppe Administratoren auf dem hinzuzufügenden Namespaceserver den Benutzer hinzufügen.|
|Verwalten eines domänenbasierten Namespaces|Lokale Administratorgruppe auf jedem Namespaceserver| Klicken Sie mit der rechten Maustaste in der Konsolenstruktur auf den domänenbasierten Namespaces und dann auf **Delegieren von Verwaltungsberechtigungen**. |
|Erstellen eines eigenständigen Namespace|Lokale Administratorgruppe auf dem Namespaceserver| Fügen Sie der lokalen Gruppe Administratoren auf dem Namespaceserver den Benutzer hinzu. |
|Verwalten eines eigenständigen Namespace*|Lokale Administratorgruppe auf dem Namespaceserver| Klicken Sie mit der rechten Maustaste in der Konsolenstruktur auf den eigenständigen Namespace und dann auf **Delegieren von Verwaltungsberechtigungen**. Oder verwenden Sie [Set-DfsnRoot GrantAdminAccounts](https://technet.microsoft.com/itpro/powershell/windows/dfsn/set-dfsnroot) und [Set-DfsnRoot RevokeAdminAccounts](https://technet.microsoft.com/itpro/powershell/windows/dfsn/set-dfsnroot). Windows PowerShell Cmdlets (wurden in Windows Server 2012 eingeführt).|
|Erstellen einer Replikationsgruppe oder Aktivieren der DFS-Replikation für einen Ordner|Domänen-Admins werden in der Domäne gruppiert, in der der Namespace konfiguriert ist| Klicken Sie mit der rechten Maustaste in der Konsolenstruktur unter dem Knoten Replikation auf **Delegieren von Verwaltungsberechtigungen**. |

<br />

\*Delegieren von Verwaltungsberechtigungen zum Verwalten eines eigenständigen Namespaces gewährt nicht dem Benutzer die Möglichkeit zum Anzeigen und Verwalten der Sicherheit mithilfe der **Delegierung** Registerkarte, sofern der Benutzer ein Mitglied der lokalen Gruppe "Administratoren" auf der Namespaceserver. Dieses Problem tritt auf, da der DFS-Verwaltungs-Snap-In die freigegebenen Zugriffssteuerungslisten (Discretionary Access Control Lists, DACLs) für den eigenständigen Namespace in der Registrierung nicht abrufen kann. Um das Snap-In zur Anzeige von Delegierungsinformationen zu aktivieren, müssen Sie die Schritte in der Microsoft befolgen<sup>®</sup> Knowledge Base-Artikel: [KB314837: Gewusst wie: Verwalten des Remotezugriffs in der Registrierung](https://go.microsoft.com/fwlink?linkid=46803)