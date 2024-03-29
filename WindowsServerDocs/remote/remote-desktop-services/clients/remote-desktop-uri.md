---
title: URI-Schema für Remotedesktopclients
description: Lerne das Uniform Resource Identifier-Schema für Remotedesktopclients kennen.
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: remote-desktop-services
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0c3f1eb6-835c-4522-99ff-56c6ee4bb911
author: lizap
manager: dongill
ms.author: elizapo
ms.date: 06/11/2018
ms.localizationpriority: medium
ms.openlocfilehash: f2934fed43c8f4feec2f321d684cc3593933eb5d
ms.sourcegitcommit: 3743cf691a984e1d140a04d50924a3a0a19c3e5c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2019
ms.locfileid: "63743852"
---
# <a name="remote-desktop-client-universal-resource-identifier-uri-scheme-support"></a>Unterstützung für das Uniform Resource Identifier-Schema (URI) für Remotedesktopclients

>Gilt für: Windows Server, Version 1803, Windows Server 2019, Windows Server 2016, Windows Server 2012 R2

Durch Aktivierung eines URI-Schemas (Uniform Resource Identifier) können IT-Experten und Entwickler Features der Remotedesktopclients über Plattformen hinweg integrieren und die Benutzerfreundlichkeit verbessern, da diese Integration Folgendes ermöglicht: 

- Anwendungen von Drittanbietern können Microsoft Remotedesktop starten und Remotesitzungen mit vordefinierten Einstellungen (die als Teil der URI-Zeichenfolge bereitgestellt werden) einrichten.
- Endbenutzer können Remoteverbindungen über vorkonfigurierte URLs starten.

>[!NOTE]
> Die Verwendung eines URI zum Herstellen einer Verbindung mit dem Remotedesktopclient wird für Windows-Betriebssysteme NICHT unterstützt. Verwende den URI mit macOS-, iOS- und Android-Geräten.

Microsoft-Remotedesktop verwendet das URI-Schema „rdp://Abfragezeichenfolge“ zum Speichern vorkonfigurierter Attributeinstellungen, die beim Starten des Clients verwendet werden. Die Abfragezeichenfolgen stellen ein oder mehrere RDP-Attribute dar, die in der URL bereitgestellt werden. 

Die RDP-Attribute werden durch das kaufmännische Und-Zeichen (&) getrennt. Bei einer Verbindung mit einem PC lautet die Zeichenfolge zum Beispiel wie folgt:

```
rdp://full%20address=s:mypc:3389&audiomode=i:2&disable%20themes=i:1
```

Diese Tabelle enthält eine vollständige Liste der unterstützten Attribute, die mit dem iOS, Mac und Android Remotedesktopclients verwendet werden kann. (Ein "X" in der Spalte mit der Plattform gibt an, dass das Attribut unterstützt wird. Die in spitzen Klammern (<>) eingeschlossenen Werte sind die von den Remotedesktopclients unterstützten Werte.)

| **RDP-Attribut**                                           | **Android** | **Mac** | **iOS** |
|---------------------------------------------------------|---------|-----|-----|
| allow desktop composition=i:&lt;0 oder 1&gt;                    | x       | x   | x   |
| allow font smoothing=i:<0 oder 1&gt;                         | x       | x   | x   |
| alternate shell=s:&lt;Zeichenfolge&gt;                              | x       | x   | x   |
| [audiomode=i:&lt;0, 1 oder 2&gt;](https://technet.microsoft.com/library/ff393707.aspx)                                | x       | x   | x   |
| [authentication level=i:&lt;0 oder 1&gt;](https://technet.microsoft.com/library/ff393709.aspx)                         | x       | x   | x   |
| connect to console=i:&lt;0 oder 1&gt;                           | x       | x   | x   |
| disable cursor settings=i:&lt;0 oder 1&gt;                      | x       | x   | x   |
| disable full window drag=i:&lt;0 oder 1&gt;                     | x       | x   | x   |
| disable menu anims=i:&lt;0 oder 1&gt;                           | x       | x   | x   |
| disable themes=i:&lt;0 oder 1&gt;                               | x       | x   | x   |
| disable wallpaper=i:&lt;0 oder 1&gt;                            | x       | x   | x   |
| [drivestoredirect=s:*](https://technet.microsoft.com/library/ff393728(v=ws.10).aspx) (Dies ist der einzige unterstützte Wert) | x       | x   |     |
| [desktopheight=i:&lt;Wert in Pixeln&gt;](https://technet.microsoft.com/library/ff393702.aspx)                       |         | x   |     |
| [desktopwidth=i:&lt;Wert in Pixeln&gt;](https://technet.microsoft.com/library/ff393697.aspx)                        |         | x   |     |
| [domain=s:&lt;Zeichenfolge&gt;](https://technet.microsoft.com/library/ff393673.aspx)                           | x | x | x |
| [full address=s:&lt;Zeichenfolge&gt;](https://technet.microsoft.com/library/ff393661.aspx)                     | x | x | x |
| gatewayhostname=s:&lt;Zeichenfolge&gt;                  | x | x | x |
| [gatewayusagemethod=i:&lt;1 oder 2&gt;](https://msdn.microsoft.com/aa381329.aspx)               | x | x | x |
| [prompt for credentials on client=i:&lt;0 oder 1&gt;](https://technet.microsoft.com/library/ff393660(v=ws.10).aspx) |   | x |   |
| [loadbalanceinfo=s:&lt;Zeichenfolge&gt;](https://technet.microsoft.com/library/ff393684.aspx)                  | x | x | x |
| [redirectprinters=i:&lt;0 oder 1&gt;](https://technet.microsoft.com/library/ff393671(v=ws.10).aspx)                 |   | x |   |
| remoteapplicationcmdline=s:&lt;Zeichenfolge&gt;         | x | x | x |
| remoteapplicationmode=i:&lt;0 oder 1&gt;            | x | x | x |
| remoteapplicationprogram=s:&lt;Zeichenfolge&gt;         | x | x | x |
| shell working directory=s:&lt;Zeichenfolge&gt;          | x | x | x |
| Use redirection server name=i:&lt;0 oder 1&gt;      | x | x | x |
| [username=s:&lt;Zeichenfolge&gt;](https://technet.microsoft.com/library/ff393678.aspx)                         | x | x | x |
| [screen mode id=i:&lt;1 oder 2&gt;](https://technet.microsoft.com/library/ff393692.aspx)                   |   | x |   |
| [session bpp=i:&lt;8, 15, 16, 24 oder 32&gt;](https://technet.microsoft.com/library/ff393680.aspx)        |   | x |   |
| [use multimon=i:&lt;0 oder 1&gt;](https://technet.microsoft.com/library/ff393695(v=ws.10).aspx)          |   | x |   |