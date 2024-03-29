---
title: inaktiv
description: 'Windows-Befehle Thema ***- '
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f4fb4695-4e66-4166-b4ab-2c86a4605580
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 9c8ded732d984830c7892720f75938979f1abb67
ms.sourcegitcommit: eaf071249b6eb6b1a758b38579a2d87710abfb54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66438166"
---
# <a name="inactive"></a>inaktiv



Auf Basisdatenträgern des master Boot Record (MBR) markiert die Systempartition oder eine Partition als Startpartition mit Fokus als inaktiv.

## <a name="syntax"></a>Syntax

```
inactive
```

## <a name="remarks"></a>Hinweise

> [!CAUTION]
> Der Computer möglicherweise nicht ohne eine aktive Partition gestartet. Wenn Sie ein erfahrener Benutzer einem eingehenden Verständnis der Windows-Familie von Betriebssystemen sind nicht markieren Sie eine System- oder Startvolume Partition als inaktiv.</br>> Wenn Sie nicht, starten Sie den Computer nach der System- oder Startvolume Partition als inaktiv markieren können, legen Sie die Windows Setup-CD in das CD-ROM-Laufwerk, den Computer neu starten, und reparieren Sie dann auf die Partition mithilfe der **Fixmbr** und **Fixboot** Befehle in der Wiederherstellungskonsole.
> -   Nachdem Sie die Systempartition oder eine Partition als Startpartition als inaktiv markieren, startet Ihren Computer aus der nächsten Option im BIOS, z. B. das CD-ROM-Laufwerk oder ein Pre-Boot eXecution Environment (PXE) angegeben.
> -   Eine aktive Partition der System- oder Startvolume muss ausgewählt werden, damit dieser Vorgang erfolgreich ausgeführt werden. Verwenden der **wählen Partition** Befehl aus, wählen Sie die aktive Partition und verschiebt den Fokus auf sie.

## <a name="BKMK_examples"></a>Beispiele für

```
inactive
```

#### <a name="additional-references"></a>Weitere Verweise

[Erläuterung zur Befehlszeilensyntax](command-line-syntax-key.md)

