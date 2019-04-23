---
title: Verwenden den Befehl Remove-DriverGroupPackages
description: 'Windows-Befehle Thema ***- '
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 7b499635-6285-491c-8854-5665489f4364
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 8c00251dd07fca2491fedf6aed0c6989ee65a0dc
ms.sourcegitcommit: 0d0b32c8986ba7db9536e0b8648d4ddf9b03e452
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2019
ms.locfileid: "59866011"
---
# <a name="using-the-remove-drivergrouppackages-command"></a>Verwenden den Befehl Remove-DriverGroupPackages

>Gilt für: WindowsServer (Halbjährlicher Kanal), Windows Server 2016, Windows Server 2012 R2, WindowsServer 2012

wird die Treiberpakete in einer Treibergruppe auf einem Server entfernt.
## <a name="syntax"></a>Syntax
```
wdsutil /remove-DriverGroupPackages /DriverGroup:<Group Name> [/Server:<Server Name>] /Filtertype:<Filter type> /Operator:{Equal | NotEqual | GreaterOrEqual | LessOrEqual | Contains} /Value:<Value> [/Value:<Value> ...]
```
## <a name="parameters"></a>Parameter
|Parameter|Beschreibung|
|-------|--------|
|/DriverGroup:<Group Name>|Gibt den Namen der Gruppe "Treiber".|
|[/Server:<Server name>]|Gibt den Namen des Servers an. Dies kann den NetBIOS-Namen oder den vollqualifizierten Domänennamen sein. Wenn ein Servername nicht angegeben ist, wird der lokale Server verwendet.|
|/Filtertype:<Filter type>|Gibt das Attribut des zu suchenden Treiberpakets. Sie können mehrere Attribute in einem einzigen Befehl angeben. Sie müssen auch angeben, **/Operator** und **-Wert-** mit dieser Option.<br /><br /><Filter type> Dabei kann es sich um eine der folgenden sein:<br /><br />**PackageId**<br /><br />**PackageName**<br /><br />**PackageEnabled**<br /><br />**Packagedateadded**<br /><br />**PackageInfFilename**<br /><br />**PackageClass**<br /><br />**PackageProvider**<br /><br />**PackageArchitecture**<br /><br />**PackageLocale**<br /><br />**PackageSigned**<br /><br />**PackagedatePublished**<br /><br />**Packageversion**<br /><br />**Driverdescription**<br /><br />**DriverManufacturer**<br /><br />**DriverHardwareId**<br /><br />**DrivercompatibleId**<br /><br />**DriverExcludeId**<br /><br />**DriverGroupId**<br /><br />**DriverGroupName**|
|/Operator:{Equal &#124; NotEqual &#124; GreaterOrEqual &#124; LessOrEqual &#124; Contains}|Gibt die Beziehung zwischen dem Attribut und die Werte. Sie können nur angeben **Contains** mit Zeichenfolgenattributen. Sie können nur angeben **grösser oder gleich** und **kleiner oder gleich** mit Datum und die Version-Attribute.|
|Wert:<Value>|Gibt den Wert für die angegebene Suche <attribute>. Sie können angeben, mehrere Werte für ein einzelnes **/Filtertype**. Die folgende Liste beschreibt die Attribute, die Sie für jeden Filter geben können. Weitere Informationen zu diesen Attributen finden Sie unter [Treiber und Paket-Attribute](https://go.microsoft.com/fwlink/?LinkId=166895) (https://go.microsoft.com/fwlink/?LinkId=166895).<br /><br />-PackageId - Geben Sie eine gültige GUID. Zum Beispiel: {4d36e972-e325-11ce-bfc1-08002be10318}.<br />-Geben Sie Paketname jeder string-Wert.<br />-Geben Sie PackageEnabled - **Ja** oder **keine**.<br />-Packagedateadded - Geben Sie das Datum im folgenden Format: JJJJ/MM/TT<br />-Geben Sie PackageInfFilename jeder string-Wert.<br />-PackageClass - Geben Sie einen gültigen Klassennamen oder den Klassen-GUID. Zum Beispiel: **Laufwerk**, **Net**, oder {4d36e972-e325-11ce-bfc1-08002be10318}.<br />-Geben Sie PackageProvider jeder string-Wert.<br />-Geben Sie PackageArchitecture - **X86**, **X64**, oder **ia64**.<br />-PckageLocale - Geben Sie einen gültiger Sprachbezeichner. Zum Beispiel: **En-US** oder **es-ES**.<br />-Geben Sie PackageSigned - **Ja** oder **keine**.<br />-PackagedatePublished - Geben Sie das Datum im folgenden Format: JJJJ/MM/TT<br />-Packageversion - Geben Sie die Version im folgenden Format: a.b.x.y. Zum Beispiel: 6.1.0.0<br />-Geben Sie Driverdescription jeder string-Wert.<br />-Geben Sie DriverManufacturer jeder string-Wert.<br />-DriverHardwareId - Geben Sie einen beliebigen Zeichenfolgenwert.<br />-DrivercompatibleId - Geben Sie einen beliebigen Zeichenfolgenwert.<br />-DriverExcludeId - Geben Sie einen beliebigen Zeichenfolgenwert.<br />-DriverGroupId - Geben Sie eine gültige GUID. Zum Beispiel: {4d36e972-e325-11ce-bfc1-08002be10318}.<br />-Geben Sie DriverGroupName jeder string-Wert.|
## <a name="BKMK_examples"></a>Beispiele für
Geben Sie eine der folgenden Schritte aus, um Treiberpakete in einer Treibergruppe zu entfernen:
```
wdsutil /verbose /remove-DriverGroupPackages /DriverGroup:printerdrivers
/Filtertype:DriverManufacturer /Operator:NotEqual /Value:Name1 /Value:Name2
```
```
wdsutil /verbose /remove-DriverGroupPackages /DriverGroup:DisplayDrivers
/Filtertype:PackageArchitecture /Operator:Equal /Value:x86
/Filtertype:Packagedateadded /Operator:LessOrEqual /Value:2008/01/01
```
#### <a name="additional-references"></a>Zusätzliche Referenzen
[Befehlszeilen-Syntaxschlüssel](command-line-syntax-key.md)
[mit dem Remove-DriverGroupPackage-Befehl](using-the-remove-drivergrouppackage-command.md)