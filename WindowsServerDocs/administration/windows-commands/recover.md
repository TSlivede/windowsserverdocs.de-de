---
title: recover
description: 'Windows-Befehle Thema ***- '
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: cf9be2e3-90c8-4773-a201-dc503b91948e
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: d6b9b5544394bfc69a2dc9f7be26ed8355a3f690
ms.sourcegitcommit: eaf071249b6eb6b1a758b38579a2d87710abfb54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66441962"
---
# <a name="recover"></a>recover



Lesbare Informationen aus einem fehlerhaften Datenträger wiederhergestellt werden.

Beispiele für das Verwenden dieses Befehls finden Sie unter [Beispiele](#BKMK_examples).

## <a name="syntax"></a>Syntax

```
recover [<Drive>:][<Path>]<FileName>
```

## <a name="parameters"></a>Parameter

|           Parameter           |                                          Beschreibung                                          |
|-------------------------------|-----------------------------------------------------------------------------------------------|
| [\<Drive>:][<Path>]<FileName> | Gibt den Speicherort und Namen der Datei, die Sie wiederherstellen möchten. *FileName* ist erforderlich. |
|              /?               |                             Zeigt die Hilfe an der Eingabeaufforderung an.                              |

## <a name="remarks"></a>Hinweise

-   Die **wiederherstellen** Befehl liest eine Datei, Sektor für Sektor, und stellt Sie Daten aus der guten Sektoren wieder her. Daten in fehlerhaften Sektoren sind verloren gegangen.
-   Fehlerhafte Bereiche von gemeldeten **Chkdsk** wurden als "fehlerhaft" markiert, wenn Ihr Datenträger für den Betrieb vorbereitet wurde. Sie stellen keine Gefahr, dar und **wiederherstellen** wirkt sich diese nicht.
-   Da alle Daten in fehlerhaften Sektoren geht verloren, wenn Sie eine Datei wiederherstellen, sollten Sie nur eine Datei zu einem Zeitpunkt wiederherstellen.
-   Sie können keine Platzhalterzeichen ( **&#42;** und **?** ) mit der **wiederherstellen** Befehl. Sie müssen angeben, eine Datei (und den Speicherort der Datei, sofern es nicht im aktuellen Verzeichnis vorhanden ist).

## <a name="BKMK_examples"></a>Beispiele für

Um die Datei Fabel.txt im \Fiction Verzeichnis auf Laufwerk D wiederherzustellen, geben Sie Folgendes ein:
```
recover d:\fiction\story.txt 
```

#### <a name="additional-references"></a>Weitere Verweise

[Erläuterung zur Befehlszeilensyntax](command-line-syntax-key.md)