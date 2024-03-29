---
ms.assetid: 3ea48a72-20a2-4da4-84e4-26b5728513ce
title: Planen der Dateizugriffsüberwachung
description: ''
author: billmath
ms.author: billmath
manager: femila
ms.date: 05/31/2017
ms.topic: article
ms.prod: windows-server-threshold
ms.technology: identity-adds
ms.openlocfilehash: 65e941f6741298da54186be10bd9c0add115ea14
ms.sourcegitcommit: 0d0b32c8986ba7db9536e0b8648d4ddf9b03e452
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2019
ms.locfileid: "59820901"
---
# <a name="plan-for-file-access-auditing"></a>Planen der Dateizugriffsüberwachung

>Gilt für: Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Die Informationen in diesem Thema wird erläutert, die Sicherheit, Überwachung Verbesserungen, die in Windows Server 2012 und neue eingeführt werden Einstellungen, die Sie berücksichtigen sollten überwachen, wie Sie die dynamische Zugriffssteuerung in Ihrem Unternehmen bereitstellen. Welche Überprüfungsrichtlinieneinstellungen Sie letztlich bereitstellen, hängt von Ihren Zielen ab. Dazu können die Überprüfung der Einhaltung rechtlicher Bestimmungen, die Überwachung, die forensische Analyse und die Problembehandlung gehören.  
  
> [!NOTE]  
> Weitere Informationen zum Planen und Bereitstellen einer übergreifenden Sicherheitsüberprüfungsstrategie für Ihr Unternehmen erhalten Sie unter [Planen und Bereitstellen von erweiterten Sicherheitsüberwachungsrichtlinien](https://go.microsoft.com/fwlink/?LinkID=191139). Weitere Informationen zum Konfigurieren und Bereitstellen einer Sicherheitsüberwachungsrichtlinie finden Sie unter [Schrittweise Anleitung für die erweiterte Sicherheitsüberwachungsrichtlinie](https://go.microsoft.com/fwlink/?LinkID=191141).  
  
Die folgenden Überwachung Sicherheitsfunktionen in Windows Server 2012 können mit der dynamischen Zugriffssteuerung verwendet werden, erweitern Sie Ihre Überwachung Gesamtsicherheitsstrategie.  
  
-   **Ausdrucksbasierte Überwachungsrichtlinien** Mit der dynamischen Zugriffssteuerung können Sie gezielte Überprüfungsrichtlinien mithilfe von Ausdrücken erstellen, die auf Benutzer-, Computer- und Ressourcenansprüchen basieren. Sie können beispielsweise eine Überwachungsrichtlinie erstellen, um alle Lese- und Schreibvorgänge für Dateien zu überwachen, die von Mitarbeitern ohne Hochsicherheitsberechtigung als besonders wichtig für das Geschäft klassifiziert wurden. Ausdrucksbasierte Überwachungsrichtlinien können direkt für eine Datei oder einen Ordner oder zentral durch eine Gruppenrichtlinie erstellt werden. Weitere Informationen finden Sie im Thema zu [Gruppenrichtlinien mit globaler Objektzugriffsüberwachung](https://go.microsoft.com/fwlink/?LinkId=241498).  
  
-   **Zusätzliche Informationen aus der Objektzugriffsüberwachung**. Dateizugriffsüberwachung ist nicht neu für Windows Server 2012. Mit der entsprechenden Überwachungsrichtlinie generieren die Windows- und Windows Server-Betriebssysteme jedes Mal, wenn ein Benutzer auf eine Datei zugreift, ein Überwachungsereignis. Vorhandene Dateizugriffsereignisse (4656, 4663) enthaltenen Informationen zu den Attributen der Datei, auf die zugegriffen wurde. Diese Informationen können von Tools für die Ereignisprotokollfilterung verwendet werden, um Ihnen bei der Identifizierung der wichtigsten Überwachungsereignisse zu helfen. Weitere Informationen finden Sie im Thema zur [Handleänderungsüberwachung](https://technet.microsoft.com//library/dd772626(WS.10).aspx) und zum [Sicherheitskonten-Manager für die Überwachung](https://go.microsoft.com/fwlink/?LinkId=241501).  
  
-   **Weitere Informationen aus Benutzeranmeldeereignissen**. Mit der entsprechenden Überwachungsrichtlinie generieren die Windows-Betriebssysteme jedes Mal, wenn sich ein Benutzer lokal oder remote an einem Computer anmeldet, ein Überwachungsereignis. In Windows Server 2012 oder Windows 8 können Sie auch Benutzer- und geräteansprüchen, die Sicherheitstoken eines Benutzers zugeordnet überwachen. Dazu gehören beispielsweise %%amp;quot;Abteilung%%amp;quot;, %%amp;quot;Unternehmen%%amp;quot;, %%amp;quot;Projekt%%amp;quot; und Sicherheitsfreigaben. Ereignis 4626 enthält Informationen zu diesen Benutzer- und Geräteansprüchen, die von Tools für die Überwachungsprotokollverwaltung genutzt werden, um Benutzeranmeldeereignisse mit Objektzugriffsereignissen in Verbindung zu bringen, um die Ereignisfilterung basierend auf Dateiattributen und Benutzerattributen zu ermöglichen. Weitere Informationen zur Benutzeranmeldeüberwachung finden Sie im Thema zur [Überwachung der Anmeldung](https://go.microsoft.com/fwlink/?LinkId=241502).  
  
-   **Änderungsnachverfolgung für neue Typen von sicherungsfähigen Objekten**. Das Nachverfolgen von Änderungen an sicherungsfähigen Objekten kann in den folgenden Szenarios wichtig sein:  
  
    -   **Änderungsnachverfolgung für zentrale Zugriffsrichtlinien und zentrale Zugriffsregeln**. Zentrale Zugriffsrichtlinien und zentrale Zugriffsregeln definieren die zentrale Richtlinie, die zum Steuern des Zugriffs auf kritische Ressourcen verwendet werden kann. Alle Änderungen an diesen Richtlinien können sich direkt auf die Dateizugriffsberechtigungen auswirken, die Benutzern auf mehreren Computern gewährt werden. Daher kann das Nachverfolgen von Änderungen an zentralen Zugriffsrichtlinien und zentralen Zugriffsregeln wichtig für Ihre Organisation sein. Da zentrale Zugriffsrichtlinien und zentrale Zugriffsregeln in Active Directory-Domänendienste (AD DS) gespeichert werden, können Sie Änderungsversuche überwachen, wie Sie auch Änderungen an anderen sicherungsfähigen Objekten in AD DS überwachen. Weitere Informationen finden Sie im Thema zum [Überwachen des Zugriffs auf Verzeichnisdienste](https://technet.microsoft.com/library/dd941618(WS.10).aspx).  
  
    -   **Änderungsnachverfolgung für Definitionen im Anspruchswörterbuch**. Anspruchsdefinitionen umfassen den Anspruchsnamen, die Beschreibung und mögliche Werte. Alle Änderungen an der Anspruchsdefinition können sich auf die Zugriffsberechtigungen für kritische Ressourcen auswirken. Daher kann das Nachverfolgen von Änderungen an Anspruchsdefinitionen wichtig für Ihre Organisation sein. Wie zentrale Zugriffsrichtlinien und zentrale Zugriffsregeln werden auch Anspruchsdefinitionen in AD DS gespeichert. Daher können sie wie alle anderen sicherungsfähigen Objekte in AD DS überwacht werden. Weitere Informationen finden Sie im Thema zum [Überwachen des Zugriffs auf Verzeichnisdienste](https://technet.microsoft.com/library/dd941618(WS.10).aspx).  
  
    -   **Änderungsnachverfolgung für Dateiattribute**. Dateiattribute bestimmen, welche zentrale Zugriffsregel für die Datei gilt. Eine Änderung an den Dateiattributen kann sich potenziell auf die Zugriffsbeschränkungen der Datei auswirken. Daher kann es wichtig sein, Änderungen an Dateiattributen nachzuverfolgen. Sie können Änderungen an Dateiattributen auf jedem beliebigen Computer durch Konfigurieren der Überwachung der Autorisierungsrichtlinienänderung nachverfolgen. Weitere Informationen finden Sie im Thema zum [Überwachen der Autorisierungsrichtlinienänderung](https://go.microsoft.com/fwlink/?LinkId=241504) und zur [Objektzugriffsüberwachung für Dateisysteme](https://go.microsoft.com/fwlink/?LinkId=241505). In Windows Server 2012 unterscheidet Ereignis 4911 Dateiattributs-richtlinienänderungen von anderen Autorisierungsrichtlinien-Änderungsereignissen.  
  
    -   **Änderungsnachverfolgung für die einer Datei zugeordnete zentrale Zugriffsrichtlinie**. . Ereignis 4913 zeigt die Sicherheits-IDs (SIDs) der alten und neuen zentralen Zugriffsrichtlinien an. Jede zentrale Zugriffsrichtlinie verfügt außerdem über einen Anzeigenamen, der mithilfe dieser Sicherheits-ID gesucht werden kann. Weitere Informationen finden Sie im Thema zum [Überwachen der Autorisierungsrichtlinienänderung](https://go.microsoft.com/fwlink/?LinkId=241504).  
  
    -   **Änderungsnachverfolgung für Benutzer- und Computerattribute**. Wie Dateien Benutzer- und Computerobjekte Attribute aufweisen, und Änderungen an diesen Attributen können der Benutzer den Zugriff auf Dateien auswirken. Daher kann es sinnvoll sein, Änderungen an Benutzer- oder Computerattributen nachzuverfolgen. Benutzer- und Computerobjekte werden in AD DS gespeichert. Daher können Änderungen an ihren Attributen überwacht werden. Weitere Informationen finden Sie im Thema zum [DS-Zugriff](https://go.microsoft.com/fwlink/?LinkId=241508).  
  
-   **Richtlinienänderungsbereitstellung**. Änderungen an zentralen Zugriffsrichtlinien können sich auf die Zugriffssteuerungsentscheidungen auf allen Computern, auf denen die Richtlinien durchgesetzt werden, auswirken. Eine unzureichende Richtlinie könnte mehr Zugriff als gewünscht gewähren, und eine zu restriktive Richtlinie könnte eine große Anzahl an Helpdeskanrufen generieren. Es kann also äußerst sinnvoll sein, Änderungen an einer zentralen Zugriffsrichtlinie zu überprüfen, bevor die Änderung erzwungen wird. Zu diesem Zweck Konzept Windows Server 2012 das der "Staging". Mit der Bereitstellung können Benutzer vorgeschlagene Richtlinienänderungen überprüfen, bevor sie erzwungen werden. Zum Verwenden der Richtlinienbereitstellung werden vorgeschlagene Richtlinien mit den erzwungenen Richtlinien bereitgestellt. Bereitgestellte Richtlinien gewähren oder verweigern aber keine Berechtigungen. Windows Server 2012 protokolliert stattdessen, ein Überwachungsereignis (4818) jedes Mal, wenn das Ergebnis der zugriffsüberprüfung, die die bereitgestellte Richtlinie verwendet aus dem Ergebnis einer zugriffsüberprüfung unterscheidet, die die erzwungene Richtlinie verwendet.  
  


