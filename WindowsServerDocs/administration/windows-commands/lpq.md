---
title: lpq
description: 'Windows-Befehle Thema ***- '
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: bb6abcc4-310a-4fa4-927b-4084b62ca02e vhorne
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 18ff1ff3ecbc2df0a437ec8a465dec9a12123ede
ms.sourcegitcommit: eaf071249b6eb6b1a758b38579a2d87710abfb54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66437508"
---
# <a name="lpq"></a>lpq

>Gilt für: WindowsServer (Halbjährlicher Kanal), Windows Server 2016, Windows Server 2012 R2, WindowsServer 2012

Zeigt den Status einer Druckwarteschlange auf einem Computer unter (LPD Line Printer Daemon).  

## <a name="syntax"></a>Syntax  
```  
lpq -S <ServerName> -P <printerName> [-l]  
```  
## <a name="parameters"></a>Parameter  

|    Parameter     |                                                                        Beschreibung                                                                        |
|------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| -S <ServerName>  | Gibt (nach Name oder IP-Adresse) ein, den Computer oder die Druckerfreigabe Gerät, das die LPD-Druckwarteschlange mit dem Status gehostet wird, die Sie anzeigen möchten. Erforderlich. |
| -P <printerName> |                           Gibt an, (nach Namen) der Drucker für die Druckwarteschlange mit dem Status, den Sie anzeigen möchten. Erforderlich.                           |
|        -l        |                                      Gibt an, dass Informationen über den Status der Druckwarteschlange angezeigt werden soll.                                      |
|        /?        |                                                           Zeigt die Hilfe an der Eingabeaufforderung an.                                                            |

## <a name="remarks"></a>Hinweise  
Die **' -s'** und **-P** Parameter wird die Groß-/Kleinschreibung beachtet, und müssen in Großbuchstaben eingegeben werden.  
## <a name="BKMK_examples"></a>Beispiele für  
Dieses Beispiel zeigt, wie Sie den Status der Druckwarteschlange Laserprinter1 auf einem Host LPD am 10.0.0.45 anzeigen:  
```  
lpq -S 10.0.0.45 -P Laserprinter1  
```  
#### <a name="additional-references"></a>Zusätzliche Referenzen  
[Erläuterung zur Befehlszeilensyntax](command-line-syntax-key.md)  
[Druckbefehlsreferenz](print-command-reference.md)  
