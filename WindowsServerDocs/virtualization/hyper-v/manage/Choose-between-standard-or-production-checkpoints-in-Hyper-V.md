---
title: Wählen Sie zwischen Standard- und produktionsprüfpunkten im Hyper-V
description: Bietet Anweisungen zum Konfigurieren eines virtuellen Computers für die Verwendung von Standard- und produktionsprüfpunkten
ms.prod: windows-server-threshold
ms.service: na
manager: dongill
ms.technology: compute-hyper-v
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 92bb573b-03b7-470e-b72e-e35edf52b349
author: KBDAzure
ms.author: kathydav
ms.date: 10/04/2016
ms.openlocfilehash: cf1144886ec5ae723b7747bb7dd72f235944d06c
ms.sourcegitcommit: 3743cf691a984e1d140a04d50924a3a0a19c3e5c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2019
ms.locfileid: "67141352"
---
# <a name="choose-between-standard-or-production-checkpoints-in-hyper-v"></a>Wählen Sie zwischen Standard- und produktionsprüfpunkten im Hyper-V

>Gilt für: Windows 10, WindowsServer 2016, Microsoft Hyper-V Server 2016, WindowsServer 2019, Microsoft Hyper-V-Server 2019

  
Ab Windows Server 2016 und Windows 10, können Sie zwischen Standard- und produktionsprüfpunkten zu verstehen für jeden virtuellen Computer auswählen. Produktionsprüfpunkte werden standardmäßig für neue virtuelle Computer.
  
- Produktionsprüfpunkte sind "Zeitpunkt"-Images einer virtuellen Maschine, die später auf eine Weise wiederhergestellt werden kann, die für alle produktionsworkloads vollständig unterstützt wird. Dies erfolgt mithilfe von Sicherungstechnologie innerhalb des Gastbetriebssystems zum Erstellen des Prüfpunkts anstatt mit Technologie zum Speichern des Zustands.  
  
- Standardprüfpunkte die Zustand, Daten und Hardware-Konfiguration eines ausgeführten virtuellen Computers zu erfassen und sind für die Verwendung in Entwicklungs- und Testszenarien vorgesehen. Standardprüfpunkte ist hilfreich, wenn müssen Sie einen bestimmten Status oder Bedingung für einen ausgeführten virtuellen Computer neu erstellen, damit Sie ein Problem beheben können.  
 
  ## <a name="change-checkpoints-to-production-or-standard-checkpoints"></a>Ändern Sie die Prüfpunkte in Produktions- oder standardprüfpunkte  
  
1.  In **Hyper-V-Manager**mit der rechten Maustaste auf den virtuellen Computer, und klicken Sie auf **Einstellungen**.  
  
2.  Unter den **Management** wählen Sie im Abschnitt **Prüfpunkte**.  
  
3.  Wählen Sie entweder „Produktionsprüfpunkte“ oder „Standardprüfpunkte“ aus.  
  
    Wenn Sie auf "produktionsprüfpunkte" auswählen, können Sie auch angeben, ob der Host einen standardprüfpunkt erstellen sollten, wenn kein produktionsprüfpunkt erstellt werden, kann nicht. Wenn Sie dieses Kontrollkästchen deaktivieren, und kein produktionsprüfpunkt kann nicht erstellt werden, wird kein Prüfpunkt ausgeführt.  
  
4.  Wenn Sie die Konfigurationsdateien für den Prüfpunkt in einem anderen Ort speichern möchten, ändern Sie ihn in das **Prüfpunkt-Dateispeicherort** Abschnitt.  
  
5.  Klicken Sie auf **übernehmen** zum Speichern der Änderungen. Wenn Sie fertig sind, klicken Sie auf **OK** um das Dialogfeld zu schließen.  
  
> [!NOTE]
> Nur **Produktionsprüfpunkte** für Gäste, die Active Directory Domain Services (Domänencontroller) oder Active Directory Lightweight Directory Services-Rolle ausgeführt werden.

## <a name="see-also"></a>Siehe auch  
  
-   [Produktionsprüfpunkte](../What-s-new-in-Hyper-V-on-Windows.md#production-checkpoints-new)  
  
-   [Aktivieren oder Deaktivieren von Prüfpunkten](Enable-or-disable-checkpoints-in-Hyper-V.md)  
  


