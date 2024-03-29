---
ms.assetid: 0379abc3-25c7-46ab-9a6b-80a5152365b0
title: Benutzerdefinierte Webdesigns in AD FS
description: ''
author: billmath
ms.author: billmath
manager: femila
ms.date: 05/31/2017
ms.topic: article
ms.prod: windows-server-threshold
ms.technology: identity-adfs
ms.openlocfilehash: 2bce52a5704706ad72799d00879e2f4e48f9d703
ms.sourcegitcommit: 0b5fd4dc4148b92480db04e4dc22e139dcff8582
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2019
ms.locfileid: "66189247"
---
# <a name="custom-web-themes-in-ad-fs"></a>Benutzerdefinierte Webdesigns in AD FS 

Das Design, das versandt wird\-von\-der\-Feld standardmäßig aufgerufen wird. Sie können das Standarddesign exportieren und verwenden, um schnell anzufangen. Sie können das Aussehen und Verhalten anpassen, unter anderem das Layout, indem Sie die CSS-Datei ändern, das neue Design importieren und anwenden und dann das angepasste Aussehen und Verhalten verwenden. Wenn Sie die CSS-Datei verwenden, können Sie zudem einfacher mit Ihren Webdesignern zusammenarbeiten.  
  
Mit dem folgenden Cmdlet erstellen Sie ein benutzerdefiniertes Webdesign, das das Standardwebdesign dupliziert.  
  
  
`New-AdfsWebTheme –Name custom –SourceName default ` 

  
Sie können die CSS-Datei ändern und das neue Webdesign durch Verwendung der neuen CSS-Datei konfigurieren. Verwenden Sie zum Exportieren eines Webdesigns das folgende Cmdlet.  
  

    Export-AdfsWebTheme –Name default –DirectoryPath c:\theme  

  
Verwenden Sie zum Anwenden der CSS-Datei auf das neue Design das folgende Cmdlet.  
  

    Set-AdfsWebTheme –TargetName custom –StyleSheet @{path=”c:\NewTheme.css”}  
  
  
Mit dem folgenden Cmdlet erstellen Sie ein benutzerdefiniertes Webdesign über ein neues Stylesheet.  
  
  
`New-AdfsWebTheme –Name custom –StyleSheet @{path=”c:\NewTheme.css”} –RTLStyleSheetPath c:\NewRtlTheme.css ` 
  
  
  
Verwenden Sie zum Anwenden des benutzerdefinierten Webdesigns für AD FS das folgende Cmdlet aus.  
  

`Set-AdfsWebConfig -ActiveThemeName custom`  

  
Um JavaScript zu AD FS hinzuzufügen, verwenden Sie das folgende Cmdlet aus.  
  
 
    Set-AdfsWebTheme -TargetName custom -AdditionalFileResource @{Uri=’ /adfs/portal/script/onload.js’;path="D:\inetpub\adfsassets\script\onload.js"}  


## <a name="additional-references"></a>Weitere Verweise 
[AD FS-Anmeldung Benutzeranpassung](AD-FS-user-sign-in-customization.md)  
