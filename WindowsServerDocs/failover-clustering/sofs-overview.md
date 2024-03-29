---
title: Übersicht über Dateiserver mit horizontaler Skalierung für Anwendungsdaten
description: Übersicht über das Feature Scale-Out File Server für Windows Server 201 R2 und Windows Server 2012.
ms.prod: windows-server-threshold
ms.topic: article
author: JasonGerend
ms.author: jgerend
ms.technology: storage-failover-clustering
ms.date: 04/26/2018
ms.localizationpriority: medium
ms.openlocfilehash: e38c53c3458c3f66f24ea2ddaa66febf508c4568
ms.sourcegitcommit: eaf071249b6eb6b1a758b38579a2d87710abfb54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66442457"
---
# <a name="scale-out-file-server-for-application-data-overview"></a>Übersicht über Dateiserver mit horizontaler Skalierung für Anwendungsdaten

>Gilt für: Windows Server 2012 R2, Windows Server 2012

Der Dateiserver mit horizontaler Skalierung soll Dateifreigaben mit horizontaler Skalierung bereitstellen, die fortlaufend als dateibasierter Serveranwendungsspeicher verfügbar sind. Dateifreigaben mit horizontaler Skalierung ermöglichen das Freigeben eines Ordners von mehreren Knoten des gleichen Clusters. Der Schwerpunkt dieses Szenarios ist die Planung und Bereitstellung eines Dateiservers mit horizontaler Skalierung.

Sie können mithilfe einer der folgenden Methoden einen gruppierten Dateiserver bereitstellen und konfigurieren:

- **Dateiserver für horizontales Skalieren für Anwendungsdaten** dieser gruppierte Dateiserver unter Windows Server 2012 eingeführt wurde, und ermöglicht das Speichern von serveranwendungsdaten, wie z. B. Hyper-V-VM-Dateien auf Dateifreigaben. dabei erhalten ein ähnliches Level an Zuverlässigkeit, Verfügbarkeit, Verwaltbarkeit und hoher Leistung, die Sie von einem Storage Area Network erwarten würden. Alle Dateifreigaben sind auf allen Knoten gleichzeitig online. Die dieser Art von gruppiertem Dateiserver zugeordneten Dateifreigaben werden als Dateifreigaben mit horizontaler Skalierung bezeichnet. Dies wird mitunter als Aktiv/Aktiv bezeichnet. Dies ist der empfohlene Dateiservertyp beim Bereitstellen von entweder Hyper-V über Server Message Block (SMB) oder Microsoft SQL Server über SMB.
- **Dateiserver zur allgemeinen Verwendung** Dies ist die Weiterführung des gruppierten Dateiservers, der seit der Einführung des Failoverclusterings in Windows Server unterstützt wird. Diese Art von gruppiertem Dateiserver (und damit alle dem gruppierten Dateiserver zugeordneten Dateifreigaben) ist jeweils auf einem Knoten online. Dies wird mitunter als Aktiv/Passiv oder zweifach aktiv bezeichnet. Die dieser Art von gruppiertem Dateiserver zugeordneten Dateifreigaben werden als gruppierte Dateifreigaben bezeichnet. Dies ist der empfohlenen Dateiservertyp bei der Bereitstellung von Information-Worker-Szenarien.

## <a name="scenario-description"></a>Beschreibung des Szenarios

Mithilfe von Dateifreigaben mit horizontaler Skalierung können Sie denselben Ordner auf mehreren Knoten eines Clusters freigeben. Z. B. Wenn Sie einen Dateiservercluster mit vier Knoten, der Server Message Block (SMB)-Skalierung verwendet wird verfügen, kann ein Computer unter Windows Server 2012 R2 oder Windows Server 2012-Dateifreigaben aus jeder der vier Knoten zugreifen. Dies wird mit neuen Windows Server-Features für das Failoverclustering und Funktionen des Windows-Dateiserverprotokolls SMB 3.0 erreicht. Dateiserveradministratoren können Dateifreigaben mit horizontaler Skalierung und fortlaufend verfügbare Dateidienste für Serveranwendungen bereitstellen und auf höheren Bedarf reagieren, indem sie schnell weitere Server online schalten. All dies ist in einer Produktionsumgebung möglich und erfolgt für die Serveranwendung vollständig transparent.

Zu den wichtigsten Vorteilen des Dateiservers mit horizontaler Skalierung gehören folgende:

- **Aktiv / aktiv-Dateifreigaben**. Alle Knoten des Clusters können akzeptieren und Verarbeiten von SMB-Clientanforderungen. Da auf den Inhalt der Dateifreigaben über alle Clusterknoten gleichzeitig zugegriffen werden kann, ermöglichen Cluster und Clients mit SMB 3.0 gemeinsam transparentes Failover auf alternative Clusterknoten bei geplanten Wartungsarbeiten und bei nicht geplanten Fehlern mit Dienstunterbrechung.
- **Erhöhte Bandbreite**. Die maximale freigabebandbreite ist der Gesamtbandbreite aller Dateiserver-Clusterknoten. Im Gegensatz zu vorherigen Versionen von Windows Server wird die Gesamtbandbreite nicht mehr durch die Bandbreite eines einzelnen Clusterknotens begrenzt, sondern durch die Möglichkeiten des unterstützenden Speichersystems. Sie können die Gesamtbandbreite erhöhen, indem Sie Knoten hinzufügen.
- **CHKDSK ohne Ausfallzeiten**. CHKDSK wurde in Windows Server 2012 erheblich verbessert, um die Zeit erheblich zu verkürzen, die ein Dateisystem bei Reparaturen offline ist. Mit den freigegebenen Clustervolumes (Clustered Shared Volumes, CSVs) wird dies noch weiter verbessert, da die Offlinephase ganz entfällt. In einem CSV-Dateisystem (CSVFS) kann CHKDSK verwendet werden, ohne dass sich Auswirkungen auf Anwendungen mit geöffneten Handles im Dateisystem ergeben.
- **Gruppierten Cache für freigegebene Clustervolumes**. Freigegebene Clustervolumes in Windows Server 2012 führt die Unterstützung für einen Lesecache, der deutlich Leistung in bestimmten Szenarien, z. B. in Virtual Desktop Infrastructure (VDI) verbessern kann.
- **Einfachere Verwaltung**. Mit Scale-Out File Server erstellen Sie die Scale Out File Server, und fügen Sie dann die benötigten freigegebenen Clustervolumes und Dateifreigaben hinzu. Es ist nicht mehr notwendig, mehrere Clusterdateiserver jeweils mit separaten Clusterdatenträgern zu erstellen und dann Platzierungsrichtlinien zu entwickeln, um Aktivität auf den einzelnen Clusterknoten sicherzustellen.
- **Automatisches Neuverteilen von Clients für Dateiserver für horizontales Skalieren**. In Windows Server 2012 R2 verbessert automatische neuverteilung die Skalierbarkeit und verwaltbarkeit für Dateiserver mit horizontaler. SMB-Clientverbindungen werden nach Dateifreigabe (und nicht nach Server) nachverfolgt. Clients werden dann an den Clusterknoten mit dem besten Zugriff auf das von der Dateifreigabe verwendete Volume umgeleitet. Dadurch wird die Effizienz gesteigert, da der Umleitungsdatenverkehr zwischen Dateiserverknoten verringert wird. Clients werden nach der Anfangsverbindung und bei einer Neukonfiguration des Clusterspeichers umgeleitet.

## <a name="in-this-scenario"></a>Inhalt dieses Szenarios

Die folgenden Themen bieten hilfreiche Informationen, um einen Dateiserver mit horizontaler Skalierung bereitzustellen:

- [Planen Sie für Dateiserver mit horizontaler Skalierung-Server](<https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/jj134258(v%3dws.11)>)

  - [Schritt 1: Planen des Speichers auf dem Dateiserver für horizontales Skalieren](<https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/jj134181%28v%3dws.11%29>)
  - [Schritt 2: Plan for Networking in Scale-Out Dateiserver](<https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/jj134253%28v%3dws.11%29>)

- [Bereitstellen eines Dateiservers für horizontales Skalieren](<https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831359%28v%3dws.11%29>)

  - [Schritt 1: Installieren der erforderlichen Komponenten für Dateiserver mit horizontaler Skalierung-Server](<https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831478%28v%3dws.11%29>)
  - [Schritt 2: Konfigurieren eines Dateiservers für horizontales Skalieren](<https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831718%28v%3dws.11%29>)
  - [Schritt 3: Konfigurieren von Hyper-V für die Scale Out File Server verwenden](<https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831463%28v%3dws.11%29>)
  - [Schritt 4: Konfigurieren von Microsoft SQL Server für den Scale Out File Server verwenden](<https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831815%28v%3dws.11%29>)

## <a name="when-to-use-scale-out-file-server"></a>Anwendungsbereiche eines Dateiservers mit horizontaler Skalierung

Sie sollten einen Dateiserver mit horizontaler Skalierung nicht verwenden, wenn die Arbeitsauslastung eine hohe Anzahl von Metadatenvorgängen generiert, beispielsweise Öffnen von Dateien, Schließen von Dateien, Erstellen neuer Dateien oder Umbenennen vorhandener Dateien. Ein typischer Information-Worker generiert zahlreiche Metadatenvorgänge. Sie sollten einen Dateiserver mit horizontaler Skalierung verwenden, wenn die damit verbundene Skalierbarkeit und Einfachheit für Sie von Interesse ist und Sie nur Technologien benötigen, die von einem Dateiserver mit horizontaler Skalierung unterstützt werden.

In der folgenden Tabelle sind die neuen Funktionen in SMB 3.0, die gängigen Windows-Dateisysteme, Datenverwaltungstechnologien für Dateiserver und übliche Arbeitsauslastungen aufgeführt. Sie können sehen, ob die Technologie mit horizontaler Skalierung unterstützt wird oder ein herkömmlicher gruppierter Dateiserver (auch bekannt als ein Dateiserver zur allgemeinen Verwendung) erforderlich ist.

<table>
<thead>
<tr class="header">
<th>Technologiebereich</th>
<th>Feature</th>
<th>Dateiservercluster zur allgemeinen Verwendung</th>
<th>Dateiserver mit horizontaler Skalierung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>SMB</td>
<td>Fortlaufende Verfügbarkeit von SMB</td>
<td>Ja</td>
<td>Ja</td>
</tr>
<tr class="even">
<td>SMB</td>
<td>SMB Multichannel</td>
<td>Ja</td>
<td>Ja</td>
</tr>
<tr class="odd">
<td>SMB</td>
<td>SMB Direct</td>
<td>Ja</td>
<td>Ja</td>
</tr>
<tr class="even">
<td>SMB</td>
<td>SMB-Verschlüsselung</td>
<td>Ja</td>
<td>Ja</td>
</tr>
<tr class="odd">
<td>SMB</td>
<td>SMB – Transparentes Failover</td>
<td>Ja (wenn kontinuierliche Verfügbarkeit aktiviert ist)</td>
<td>Ja</td>
</tr>
<tr class="even">
<td>Dateisystem</td>
<td>NTFS</td>
<td>Ja</td>
<td>Nicht verfügbar</td>
</tr>
<tr class="odd">
<td>Dateisystem</td>
<td>Robustes Dateisystem (<a href="https://docs.microsoft.com/windows-server/storage/refs/refs-overview">ReFS</a>)</td>
<td>Mit Storage empfohlen "direkte Speicherplätze"</td>
<td>Mit Storage empfohlen "direkte Speicherplätze"</td>
</tr>
<tr class="even">
<td>Dateisystem</td>
<td>Dateisystem des freigegebenen Clustervolumes (CSV)</td>
<td>Nicht verfügbar</td>
<td>Ja</td>
</tr>
<tr class="odd">
<td>Dateiverwaltung</td>
<td>BranchCache</td>
<td>Ja</td>
<td>Nein</td>
</tr>
<tr class="even">
<td>Dateiverwaltung</td>
<td>Datendeduplizierung (WindowsServer 2012)</td>
<td>Ja</td>
<td>Nein</td>
</tr>
<tr class="odd">
<td>Dateiverwaltung</td>
<td>Datendeduplizierung (Windows Server 2012 R2)</td>
<td>Ja</td>
<td>Ja (nur VDI)</td>
</tr>
<tr class="even">
<td>Dateiverwaltung</td>
<td>DFS-Namespace (DFSN) – Stammserverstamm</td>
<td>Ja</td>
<td>Nein</td>
</tr>
<tr class="odd">
<td>Dateiverwaltung</td>
<td>DFS-Namespace (DFSN) – Zielserver für Ordner</td>
<td>Ja</td>
<td>Ja</td>
</tr>
<tr class="even">
<td>Dateiverwaltung</td>
<td>DFS-Replikation (DFSR)</td>
<td>Ja</td>
<td>Nein</td>
</tr>
<tr class="odd">
<td>Dateiverwaltung</td>
<td>Ressourcen-Manager für Dateiserver (Bildschirme und Kontingente)</td>
<td>Ja</td>
<td>Nein</td>
</tr>
<tr class="even">
<td>Dateiverwaltung</td>
<td>Dateiklassifizierungsinfrastruktur</td>
<td>Ja</td>
<td>Nein</td>
</tr>
<tr class="odd">
<td>Dateiverwaltung</td>
<td>Dynamische Zugriffssteuerung (anspruchsbasierter Zugriff)</td>
<td>Ja</td>
<td>Nein</td>
</tr>
<tr class="even">
<td>Dateiverwaltung</td>
<td>Ordnerumleitung</td>
<td>Ja</td>
<td>nicht empfohlen.<em></td>
</tr>
<tr class="odd">
<td>Dateiverwaltung</td>
<td>Offlinedateien (clientseitiges Zwischenspeichern)</td>
<td>Ja</td>
<td>Nicht empfohlen</em></td>
</tr>
<tr class="even">
<td>Dateiverwaltung</td>
<td>Roamingbenutzerprofile</td>
<td>Ja</td>
<td>nicht empfohlen.<em></td>
</tr>
<tr class="odd">
<td>Dateiverwaltung</td>
<td>Basisverzeichnisse</td>
<td>Ja</td>
<td>Nicht empfohlen</em></td>
</tr>
<tr class="even">
<td>Dateiverwaltung</td>
<td>Arbeitsordner</td>
<td>Ja</td>
<td>Nein</td>
</tr>
<tr class="odd">
<td>NFS</td>
<td>NFS-Server</td>
<td>Ja</td>
<td>Nein</td>
</tr>
<tr class="even">
<td>Anwendungen</td>
<td>Hyper-V</td>
<td>Nicht empfohlen</td>
<td>Ja</td>
</tr>
<tr class="odd">
<td>Anwendungen</td>
<td>Microsoft SQL Server</td>
<td>Nicht empfohlen</td>
<td>Ja</td>
</tr>
</tbody>
</table>

\* Ordnerumleitung, Offlinedateien, Roamingbenutzerprofile oder Startseite Verzeichnisse generieren Sie eine große Anzahl von Schreibvorgängen, die sofort (ohne Pufferung) auf den Datenträger geschrieben werden muss, wenn fortlaufend verfügbare Dateifreigaben verwenden, Dies verringert die Leistung im Vergleich zu Allgemeine Dateifreigaben. Fortlaufend verfügbare Dateifreigaben sind zudem nicht mit dem Ressourcen-Manager für Dateiserver und PCs unter Windows XP kompatibel. Darüber hinaus wechseln Offlinedateien ggf. 3-6 Minuten nicht in den Offlinemodus, nachdem ein Benutzer den Zugriff auf eine Freigabe verloren hat, was Benutzer stören kann, die noch nicht den Modus "Immer offline" von Offlinedateien nutzen.

## <a name="practical-applications"></a>Praktische Anwendungsfälle

Dateiserver mit horizontaler Skalierung eignen sich ideal für die Speicherung von Serveranwendungen. Es folgen einige Beispiele für Serveranwendungen, die ihre Daten in einer Dateifreigabe mit horizontaler Skalierung speichern können:

- Der IIS-Webserver (Internetinformationsdienste) kann Konfigurationen und Daten für Websites in einer Dateifreigabe mit horizontaler Skalierung speichern. Weitere Informationen finden Sie unter [Freigegebene Konfiguration](http://www.iis.net/learn/manage/managing-your-configuration-settings/shared-configuration_264).
- Hyper-V kann Konfigurationen und aktive virtuelle Datenträger in einer Dateifreigabe mit horizontaler Skalierung speichern. Weitere Informationen finden Sie unter [Bereitstellen von Hyper-V über SMB](<https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/jj134187(v%3dws.11)>).
- SQL Server kann aktive Datenbankdateien in einer Dateifreigabe mit horizontaler Skalierung speichern. Weitere Informationen finden Sie unter [Installieren von SQL Server mit SMB-Dateifreigabe als Speicheroption](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server-with-smb-fileshare-as-a-storage-option).
- Virtual Machine Manager (VMM) kann eine Bibliotheksfreigabe (mit Vorlagen für virtuelle Computer und zugehörigen Dateien) in einer Dateifreigabe mit horizontaler Skalierung speichern. Der Bibliothekserver selbst kann jedoch keines Dateiservers für horizontales Skalieren werden – es muss auf einem eigenständigen Server oder einem Failovercluster, das den Scale-Out File Server-Clusterrolle nicht verwendet werden.

Wenn Sie eine Dateifreigabe mit horizontaler Skalierung als Bibliotheksfreigabe verwenden, können Sie nur Technologien nutzen, die mit dem Dateiserver mit horizontaler Skalierung kompatibel sind. Sie können beispielsweise nicht die DFS-Replikation verwenden, um eine Bibliotheksfreigabe zu replizieren, die in einer Dateifreigabe mit horizontaler Skalierung gehostet wird. Es ist auch wichtig, dass für den Dateiserver mit horizontaler Skalierung die neuesten Softwareupdates installiert sind.

Zum Verwenden einer Dateifreigabe mit horizontaler Skalierung fügen Sie zunächst einen Bibliotheksserver (wahrscheinlich einen virtuellen Computer) mit einer lokalen Freigabe bzw. ohne Freigaben hinzu. Wenn Sie eine Bibliotheksfreigabe hinzufügen, wählen Sie eine Dateifreigabe, die auf einem Dateiserver mit horizontaler Skalierung gehostet wird. Diese Freigabe muss von VMM verwaltet werden und ausschließlich für die Verwendung durch den Bibliotheksserver erstellt worden sein. Stellen Sie außerdem sicher, dass auf dem Dateiserver mit horizontaler Skalierung die neuesten Updates installiert werden. Weitere Informationen zum Hinzufügen von Bibliothekservern und Bibliotheksfreigaben finden Sie unter [Hinzufügen von Profilen zur VMM-Bibliothek](https://docs.microsoft.com/system-center/vmm/library-profiles?view=sc-vmm-1801). Eine Liste der derzeit verfügbaren Hotfixes für Datei- und Speicherdienste finden Sie im [Microsoft Knowledge Base-Artikel 2899011](https://support.microsoft.com/help/2899011/list-of-currently-available-hotfixes-for-the-file-services-technologie).

>[!NOTE]
>Einige Benutzer, wie z. B. Information-Worker, haben Arbeitsauslastungen, die eine größere Auswirkung auf die Leistung haben. Vorgänge wie das Öffnen und Schließen von Dateien, das Erstellen neuer Dateien und das Umbenennen vorhandener Dateien haben Auswirkungen auf die Leistung, wenn sie durch mehrere Benutzer erfolgen. Wenn eine Dateifreigabe mit fortlaufender Verfügbarkeit aktiviert ist, bietet diese Datenintegrität, wirkt sich aber auch auf die allgemeine Leistung aus. Die fortlaufende Verfügbarkeit erfordert das Schreiben von Daten auf den Datenträger, damit bei einem Ausfall eines Clusterknotens in einem Dateiserver mit horizontaler Skalierung die Integrität gewährleistet ist. Daher muss ein Benutzer, der mehrere große Dateien auf einen Dateiserver kopiert, in einer fortlaufend verfügbaren Dateifreigabe mit einer erheblich langsameren Leistung rechnen.

## <a name="features-included-in-this-scenario"></a>In diesem Szenario enthaltene Features

In der folgenden Tabelle werden die Features dieses Szenarios und die Art der bereitgestellten Unterstützung aufgeführt.

<table>
<thead>
<tr class="header">
<th>Feature</th>
<th>Auf welche Weise dieses Szenario unterstützt wird</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="failover-clustering.md">Failoverclustering</a></td>
<td>Failovercluster werden die folgenden Features in Windows Server 2012, um die Unterstützung von Dateiservern mit horizontaler hinzugefügt: Verteilter Netzwerkname, den Ressourcentyp für den Scale-Out File Server, freigegebenen Clustervolumes (CSV) 2 und die Rolle für die horizontale Skalierung hohe Verfügbarkeit des Dateiservers. Weitere Informationen zu diesen Funktionen finden Sie unter <a href="https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265972(v%3dws.11)">was&#39;s neues beim Failoverclustering unter Windows Server 2012 [umgeleitet]</a>.</td>
</tr>
<tr class="even">
<td><a href="https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831795(v%3dws.11)">Server Message Block</a></td>
<td>SMB 3.0 wurde die folgenden Features in Windows Server 2012 mit horizontaler Skalierung unterstützen: SMB Transparent Failover, SMB Multichannel und SMB Direct.<br />
<br />
Weitere Informationen zu neuen und geänderten Funktionen für SMB unter Windows Server 2012 R2, finden Sie unter <a href="https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831474(v%3dws.11)">was&#39;s New in SMB unter Windows Server</a>.</td>
</tr>
</tbody>
</table>

## <a name="more-information"></a>Weitere Informationen

- [Entwurfsüberlegungen für Softwaredefinierten Speicher](<https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/mt243829(v%3dws.11)>)
- [Erhöhen der Server-, Speicher- und Netzwerkverfügbarkeit](<https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831437(v%3dws.11)>)
- [Bereitstellen von Hyper-V über SMB](<https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/jj134187(v%3dws.11)>)
- [Schnelle und effiziente Dateiserver bereitstellen für Serveranwendungen](<https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831723(v%3dws.11)>)
- [To scale out or not to scale out, that is the question](https://blogs.technet.com/b/filecab/archive/2013/12/05/to-scale-out-or-not-to-scale-out-that-is-the-question.aspx) (Blogbeitrag)
- [Ordnerumleitung, Offlinedateien und Roamingbenutzerprofile](<https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh848267(v%3dws.11)>)