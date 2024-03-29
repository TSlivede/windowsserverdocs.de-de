---
title: Mithilfe des neuen CaptureImage-Befehls
description: 'Windows-Befehle Thema ***- '
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2dfd08f0-be59-4715-96e6-c498305873f4
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 00f15ae7ee1a7ab1ac1f71599d2cae9bb51d921e
ms.sourcegitcommit: eaf071249b6eb6b1a758b38579a2d87710abfb54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66440417"
---
# <a name="using-the-new-captureimage-command"></a>Mithilfe des neuen CaptureImage-Befehls



Erstellt ein neues Capture-Image aus einem vorhandenen Startabbild an. Aufzeichnungsimages sind, dass die Startabbilder, die der Windows-Bereitstellungsdienste starten Hilfsprogramm statt Setup erfassen. Wenn Sie einen Referenzcomputer zugreifen (die mit Sysprep vorbereitet wurde) mit einem aufzeichnungsimage starten, wird ein Assistent erstellt ein Installationsimage des Referenzcomputers und speichert es als eine Windows-Abbilddatei (WIM). Sie können auch das Bild hinzufügen, auf die Medien (z. B. einer CD, DVD oder USB-Laufwerk), und starten Sie dann auf einen Computer aus, dass die Medien. Nachdem Sie das Installationsabbild erstellt haben, können Sie das Image mit dem Server für die Bereitstellung der PXE-Start hinzufügen. Weitere Informationen finden Sie unter Erstellen von Images ([https://go.microsoft.com/fwlink/?LinkId=115311](https://go.microsoft.com/fwlink/?LinkId=115311)).

## <a name="syntax"></a>Syntax

```
WDSUTIL [Options] /New-CaptureImage [/Server:<Server name>]
     /Image:<Image name>
     /Architecture:{x86 | ia64 | x64}
     [/Filename:<File name>]
     /DestinationImage
        /FilePath:<File path and name>
        [/Name:<Name>]
        [/Description:<Description>]
        [/Overwrite:{Yes | No | Append}]
        [/UnattendFilePath:<File path>]
```

## <a name="parameters"></a>Parameter

|        Parameter         |                                                                                                                                                                                                                         Beschreibung                                                                                                                                                                                                                          |
|--------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [/ Server:\<Servername >] |                                                                                                                                       Gibt den Namen des Servers an. Hierbei kann es sich um den NetBIOS-Namen oder den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) handeln. Wenn kein Servername angegeben wird, wird der lokale Server verwendet werden.                                                                                                                                        |
|   / Image:\<Image-Name >   |                                                                                                                                                                                                         Gibt den Namen des Startabbilds Quelle.                                                                                                                                                                                                         |
|   / Architektur: {x 86    |                                                                                                                                                                                                                             ia64                                                                                                                                                                                                                             |
| [/ Filename: \<Dateiname >] |                                                                                                                                                                            Wenn das Bild kann nicht eindeutig anhand des Namens identifiziert werden, müssen Sie diese Option verwenden, um den Dateinamen angeben.                                                                                                                                                                            |
|    /DestinationImage     | Gibt die Einstellungen für das Zielabbild. Sie geben Sie die Einstellungen, die mithilfe der folgenden Optionen:</br>-   /FilePath: \<Dateipfad und > legt den vollständigen Pfad für das neue Capture-Image.</br>-[/ Name: \<Name >]-legt den Anzeigenamen des Images fest. Wenn kein Anzeigename angegeben wird, wird der Anzeigename des Quellbilds verwendet werden.</br>-[/ Description: \<Beschreibung >]-legt die Beschreibung des Images fest.</br>-[/ Overwrite: {Yes |

## <a name="BKMK_examples"></a>Beispiele für

Erstellen ein Aufzeichnungsabbild, und nennen Sie sie WinPECapture.wim, geben Sie Folgendes ein:
```
WDSUTIL /New-CaptureImage /Image:"WinPE boot image" /Architecture:x86 /DestinationImage /FilePath:"C:\Temp\WinPECapture.wim"
```
Um ein Aufzeichnungsabbild erstellen und die angegebenen Einstellungen anzuwenden, geben Sie Folgendes ein:
```
WDSUTIL /Verbose /Progress /New-CaptureImage /Server:MyWDSServer /Image:"WinPE boot image" /Architecture:x64 /Filename:boot.wim 
/DestinationImage /FilePath:"\\Server\Share\WinPECapture.wim" /Name:"New WinPE image" /Description:"WinPE image with capture utility" /Overwrite:No /UnattendFilePath:"\\Server\Share\WDSCapture.inf"
```

#### <a name="additional-references"></a>Weitere Verweise

[Erläuterung zur Befehlszeilensyntax](command-line-syntax-key.md)