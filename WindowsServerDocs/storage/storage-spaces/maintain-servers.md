---
title: Server für Direkte Speicherplätze zu Wartungszwecken offline schalten
ms.prod: windows-server-threshold
ms.author: eldenc
ms.manager: eldenc
ms.technology: storage-spaces
ms.topic: article
author: eldenchristensen
ms.date: 10/08/2018
Keywords: Direkte Speicherplätze (S2D), Wartung
ms.assetid: 73dd8f9c-dcdb-4b25-8540-1d8707e9a148
ms.localizationpriority: medium
ms.openlocfilehash: 96ae0ad0d1def12ab68466f0a9ae60d0afcc2c17
ms.sourcegitcommit: 0d0b32c8986ba7db9536e0b8648d4ddf9b03e452
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2019
ms.locfileid: "59871221"
---
# <a name="taking-a-storage-spaces-direct-server-offline-for-maintenance"></a>Server für Direkte Speicherplätze zu Wartungszwecken offline schalten

> Gilt für: Windows Server 2019, Windows Server 2016

Dieses Thema enthält Informationen zum korrekten Neustart und zum Herunterfahren von Servern mit [Direkten Speicherplätzen](storage-spaces-direct-overview.md).

Wenn Sie einen Server mit direkten Speicherplätzen offline schalten (herunterfahren) werden ebenfalls Teile der auf allen Servern im Cluster freigegebenen Speicher offline geschaltet. Dies erfordert das Anhalten des Servers, den Sie offline schalten möchten und das Verteilen der Rollen auf andere Servern im Cluster sowie das Überprüfen, dass alle Daten auf anderen Servern in dem Cluster verfügbar sind, damit die Daten gesichert sind und während der Wartung verfügbar bleiben.

Gehen Sie folgendermaßen vor, um einen Server in einem Cluster mit direkten Speicherplätzen ordnungsgemäß anzuhalten, bevor es offline geschaltet wird. 

   > [!IMPORTANT]
   > Verwenden Sie zum Installieren von Updates auf einem „Direkte Speicherplätze“-Cluster Clusterfähiges Aktualisieren (CAU), das die in diesem Thema erklärten Verfahren automatisch ausführt, damit Sie beim Installieren von Updates nichts unternehmen müssen. Weitere Informationen finden Sie unter [Clusterfähiges Aktualisieren (CAU)](https://technet.microsoft.com/library/hh831694.aspx).

## <a name="verifying-its-safe-to-take-the-server-offline"></a>Überprüfen, ob es sicher ist den Server offline zu schalten

Vor dem Offline-Schalten eines Servers für die Wartung, stellen Sie sicher, dass alle Ihre Volumes fehlerfrei sind.

Zu diesem Zweck öffnen Sie eine PowerShell-Sitzung mit Administratorrechten, und führen Sie den folgenden Befehl aus, um den Volumestatus zu ermitteln.

```PowerShell
Get-VirtualDisk 
```

Hier ist ein Beispiel dafür, wie die Ausgabe aussehen könnte:
```
FriendlyName ResiliencySettingName OperationalStatus HealthStatus IsManualAttach Size
------------ --------------------- ----------------- ------------ -------------- ----
MyVolume1    Mirror                OK                Healthy      True           1 TB
MyVolume2    Mirror                OK                Healthy      True           1 TB
MyVolume3    Mirror                OK                Healthy      True           1 TB
```

Überprüfen Sie, dass die **HealthStatus** -Eigenschaft für jedes Volume (virtuelle Festplatte) **fehlerfrei** ist.

Navigieren Sie dazu im Failovercluster-Manager zu **Speicher** > **Datenträger**.

Überprüfen Sie, ob die **Status**-Spalte für jedes Volume (virtuelle Festplatte) auf **Online** festgelegt ist.

## <a name="pausing-and-draining-the-server"></a>Anhalten und Ausgleichen des Servers

Vor dem Neustart oder Herunterfahren des Servers, müssen Sie alle Rollen wie beispielsweise virtuelle Computer angehalten und ausgeglichen (ausgeblendet) werden. Dies bietet den direkten Speicherplätzen die Möglichkeit, problemlos Daten zu leeren und zu schreiben, um sicherzustellen, dass das Herunterfahren für alle Anwendungen transparent ist, die auf diesem Server ausgeführt werden.

   > [!IMPORTANT]
   > Vor dem Neustart oder Herunterfahren von Cluster-Servern, müssen Sie angehalten und ausgeglichen werden.

Führen Sie das folgende Cmdlet in PowerShell (als Administrator) zum Anhalten und Ausgleichen aus.

```PowerShell
Suspend-ClusterNode -Drain
```

Um dies im Failovercluster-Manager durchzuführen, wechseln Sie zu **Knoten**, klicken Sie mit der rechten Maustaste auf den Projektknoten und wählen Sie dann **Anhalten** > **Rollen ausgleichen** aus.

![Anhalten-Ausgleichen](media/maintain-servers/pause-drain.png)

Alle virtuellen Computer beginnen mit der Livemigration zu anderen Servern im Cluster. Dieser Vorgang kann einige Minuten dauern.

   > [!NOTE]
   > Wenn Sie den Clusterknoten ordnungsgemäß anhalten und abgleichen, führt Windows eine automatische Prüfung durch, um sicherzustellen, dass der Vorgang fortgesetzt werden kann. Wenn beschädigte Volumes vorhanden sind, wird der Vorgang beendet und gewarnt, dass eine Fortsetzung nicht mehr sicher durchgeführt werden kann.

![Sicherheitsüberprüfung](media/maintain-servers/safety-check.png)

## <a name="shutting-down-the-server"></a>Server herunterfahren

Wenn der Server das Ausgleichen abgeschlossen hat, wird **Angehalten** im Failovercluster-Manager und PowerShell angezeigt.

![Angehalten](media/maintain-servers/paused.png)

Sie können den Computer jetzt problemlos neu starten oder herunterfahren, genau wie gewohnt (z. B. mithilfe der Restart-Computer oder Stop-Computer-PowerShell-Cmdlets).

```PowerShell
Get-VirtualDisk 

FriendlyName ResiliencySettingName OperationalStatus HealthStatus IsManualAttach Size
------------ --------------------- ----------------- ------------ -------------- ----
MyVolume1    Mirror                Incomplete        Warning      True           1 TB
MyVolume2    Mirror                Incomplete        Warning      True           1 TB
MyVolume3    Mirror                Incomplete        Warning      True           1 TB
```

Unvollständig oder Operational Status "heruntergestuft" ist normal, wenn Knoten heruntergefahren werden, oder Starten/Beenden des Clusters auf einem Knoten service und sollten kein Problem. Alle Ihre Volumes bleiben online und verfügbar.

## <a name="resuming-the-server"></a>Den Server fortsetzen

Wenn der Server Arbeitslasten erneut hosten soll, setzen Sie den Vorgang fort.

Führen Sie das folgende Cmdlet in PowerShell (als Administrator) zum Fortsetzen aus.

```PowerShell
Resume-ClusterNode
```

Um die zuvor auf dem Server ausgeführten Rollen zurück zu verschieben, verwenden Sie das optionale **- Failback**-Kennzeichen.

```PowerShell
Resume-ClusterNode –Failback Immediate
```

Um dies im Failovercluster-Manager durchzuführen, wechseln Sie zu **Knoten**, klicken Sie mit der rechten Maustaste auf den Projektknoten und wählen Sie dann **Fortsetzen** > **Rollen zurücksetzen** aus.

![Fortsetzen-Failback](media/maintain-servers/resume-failback.png)

## <a name="waiting-for-storage-to-resync"></a>Auf Neusynchronisierung des Speichers warten

Wenn der Server wieder aufgenommen wird, müssen neuen Schreibvorgänge, die aufgetreten sind, während sie nicht verfügbar war erneut synchronisieren. Dies erfolgt automatisch. Bei der Verwendung der intelligenten Änderungsnachverfolgung ist es nicht erforderlich, *alle* Daten zu überprüfen oder zu synchronisieren sondern nur diejenigen, die geändert wurden. Dieser Prozess wird gedrosselt, um den Einfluss auf die Produktionsarbeitsauslastungen zu verringern. Je nachdem, wie lange der Server angehalten wurde und wie viel neue Daten geschrieben wurden kann dies mehrere Minuten dauern.

Sie müssen warten, bis die Synchronisierung abgeschlossen ist, bevor Sie einen anderen Server im Cluster offline nehmen.

Führen Sie das folgende Cmdlet in PowerShell (als Administrator) zum Überwachen des Status aus.

```PowerShell
Get-StorageJob
```
Hier sehen eine Beispielausgabe von neu synchronisierten (reparierten) Aufträgen:
```
Name   IsBackgroundTask ElapsedTime JobState  PercentComplete BytesProcessed BytesTotal
----   ---------------- ----------- --------  --------------- -------------- ----------
Repair True             00:06:23    Running   65              11477975040    17448304640
Repair True             00:06:40    Running   66              15987900416    23890755584
Repair True             00:06:52    Running   68              20104802841    22104819713
```

**BytesTotal** zeigt, wie viel Speicherplatz neu synchronisiert werden muss. **PercentComplete** zeigt den Fortschritt an.

   > [!WARNING]
   > Das Offlineschalten eines anderen Servers kann nicht sicher durchgeführt werden, bis die Reparatur der Aufträge beendet ist.

In dieser Zeit werden die Volumes als **Warnung** angezeigt, was normal ist. 

Wenn Sie z. B. das Cmdlet `Get-VirtualDisk` verwenden, wird möglicherweise folgende Ausgabe angezeigt:
```
FriendlyName ResiliencySettingName OperationalStatus HealthStatus IsManualAttach Size
------------ --------------------- ----------------- ------------ -------------- ----
MyVolume1    Mirror                InService         Warning      True           1 TB
MyVolume2    Mirror                InService         Warning      True           1 TB
MyVolume3    Mirror                InService         Warning      True           1 TB
```

Sobald die Aufträge abgeschlossen ist, überprüfen Sie mithilfe des Cmdlet `Get-VirtualDisk`, ob die Volumes als **Fehlerfrei** angezeigt werden. Ausgabebeispiel:

```
FriendlyName ResiliencySettingName OperationalStatus HealthStatus IsManualAttach Size
------------ --------------------- ----------------- ------------ -------------- ----
MyVolume1    Mirror                OK                Healthy      True           1 TB
MyVolume2    Mirror                OK                Healthy      True           1 TB
MyVolume3    Mirror                OK                Healthy      True           1 TB
```

Sie können andere Server im Cluster jetzt anhalten und neu starten.

## <a name="how-to-update-storage-spaces-direct-nodes-offline"></a>Vorgehensweise beim Aktualisieren von "direkte Speicherplätze" Knoten offline geschaltet
Verwenden Sie die folgenden Schritte aus, um den Pfad Ihrem "direkte Speicherplätze" System schnell. Sie umfasst Planung eines Wartungsfensters und das System herunterzufahren, für das Patchen. Liegt ein wichtiges Sicherheitsupdate, das Sie benötigen schnell angewendet werden, oder vielleicht müssen Sie sicherstellen, dass das Patchen des Wartungsfensters abgeschlossen wird, kann diese Methode für Sie sein. Dieser Prozess bietet Sie den Cluster "direkte Speicherplätze", sie patches und schaltet sie Sie erneut. Der Nachteil besteht in Ausfallzeiten für die gehosteten Ressourcen.

1. Planen des Wartungsfensters an.
2. Schalten Sie die virtuellen Datenträger offline.
3. Beenden Sie den Cluster, um den Speicherpool offline zu schalten. Führen Sie die **Stop-Cluster** Cmdlet oder verwenden Sie Failovercluster-Manager, um den Cluster zu beenden.
4. Legen Sie den Clusterdienst auf **deaktiviert** in "Services.msc" auf jedem Knoten. Dadurch wird verhindert, dass den Clusterdienst gestartet und gepatcht werden.
5. Wenden Sie das kumulative Update für Windows Server, und alle erforderlichen Servicing Stack-Updates an alle Knoten. (Sie können aktualisieren alle Knoten gleichzeitig, keinen Grund zu warten, da der Cluster ausgefallen ist).  
6. Starten Sie den Knoten neu, und stellen Sie sicher, dass alles in Ordnung ist.
7. Gruppe, die der Clusterdienst an **automatische** auf jedem Knoten.
8. Starten Sie den Cluster ein. Führen Sie die **Start des Clusters** Cmdlet oder Failovercluster-Manager verwenden. 

   Warten sie einige Minuten.  Stellen Sie sicher, dass der Speicherpool fehlerfrei ist.
9. Schalten Sie die virtuellen Datenträger wieder online geschaltet.
10. Überwachen des Status der virtuellen Datenträger durch Ausführen der **Get-Volume** und **Get-VirtualDisk** Cmdlets.


## <a name="see-also"></a>Siehe auch

- [Übersicht über Storage "direkte Speicherplätze"](storage-spaces-direct-overview.md)
- [Cluster-Aware aktualisieren (CAU)](https://technet.microsoft.com/library/hh831694.aspx)
