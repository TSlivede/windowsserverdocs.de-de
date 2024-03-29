---
title: Verwalten der Stationshardware
description: Bietet eine Übersicht über das Verwalten der Hardware für MultiPoint-Stationen
ms.custom: na
ms.prod: windows-server-threshold
ms.technology: multipoint-services
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 429b8539-b17a-4e01-9576-860600466451
author: lizap
manager: dongill
ms.author: elizapo
ms.date: 08/04/2016
ms.openlocfilehash: 3a1cdfd12c9bd6a21fec9cbfffae04573ef5ea98
ms.sourcegitcommit: 0d0b32c8986ba7db9536e0b8648d4ddf9b03e452
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2019
ms.locfileid: "59841631"
---
# <a name="manage-station-hardware"></a>Verwalten der Stationshardware
Ein MultiPoint Services-System besteht aus einem einzelnen Computer und mindestens eine Station. Der stationshardware besteht in der Regel ein stationshub, Maus, Tastatur und Videomonitor aus. Stationen sind üblicherweise physisch mit dem Computer verbunden.  
  
Die folgende Abbildung zeigt ein Beispiellayout für ein MultiPoint Services-System mit vier Stationen. Jede Station ist auf dem MultiPoint Services-Computer mit einem USB-Hub und Grafikkarten für mehrere Monitore verbunden. Die folgende Abbildung stellt keine Stationen dar, die mithilfe von Multi-Factor-Hubs verbunden sind.  
   
![Layout eines MultiPoint Services-USB-basierten Systems](./media/WMSMultiPointServerUSBSystemLayout.gif)  
  
In den Themen dieses Abschnitts wird beschrieben, wie Sie den Status der an das MultiPoint Services-System angeschlossenen Hardware anzeigen können. Ferner erhalten Sie detaillierte Informationen zu den Arten von USB-Geräten und anderen Hardwareperipheriegeräten, mit denen eine MultiPoint Services-Station eingerichtet werden kann. Im Folgenden finden Sie eine kurze Beschreibung der in diesem Abschnitt enthaltenen Themen, mit deren Hilfe Sie Hardware auswählen und Ihre MultiPoint Services-Station einrichten können.  
  
## <a name="view-hardware-status"></a>Anzeigen des Hardwarestatus  
Im MultiPoint-Manager können Sie die **Stationen** Registerkarte zum Anzeigen des Status der Stationen und Hardwaregeräte, die mit dem MultiPoint Services-Computer verbunden sind. Weitere Informationen zum Anzeigen des Status Ihres MultiPoint Services-Computers und der daran angeschlossenen Hardwaregeräte finden Sie im Thema [Anzeigen des Hardwarestatus](View-Hardware-Status.md).  
  
## <a name="work-with-usb-devices"></a>Arbeiten mit USB-Geräten  
USB-Geräte und andere Hardwareperipheriegeräte im MultiPoint Services-System funktionieren unterschiedlich, je nachdem, ob sie an den MultiPoint Services-Computer oder eine MultiPoint Services-Station angeschlossen sind. Im Thema [Arbeiten mit USB-Geräten](Work-with-USB-Devices.md) wird beschrieben, wie unterschiedliche Hardwaregeräte in diesen Szenarios funktionieren können. Zudem bietet das Thema ausführliche Informationen für die Arbeit mit Stationshubs.  
  
## <a name="work-with-video-devices"></a>Arbeiten mit Videogeräten  
Im Thema [Arbeiten mit Videogeräten](Work-with-Video-Devices.md) wird erläutert, wie Videogeräte, z.B. Monitore oder Projektoren, funktionieren, wenn sie an einen Computer in Ihrem MultiPoint Services-System oder an eine MultiPoint Services-Station angeschlossen werden.  
  
## <a name="set-up-a-station"></a>Einrichten einer Station  
Im Thema [Einrichten einer Station](Set-Up-a-Station.md) wird beschrieben, wie die Hardwareperipheriegeräte an einen MultiPoint Services-Stationshub angeschlossen werden, um eine MultiPoint Services-Station zu erstellen. MultiPoint Services unterstützt zwei Typen von Stationshubs:  
  
-   Eine extern ausgeschaltet oder Bus betriebene mehreren Ports *USB-Hub* , die eine Maus, Tastatur und andere USB-Peripheriegeräte unterstützen können  
  
-   *Multifunktionshubs*, die mit einer integrierten Grafikkarte und Anschlüssen für Maus, Tastatur und Audioperipheriegeräte ausgestattet sein können.  
  
Beide Arten von Stationshubs werden über ein USB-Kabel an den Computer angeschlossen. Mit den Verfahren im Thema [Einrichten einer Station](Set-Up-a-Station.md) wird beschrieben, wie Hardwaregeräte an die unterschiedlichen Stationshubs angeschlossen werden.  
  
## <a name="see-also"></a>Siehe auch  
[Anzeigen des Hardwarestatus](View-Hardware-Status.md)  
[Arbeiten mit USB-Geräten](Work-with-USB-Devices.md)  
[Arbeiten mit Videogeräten](Work-with-Video-Devices.md)  
[Einrichten einer Station](Set-Up-a-Station.md)