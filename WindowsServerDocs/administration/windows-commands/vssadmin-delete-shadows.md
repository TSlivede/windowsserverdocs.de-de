---
title: Vssadmin löschen Schatten
description: Eine Beschreibung des Befehls Shadows Vssadmin löschen.
ms.prod: windows-server-threshold
ms.topic: article
author: JasonGerend
ms.author: jgerend
ms.technology: storage
ms.date: 05/18/2018
ms.localizationpriority: medium
ms.openlocfilehash: 83074017e4ae412cf0aec654f6ab5901ad8039e2
ms.sourcegitcommit: 2977c707a299929c6ab0d1e0adab2e1c644b8306
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "63706630"
---
# <a name="vssadmin-delete-shadows"></a>Vssadmin löschen Schatten

>Gilt für: Windows 10, Windows 8.1, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008

Löscht ein angegebenes Volume Schattenkopien.

## <a name="syntax"></a>Syntax

```PowerShell
vssadmin delete shadows /for=<ForVolumeSpec> [/oldest | /all | /shadow=<ShadowID>] [/quiet]
```

## <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---|---|
|/for=\<ForVolumeSpec>|Gibt an, welches Volume die Schattenkopie gelöscht werden.|
|/oldest|Wird nur die älteste Schattenkopie gelöscht.|
|/ all|Löscht alle Schattenkopien für das angegebene Volume.|
|/shadow=\<ShadowID>|Löscht die Schattenkopie durch ShadowID angegeben. Verwenden Sie zum Abrufen der Schattenkopie-ID der **Vssadmin Liste Shadows** Befehl. Wenn Sie eine Schattenkopie-ID eingeben, verwenden Sie das folgende Format, in dem jede *X* steht für eine hexadezimale Zeichen:<br><br>XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX|
|/quiet|Gibt an, dass Nachrichten während der Ausführung durch der Befehl nicht angezeigt wird.|

## <a name="remarks"></a>Hinweise

Sie können nur mit dem Clients zugängliche Schattenkopien gelöscht.

## <a name="examples"></a>Beispiele

Um die älteste Schattenkopie des Volumes C zu löschen, geben Sie folgenden Befehl aus:

```PowerShell
vssadmin delete shadows /for=c: /oldest
```

## <a name="additional-references"></a>Weitere Verweise

* [Befehlszeilensyntax](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/cc771080(v%3dws.11))
* [Vssadmin](vssadmin.md)
* [Vssadmin Liste Schatten](vssadmin-list-shadows.md)