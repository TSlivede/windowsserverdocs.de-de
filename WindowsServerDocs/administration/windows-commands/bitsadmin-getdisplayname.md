---
title: bitsadmin getdisplayname
description: Windows-Befehle Thema **Bitsadmin Getdisplayname** -Ruft den Anzeigenamen des angegebenen Auftrags.
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: e5c0e76c-4cc6-42d8-ac30-30bf3dc11b9b
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: c1ef16f54b7b825e4293a3870d8181985b83843b
ms.sourcegitcommit: 0d0b32c8986ba7db9536e0b8648d4ddf9b03e452
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2019
ms.locfileid: "59857601"
---
# <a name="bitsadmin-getdisplayname"></a>bitsadmin getdisplayname



Ruft den Anzeigenamen des angegebenen Auftrags ab.

## <a name="syntax"></a>Syntax

```
bitsadmin /GetDisplayName <Job>
```

## <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------|-----------|
|Auftrag|Anzeigenamen oder die GUID des Auftrags|

## <a name="BKMK_examples"></a>Beispiele für

Das folgende Beispiel ruft den Anzeigenamen für den Auftrag mit dem Namen *MyDownloadJob*.
```
C:\>bitsadmin /GetDisplayName myDownloadJob
```
Weitere Verweise

[Befehlszeilensyntax](command-line-syntax-key.md)