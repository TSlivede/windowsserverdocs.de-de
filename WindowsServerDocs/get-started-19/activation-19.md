---
title: Windows Server 2019-Aktivierung
description: So wird Windows Server 2019 aktiviert.
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: server-general
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 99f7daa4-30ce-4d13-be65-0a4d55cca754
author: coreyp-at-msft
ms.author: coreyp
manager: jasgroce
ms.localizationpriority: medium
ms.openlocfilehash: 4cc669fee4fbd31edc8813f16761ecb9f90532df
ms.sourcegitcommit: 3743cf691a984e1d140a04d50924a3a0a19c3e5c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2019
ms.locfileid: "66810916"
---
# <a name="windows-server-2019-activation"></a>Windows Server 2019-Aktivierung

>Gilt für: Windows Server 2019, Windows Server 2016

Die folgenden Informationen erläutern die anfänglichen Planungsüberlegungen, die du zur Aktivierung der Schlüsselverwaltungsdienste (Key Management Services, KMS) für Windows Server 2019 überprüfen musst. Informationen zur KMS-Aktivierung im Zusammenhang mit älteren als den hier aufgeführten Betriebssystemen findest du unter [Schritt 1: Überprüfen und Auswählen von Aktivierungsmethoden](https://technet.microsoft.com/library/jj134256(WS.11).aspx).

KMS verwendet ein Client-Server-Modell zum Aktivieren von Clients. KMS-Clients werden zur Aktivierung mit einem KMS-Server, dem KMS-Host, verbunden. Der KMS-Host muss sich in Ihrem lokalen Netzwerk befinden.

KMS-Hosts müssen keine dedizierten Server sein, und KMS kann gleichzeitig mit anderen Diensten gehostet werden. Du kannst einen KMS-Host auf einem beliebigen physischen oder virtuellen System ausführen, auf dem Windows 10, Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows 8.1 oder Windows Server 2012 ausgeführt wird.

Ein unter Windows 10 oder Windows 8.1 ausgeführter KMS-Host kann nur Computer aktivieren, auf denen Clientbetriebssysteme ausgeführt werden.
Die folgende Tabelle fasst die Anforderungen an KMS-Hosts und Clients für Netzwerke zusammen, die Windows Server 2016-, Windows Server 2019- und Windows 10-Clients enthalten.

> [!NOTE]
> - Auf dem KMS-Server sind möglicherweise Updates erforderlich, um die Aktivierung dieser neueren Clients zu unterstützen. Wenn Sie Aktivierungsfehler erhalten, überprüfen Sie, ob die entsprechenden, unter dieser Tabelle aufgelisteten Updates vorhanden sind.
> - Wenn du mit virtuellen Computern arbeitest, findest du Informationen und AVMA-Schlüssel unter [Automatische Aktivierung virtueller Computer](vm-activation-19.md).

|Product Key-Gruppe|KMS kann gehostet werden auf|Windows-Versionen, die von diesem KMS-Host aktiviert wurden|  
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------|  
|Volumenlizenz für Windows Server 2019|Windows Server 2012 R2<br /><br />Windows Server 2016<br /><br />Windows Server 2019<br /><br />|Windows Server (Semi-Annual Channel)<br /><br />Windows Server 2019 (alle Editionen)<br /><br />Windows Server 2016 (alle Editionen)<br /><br />Windows 10 Enterprise LTSC 2019 <br /><br />Windows 10 Enterprise LTSC N 2019<br /><br />Windows 10 LTSB (2015 und 2016)<br /><br />Windows 10 Professional<br /><br />Windows 10 Enterprise<br /><br />Windows 10 Pro for Workstations<br /><br />Windows 10 Education<br /><br />Windows Server 2012 R2 (alle Editionen)<br /><br />Windows 8.1 Professional<br /><br />Windows 8.1 Enterprise<br /><br />Windows Server 2012 (alle Editionen)<br /><br />Windows Server 2008 R2 (alle Editionen)<br /><br />Windows Server 2008 (alle Editionen)<br /><br />Windows 7 Professional<br /><br />Windows 7 Enterprise<br />| 
|Volumenlizenz für Windows Server 2016|Windows Server 2012<br /><br />Windows Server 2012 R2<br /><br />Windows Server 2016<br /><br />|Windows Server (Semi-Annual Channel) <br><br>Windows Server 2016 (alle Editionen)<br /><br />Windows 10 LTSB (2015 und 2016)<br /><br />Windows 10 Professional<br /><br />Windows 10 Enterprise<br /><br />Windows 10 Pro for Workstations<br><br>Windows 10 Education<br><br>Windows Server 2012 R2 (alle Editionen)<br /><br />Windows 8.1 Professional<br /><br />Windows 8.1 Enterprise<br /><br />Windows Server 2012 (alle Editionen)<br /><br />Windows Server 2008 R2 (alle Editionen)<br /><br />Windows Server 2008 (alle Editionen)<br /><br />Windows 7 Professional<br /><br />Windows 7 Enterprise<br /><br />| 
|Volumenlizenz für Windows 10|Windows 7<br /><br /> Windows 8.1<br /><br /> Windows 10|Windows 10 Professional<br /><br /> Windows 10 Professional N<br /><br /> Windows 10 Enterprise<br /><br /> Windows 10 Enterprise N<br /><br /> Windows 10 Education<br /><br /> Windows 10 Education N<br /><br /> Windows 10 Enterprise LTSB (2015)<br /><br /> Windows 10 Enterprise LTSB N (2015)<br /><br /> Windows 10 Pro for Workstations<br><br>Windows 8.1 Professional<br /><br /> Windows 8.1 Enterprise<br /><br /> Windows 7 Professional<br /><br /> Windows 7 Enterprise<br /><br />|  
|Volumenlizenz für „WindowsServer 2012 R2 für Windows 10“|Windows Server 2008 R2<br /><br /> Windows Server2012 Standard<br /><br /> Windows Server2012 Datacenter<br /><br /> Windows Server2012R2 Standard<br /><br />Windows Server2012R2 Datacenter|Windows 10 Professional<br /><br /> Windows 10 Enterprise<br /><br />Windows 10 Enterprise LTSB (2015)<br><br>Windows 10 Pro for Workstations<br><br>Windows 10 Education<br><br> Windows Server 2012 R2 (alle Editionen)<br /><br /> Windows 8.1 Professional<br /><br /> Windows 8.1 Enterprise<br /><br /> Windows Server 2012 (alle Editionen)<br /><br /> Windows Server 2008 R2 (alle Editionen)<br /><br /> Windows Server 2008 (alle Editionen)<br /><br />Windows 7 Professional<br /><br /> Windows 7 Enterprise|

> [!NOTE]  
> Abhängig vom Betriebssystem Ihres KMS-Servers und abhängig davon, welches Betriebssystem Sie aktivieren möchten, müssen Sie möglicherweise eines oder mehrere der folgenden Updates installieren:
> - Installationen von KMS unter Windows 7 oder Windows Server 2008 R2 müssen aktualisiert werden, um die Aktivierung von Clients zu unterstützen, auf denen Windows 10 ausgeführt wird. Weitere Informationen findest du unter  [Update, mit dem Windows 7- und Windows Server 2008 R2-KMS-Hosts Windows 10 aktivieren können](https://support.microsoft.com/help/3079821/update-that-enables-windows-7-and-windows-server-2008-r2-kms-hosts-to-activate-windows-10).  
> - Installationen von KMS unter Windows Server 2012 müssen aktualisiert werden, um die Aktivierung von Clients mit Windows 10, Windows Server 2016, Windows Server 2019 oder neueren Client- oder Serverbetriebssystemen zu unterstützen. Weitere Informationen findest du unter  [Updaterollup für Windows Server 2012 vom Juli 2016](https://support.microsoft.com/help/3172615/july-2016-update-rollup-for-windows-server-2012). 
> - Installationen von KMS unter Windows 8.1 oder Windows Server 2012 R2 müssen aktualisiert werden, um die Aktivierung von Clients mit Windows 10, Windows Server 2016, Windows Server 2019 oder neueren Client- oder Serverbetriebssystemen zu unterstützen. Weitere Informationen findest du unter  [Updaterollup für Windows 8.1 und Windows Server 2012 R2 vom Juli 2016](https://support.microsoft.com/help/3172614/july-2016-update-rollup-for-windows-8.1-and-windows-server-2012-r2).  
> - Windows Server 2008 R2 kann nicht aktualisiert werden, um die Aktivierung von Clients mit Windows Server 2016, Windows Server 2019 oder neueren Betriebssystemen zu unterstützen. 

Ein einzelner KMS-Host kann eine unbegrenzte Anzahl von KMS-Clients unterstützen. Bei mehr als 50 Clients empfehlen wir, mindestens zwei KMS-Hosts einzusetzen, für den Fall, dass einer der KMS-Hosts nicht verfügbar ist. Für die meisten Organisationen sind nicht mehr als zwei KMS-Hosts für die gesamte Infrastruktur erforderlich.

# <a name="addressing-kms-operational-requirements"></a>KMS-Betriebsanforderungen
KMS kann physische und virtuelle Computer aktivieren. Zur Qualifikation für die KMS-Aktivierung muss in einem Netzwerk jedoch eine bestimmte Mindestanzahl von Computern (als Aktivierungsschwellenwert bezeichnet) vorhanden sein. KMS-Clients werden nur aktiviert, wenn der Schwellenwert nicht überschritten wird. Um sicherzustellen, dass der Aktivierungsschwellenwert nicht überschritten wird, zählt ein KMS-Host die Computer im Netzwerk, die eine Aktivierung anfordern.

KMS-Hosts zählen die Anzahl der neuesten Verbindungen. Wenn ein Client oder Server den KMS-Host kontaktiert, zählt der Host die Computer-ID als weiteren Computer und gibt dann die aktuelle Anzahl als Antwort zurück. Der Client oder Server wird aktiviert, wenn die Anzahl hoch genug ist. Clients werden aktiviert, wenn die Anzahl höher als 25 ist. Server und Volumenlizenzversionen von Microsoft Office-Produkten werden aktiviert, wenn die Anzahl fünf oder mehr ist. Der KMS zählt nur eindeutige Verbindungen der letzten 30 Tage und speichert nur die letzten 50 Kontakte.

KMS-Aktivierungen sind 180 Tage lang gültig – dieser Zeitraum wird als Aktivierungsgültigkeitsintervall bezeichnet. Damit sie aktiviert bleiben, müssen KMS-Clients ihre Aktivierung erneuern, indem sie mindestens einmal alle 180 Tage eine Verbindung mit dem KMS-Host herstellen. KMS-Clientcomputer versuchen standardmäßig alle sieben Tage, ihre Aktivierung zu erneuern. Sobald die Aktivierung eines Clients erneuert worden ist, beginnt der Gültigkeitszeitraum der Aktivierung von vorne.

# <a name="addressing-kms-functional-requirements"></a>KMS-Funktionsanforderungen

Die KMS-Aktivierung erfordert eine TCP/IP-Verbindung. KMS-Hosts und -Clients sind standardmäßig für die Verwendung von Domain Name System (DNS) konfiguriert. KMS-Hosts verwenden standardmäßig dynamische DNS-Updates zum automatischen Veröffentlichen der erforderlichen Informationen, sodass KMS-Clients die Hosts erkennen und eine Verbindung mit ihnen herstellen können. Sie können diese Standardeinstellungen übernehmen oder KMS-Hosts und -Clients manuell konfigurieren, wenn Sie spezielle Anforderungen bezüglich der Netzwerk- und Sicherheitskonfigurationen haben.

Nach dem Aktivieren des ersten KMS-Hosts, kann der dazu verwendete KMS-Schlüssel zum Aktivieren von bis zu fünf weiteren KMS-Hosts in Ihrem Netzwerk verwendet werden. Nach dem Aktivieren eines KMS-Hosts können Administratoren diesen Host bis zu neun Mal mit demselben Schlüssel erneut aktivieren.

Wenn Ihre Organisation mehr als sechs KMS-Hosts benötigt, sollten Sie zusätzliche Aktivierungen für den KMS-Schlüssel Ihrer Organisation anfordern, z. B. wenn Sie über zehn physische Standorte und einen Volumenlizenzvertrag verfügen und möchten, dass für jeden Standort ein lokaler KMS-Host vorhanden ist.

> [!NOTE] 
> Wenden Sie sich an Ihr Activation Call Center, um diese Ausnahme anzufordern. Weitere Informationen finden Sie unter [Microsoft Volume Licensing](https://go.microsoft.com/fwlink/?LinkID=73076).

Computer, auf denen Volumenlizenzeditionen von Windows 10, Windows Server 2019, Windows Server 2016, Windows 8.1, Windows Server 2012 R2, Windows Server 2012, Windows Server 7 oder Windows Server 2008 R2 ausgeführt werden, sind standardmäßig KMS-Clients und benötigen keine zusätzliche Konfiguration.

Wenn für einen Computer die Umstellung von einem KMS-Host, einer MAK-Version oder einer Einzelhandelsversion von Windows auf einen KMS-Client durchgeführt werden soll, muss der entsprechende KMS-Clientsetupschlüssel installiert werden. Weitere Informationen findest du unter  [KMS-Clientsetupschlüssel](../get-started/KMSclientkeys.md). 
 

 
