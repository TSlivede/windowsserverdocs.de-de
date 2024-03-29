---
title: Migrieren eines domänenbasierten Namespace zum Windows Server 2008-Modus
description: Dieser Artikel beschreibt die Vorgehensweise beim Migrieren eines domänenbasierten Namespaces zum Windows Server 2008-Modus
ms.date: 6/5/2017
ms.prod: windows-server-threshold
ms.technology: storage
ms.topic: article
author: JasonGerend
manager: brianlic
ms.author: jgerend
ms.openlocfilehash: e2624e53d306dd198525b0abe8adf96fe6060bc1
ms.sourcegitcommit: 0d0b32c8986ba7db9536e0b8648d4ddf9b03e452
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2019
ms.locfileid: "59847861"
---
# <a name="migrate-a-domain-based-namespace-to-windows-server-2008-mode"></a>Migrieren Sie einen domänenbasierten Namespace zum Windows Server 2008-Modus

> Gilt für: WindowsServer 2019, WindowsServer (Halbjährlicher Kanal), WindowsServer 2016, Windows Server 2012 R2, WindowsServer 2012, Windows Server 2008 R2, WindowsServer 2008

Der Windows Server 2008-Modus für domänenbasierte Namespaces unterstützt Support für die zugriffsbasierte Aufzählung und eine bessere Skalierbarkeit.

## <a name="to-migrate-a-domain-based-namespace-to-windows-server-2008-mode"></a>So migrieren Sie einen domänenbasierten Namespace zum Windows Server 2008-Modus

Um einen domänenbasierten Namespace vom Windows 2000 Server-Modus zum Windows Server 2008-Modus zu migrieren, müssen Sie den Namespace in eine Datei exportieren, den Namespace löschen und ihn neu im Windows Server 2008-Modus erstellen und anschließend in die Namespaceeinstellungen importieren. Führen Sie dazu die nachfolgend aufgeführten Schritte aus:

1.  Öffnen Sie ein Eingabeaufforderungsfenster, und geben Sie den folgenden Befehl aus, um den Namespace in eine Datei exportieren, in denen \\ \\ *Domäne*\\*Namespace* ist der Name des der entsprechenden Domäne, und des Namespace und *Pfad\\Filename* ist der Pfad und Dateiname der Datei für den Export:
     ```
     Dfsutil root export \\domain\namespace path\filename.xml 
     ```
2.  Notieren Sie sich den Pfad ( \\ \\ *Server* \\ *freigeben* ) für jeden Namespaceserver. Sie müssen Namespaceserver manuell auf den neu erstellten Namespace hinzufügen, da „Dfsutil” keine Namespaceserver importieren kann.
3.  Klicken Sie mit der rechten Maustaste unter DFS-Verwaltung auf die Namespaces, und klicken Sie dann auf **Löschen**, oder geben Sie den folgenden Befehl in eine Eingabeaufforderung ein, <br /> wo \\ \\ *Domäne*\\*Namespace* ist der Name der entsprechenden Domäne und des Namespace:
     ```
     Dfsutil root remove \\domain\namespace
     ```
4.  Erstellen Sie in der DFS-Verwaltung erneut den Namespace mit dem gleichen Namen, verwenden Sie allerdings den Windows Server 2008-Modus, oder geben Sie den folgenden Befehl in eine Eingabeaufforderung ein, wobei <br /> \\\\*Server*\\*Namespace* ist der Name des entsprechenden Servers und der Freigabe für den Namespacestamm:
     ```
     Dfsutil root adddom \\server\namespace v2
     ```
5.  Um den Namespace aus der Exportdatei zu importieren, geben Sie den folgenden Befehl in eine Eingabeaufforderung ein, wobei <br /> \\\\*Domäne*\\*Namespace* ist der Name der entsprechenden Domäne und des Namespace und *Pfad\\Filename* ist der Pfad und Dateiname der die zu importierende Datei:
     ```
     Dfsutil root import merge path\filename.xml \\domain\namespace
     ```

    > [!NOTE]
    > Um die erforderliche Zeit während des Imports eines großen Namespaces zu minimieren, führen Sie den Stamm-Importbefehl **Dfsutil** lokal auf einem Namespaceserver aus.
6.  Fügen Sie alle verbleibenden Namespaceserver auf den neu erstellten Namespace hinzu, indem Sie mit der rechten Maustaste auf den Namespace in der DFS-Verwaltung klicken und dann auf **Namespace-Server hinzufügen**, oder geben Sie den folgenden Befehl in eine Eingabeaufforderung ein, wobei <br /> \\\\*Server*\\*freigeben* ist der Name des entsprechenden Servers und der Freigabe für den Namespacestamm:
     ```
     Dfsutil target add \\server\share 
     ```

    > [!NOTE]
    > Sie können Namespaceserver vor dem Importieren des Namespaces hinzufügen, dies führt allerdings dazu, dass die Namespaceserver die Metadaten für den Namespace inkrementell herunterladen anstatt den gesamten Namespace sofort nach dem Hinzufügen als Namespaceserver herunterzuladen.

## <a name="see-also"></a>Siehe auch
-   [Bereitstellen von DFS-Namespaces](deploying-dfs-namespaces.md)
-   [Wählen Sie einen Namespace-Typ](choose-a-namespace-type.md)