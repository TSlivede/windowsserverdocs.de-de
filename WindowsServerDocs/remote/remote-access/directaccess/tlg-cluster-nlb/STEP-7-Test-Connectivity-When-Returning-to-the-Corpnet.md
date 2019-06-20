---
title: Schritt 7 Testen der Konnektivität bei der Rückkehr zum Unternehmensnetzwerk
description: 'Dieses Thema ist Teil der Testumgebungsanleitung: Vorführen von DirectAccess in einem Cluster mit Windows NLB für Windows Server 2016'
manager: brianlic
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology:
- networking-da
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 5a7252d0-6db8-4a9d-98ee-75082ecd2929
ms.author: pashort
author: shortpatti
ms.openlocfilehash: af22b1bbc923b9a06e4aebb910690050af1b7492
ms.sourcegitcommit: eaf071249b6eb6b1a758b38579a2d87710abfb54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66446631"
---
# <a name="step-7-test-connectivity-when-returning-to-the-corpnet"></a>Schritt 7 Testen der Konnektivität bei der Rückkehr zum Unternehmensnetzwerk

>Gilt für: WindowsServer (Halbjährlicher Kanal), WindowsServer 2016

Viele der Benutzer wechselt zwischen Remotestandorten und des Unternehmensnetzwerks, daher es wichtig ist, dass, wenn sie mit dem Unternehmensnetzwerk zurückgeben, dass sie den Zugriff auf Ressourcen ohne konfigurationsänderungen vornehmen zu müssen ändert können. Remote-Zugriff macht dies möglich, da bei der DirectAccess-Client in das Unternehmensnetzwerk zurückkehrt, herstellen eine Verbindung mit der Netzwerkadressenserver ist. Sobald die HTTPS-Verbindung mit dem Netzwerkadressenserver erfolgreich hergestellt wurde, wird der DirectAccess-Client deaktiviert die DirectAccess-Clientkonfiguration und verwendet eine direkte Verbindung zum Unternehmensnetzwerk.  
  
### <a name="test-connectivity-on-client1"></a>Testen der Konnektivität auf CLIENT1  
  
1. Herunterfahren von "client1", und trennen Sie CLIENT1 mit dem Subnetz "Homenet" oder einen virtuellen Switch, und verbinden Sie es mit dem Subnetz "Corpnet" oder den virtuellen Switch. Aktivieren Sie "client1", und melden Sie sich als "corp\user1".  
  
2. Öffnen Sie ein Windows PowerShell-Fenster mit erhöhten Rechten, geben **Ipconfig/all**, und drücken Sie EINGABETASTE. Die Ausgabe wird angeben, dass "client1" eine lokale IP-Adresse hat und es ist keine aktive 6to4, Teredo oder IP-HTTPS-Tunnel.  
  
3. Testen der Konnektivität auf die Netzwerkfreigabe auf APP2. Auf der **starten** geben<strong>\\\APP2\Files</strong>, und drücken Sie dann die EINGABETASTE. Sie werden können zum Öffnen der Datei in diesem Ordner.  
  

