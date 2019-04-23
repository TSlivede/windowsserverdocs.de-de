---
ms.assetid: a0c6dbfe-d898-496d-9356-825f7fbd90ec
title: Fsutil 8dot3name
ms.prod: windows-server-threshold
manager: dmoss
ms.author: toklima
author: toklima
ms.technology: storage
audience: IT Pro
ms.topic: article
ms.date: 10/16/2017
ms.openlocfilehash: 4e8d67de42342f5a0828df9f57ca6d7e2870586e
ms.sourcegitcommit: 0d0b32c8986ba7db9536e0b8648d4ddf9b03e452
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2019
ms.locfileid: "59873191"
---
# <a name="fsutil-8dot3name"></a>Fsutil 8dot3name

>Gilt für: WindowsServer (Halbjährlicher Kanal), WindowsServer 2016, Windows 10, Windows Server 2012 R2, Windows 8.1, WindowsServer 2012, Windows 8, Windows Server 2008 R2, Windows 7

Abfragen oder ändert die Einstellungen für Kurznamen (8.3) Verhalten, darunter:

-   Die aktuelle Einstellung für das Verhalten der kurze Name Abfragen

-   Überprüfen Sie den angegebenen Verzeichnispfad für die Registrierungsschlüssel, die betroffen sein könnten, wenn Sie kurze Namen aus den angegebenen Verzeichnispfad entfernt wurden

-   Ändern Sie die Einstellung, die den kurzen Namen Verhalten steuert. Diese Einstellung kann angewendet werden, um ein bestimmtes Volume oder die Standardeinstellung für das Volume.

-   Entfernen Sie die Kurznamen für alle Dateien in einem Verzeichnis

Beispiele für das Verwenden dieses Befehls finden Sie unter [Beispiele](#BKMK_examples).

## <a name="syntax"></a>Syntax

```
fsutil 8dot3name [query] [<VolumePath>]
fsutil 8dot3name [scan] [/s] [/l [<log file>] ] [/v] <DirectoryPath>
fsutil 8dot3name [set] { <DefaultValue> | <VolumePath> {1|0}}
fsutil 8dot3name [strip] [/t] [/s] [/f] [/l [<log file.] ] [/v] <DirectoryPath>
```

## <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|-------------|---------------|
|Abfragen [<VolumePath>]|Fragt das Dateisystem für den Status der Erstellungsverhalten der 8.3-Kurznamen ab.<br /><br />Wenn eine *%VolumePath* ist nicht als Parameter angegeben, wird die Einstellung der 8dot3name Erstellung Verhalten für alle Volumes angezeigt.|
|Überprüfung <DirectoryPath>|Durchsucht die Dateien, die sich in der angegebenen *DirectoryPath* für Registrierungsschlüssel, die betroffen sein könnten, wenn der 8.3-Kurznamen aus dem Dateinamen entfernt wurden.|
|set { <DefaultValue> &#124; <VolumePath>}|Ändert das Verhalten des Dateisystems für die 8.3-Name-Erstellung in den folgenden Fällen:<br /><br /><ul><li>Wenn *DefaultValue* angegeben ist, den Registrierungsschlüssel **HKLM\System\CurrentControlSet\Control\FileSystem\NtfsDisable8dot3NameCreationNtfsDisable8dot3NameCreationNtfsDisable8dot3NameCreation**, festgelegt ist, um die *DefaultValue*.<br /><br />    Die *DefaultValue* können die folgenden Werte aufweisen:<br /><br /><ul><li>**0**: Ermöglicht die 8.3-Name-Erstellung für alle Volumes auf dem System.</li><li>**1**: Deaktiviert die 8.3-Name-Erstellung für alle Volumes auf dem System.</li><li>**2**: Legt Erstellung der 8.3-Namen pro Volume fest.</li><li>**3**: Deaktiviert die 8.3-Name-Erstellung für alle Volumes mit Ausnahme der Systemvolume.</li></ul></li><li>Wenn eine *%VolumePath* angegeben ist, werden die angegebenen Volumes auf dem Datenträger 8dot3name Flageigenschaften zum Aktivieren der 8.3-Name-Erstellung für ein bestimmtes Volume festgelegt (**0**) oder eine Gruppe zum Deaktivieren der Erstellung der 8.3-Namen auf der das angegebene Laufwerk (**1**).<br /><br />    Sie müssen das Standardverhalten des-Datei für die Erstellung der 8.3-Namen festlegen, auf den Wert **2** aktivieren oder Deaktivieren der 8.3-Name-Erstellung für ein bestimmtes Volume zu können.</li></ul>|
|Bereichsstreifen <DirectoryPath>|Entfernt die 8.3-Dateinamen für alle Dateien, die sich in der angegebenen *DirectoryPath*. Der 8.3-Dateiname wird nicht für alle Dateien entfernt, in denen die *DirectoryPath* kombiniert mit der Datei enthält mehr als 260 Zeichen.<br /><br />Dieser Befehl listet jedoch ändert sich nicht auf die Registrierungsschlüssel, die auf die Dateien zu verweisen, die 8.3-Dateinamen, die dauerhaft entfernt.<br /><br />Weitere Informationen zu den Auswirkungen der dauerhaft die 8.3-Dateinamen aus Dateien zu entfernen, finden Sie unter ["Hinweise"](Fsutil-8dot3name.md#BKMK_remarks).|
|<VolumePath>|Gibt den Namen des Laufwerks, gefolgt von einem Doppelpunkt oder die GUID im Format **Volume {***GUID***}**.|
|/f|Gibt an, dass alle Dateien, die sich in der angegebenen *DirectoryPath* wurden die 8.3-Dateinamen entfernt werden, auch wenn Registrierungsschlüssel, die auf Dateien, die mit dem 8.3-Dateinamen verweisen. In diesem Fall der Vorgang entfernt die 8.3-Dateinamen, aber keine Registrierungsschlüssel, die auf die Dateien zu, die die 8.3-Dateinamen verwenden verweisen, nicht geändert. **Warnung:** Es wird empfohlen, dass Sie das Verzeichnis bzw. die Volumes vor der Verwendung Sichern der **/f** Parameter einschließlich die Unfähigkeit, deinstallieren Sie da dies zu unerwarteten Anwendungsfehler, führen möglicherweise zu Programme.|
|/l [<log file>]|Gibt an, eine Protokolldatei, in denen Informationen geschrieben werden.<br /><br />Wenn die **/l** Parameter nicht angegeben ist, wird alle Informationen in die Standard-Protokolldatei geschrieben:<br /><br />**% temp%\8dot3_removal_log@ (***GMT-YYYY-MM-TT-HH-MM-SS***) .log**|
|/s|Gibt an, dass der Vorgang soll, auf die Unterverzeichnisse des angegebenen angewendet werden *DirectoryPath*.|
|/t|Gibt an, dass das Entfernen der 8.3-Dateinamen im Testmodus ausgeführt werden soll. Alle Vorgänge mit Ausnahme der 8.3-Dateinamen das eigentliche löschen, werden ausgeführt. Sie können Testmodus verwenden, um die Registrierung zu ermitteln, Schlüssel in Dateien zu verweisen, die 8.3-Dateinamen.|
|/v|Gibt an, dass alle Informationen, der in die Protokolldatei geschrieben wird, auch in der Befehlszeile angezeigt wird.|

## <a name="BKMK_remarks"></a>"Hinweise"

-   8.3-Dateinamen dauerhaft entfernt, und Ändern von Registrierungsschlüsseln, die auf die 8.3-Dateinamen zeigen nicht können zu unerwarteten Anwendungsfehler, z. B. nicht zum Deinstallieren einer Anwendung führen. Es wird empfohlen, dass Sie zuerst das Verzeichnis bzw. die Volumes vor dem Sichern Sie versuchen, die 8.3-Dateinamen zu entfernen.

## <a name="BKMK_examples"></a>Beispiele für
Geben Sie Folgendes ein, um das Verhalten deaktivieren 8.3 Name eines Datenträgervolumes abzufragen, die mit der GUID, {928842df-5a01-11de-a85c-806e6f6e6963}, angegeben wird:

```
fsutil 8dot3name query Volume{928842df-5a01-11de-a85c-806e6f6e6963}
```

Sie können auch das Verhalten der 8.3-Namen mithilfe von Abfragen die **Verhalten** Unterbefehl.

So entfernen Sie die 8.3-Dateinamen in der *D:\MyData* Verzeichnis und alle Unterverzeichnisse, die beim Schreiben der Informationen in die Protokolldatei, die als angegeben wird *mylogfile.log*, Typ:

```
fsutil 8dot3name strip /l mylogfile.log /s d:\MyData
```

### <a name="additional-references"></a>Weitere Verweise
[Befehlszeilensyntax](Command-Line-Syntax-Key.md)

[Fsutil](Fsutil.md)

[Fsutil 8dot3name](Fsutil-8dot3name.md)

[Fsutil behavior](Fsutil-behavior.md)

