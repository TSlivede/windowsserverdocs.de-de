---
title: Neues in den Remotedesktopdiensten
description: Enthält eine Beschreibung neuer RDS-Features in Windows Server 2016.
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: remote-desktop-services
ms.author: chrimo
ms.date: 10/11/2016
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 04d52dff-e61b-4633-9908-be8600abc2ba
author: ChristianMontoya
manager: scottman
ms.openlocfilehash: ad13fdce251c1f84bac725e9f1ee266c6aae5e13
ms.sourcegitcommit: 3743cf691a984e1d140a04d50924a3a0a19c3e5c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2019
ms.locfileid: "63711794"
---
# <a name="whats-new-in-remote-desktop-services"></a>Neues in den Remotedesktopdiensten

Remotedesktopdienste (Remote Desktop Services, RDS) basieren auf Windows Server 2016 und sind eine Virtualisierungsplattform für ein breites Spektrum von Kundenszenarien. An der Verbesserung der RDS-Lösung sind neben dem Remotedesktopteam auch andere Technologiepartner bei Microsoft beteiligt. Die folgenden Szenarien und Technologien wurden in Windows Server 2016 neu hinzugefügt oder verbessert.

Sieh dir dazu auch das folgende Video von der Ignite 2016 an: [Harness RDS improvements in Windows Server 2016](https://channel9.msdn.com/Events/Ignite/2016/BRK3098) (Nutzen von RDS-Verbesserungen in Windows Server 2016). In diesem Video geht das Produktteam auf alle neuen und verbesserten Features der Remotedesktopdienste ein (einschließlich vGPU-Unterstützung). 

## <a name="app-compatibility---windows-server-2016-and-windows-10"></a>App-Kompatibilität: Windows Server 2016 und Windows 10
Windows Server 2016 hat das gleiche Fundament wie Windows 10, wodurch es so aussieht und sich so verhält, wie du es von einem Desktop erwartest. Darüber hinaus können damit größtenteils die gleichen Anwendungen ausgeführt werden. In Kombination mit den Grafikfunktionen (weiter unten) bietet Windows Server 2016 eine Umgebung, in der alle Benutzer produktiv arbeiten können. 

## <a name="azure-sql-database---the-new-database-for-your-highly-available-environment"></a>Azure SQL-Datenbank: die neue Datenbank für eine hoch verfügbare Umgebung
Der Remotedesktop-Verbindungsbroker kann alle Bereitstellungsinformationen (wie etwa Verbindungszustände und Benutzer-/Hostzuordnungen) in einer gemeinsam genutzten SQL-Datenbank speichern – beispielsweise in einer Azure SQL-Datenbank. Vergiss das Bereitstellungshandbuch für SQL Server-Always On-Verfügbarkeitsgruppen, schnapp dir die Verbindungszeichenfolge für die Azure SQL-Datenbank, und nutze deine hoch verfügbare Umgebung.

Weitere Informationen: [New Windows Server 2016 Capability: Use Azure SQL DB for your Remote Desktop Connection Broker high availability en...](https://blogs.technet.microsoft.com/enterprisemobility/2016/05/03/new-windows-server-2016-capability-use-azure-sql-db-for-your-remote-desktop-connection-broker-high-availability-environment/) (Neue Windows Server 2016-Funktion: Verwenden von Azure SQL-Datenbank für deine Hochverfügbarkeitsumgebung mit dem Remotedesktop-Verbindungsbroker)

## <a name="graphics---solving-graphics-needs-across-various-scenarios"></a>Grafik: Erfüllung der Grafikanforderungen verschiedenster Szenarien
Dank der diskreten Gerätezuweisung von Hyper-V kannst du nun GPUs auf einem Hostcomputer direkt einem virtuellen Computer zuordnen, damit sie von dessen Anwendungen mit GPU-Bedarf genutzt werden können. Die RemoteFX-vGPU unterstützt nun OpenGL 4.4, OpenCL 1.1, 4K-Auflösung und virtuelle Windows Server-Computer.

Weitere Informationen: [Diskrete Gerätezuweisung](https://blogs.technet.microsoft.com/virtualization/2015/11/)

## <a name="rd-connection-broker---improved-connection-handling-during-logon-storms"></a>RD-Verbindungsbroker: verbesserte Verbindungsverarbeitung bei hohem Anmeldeaufkommen
Dank der verbesserten Verbindungsverarbeitung kann der RD-Verbindungsbroker nun mehr als 10.000 gleichzeitige Anmeldeanforderungen verarbeiten und kommt somit auch mit Anmeldespitzen zurecht. Der verbesserte RD-Verbindungsbroker vereinfacht auch die Wartung der Bereitstellung, da Server schneller wieder der Umgebung hinzugefügt werden können.

Weitere Informationen: [Improved Remote Desktop Connection Broker Performance with Windows Server 2016 and Windows Server 2012 R2 Hotfix](https://blogs.technet.microsoft.com/enterprisemobility/2015/12/15/improved-remote-desktop-connection-broker-performance-with-windows-server-2016-and-windows-server-2012-r2-hotfix-kb3091411/) (Leistungsverbesserung für den Remotedesktop-Verbindungsbroker mit Hotfix für Windows Server 2016 and Windows Server 2012 R2)

## <a name="rdp-10---new-capabilities-built-into-the-protocol"></a>RDP 10: neue, in das Protokoll integrierte Funktionen
RDP 10 verwendet jetzt den H.264/AVC 444-Codec zur angemessenen Optimierung von Videos und Text. Ab diesem Release wird auch die Verwendung eines Stifts in Remotedesktopsitzungen unterstützt. Mit diesen Funktionen kommen deine Remotesitzungen noch näher an eine lokale Sitzung heran.  

Weitere Informationen: [Remote Desktop Protocol (RDP) 10 AVC/H.264 improvements in Windows 10 and Windows Server 2016 Technical Preview](https://blogs.technet.microsoft.com/enterprisemobility/2016/01/11/remote-desktop-protocol-rdp-10-avch-264-improvements-in-windows-10-and-windows-server-2016-technical-preview/) (RDP 10 (Remotedesktopprotokoll): AVC/H.264-Verbesserungen in Windows 10 und Windows Server 2016)

## <a name="personal-session-desktops---providing-individual-desktops-to-any-end-user"></a>Persönliche Sitzungsdesktops: individuelle Desktops für jeden Endbenutzer
Persönliche Sitzungsdesktops sind eine neue Möglichkeit zum Hosten eigener persönlicher Desktops in der Cloud. Administratorrechte und dedizierte Sitzungshosts tragen zur Vereinfachung von Hostingumgebungen bei und ermöglichen es den Benutzern, den Desktop wie ihren eigenen zu verwalten.

Weitere Informationen: [Verwenden von persönlichen Sitzungsdesktops mit Remotedesktopdiensten](rds-personal-session-desktops.md)
