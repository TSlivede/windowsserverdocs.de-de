---
title: Erstellen einer benutzerdefinierten Dateiverwaltungsaufgabe
description: Dieser Artikel beschreibt, wie Sie eine benutzerdefinierte Dateiverwaltungsaufgabe und benutzerdefinierten Aufgaben erstellen.
ms.date: 7/7/2017
ms.prod: windows-server-threshold
ms.technology: storage
ms.topic: article
author: JasonGerend
manager: brianlic
ms.author: jgerend
ms.openlocfilehash: dd52a94657fb73d28b3bc1552a058b7f3ca954ff
ms.sourcegitcommit: 0d0b32c8986ba7db9536e0b8648d4ddf9b03e452
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2019
ms.locfileid: "59867261"
---
# <a name="create-a-custom-file-management-task"></a>Erstellen einer benutzerdefinierten Dateiverwaltungsaufgabe

> Gilt für: WindowsServer (Halbjährlicher Kanal), WindowsServer 2016, Windows Server 2012 R2, WindowsServer 2012, Windows Server 2008 R2

Ablauf ist nicht immer eine gewünschte Aktion, die auf Dateien ausgeführt werden sollte. Dateiverwaltungsaufgaben ermöglichen Ihnen, benutzerdefinierte Befehle auszuführen.

> [!Note]
> Bei diesem Verfahren wird davon ausgegangen, dass Sie mit den Dateiverwaltungsaufgaben vertraut sind und behandelt daher nur die Registerkarte **Aktion**, in der benutzerdefinierte Einstellungen konfiguriert werden.

## <a name="to-create-a-custom-task"></a>So erstellen Sie eine benutzerdefinierte Aufgabe

1.  Klicken Sie auf den Knoten **Dateiverwaltungsaufgaben**.

2.  Klicken Sie mit der rechten Maustaste auf **Dateiverwaltungsaufgaben**und dann auf **Dateiverwaltungsaufgabe erstellen** (oder klicken Sie auf **Dateiverwaltungsaufgabe erstellen** im Bereich **Aktionen** aus). Daraufhin wird das Dialogfeld **Dateiverwaltungsaufgabe erstellen** geöffnet.

3.  Geben Sie auf der Registerkarte **Aktion** folgende Informationen ein:

    -   **Typ**. Wählen Sie **Benutzerdefiniert** aus dem Dropdownmenü aus.
    -   **Ausführbar**. Navigieren Sie zu dem Befehl oder geben Sie den Befehl ein, wenn die Dateiverwaltungsaufgabe Dateien verarbeitet. Diese ausführbare Datei muss als schreibbar festgelegt werden, damit der Schreibzugriff nur durch Administratoren und das System erfolgen kann. Wenn andere Benutzer über Schreibzugriff auf die ausführbare Datei verfügen, wird sie nicht ordnungsgemäß ausgeführt.
    -   **Befehlseinstellungen**. Um die Argumente zu konfigurieren, die an die ausführbare Datei übergeben werden, wenn ein Dateiverwaltungsauftrag die Dateien verarbeitet, ändern Sie das Textfeld **Argumente**. Um zusätzliche Variablen in den Text einzufügen, platzieren Sie den Cursor in den Speicherort des Textfelds, in den Sie die Variablen einfügen möchten, wählen Sie die Variable aus, die Sie einfügen möchten und klicken Sie dann auf **Variable einfügen**. Der Text in Klammern fügt Informationen über die Variable ein, der von der ausführbaren Datei empfangen werden kann. Z. B. die \[Quelldateipfad\] Variable fügt den Namen der Datei, die von der ausführbaren Datei verarbeitet werden sollen. Optional: Klicken Sie auf die Schaltfläche **Arbeitsverzeichnis**, um den Speicherort der benutzerdefinierten ausführbaren Datei anzugeben.
    -   **Befehlssicherheit**. Konfigurieren Sie die Sicherheitseinstellungen für diese ausführbare Datei. Standardmäßig wird der Befehl als lokaler Dienst ausgeführt, dem restriktivsten Konto.

4.  Klicken Sie auf **OK**.

## <a name="see-also"></a>Siehe auch

-   [Klassifizierungsverwaltung](classification-management.md)
-   [Dateiverwaltungsaufgaben](file-management-tasks.md)