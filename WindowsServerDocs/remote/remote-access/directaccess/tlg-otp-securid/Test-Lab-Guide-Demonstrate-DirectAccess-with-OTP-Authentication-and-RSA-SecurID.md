---
title: 'Testumgebungsanleitung: Vorführung von DirectAccess mit OTP-Authentifizierung und RSA SecurID'
description: 'Dieses Thema ist Teil der Testumgebungsanleitung: veranschaulichen von DirectAccess mit OTP-Authentifizierung und RSA SecurID für Windows Server 2016'
manager: brianlic
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: networking-da
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 10c7a49c-5671-4bec-b562-13fdd67f4629
ms.author: pashort
author: shortpatti
ms.openlocfilehash: 7ac60bdd5d8259197641a6aeaf332d8e671a7e97
ms.sourcegitcommit: afb0602767de64a76aaf9ce6a60d2f0e78efb78b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2019
ms.locfileid: "67281251"
---
# <a name="test-lab-guide-demonstrate-directaccess-with-otp-authentication-and-rsa-securid"></a>Testumgebungsanleitung: Vorführen von DirectAccess mit OTP-Authentifizierung und RSA SecurID

>Gilt für: WindowsServer (Halbjährlicher Kanal), WindowsServer 2016

RAS ist eine Serverrolle in das Windows Server 2016, Windows Server 2012 R2 und Windows Server 2012-Betriebssystem, das Remotebenutzern den sicheren Zugriff auf interne Netzwerkressourcen, die über DirectAccess oder virtuelle private Netzwerke (VPNs) mit dem Routing ermöglicht und RAS-Dienst (RRAS). Diese Anleitung enthält schrittweise Anweisungen zum Erweitern der [Test Lab Guide: Demonstrate DirectAccess Single Server-Setup mit gemischten IPv4 und IPv6-](https://go.microsoft.com/fwlink/p/?LinkId=237004) veranschaulicht eine Konfiguration des Remotezugriffs Einmalkennwort (OTP).  
  
> [!WARNING]  
> Das Design der vorliegenden testumgebungsanleitung enthält Infrastrukturserver, z. B. einen Domänencontroller und einer Zertifizierungsstelle (CA), die entweder Windows Server 2012 R2 oder Windows Server 2012 ausgeführt werden. Mit der vorliegenden testumgebungsanleitung Infrastrukturserver zu konfigurieren, auf denen andere Betriebssysteme ausgeführt werden nicht getestet wurde, und Anweisungen zum Konfigurieren von anderen Betriebssystemen sind in dieser Anleitung nicht enthalten.  
  
## <a name="about-this-guide"></a>Informationen zur Anleitung  
Remote Access in Windows Server 2016, Windows Server 2012 R2 und Windows Server 2012 fügt Unterstützung für die Clientauthentifizierung mit OTP hinzu. Für die Zwecke dieser testumgebung wird nur RSA SecurID zur Veranschaulichung der OTP-Funktionalität mit dem Remotezugriff verwendet. Andere RADIUS-basierten OTP-Lösungen werden ebenfalls unterstützt, aber nicht Bestandteil dieser testumgebung sind. Diese Anleitung enthält Anweisungen zum Konfigurieren und Veranschaulichen des Remotezugriffs mit sechs Servern und zwei Clientcomputern. Der abgeschlossenen Remotezugriff mit OTP-testumgebung simuliert ein Intranet, im Internet und einem Heimnetzwerk und veranschaulicht die remotezugriffsfunktionalität in verschiedenen internetverbindungsszenarios.  
  
> [!IMPORTANT]  
> Diese Testumgebung ist eine Machbarkeitsstudie mit der minimalen Anzahl an Computern. Die in dieser Anleitung beschriebene Konfiguration ist nur für Testzwecke geeignet und sollte nicht in einer Produktionsumgebung verwendet werden.  
  


