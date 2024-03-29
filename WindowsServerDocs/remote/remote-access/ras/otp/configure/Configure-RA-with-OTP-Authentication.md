---
title: Planen des Remotezugriffs mit OTP-Authentifizierung
description: Dieses Thema ist Teil des Leitfadens Bereitstellen von Remotezugriff mit OTP-Authentifizierung in Windows Server 2016.
manager: brianlic
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: networking-ras
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 82505b18-dd77-4dd1-aa27-b2962b8241ca
ms.author: pashort
author: shortpatti
ms.openlocfilehash: 76a3980d2169afd4e36692210e063f230fd863a4
ms.sourcegitcommit: afb0602767de64a76aaf9ce6a60d2f0e78efb78b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2019
ms.locfileid: "67282471"
---
# <a name="configure-remote-access-with-otp-authentication"></a>Planen des Remotezugriffs mit OTP-Authentifizierung

>Gilt für: WindowsServer (Halbjährlicher Kanal), WindowsServer 2016

 Windows Server 2016 und Windows Server 2012 werden DirectAccess und Routing- und RAS-Dienst (RRAS) VPN in einer einzigen remotezugriffsrolle kombinieren. Diese Übersicht bietet eine Einführung in die Konfigurationsschritte zum Bereitstellen von einer einzelnen Windows Server 2016 oder Windows Server 2012-Remotezugriff für mehrere Standorte Bereitstellung erforderlich sind.  


- [Schritt 1: Implementieren eine Einzelserverbereitstellung für den Remotezugriff](../../multisite/configure/Step-1-Implement-a-Single-Server-Remote-Access-Deployment.md). Installieren Sie und konfigurieren Sie einer RAS-Servers. Anweisungen hierzu finden Sie unter [Bereitstellen eines einzelnen DirectAccess-Servers mit erweiterten Einstellungen](https://technet.microsoft.com/windows-server-docs/networking/remote-access/directaccess/single-server-advanced/deploy-a-single-directaccess-server-with-advanced-settings).

- [Schritt 2: Konfigurieren des RADIUS-Servers](Step-2-Configure-the-RADIUS-Server.md).

- [Schritt 3: Konfigurieren von RAS-Servers für OTP](Step-3-Configure-the-Remote-Access-Server-for-OTP.md).

- [Schritt 4: Überprüfen von DirectAccess mit OTP](Step-4-Verify-DirectAccess-with-OTP.md).
  


