---
ms.assetid: 25f5aff1-6abf-4dea-b531-f1d9943bc181
title: AD FS Anpassung in Windows Server 2016
description: ''
author: billmath
ms.author: billmath
manager: femila
ms.date: 05/31/2017
ms.topic: article
ms.prod: windows-server-threshold
ms.technology: identity-adfs
ms.openlocfilehash: 7f990c3412707e38a00110ac4d3cb3787fa18ee3
ms.sourcegitcommit: 216d97ad843d59f12bf0b563b4192b75f66c7742
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68476531"
---
# <a name="ad-fs-customization-in-windows-server-2016"></a>AD FS Anpassung in Windows Server 2016


Als Reaktion auf Feedback von Organisationen, die AD FS verwenden, haben wir zusätzliche Tools hinzugefügt, mit denen die Benutzeranmeldung für einzelne, durch AD FS geschützte Anwendungen angepasst werden kann.  
Neben dem Angeben von Webanwendungen pro Anwendung (z. b. Beschreibungstext und Verknüpfungen) können Sie jetzt auch ganze Webdesigns pro Anwendung angeben.  Dies schließt Logo, Illustration, Stylesheets oder eine gesamte Datei "OnLoad. js" ein.  
  
## <a name="global-settings"></a>Globale Einstellungen    
Allgemeine globale Einstellungen finden Sie unter [Anpassen der AD FS Anmelde Seiten](https://technet.microsoft.com/library/dn280950.aspx) , die mit AD FS in Windows Server 2012 R2 ausgeliefert wurden.  
  
## <a name="pre-requisites"></a>Voraussetzungen  
Die folgenden Voraussetzungen sind erforderlich, bevor Sie die in diesem Dokument beschriebenen Verfahren ausführen.  
  
-   AD FS in Windows Server 2016 TP4 oder höher  
  
## <a name="configure-ad-fs-relying-parties"></a>Konfigurieren AD FS vertrauenden Seiten  
Gemäß den unten aufgeführten PowerShell-Beispielen können die Webelemente und Designs der vertrauenden Seite für die Anmeldung konfiguriert werden:  
  
### <a name="customize-messages"></a>Anpassen von Nachrichten  
  
```  
PS C:\>Set-AdfsRelyingPartyWebContent  
    -TargetRelyingPartyName "<RP trust Name>"  
    -CompanyName "This text appears in place of the federation service display name"  
    -OrganizationalNameDescriptionText "This text appears right below the company name"  
    -SignInPageDescription "This text appears below the credential prompt"  
```  
  
### <a name="customize-company-name-logo-and-image"></a>Anpassen von Firmenname, Logo und Image  
  
```  
PS C:\>Set-AdfsRelyingPartyWebTheme  
    -TargetRelyingPartyName "<RP trust Name>"  
    -Logo @{path="C:\Images\applogo.png"}  
    -Illustration @{path="C:\Images\appillustration.jpg"}  
```  
  
### <a name="customize-entire-page"></a>Gesamte Seite anpassen  
  
```  
PS C:\>Set-AdfsRelyingPartyWebTheme  
    -TargetRelyingPartyName "<RP trust Name>"  
    -OnLoadScriptPath @{path="c:\scripts\adfstheme\onload.js"}  
```  
  
## <a name="custom-themes-and-advanced-custom-themes"></a>Benutzerdefinierte Designs und Erweiterte benutzerdefinierte Themen  
  
Informationen zu benutzerdefinierten Designs finden Sie unter [Anpassen der AD FS Anmelde Seiten](https://technet.microsoft.com/library/dn280950.aspx) und [Erweiterte Anpassung von AD FS Anmelde Seiten.](https://technet.microsoft.com/library/dn636121.aspx)  
  
## <a name="assigning-custom-web-themes-per-rp"></a>Zuweisen von benutzerdefinierten Webdesigns pro RP  
  
Verwenden Sie das folgende Verfahren, um ein benutzerdefiniertes Design pro RP zuzuweisen:  
  
1. Erstellen Sie ein neues Design als Kopie für das standardmäßige globale Design in AD FS  
<code>New-AdfsWebTheme -Name AppSpecificTheme -SourceName default</code>2. Design für Anpassung exportieren<code>Export-AdfsWebTheme -Name AppSpecificTheme -DirectoryPath c:\appspecifictheme</code>  
3.Anpassen von Designdateien (Bilder, CSS, OnLoad. js) in Ihrem bevorzugten Editor oder Ersetzen der Datei 4. "angepasste Dateien importieren" aus dem Dateisystem in "AD FS" (Ziel des neuen Designs)<code>Set-AdfsWebTheme -TargetName AppSpecificTheme -AdditionalFileResource @{Uri='/adfs/portal/script/onload.js';Path="c:\appspecifictheme\script\onload.js"}</code>  
5.Anwenden des neuen, angepassten Designs auf die spezifische RP (oder RP)<code>Set-AdfsRelyingPartyWebTheme -TargetRelyingPartyName urn:app1 -SourceWebThemeName AppSpecificTheme</code>  
  
## <a name="home-realm-discovery"></a>Startbereichsermittlung  
Informationen zur Unterschiede bei der Startbereichs Anpassung finden Sie unter [Anpassen der AD FS Anmelde Seiten](https://technet.microsoft.com/library/dn280950.aspx).  
  
## <a name="updated-password-page"></a>Aktualisierte Kenn Wort Seite  
Weitere Informationen zum Anpassen der Seite zum Aktualisieren des Kennworts finden Sie unter [Anpassen der AD FS Anmelde Seiten](https://technet.microsoft.com/library/dn280950.aspx).  
  
## <a name="customizing-and-alternate-ids"></a>Anpassen und Alternative IDs  
Benutzer können sich bei Active Directory-Verbunddienste (AD FS) (AD FS)-aktivierten Anwendungen mit einer beliebigen Form von Benutzer Bezeichnern anmelden, die von Active Directory Domain Services (AD DS) akzeptiert wird. Hierzu gehören Benutzer Prinzipal Namen (User Principal Namesjohndoe@contoso.com, UPNs) () oder Domänen qualifizierte SAM-Kontonamen (contoso\johndoe oder contoso. com\johndoe).  Weitere Informationen hierzu finden Sie unter [Konfigurieren einer alternativen Anmelde-ID.](Configuring-Alternate-Login-ID.md)  
  
Sie können außerdem die AD FS Anmeldeseite anpassen, um Endbenutzern einen Hinweis zur alternativen Anmelde-ID zu senden. Weitere Informationen finden Sie in der Beschreibung der angepassten Anmeldeseite. Weitere Informationen finden Sie unter [Anpassen der AD FS Anmelde Seiten.](https://technet.microsoft.com/library/dn280950.aspx)   
  
Hierzu können Sie auch die Zeichenfolge "Anmelden mit dem Organisations Konto" über dem Feld "Benutzername" anpassen.  Weitere Informationen hierzu finden Sie unter [Erweiterte Anpassung der AD FS Anmelde Seiten](https://technet.microsoft.com/library/dn636121.aspx).  

## <a name="additional-references"></a>Weitere Verweise 
[AD FS Anpassung der Benutzeranmeldung](AD-FS-user-sign-in-customization.md)  
