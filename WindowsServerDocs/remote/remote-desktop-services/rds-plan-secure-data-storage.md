---
title: 'Remotedesktopdienste: Schützen von Datenspeicher'
description: Planungsinformationen für das sichere Speichern von Daten mithilfe von Benutzerprofil-Datenträgern (User Profile Disks, UPDs) in RDS
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: remote-desktop-services
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 37b7f68e-7c3a-4190-a52f-99ae96885fae
author: lizap
ms.author: elizapo
ms.date: 11/21/2016
manager: dongill
ms.openlocfilehash: c3c7be624e3b093347807a5ee131270d3c802f1a
ms.sourcegitcommit: 3743cf691a984e1d140a04d50924a3a0a19c3e5c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2019
ms.locfileid: "66805160"
---
# <a name="remote-desktop-services---secure-data-storage-with-upds"></a>Remotedesktopdienste: Schützen von Datenspeicher mit Benutzerprofil-Datenträgern

>Gilt für: Windows Server (halbjährlicher Kanal), Windows Server 2019, Windows Server 2016

Speichere Unternehmensressourcen, benutzerspezifische Personalisierungsdaten und Einstellungen sicher lokal oder in Azure. RD-Sitzungshosts nutzen AD-Authentifizierung und stellen Benutzern auf sichere Weise die Ressourcen zur Verfügung, die sie in einer personalisierten Umgebung benötigen. 

Ein wichtiger Aspekt beim Verwalten einer RDS-Bereitstellung besteht darin, Benutzern eine konsistente Umgebung bereitzustellen, unabhängig vom Endpunkt, über den sie auf ihre Remoteressourcen zugreifen. Dank Benutzerprofil-Datenträgern (User Profile Disks, UPDs) stehen Benutzerdaten, Anpassungen und Anwendungseinstellungen einem Benutzer innerhalb einer einzelnen Sammlung überall zur Verfügung. Bei einem Benutzerprofil-Datenträger handelt es sich um eine benutzer- und sammlungsspezifische VHD-Datei in einer zentralen Freigabe, die bei der Anmeldung eines Benutzers in seine Sitzung eingebunden wird. Der Benutzerprofil-Datenträger wird während der Sitzungsdauer als lokales Laufwerk behandelt. 

Aus Sicht des Benutzers bietet der Benutzerprofil-Datenträger eine vertraute Umgebung: Er speichert seine Dokumente im Ordner „Dokumente“ (auf dem vermeintlich lokalen Laufwerk), ändert seine App-Einstellungen wie gewohnt und nimmt Anpassungen an seiner Windows-Umgebung vor. Alle diese Daten, einschließlich der Registrierungsstruktur, werden auf dem Benutzerprofil-Datenträger gespeichert und endgültig in einer zentralen Netzwerkfreigabe gespeichert. Benutzerprofil-Datenträger sind nur für den Benutzer verfügbar, wenn er aktiv mit einem Desktop oder mit RemoteApp verbunden ist. Roaming ist für Benutzerprofil-Datenträger nur innerhalb einer Sammlung möglich, da das gesamte Verzeichnis `C:\Users\<username\>` des Benutzers (einschließlich „AppData\Local“) auf dem Benutzerprofil-Datenträger gespeichert ist.

Du kannst [PowerShell-Cmdlets](https://technet.microsoft.com/library/jj215443.aspx) verwenden, um den Pfad zur zentralen Freigabe, die Größe der einzelnen Benutzerprofil-Datenträger sowie die Ordner festzulegen, die in das auf dem Benutzerprofil-Datenträger gespeicherte Profil aufgenommen bzw. davon ausgeschlossen werden sollen. Alternativ kannst du Benutzerprofil-Datenträger über den Server-Manager aktivieren. Navigiere dazu zu **Remotedesktopdienste** > **Sammlungen** > **Desktopsammlung** > **Desktop Collection Properties (Desktopsammlungseigenschaften)**  > **Benutzerprofil-Datenträger**. Beachte, dass Benutzerprofil-Datenträger für alle Benutzer einer gesamten Sammlung und nicht nur für bestimmte Benutzer in dieser Sammlung aktiviert bzw. deaktiviert werden. Benutzerprofil-Datenträger müssen in einer zentralen Dateifreigabe gespeichert werden, für die die Server in der Sammlung über Vollzugriff verfügen. 

Du kannst Hochverfügbarkeit für deine Benutzerprofil-Datenträger erzielen, indem du sie mit [direkten Speicherplätzen](rds-storage-spaces-direct-deployment.md) in Azure speicherst. 