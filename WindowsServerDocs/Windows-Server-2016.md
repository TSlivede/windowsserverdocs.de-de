---
redirect_url: /windows-server/windows-server
ms.openlocfilehash: a852dfdda87aa37b403176483ea85f9bdb059e68
ms.sourcegitcommit: eaf071249b6eb6b1a758b38579a2d87710abfb54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66436000"
---
# <a name="windows-server-2016"></a>Windows Server 2016

Diese Bibliothek enthält Informationen für IT-Spezialisten für die Bewertung, Planung, Bereitstellung, Sicherung und das Verwalten von Windows Server 2016.

> [!Note] 
> Die nächste Version von Windows Server wird geändert. Finden Sie Detail zu den Neuigkeiten in der [Übersicht: Windows Server, Semi-Annual Channel](./get-started/semi-annual-channel-overview.md). 

[![Windows Server 2016-Übersichtsvideo](media/front-page-video.png)](https://www.youtube-nocookie.com/embed/V8oF0JpDzaM)

<table border="0" width="100%" align='center'>
  <tr style="text-align:center;">
    <td align='center' style="width:25%; border:0;">
      <a href="/windows-server/get-started/what-s-new-in-windows-server-2016"> &lt;img height=145 src=&quot;media/whats-new-highlight.png&quot; alt=&quot;What&#39;s new icon&quot; title=&quot;Whats new in Windows Server 16?&quot;/&gt;</a>
        <br/>Was&#39;neues?
    </td>
    <td align='center' style="width:25%; border:0;">
      <a href="/windows-server/get-started/server-basics"> &lt;IMG Height = 145 Src =&quot;Media/1-getstarted.png&quot; Alt =&quot;Get Symbol "gestartet"&quot; Title =&quot;erste Schritte mit Windows Server-16&quot; /&gt;</a>
      <br/>Erste Schritte </td>
    <td align='center' style="width:25%; border:0;">
      <a href="/windows-server/administration/index"> &lt;img height=145 src=&quot;media/8-management.png&quot; alt=&quot;administer icon&quot; title=&quot;Administer Windows Server&quot; /&gt;</a>
      <br/>Verwalten </td>
    <td align='center' style="width:25%; border:0;">
      <a href="/windows-server/failover-clustering/failover-clustering-overview"> &lt;img height=145 src=&quot;media/3-failover.png&quot; alt=&quot;Failover clustering icon&quot; title=&quot;Windows Server Failover clustering&quot; /&gt;</a>
      <br/>Failoverclustering </td>
  </tr>
  <tr style="text-align:center;">
    <td align='center' style="width:25%; border:0;"><br/>
      <a href="/windows-server/identity/identity-and-access"> &lt;img height=145 src=&quot;media/4-identity.png&quot; alt=&quot;Identity and access icon&quot; title=&quot;Windows Server Identity and Access&quot; /&gt;</a>
      <br>Identität und Zugriff </td>
    <td align='center' style="width:25%; border:0;"><br/>
      <a href="/windows-server/networking/networking"> &lt;img height=145 src=&quot;media/6-networking.png&quot; alt=&quot;Networking icon&quot; title=&quot;Windows Server Networking&quot; /&gt; </a>
      <br/>Netzwerk </td>
    <td align='center' style="width:25%; border:0;"><br/>
      <a href="/windows-server/remote/index"> &lt;IMG Height = 145 Src =&quot;media/remote.png&quot; Alt =&quot;Symbol "remote"&quot; Title =&quot;Remote und die serververwaltung&quot; /&gt; </a>
      <br/>Remotezugriff </td>
    <td align='center' style="width:25%; border:0;"><br/>
      <a href="/windows-server/security/security-and-assurance"> &lt;IMG Height = 145 Src =&quot;Media/5-security.png&quot; Alt =&quot;Sicherheitssymbol&quot; Title =&quot;Windows Server-Sicherheit und Zusicherungen&quot; /&gt; </a>
      <br/>Sicherheit und Zusicherungen </td>
  </tr>
  <tr style="text-align:center;">
    <td align='center' style="width:25%; border:0;">&nbsp;</td>
    <td align='center' style="width:25%; border:0;"><br>
      <a href="/windows-server/storage/storage"> &lt;IMG Height = 145 Src =&quot;Media/7-storage.png&quot; Alt =&quot;speichersymbol&quot; Title =&quot;Windows Server-Speicher&quot; /&gt; </a>
      <br/>Speicher </td>
   <td align='center' style="width:25%; border:0;"><br/>
      <a href="/windows-server/virtualization/virtualization"> &lt;img height=145 src=&quot;media/virtualization.png&quot; alt=&quot;virtualization icon&quot; title=&quot;Windows Server Virtualization&quot; /&gt;</a>
      <br/>Virtualisierung </td>
    <td align='center' style="width:25%; border:0;">&nbsp; </td>
  </tr>
</table>

<br/>

> [!Note] 
> Um in Windows Server 2016 verfügbare neue Features und Funktionen aus erster Hand auszuprobieren, können Sie unter [Windows Server Evaluierungsversionen](https://www.microsoft.com/evalcenter/evaluate-windows-server-2016) eine Evaluierungsversion herunterladen. 


## <a name="windows-server-2016-editions"></a>Windows Server 2016-Editionen

Windows Server 2016 ist unter Standard Edition, Datacenter Edition und Essentials Edition verfügbar. Windows Server 2016 Datacenter umfasst unbegrenzte Virtualisierungsrechte sowie neue Funktionen zum Erstellen eines softwaredefinierten Rechenzentrums. Windows Server 2016 Standard bietet Funktionen auf Unternehmensebene mit eingeschränkten Virtualisierungsrechten. Windows Server Essentials ist ein idealer erster Server mit Cloudverbindung. Dieser verfügt über seine eigene [umfassende Dokumentation](https://go.microsoft.com/fwlink/?LinkID=827171). Der Fokus des Inhalts hier liegt auf Standard Edition und Datacenter Edition. In der folgenden Tabelle sind die Hauptunterschiede zwischen Standard Edition und Datacenter Edition kurz zusammengefasst:

|Feature|Datacenter|Standard|  
|-------------------|----------|-----------------------|  
|Hauptfunktionen von Windows Server| ja| ja|
|Betriebssystemumgebungen (operating system environments, OSEs)/Hyper-V-Container|unbegrenzt|   2|
|Windows Server-Container|unbegrenzt|   unbegrenzt|
|Host-Überwachungsdienst| ja| ja|
|Nano Server-Installationsoption| ja| ja|
|Speicherfunktionen einschließlich Direkte Speicherplätze und Speicherreplikat| ja| nein|
|Abgeschirmte virtuelle Computer| ja| nein|
|Software-Defined Networking-Infrastruktur (Netzwerkcontroller, Softwarelastenausgleich und mehrinstanzenfähiges Gateway)| ja| nein|

Weitere Informationen finden Sie unter [Preise und Lizenzierung für Windows Server 2016](https://www.microsoft.com/en-us/cloud-platform/windows-server-pricing) und [Vergleichen von Funktionen in Windows Server-Versionen](https://www.microsoft.com/en-us/cloud-platform/windows-server-comparison).

## <a name="installation-options"></a>Installationsoptions

*Sowohl Standard Edition als auch Datacenter Edition bieten drei Installationsoptionen:

- **Server Core:** Diese Option reduziert den auf dem Datenträger erforderlichen Festplattenspeicher, die potenzielle Angriffsfläche und insbesondere die Wartungsanforderungen. Dies ist die **empfohlene** Option, sofern Sie keinen besonderen Bedarf an zusätzlichen Benutzeroberflächenelementen und grafischen Verwaltungstools haben.
- **Server mit Desktopdarstellung:** Mit dieser Option werden die Standardbenutzeroberfläche und alle Tools installiert, einschließlich Kundenerfahrungsfeatures, die in Windows Server 2012 R2 eine separate Installation erforderten. Serverrollen und Features werden mit dem Server-Manager oder anderen Methoden installiert.
- **Nano Server:** Dabei handelt es sich um ein remote verwaltetes Serverbetriebssystem, das für private Clouds und Rechenzentren optimiert ist. Das Betriebssystem ähnelt Windows Server im Modus Server Core, ist aber deutlich kleiner, bietet keine Möglichkeit zur lokalen Anmeldung, und unterstützt ausschließlich 64-Bit-Anwendungen, Tools und Agents. Es beansprucht weit weniger Speicherplatz, wird erheblich schneller eingerichtet und erfordert wesentlich weniger Updates und Neustarts als die anderen Optionen.

>[!Note]
> Im Gegensatz zu einigen früheren Versionen von Windows Server ist eine Konvertierung zwischen Server Core und Servern mit Desktopdarstellung nach der Installation nicht möglich. Wenn Sie beispielsweise Server Core installieren und später Server mit Desktopdarstellung verwenden möchten (und umgekehrt), sollten Sie eine Neuinstallation vornehmen.


Nun, da Sie wissen, welche Edition und welche Installationsoption für Sie geeignet ist, klicken Sie auf eine der nachstehenden Optionen, um mit Windows Server 2016 zu beginnen.
<br/>
<br/>

<table border="0" width="100%" align='center'>
  <tr style="text-align:center;">
    <td align='center' style="width:33%; border:0;">
      <a  href="/windows-server/get-started/getting-started-with-nano-server"> <img width="175" src="media/nano.png" alt="Icon representing Nano server" title="Nano Server - Geringstes Gewicht" /><br/>Nano Server - <br/>Geringste Gewicht</a>
    </td>
    <td align='center' style="width:33%; border:0;"><a href="/windows-server/get-started/getting-started-with-server-core"> <img width="175" src="media/servercore.png" alt="Icon representing the Server Core installation" title="Server Core - Empfohlen" /><br/>Server Core - <br/>Empfohlen</a></td>
   <td align='center' style="width:33%; border:0;"><a href="/windows-server/get-started/getting-started-with-server-with-desktop-experience"><img width="175" src="media/desktop.png" alt="Icon representing the full desktop experience installation option for Windows Server" title="Desktopdarstellung - Umfassende Benutzererfahrung" /><br/>Desktopdarstellung - <br/>Komplette-Schnittstelle</a></td>
  </tr>
</table>

## <a name="windows-server-software-defined-datacenter-sddc"></a>Windows Server-Software-Defined Datacenter (SDDC)

Virtualisierte Speicher-, Netzwerk-, Sicherheits- und Management-Technologien sind die Bausteine von Windows Server Software-Defined Datacenter (SDDC).
<br/>
<br/>

<table border="0" width="100%" align='center'>
  <tr style="text-align:center;">
    <td align='center' style="width:10%; border:0;"></td>
    <td align='center' style="width:50%; border:0;"><a href="/windows-server/sddc"><img width="400" src="media/sddc/WS16-heading.png" alt="Icon representing SDDC" title="Windows Server-Software-Defined Datacenter (SDDC)" /><br/>Windows Server Software-Defined Datacenter (SDDC)</a></td>
    <td align='center' style="width:10%; border:0;"></td>
  </tr>
</table>
