---
title: Ändern des Zeitraums für die Zwischenspeicherung von Verweisen auf Clients
description: Dieser Artikel beschreibt, wie Sie die Dauer der Zwischenspeicherung von Verweisen auf Clients
ms.date: 6/5/2017
ms.prod: windows-server-threshold
ms.technology: storage
ms.topic: article
author: JasonGerend
manager: brianlic
ms.author: jgerend
ms.openlocfilehash: 08a1212c983de6e2492609330c1be222286e9e8f
ms.sourcegitcommit: 0d0b32c8986ba7db9536e0b8648d4ddf9b03e452
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2019
ms.locfileid: "59888771"
---
# <a name="change-the-amount-of-time-that-clients-cache-referrals"></a>Ändern Sie den Zeitraum für die Zwischenspeicherung von Verweisen auf Clients

> Gilt für: WindowsServer 2019, WindowsServer (Halbjährlicher Kanal), WindowsServer 2016, Windows Server 2012 R2, WindowsServer 2012, Windows Server 2008 R2, WindowsServer 2008

Ein Verweis ist eine sortierte Zielliste, die ein Client-PC von einem Domänencontroller oder Namespaceserver empfängt, wenn der Benutzer auf einen Namespacestamm oder -ordner mit Zielen im Namespace zugreift. Sie können den Zwischenspeicherungszeitraum bis zur Anforderung eines neuen Verweises durch die Clients anpassen.

## <a name="to-change-the-amount-of-time-that-clients-cache-namespace-root-referrals"></a>So ändern Sie die Dauer der Zwischenspeicherung von Namespacestammverweisen auf Clients

1.  Klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **DFS-Verwaltung**.

2.  Klicken Sie in der Konsolenstruktur unter dem Knoten **Namespaces** mit der rechten Maustaste auf einen Namespace, und klicken Sie anschließend auf **Eigenschaften**.

3.  Geben Sie auf der Registerkarte **Verweise** im Textfeld **Cachedauer (in Sekunden)** den Zeitraum (in Sekunden) ein, für den Namespacestammverweise von Clients zwischengespeichert werden sollen. Die Standardeinstellung beträgt 300 Sekunden (fünf Minuten).

> [!TIP]
> Um die Dauer der Zwischenspeicherung von Namespacestammverweisen auf Clients mithilfe von Windows PowerShell zu ändern, verwenden Sie das Cmdlet [Set-DfsnRoot TimeToLiveSec](https://technet.microsoft.com/library/jj884281.aspx). Diese Cmdlets wurden in Windows Server 2012 eingeführt.

## <a name="to-change-the-amount-of-time-that-clients-cache-folder-referrals"></a>So ändern Sie den Zeitraum für die Zwischenspeicherung von Ordnerverweisen auf Clients

1.  Klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **DFS-Verwaltung**.

2.  Klicken Sie in der Konsolenstruktur unter dem Knoten **Namespaces** mit der rechten Maustaste auf einen Ordner mit Zielen, und klicken Sie anschließend auf **Eigenschaften**.

3.  Geben Sie auf der Registerkarte **Verweise** im Textfeld **Cachedauer (in Sekunden)** den Zeitraum (in Sekunden) ein, für den Ordnerverweise von Clients zwischengespeichert werden sollen. Die Standardeinstellung beträgt 1800 Sekunden (30 Minuten).

## <a name="see-also"></a>Siehe auch

-   [Optimieren von DFS-Namespaces](tuning-dfs-namespaces.md)
-   [Delegieren von Verwaltungsberechtigungen für DFS-Namespaces](delegate-management-permissions-for-dfs-namespaces.md)


