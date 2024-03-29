---
title: Migrieren von Rollen und Features
description: ''
ms.custom: na
ms.prod: windows-server
ms.reviewer: na
ms.suite: na
ms.date: 04/03/2017
ms.technology: server-general
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0f78ef4c-dd12-4b1b-8c6e-251dd803c5d1
author: jaimeo
ms.author: jaimeo
manager: dougkim
ms.localizationpriority: medium
ms.openlocfilehash: 486c11ebd46c6fd23b3bd16cd90463f8d607287e
ms.sourcegitcommit: 3743cf691a984e1d140a04d50924a3a0a19c3e5c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2019
ms.locfileid: "66443545"
---
# <a name="migrating-roles-and-features-in-windows-server"></a>Migrieren von Rollen und Features in Windows Server

>Gilt für: Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Diese Seite enthält Links zu hilfreichen Informationen und Tools für die Migration von Rollen und Features zu Windows Server 2016, Windows Server 2012 R2 und Windows Server 2012. Viele Rollen und Features können mit den Windows Server-Migrationstools migriert werden. Hierbei handelt es sich um eine Gruppe von fünf Windows PowerShell-Cmdlets, die in Windows Server 2008 R2 zum einfachen Migrieren von Rollen- und Featureelementen und Daten eingeführt wurde.

Die Migrationshandbücher unterstützen Migrationen von angegebenen Rollen und Features zwischen Servern (keine direkten Upgrades). Sofern in den Anleitungen nicht anders angegeben, werden Migrationen zwischen physischen und virtuellen Computern sowie zwischen vollständigen Windows Server-Installationen und Servern mit Server Core-Installation unterstützt.  

## <a name="before-you-begin"></a>Vorbemerkungen

Vergewissere dich vor Beginn der Migration von Rollen und Features, dass Quell- und Zielserver über die neuesten Service Packs verfügen, die für das jeweilige Betriebssystem verfügbar sind.
Es ist jetzt auch ein E-Book mit den Windows Server 2012 R2- und Windows Server 2012-Migrationshandbüchern verfügbar. Weitere Informationen findest du im [Katalog mit den E-Books für Technologie von Microsoft](https://social.technet.microsoft.com/wiki/contents/articles/11608.e-book-gallery-for-microsoft-technologies.aspx#MigrateRoles). Hier kannst du auch das E-Book herunterladen. 

>[!NOTE]
>Bei jeder Migration und jedem Upgrade auf eine Version von Windows Server solltest du dich mit der [Microsoft Lifecycle-Richtlinie für den Support](https://support.microsoft.com/lifecycle) und dem Zeitrahmen für die jeweilige Version vertraut machen und entsprechend planen. Du kannst [nach den Lebenszyklusinformationen für die jeweils gewünschte Windows Server-Version suchen](https://support.microsoft.com/lifecycle).
 
## <a name="windows-server-2016"></a>Windows Server 2016

### <a name="migration-guides"></a>Migrationshandbücher
Derzeit werden aktualisierte Migrationshandbücher für Windows Server 2016 entwickelt. Wenn sie verfügbar sind, werden die Informationen in diesem Artikel entsprechend aktualisiert. In vielen Fällen sind die Schritte in den Windows Server 2012 R2-Migrationshandbüchern auch für Windows Server 2016 noch relevant.

- [Remotedesktopdienste](https://technet.microsoft.com/windows-server-docs/compute/remote-desktop-services/migrate-rds-role-services)
- [Webserver (IIS)](https://www.iis.net/downloads/microsoft/web-deploy)
- [Windows Server Update Services](https://technet.microsoft.com/library/hh852339.aspx)
- [MultiPoint Services](https://technet.microsoft.com/windows-server-docs/compute/remote-desktop-services/multipoint-services/multipoint-services-migrate)
 
## <a name="windows-server-2012-r2"></a>Windows Server 2012 R2

### <a name="migration-guides"></a>Migrationshandbücher
Führe die Schritte in diesen Handbüchern aus, um Rollen und Features von Servern unter Windows Server 2003, Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 oder Windows Server 2012 R2 zu Windows Server 2012 R2 zu migrieren. Windows Server-Migrationstools in Windows Server 2012 R2 unterstützen subnetzübergreifende Migrationen.

- [Install, Use, and Remove Windows Server Migration Tools](https://technet.microsoft.com/library/jj134202.aspx) (Installieren, Verwenden und Entfernen von Windows Server-Migrationstools)
- [Active Directory Certificate Services Migration Guide for Windows Server 2012 R2](https://technet.microsoft.com/library/dn486797.aspx) (Handbuch für die Migration von Active Directory-Zertifikatdiensten für Windows Server 2012 R2)
- [Migrating Active Directory Federation Services Role Service to Windows Server 2012 R2](https://technet.microsoft.com/library/dn486815.aspx) (Migrieren des Rollendiensts der Active Directory-Verbunddienste (AD FS) zu Windows Server 2012 R2)
- [Active Directory Rights Management Services Migration and Upgrade Guide](https://technet.microsoft.com/library/cc754277.aspx) (Active Directory Rights Management Services – Migrations- und Upgradehandbuch)
- [Migrate File and Storage Services to Windows Server 2012 R2](https://technet.microsoft.com/library/dn479292.aspx) (Migrieren von Datei- und Speicherdiensten zu Windows Server 2012 R2)
- [Migration von Hyper-V zu Windows Server 2012 R2 von Windows Server 2012](https://technet.microsoft.com/library/dn486799.aspx)
- [Migrate Network Policy Server to Windows Server 2012](https://technet.microsoft.com/library/hh831652) (Migrieren des Netzwerkrichtlinienservers zu Windows Server 2012)
- [Migrate Remote Desktop Services to Windows Server 2012 R2](https://technet.microsoft.com/library/dn479239.aspx) (Migrieren der Remotedesktopdienste zu Windows Server 2012 R2)
- [Migrate Windows Server Update Services to Windows Server 2012 R2](https://technet.microsoft.com/library/hh852339.aspx) (Migrieren von Windows Server Update Services zu Windows Server 2012 R2)
- [Migrate Cluster Roles to Windows Server 2012 R2](https://technet.microsoft.com/library/dn530779.aspx) (Migrieren von Clusterrollen zu Windows Server 2012 R2)
- [Migrate DHCP Server to Windows Server 2012 R2](https://technet.microsoft.com/library/dn495425.aspx) (Migrieren eines DHCP-Servers zu Windows Server 2012 R2)
 
## <a name="windows-server-2012"></a>Windows Server 2012

### <a name="migration-guides"></a>Migrationshandbücher
Führe die Schritte in diesen Handbüchern aus, um Rollen und Features von Servern unter Windows Server 2003, Windows Server 2008, Windows Server 2008 R2 oder Windows Server 2012 zu Windows Server 2012 zu migrieren. Die Windows Server-Migrationstools in Windows Server 2012 unterstützen subnetzübergreifende Migrationen.

- [Install, Use, and Remove Windows Server Migration Tools](https://technet.microsoft.com/library/jj134202) (Installieren, Verwenden und Entfernen von Windows Server-Migrationstools)
- [Migrieren von Rollendiensten der Active Directory-Verbunddienste (AD FS) zu Windows Server 2012](https://technet.microsoft.com/library/jj647765)
- [Migrate Health Registration Authority to Windows Server 2012](https://technet.microsoft.com/library/hh831513) (Migrieren der Integritätsregistrierungsstelle zu Windows Server 2012)
- [Migrate Hyper-V to Windows Server 2012 from Windows Server 2008 R2](https://technet.microsoft.com/library/jj574113) (Migrieren von Hyper-V zu Windows Server 2012 von Windows Server 2008 R2)
- [Migrate IP Configuration to Windows Server 2012](https://technet.microsoft.com/library/jj574133) (Migrieren der IP-Konfiguration zu Windows Server 2012)
- [Migrate Network Policy Server to Windows Server 2012](https://technet.microsoft.com/library/hh831652) (Migrieren des Netzwerkrichtlinienservers zu Windows Server 2012)
- [Migrate Print and Document Services to Windows Server 2012](https://technet.microsoft.com/library/jj134150) (Migrieren von Druck- und Dokumentdiensten zu Windows Server 2012)
- [Migrate Remote Access to Windows Server 2012](https://technet.microsoft.com/library/hh831423) (Migrieren des Remotezugriffs zu Windows Server 2012)
- [Migrate Windows Server Update Services to Windows Server 2012](https://technet.microsoft.com/library/hh852339) (Migrieren von Windows Server Update Services zu Windows Server 2012)
- [Upgrade Active Directory Domain Controllers to Windows Server 2012](https://technet.microsoft.com/library/hh994618.aspx) (Upgraden von Active Directory-Domänencontrollern auf Windows Server 2012)
- [Migrating Clustered Services and Applications to Windows Server 2012](https://technet.microsoft.com/library/dn486790.aspx) (Migrieren von Clusterdiensten und -anwendungen zu Windows Server 2012)
 

Weitere Ressourcen zur Migration findest du unter [Migrate Roles and Features to Windows Server 2012](https://technet.microsoft.com/library/jj134039) (Migrieren von Rollen und Features zu Windows Server 2012).

## <a name="windows-server-2008-r2"></a>Windows Server 2008 R2

### <a name="migration-guides"></a>Migrationshandbücher
Führe die Schritte in diesen Handbüchern aus, um Rollen und Features von Servern unter Windows Server 2003, Windows Server 2008 oder Windows Server 2008 R2 zu Windows Server 2008 R2 zu migrieren. Die Windows Server-Migrationstools in Windows Server 2008 R2 unterstützen keine subnetzübergreifenden Migrationen.

- [Windows Server Migration Tools Installation, Access, and Removal](https://technet.microsoft.com/library/dd379545) (Windows Server-Migrationstools: Installation, Zugriff und Entfernung)
- [Active Directory Certificate Services Migration Guide](https://technet.microsoft.com/library/ee126170) (Migrationshandbuch für die Active Directory-Zertifikatdienste)
- [Active Directory Domain Services and Domain Name System (DNS) Server Migration Guide](https://technet.microsoft.com/library/dd379558) (Handbuch für die Migration von Servern mit Active Directory Domain Services und Domain Name System (DNS))
- [BranchCache Migration Guide](https://technet.microsoft.com/library/dd548365) (BranchCache-Migrationsanleitung)
- [Dynamic Host Configuration Protocol (DHCP) Server Migration Guide](https://technet.microsoft.com/library/dd379535) (Handbuch für die Migration von DHCP-Servern (Dynamic Host Configuration Protocol))
- [File Services Migration Guide](https://technet.microsoft.com/library/dd379487) (Handbuch für die Migration von Dateidiensten)
- [HRA Migration Guide](https://technet.microsoft.com/library/ee791829) (HRA-Migrationshandbuch)
- [Hyper-V Migration Guide](https://technet.microsoft.com/library/ee849855) (Hyper-V-Migrationshandbuch)
- [IP Configuration Migration Guide](https://technet.microsoft.com/library/dd379537) (Handbuch für die Migration der IP-Konfiguration)
- [Local User and Group Migration Guide](https://technet.microsoft.com/library/dd379531) (Handbuch für die Migration lokaler Benutzer und Gruppen)
- [NPS Migration Guide](https://technet.microsoft.com/library/ee791849) (NPS-Migrationshandbuch)
- [Print Services Migration Guide](https://technet.microsoft.com/library/dd379488) (Handbuch für die Migration von Druckdiensten)
- [Remote Desktop Services Migration Guide](https://technet.microsoft.com/library/ff849223) (Handbuch zur Migration von Remotedesktopdiensten)
- [RRAS Migration Guide](https://technet.microsoft.com/library/ee822825) (RRAS-Migrationshandbuch)
- [Windows Server Migration Common Tasks and Information](https://technet.microsoft.com/library/ff400258) (Windows Server-Migration: allgemeine Aufgaben und Informationen)
- [Windows Server Update Services 3.0 SP2 Migration Guide](https://technet.microsoft.com/library/ee822826) (Migrationshandbuch für Windows Server Update Services 3.0 SP2)
 
Weitere Ressourcen zur Migration findest du unter [Migrate Server Roles to Windows Server 2008 R2](https://technet.microsoft.com/library/dd365353) (Migrieren von Serverrollen zu Windows Server 2008 R2).
