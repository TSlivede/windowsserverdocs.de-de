---
title: change
description: 'Windows-Befehle Thema ***- '
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 90012116-0fb3-4f34-a819-cf4d4b4f8981
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: f0a02302c4b99ead3701a966ba2d3fc65f6b078d
ms.sourcegitcommit: eaf071249b6eb6b1a758b38579a2d87710abfb54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66434405"
---
# <a name="change"></a>change

>Gilt für: WindowsServer (Halbjährlicher Kanal), Windows Server 2016, Windows Server 2012 R2, WindowsServer 2012

Ändert die Remotedesktop-Sitzungshost (rd Session Host)-Server-Einstellungen für Anmeldungen, COM-Anschluss Zuordnungen und den Installationsmodus.
> [!NOTE]
> In Windows Server 2008 R2 heißen die Terminaldienste nun Remotedesktopdienste. Neuerungen in der neuesten Version finden Sie unter [welche s New in Remote Desktop Services in Windows Server 2012](https://technet.microsoft.com/library/hh831527) in der technischen Bibliothek für Windows Server.
> ## <a name="syntax"></a>Syntax
> ```
> change logon
> change port
> change user
> ```
> ## <a name="parameters"></a>Parameter
> 
> |            Parameter            |                                                   Beschreibung                                                   |
> |---------------------------------|-----------------------------------------------------------------------------------------------------------------|
> | [change logon](change-logon.md) | Aktiviert oder deaktiviert die Anmeldungen von Clientsitzungen auf einen Remotedesktop-Sitzungshostserver oder zeigt den aktuellen Status der Anmeldung. |
> |  [change port](change-port.md)  |                Listet oder ändert die COM-Port-Zuordnungen mit MS-DOS-Anwendungen kompatibel ist.                |
> |  [change user](change-user.md)  |                            Ändert den Installationsmodus für den Remotedesktop-Sitzungshostserver.                             |
> 
> #### <a name="additional-references"></a>Zusätzliche Referenzen
> [Befehlszeilen-Syntaxschlüssel](command-line-syntax-key.md)
> [Remotedesktopdienste &#40;Terminaldienste&#41; -Befehlsreferenz](remote-desktop-services-terminal-services-command-reference.md)
