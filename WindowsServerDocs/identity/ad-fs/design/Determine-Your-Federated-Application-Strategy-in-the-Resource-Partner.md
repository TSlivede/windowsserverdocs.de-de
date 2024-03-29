---
ms.assetid: 9eab8c43-a0f2-4d19-a5a4-e1399f0d5f25
title: Bestimmen der Verbundanwendungsstrategie im Ressourcenpartner
description: ''
author: billmath
ms.author: billmath
manager: femila
ms.date: 05/31/2017
ms.topic: article
ms.prod: windows-server-threshold
ms.technology: identity-adfs
ms.openlocfilehash: 15a6c095648795badfae6f68f1ba2f9270219db8
ms.sourcegitcommit: 0b5fd4dc4148b92480db04e4dc22e139dcff8582
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2019
ms.locfileid: "66191464"
---
# <a name="determine-your-federated-application-strategy-in-the-resource-partner"></a>Bestimmen der Verbundanwendungsstrategie im Ressourcenpartner

Ein wichtiger Teil beim Entwerfen einer neuen Active Directory Federation Services \(AD FS\) -Infrastruktur in der Ressourcenpartnerorganisation ist Ermitteln des vollständigen Satzes von Anwendungen und Dienste, die verwendet werden, um die Teilnahme an der Verbund und welcher Kontopartner die Empfänger dieser Ressourcen werden. Bevor Sie eine Verbundanwendungs- und Servicestrategie entwerfen, berücksichtigen Sie die folgenden Fragen:  
  
-   Sie aktivieren und Bereitstellen einer ASP.NET-Anwendung oder einen Windows Communication Foundation \(WCF\) Dienst für den Verbund?  
  
-   Benötigen Benutzer in Ihrem Unternehmensnetzwerk Zugriff auf die Verbundanwendung oder den Dienst über die integrierte Windows-Authentifizierung?  
  
-   Soll die Verbundanwendung oder der Dienst von Benutzern in Ihrem Umkreisnetzwerk verwendet werden? Wird in diesem Fall die integrierte Windows-Authentifizierung erforderlich sein?  
  
-   Der Webserver, auf denen verbundanwendungen, die mit einem Windows Server-Betriebssystem und Internet Information Services gehostet sind \(IIS\)?  
  
-   Für wen stellt die Verbundanwendung oder der Dienst Ressourcen bereit?  
  
Beantwortung dieser Fragen hilft Ihnen eine solide AD FS-Entwurfs planen. Sie trägt auch dazu bei, eine Verbundanwendungs- und Dienststrategie zu erstellen, die kostengünstig ist und ressourceneffizient ist. Weitere Informationen zum Entwerfen der am besten geeigneten Verbundanwendungs- und Dienststrategie für Ihre Organisation finden Sie unter den folgenden Themen in diesem Handbuch:  
  
-   [Bereitstellen von Zugriff auf Ihre Ansprüche unterstützenden Anwendungen und Dienste für Active Directory-Benutzer](Provide-Your-Active-Directory-Users-Access-to-Your-Claims-Aware-Applications-and-Services.md)  
  
-   [Bereitstellen von Zugriff auf die Anwendungen und Dienste anderer Organisationen für Ihre Active Directory-Benutzer](Provide-Your-Active-Directory-Users-Access-to-the-Applications-and-Services-of-Other-Organizations.md)  
  
-   [Bereitstellen von Zugriff auf Ihre Ansprüche unterstützenden Anwendungen und Dienste für die Benutzer anderer Organisationen](Provide-Users-in-Another-Organization-Access-to-Your-Claims-Aware-Applications-and-Services.md)  
  
Weitere Informationen zum Erstellen einer Ansprüche\-bewusst ASP.NET-Anwendung oder WCF-Dienst finden Sie unter [Windows Identity Foundation SDK](https://go.microsoft.com/fwlink/?LinkId=122266).  
  
## <a name="see-also"></a>Siehe auch
[AD FS-Entwurfshandbuch in Windows Server 2012](AD-FS-Design-Guide-in-Windows-Server-2012.md)

