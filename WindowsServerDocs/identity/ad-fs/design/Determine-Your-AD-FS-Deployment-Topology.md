---
ms.assetid: f67b0bc9-e5af-4891-9da0-d9be539af42d
title: Identifizieren der AD FS-Bereitstellungstopologie
description: ''
author: billmath
ms.author: billmath
manager: femila
ms.date: 05/31/2017
ms.topic: article
ms.prod: windows-server-threshold
ms.technology: identity-adfs
ms.openlocfilehash: 06cc4bd37905f6bb7afbc513ffce216104654aba
ms.sourcegitcommit: 0b5fd4dc4148b92480db04e4dc22e139dcff8582
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2019
ms.locfileid: "66191480"
---
# <a name="determine-your-ad-fs-deployment-topology"></a>Identifizieren der AD FS-Bereitstellungstopologie

Der erste Schritt bei der Planung einer Bereitstellung von Active Directory Federation Services \(AD FS\) besteht darin, die einmaligen Anmelden erfüllt die geeignete Bereitstellungstopologie festzulegen\-auf \(SSO\) muss von Ihrem die Organisation. Die Themen in diesem Abschnitt beschreiben die verschiedenen Bereitstellungstopologien, die Sie mit AD FS verwenden können. Zudem werden die mit jeder Bereistellungstopologie verbundenen Vorteile und Einschränkungen beschrieben, damit Sie die am besten geeignete Topologie für Ihre speziellen geschäftlichen Anforderungen auswählen können.  
  
Bevor Sie dieses Thema zur Bereitstellungstopologie lesen, sollten Sie zunächst die in der folgenden Tabelle aufgeführt Aufgaben in der angegebenen Reihenfolge durchführen.  
  
|Empfohlene Aufgabe|Beschreibung|Referenz|  
|--------------------|---------------|-------------|  
|Überprüfen Sie, wie AD FS-Daten gespeichert und an andere Verbundserver in einer Verbundserverfarm repliziert.|Informieren Sie sich über den Zweck und die Replikationsmethoden, die für die zugrundeliegenden Daten verwendet werden können, die in der AD FS-Konfigurationsdatenbank gespeichert sind. In diesem Thema werden die Konzepte der Konfigurationsdatenbank eingeführt und die zwei Datenbanktypen beschrieben: Interne Windows-Datenbank \(WID\) und Microsoft SQL Server.|[Rolle der AD FS-Konfigurationsdatenbank](../../ad-fs/technical-reference/The-Role-of-the-AD-FS-Configuration-Database.md)|  
|Wählen Sie den AD FS-Konfigurationsdatenbanktyp aus, den Sie in Ihrer Organisation bereitstellen werden.|Betrachten Sie die verschiedenen Vorteile und Einschränkungen bei der Verwendung von WID oder SQL Server als AD FS-Konfigurationsdatenbank und die verschiedenen Anwendungsszenarien, die sie unterstützen.|[Überlegungen zur AD FS-Bereitstellungstopologie](AD-FS-Deployment-Topology-Considerations.md)|  
  
> [!NOTE]  
> Implementieren Sie grundlegende Redundanz, Lastenausgleich und die Option zum Skalieren der Verbunddienst \(ggf.\), es wird empfohlen, dass Sie über mindestens zwei Verbundserver pro Verbundserverfarm für alle produktionsumgebungen bereitstellen unabhängig von der Art der Datenbank, die Sie verwenden möchten.  
  
Wenn Sie die Inhalte der vorstehenden Tabelle durchgesehen haben, fahren Sie mit den folgenden Themen in diesem Abschnitt fort:  
  
-   [Eigenständiger Verbundserver mit WID](Stand-Alone-Federation-Server-Using-WID.md)  
  
-   [Verbundserverfarm mit WID](Federation-Server-Farm-Using-WID-2012.md)  
  
-   [Verbundserverfarm mit WID und Proxys](Federation-Server-Farm-Using-WID-and-Proxies-2012.md)  
  
-   [Verbundserverfarm mit SQL Server](Federation-Server-Farm-Using-SQL-Server-2012.md)  
  
Nach Abschluss der Auswahl der AD FS-Bereitstellungstopologie wird empfohlen, die Sie überprüfen, dass das Thema [Planen der AD FS-Serverkapazität](Planning-for-AD-FS-Server-Capacity.md) um die empfohlene Anzahl von Servern zu ermitteln, die Sie zur Unterstützung dieser Topologie bereitstellen müssen.  
  
## <a name="see-also"></a>Siehe auch
[AD FS-Entwurfshandbuch in Windows Server 2012](AD-FS-Design-Guide-in-Windows-Server-2012.md)

