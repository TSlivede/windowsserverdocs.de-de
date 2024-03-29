---
title: bootcfg delete
description: Windows-Befehle Thema **Bootcfg löschen** – Löscht einen Betriebssystem-Eintrag im Abschnitt "Betriebssysteme" der Datei "Boot.ini".
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 71382e29-9b39-41c8-9c23-cf0ff829440a
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 37f30a181402fe8a74148b42398641af3c4846b9
ms.sourcegitcommit: eaf071249b6eb6b1a758b38579a2d87710abfb54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66434763"
---
# <a name="bootcfg-delete"></a>bootcfg delete

>Gilt für: WindowsServer (Halbjährlicher Kanal), Windows Server 2016, Windows Server 2012 R2, WindowsServer 2012

Löscht einen Betriebssystem-Eintrag im Abschnitt [Betriebssysteme] der Datei "Boot.ini".

## <a name="syntax"></a>Syntax
```
bootcfg /delete [/s <computer> [/u <Domain>\<User> /p <Password>]] [/id <OSEntryLineNum>]
```
## <a name="parameters"></a>Parameter

|         Begriff         |                                                                                             Definition                                                                                              |
|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    /s <computer>     |                                         Gibt den Namen oder die IP-Adresse eines Remotecomputers (umgekehrte Schrägstriche nicht verwenden). Der Standardwert ist der lokale Computer.                                          |
| /u <Domain>\\<User>  | Führt den Befehl mit den Berechtigungen des Benutzers gemäß <User>oder <Domain> \\ <User>. Der Standardwert ist die Berechtigungen von der aktuell angemeldete Benutzer auf dem Computer, die der Befehl ausgegeben wird. |
|    /p <Password>     |                                                        Gibt das Kennwort des Benutzerkontos ein, die im angegebenen die **/u** Parameter.                                                        |
| / ID <OSEntryLineNum> |        Gibt die Zeilennummer der Betriebssystem-Eintrag im Abschnitt [Betriebssysteme] der Datei "Boot.ini" zu löschen. Die erste Zeile nach der [Betriebssysteme] Header im Abschnitt ist 1.        |
|          /?          |                                                                                Zeigt die Hilfe an der Eingabeaufforderung an.                                                                                 |

## <a name="BKMK_examples"></a>Beispiele für
Die folgenden Beispiele zeigen Informationen zur Verwendung der **Bootcfg/Delete**Befehl:
```
bootcfg /delete /id 1
bootcfg /delete /s srvmain /u maindom\hiropln /p p@ssW23 /id 3
```
#### <a name="additional-references"></a>Zusätzliche Referenzen
[Erläuterung zur Befehlszeilensyntax](command-line-syntax-key.md)
