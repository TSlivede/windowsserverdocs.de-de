---
title: Konfigurieren von Speicherberichten
description: In diesem Artikel wird beschrieben, wie Sie die Standardparameter für Speicherberichte konfigurieren
ms.date: 7/7/2017
ms.prod: windows-server-threshold
ms.technology: storage
ms.topic: article
author: JasonGerend
manager: brianlic
ms.author: jgerend
ms.openlocfilehash: f62109a8d3ea3e4e6386956789d276f9aa911e80
ms.sourcegitcommit: 0d0b32c8986ba7db9536e0b8648d4ddf9b03e452
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2019
ms.locfileid: "59885231"
---
# <a name="configure-storage-reports"></a>Konfigurieren von Speicherberichten

> Gilt für: WindowsServer (Halbjährlicher Kanal), WindowsServer 2016, Windows Server 2012 R2, WindowsServer 2012, Windows Server 2008 R2

Sie können die Standardparametern für Speicherberichte konfigurieren. Diese Standardparameter werden für Schadensberichte verwendet, die generiert werden, wenn ein Kontingent- oder Dateiprüfungsereignis auftritt. Sie werden auch für geplante und bedarfsgesteuerte Berichte verwendet und Sie können die Standardparametern außerkraftsetzen, wenn Sie die spezifischen Eigenschaften dieser Berichte festlegen.

> [!Important]
> Wenn Sie die Standardparametern für einen Bericht ändern, wirkt sich dies auf alle Schadensberichte und alle vorhandenen geplanten Berichtsaufgaben aus, die die Standardwerte verwenden.

## <a name="to-configure-the-default-parameters-for-storage-reports"></a>Sie können Sie die Standardparametern für Speicherberichte konfigurieren

1. Klicken Sie mit der rechten Maustaste in der Konsolenstruktur auf **Ressourcen-Manager für Dateiserver**, und klicken Sie dann auf **Optionen konfigurieren**. Das Dialogfeld **Optionen für den Ressourcen-Manager für Dateiserver** wird geöffnet.

2. Wählen Sie auf der Registerkarte **Speicherberichte** unter **Konfigurieren von Standardparametern** den Typ des Berichts aus, den Sie ändern möchten.

3. Klicken Sie auf **Parameter bearbeiten**.

4. Je nach Art des Berichts, den Sie auswählen, stehen Ihnen unterschiedliche Berichtsparameter für die Bearbeitung zur Verfügung. Führen Sie alle notwendigen Änderungen durch, und klicken Sie dann auf **OK**, um den Standardparametern für diese Art Bericht zu speichern.

5.  Wiederholen Sie die Schritte 2 bis 4 für jede Art von Bericht, der geändert werden soll.

6. Um eine Liste mit den Standardparametern für alle Berichte anzuzeigen, klicken Sie auf **Berichte überprüfen**. Klicken Sie anschließend auf **Schließen**.

7.  Klicken Sie auf **OK**.

## <a name="see-also"></a>Siehe auch

-   [Einstellung File Server Resource Manager-Optionen](setting-file-server-resource-manager-options.md)
-   [Speicherverwaltung für Berichte](storage-reports-management.md)