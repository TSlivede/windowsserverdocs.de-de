---
title: ntcmdprompt
description: 'Windows-Befehle Thema ***- '
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0063bdbb-dc2b-41c4-99ee-b011603aaa86
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 583f56c294e66542a75efca09e97d57ae54a8cea
ms.sourcegitcommit: eaf071249b6eb6b1a758b38579a2d87710abfb54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66436426"
---
# <a name="ntcmdprompt"></a>ntcmdprompt

>Gilt für: WindowsServer (Halbjährlicher Kanal), Windows Server 2016, Windows Server 2012 R2, WindowsServer 2012

Führt den Befehlsinterpreter **Cmd.exe**, statt **Command.com**, nach dem Beenden und bleiben: Residente Speicherresidentes ausgeführt oder nach dem Start von der Eingabeaufforderung aus, in einer MS-DOS-Anwendung.
## <a name="syntax"></a>Syntax
```
ntcmdprompt
```
### <a name="parameters"></a>Parameter

| Parameter |             Beschreibung              |
|-----------|--------------------------------------|
|    /?     | Zeigt die Hilfe an der Eingabeaufforderung an. |

## <a name="remarks"></a>Hinweise
- Wenn **Command.com** wird ausgeführt, einige Features von **Cmd.exe**, z. B. die **Doskey** Befehlsverlauf die Anzeige, sind nicht verfügbar. Wenn Sie ausführen möchten, würde die **Cmd.exe** Befehlsinterpreter, nachdem Sie ein beenden, und bleiben: Residente Speicherresidentes gestartet oder der Eingabeaufforderung aus, in einer Anwendung, die basierend auf MS-DOS gestartet haben, können Sie die **Ntcmdprompt**  Befehl. Aber bedenken, dass die TSR u. u. nicht für die Verwendung verfügbar ist, bei der Ausführung **Cmd.exe**. Zählen Sie die **Ntcmdprompt** Befehl in Ihrer **config** Datei oder die entsprechende benutzerdefinierte Startdatei in der Anwendung Informationen-Programmdatei (Pif).
  ## <a name="examples"></a>Beispiele
  Sollen **Ntcmdprompt** in Ihre **config** Datei oder der Start-Konfigurationsdatei, die in der Pif, Typ angegeben: **Ntcmdprompt**
  ## <a name="additional-references"></a>Zusätzliche Referenzen
- [Erläuterung zur Befehlszeilensyntax](command-line-syntax-key.md)

