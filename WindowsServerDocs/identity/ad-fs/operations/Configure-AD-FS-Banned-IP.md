---
title: Konfigurieren von AD FS gesperrt, IP-Adressen
description: ''
author: billmath
ms.author: billmath
manager: mtillman
ms.date: 06/28/2018
ms.topic: article
ms.prod: windows-server-threshold
ms.technology: identity-adfs
ms.openlocfilehash: 01ef992554a1e0961d8d795e9baa7730a1a1d682
ms.sourcegitcommit: 0b5fd4dc4148b92480db04e4dc22e139dcff8582
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2019
ms.locfileid: "66189891"
---
# <a name="ad-fs-and-banned-ip-addresses"></a>AD FS und gesperrten IP-Adressen


Im Juni 2018 AD FS unter Windows Server 2016 eingeführt **gesperrte** Juni 2018 mit der AD FS zu aktualisieren.  Dieses Update können Sie einen Satz von IP-Adressen Global in AD FS zu konfigurieren, damit Anforderungen von diesen IP-Adressen, oder dass die IP-Adressen haben, in der **X-forwarded-for** oder **X-ms-forwarded-Client-IP-** -Header von AD FS blockiert werden.

## <a name="adding-banned-ips"></a>Hinzufügen von IP-Adressen gesperrt
Um gesperrte IP-Adressen auf die globale Liste hinzuzufügen, verwenden die folgenden Powershell-Cmdlet:

``` powershell
PS C:\ >Set-AdfsProperties -AddBannedIps "1.2.3.4", "::3", "1.2.3.4/16"
```

Zulässige Formate

1.  IPv4
2.  IPv6
3.  CIDR-Format mit IPv4- oder IPv6

Es sind maximal 300 Einträge für gesperrten IP-Adressen ein. Sie können CIDR oder Bereich-Format verwenden, zum Verweigern von eines großen Blocks von Einträgen mit einem einzelnen Eintrag.

## <a name="removing-banned-ips"></a>Entfernen von IP-Adressen gesperrt
Um gesperrte IP-Adressen aus der globalen Liste zu entfernen, verwenden Sie die folgenden Powershell-Cmdlet:

``` powershell
PS C:\ >Set-AdfsProperties -RemoveBannedIps "1.2.3.4"
```

#### <a name="read-banned-ips"></a>Lesen gesperrt, IP-Adressen
Um den aktuellen Satz von gesperrten IP-Adressen zu lesen, verwenden Sie die folgenden Powershell-Cmdlet:

``` powershell
PS C:\ >Get-AdfsProperties 
```

Beispielausgabe:

```
BannedIpList                   : {1.2.3.4, ::3,1.2.3.4/16}
```



## <a name="additional-references"></a>Weitere Verweise  
[Bewährte Methoden zum Schützen von Active Directory Federation Services](../../ad-fs/deployment/best-practices-securing-ad-fs.md)

[Set-AdfsProperties](https://technet.microsoft.com/itpro/powershell/windows/adfs/set-adfsproperties)

[AD FS-Vorgänge](../../ad-fs/AD-FS-2016-Operations.md)
