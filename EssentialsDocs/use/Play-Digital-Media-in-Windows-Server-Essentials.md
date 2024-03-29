---
title: Wiedergeben von digitalen Medien in Windows Server Essentials
description: Beschreibt, wie Windows Server Essentials
ms.custom: na
ms.date: 10/03/2016
ms.prod: windows-server-2016-essentials
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 5f570492-ee21-471b-92c1-3fd9bfb84f55
author: nnamuhcs
ms.author: coreyp
manager: dongill
ms.openlocfilehash: f38d234768d40903615145954f1215546119344a
ms.sourcegitcommit: eaf071249b6eb6b1a758b38579a2d87710abfb54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66435943"
---
# <a name="play-digital-media-in-windows-server-essentials"></a>Wiedergeben von digitalen Medien in Windows Server Essentials

>Gilt für: Windows Server 2012 R2 Essentials, Windows Server 2012 Essentials

Digitale Medien sind Audio-, Video- und Fotoinhalte, die digital komprimiert wurden.  Windows Server Essentials ermöglicht es Computern und einigen Mediengeräten digitale, die auf dem Server gespeicherte, digitale Mediendateien wiederzugeben.  
  
 Die folgenden Themen enthalten Informationen zum Zugreifen auf und Wiedergeben von digitalen Mediendateien, die auf Windows Server Essentials gespeichert sind:  
  

-   [Übersicht über digitale Medien](Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_1)  
  
-   [Wiedergeben Sie und freigeben Sie digitaler Medien](Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_2)  
  
-   [Wiedergeben freigegebener digitaler Mediendateien von einem Remotestandort aus](Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_3)  
  
-   [Fügen Sie digitaler Mediendateien zum Server hinzu](Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_4)  
  
-   [Formatoptionen für Downloads](Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_5)  
  
-   [Einfache Tool "Dateiupload"](Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_6)  
  
-   [Anzeigen und Durchsuchen von freigegebenen digitalen Medien](Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_7)  

-   [Übersicht über digitale Medien](../use/Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_1)  
  
-   [Wiedergeben Sie und freigeben Sie digitaler Medien](../use/Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_2)  
  
-   [Wiedergeben freigegebener digitaler Mediendateien von einem Remotestandort aus](../use/Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_3)  
  
-   [Fügen Sie digitaler Mediendateien zum Server hinzu](../use/Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_4)  
  
-   [Formatoptionen für Downloads](../use/Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_5)  
  
-   [Einfache Tool "Dateiupload"](../use/Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_6)  
  
-   [Anzeigen und Durchsuchen von freigegebenen digitalen Medien](../use/Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_7)  

  
##  <a name="BKMK_1"></a> Übersicht über digitale Medien  
 Digitale Medien sind Audio-, Video- und Fotoinhalte, die codiert (digital komprimiert) wurden. Beim Codieren von Inhalten werden Audio- und Videoeingaben in eine digitale Mediendatei, z. B. eine Windows Media-Datei, konvertiert. Nach der Codierung können digitale Medien einfach bearbeitet, verteilt, von Computern wiedergegeben und über Computernetzwerke übertragen werden.  
  
 Beispiele für digitale Medien sind: Windows Media Audio (WMA), Windows Media Video (WMV), MP3, JPEG und AVI. Informationen zu den digitalen Medientypen, die von Windows Media Player unterstützt werden, finden Sie unter [Von Windows Media Player unterstützte Dateitypen](https://support.microsoft.com/kb/316992).  
  
### <a name="why-would-i-want-to-stream-my-digital-media"></a>Warum sollte ich meine digitalen Medien streamen?  
 Viele Benutzer speichern Musik, Videos und Bilder in freigegebenen Ordnern in Windows Server Essentials. Sie haben verschiedene Möglichkeiten, Medien zu nutzen:  
  
-   **Videos ansehen**. Der Server kann zum Speichern und Streamen umfangreicher Videosammlungen und TV-Aufzeichnungen auf Ihre Computer oder andere Wiedergabegeräte im Netzwerk genutzt werden. Mithilfe von Windows Media Player können Sie Videos auf eine Xbox 360 oder auf einen Computer streamen.  
  
-   **Musik wiedergeben**. Wenn Sie die Medienfreigabe für den freigegebenen Ordner **Musik** aktivieren, können Sie über Geräte, die Windows Media Connect unterstützen, auf Ihre Musik zugreifen. Nachdem die Freigabe aktiviert wurde, müssen Sie keine Benutzerkonten aktivieren oder konfigurieren, um Musik aus dem freigegebenen Ordner **Musik** zu streamen.  
  
-   **Fotodiashow präsentieren**. Sie können Ihre digitalen Fotos im freigegebenen Ordner **Fotos** auf dem Server speichern und anschließend von jedem Computer oder von einer Xbox 360 darauf zugreifen, die mit einem Fernsehgerät bei Ihnen zuhause oder im Büro verbunden ist. Sie können Fotodiashows ansehen und Ihr Fernsehgerät praktisch in einen großen Bilderrahmen verwandeln.  
  
### <a name="sharing-copy-protected-media"></a>Freigeben kopiergeschützter Medien  
  Windows Server Essentials unterstützt freigeben kopiergeschützter Medien nicht. Dazu gehört auch Musik, die über einen Online-Music Store gekauft wurde.  
  
 Kopiergeschützte Medien können nur auf dem Computer oder Gerät wiedergegeben werden, über den bzw. das sie erworben wurden. Der Kopierschutz verhindert, dass Sie Medien auf mehr als einem Computer oder Gerät abspielen, auch wenn Sie das Medium auf den Server kopieren und dort wiedergeben. Allerdings können Sie die kopiergeschützter Medien in Windows Server Essentials zu speichern und weiterhin wiedergeben des Mediums, auf dem Computer oder Gerät, das Sie verwendet haben, sie zu erwerben.  
  
##  <a name="BKMK_2"></a> Wiedergeben Sie und freigeben Sie digitaler Medien  
 Nachdem Sie Ihr Netzwerk eingerichtet und die Computer und Mediengeräte erfolgreich mit dem Servernetzwerk verbunden haben, können Sie digitale Mediendateien suchen, die Sie auf dem Server speichern und freigeben.  
  
> [!NOTE]
>  Eine aktuelle Liste der digital Media Player/Empfänger für digitale Medien, die mit Windows Server Essentials kompatibel sind, finden Sie unter den [Windows Compatibility Center](https://www.microsoft.com/windows/compatibility/CompatCenter/Home).  
  
 Sie können auf dem Server gespeicherte digitale Mediendateien auf folgende Weisen suchen und wiedergeben:  
  

-   [Suchen und Wiedergeben von Mediendateien in Windows Server Essentials auf einem Computer oder digital Media-Player im Netzwerk](Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_2.1)  
  
-   [Senden von Mediendateien in Windows Server Essentials an Windows Media Player, Xbox 360 oder einen digital Media-Player im Netzwerk](Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_SendToDevice)  

-   [Suchen und Wiedergeben von Mediendateien in Windows Server Essentials auf einem Computer oder digital Media-Player im Netzwerk](../use/Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_2.1)  
  
-   [Senden von Mediendateien in Windows Server Essentials an Windows Media Player, Xbox 360 oder einen digital Media-Player im Netzwerk](../use/Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_SendToDevice)  

  
###  <a name="BKMK_2.1"></a> Suchen und Wiedergeben von Mediendateien in Windows Server Essentials auf einem Computer oder digital Media-Player im Netzwerk  
 Wenn Ihr Gerät mit dem Windows Server Essentials-Netzwerk hinzugefügt wird, können Sie suchen und Wiedergeben von digitalen Mediendateien in einem der folgenden Methoden:  
  

-   [Suchen und Wiedergeben von Mediendateien auf einem Computer, auf der Windows Media Center ausgeführt wird](Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_WMC)  
  
-   [Suchen und Wiedergeben von Mediendateien auf einem Computer, auf dem Windows ausgeführt wird, mithilfe von Windows Media Player](Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_MWP)  
  
-   [Suchen und Wiedergeben von Mediendateien mit der Xbox 360](Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_Xbox)  
  
-   [Suchen und Wiedergeben von Mediendateien mit anderen digital Media-Player oder Empfänger, die mit Windows Server Essentials kompatibel sind](Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_Other)  
  
-   [Suchen und Wiedergeben von Mediendateien mit der Funktion für freigegebene Ordner im Launchpad](Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_SharedFolders)  
  
-   [Suchen Sie und wiedergeben Sie freigegebener Medien mithilfe von Remotewebzugriff](Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_RWA2)  

-   [Suchen und Wiedergeben von Mediendateien auf einem Computer, auf der Windows Media Center ausgeführt wird](../use/Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_WMC)  
  
-   [Suchen und Wiedergeben von Mediendateien auf einem Computer, auf dem Windows ausgeführt wird, mithilfe von Windows Media Player](../use/Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_MWP)  
  
-   [Suchen und Wiedergeben von Mediendateien mit der Xbox 360](../use/Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_Xbox)  
  
-   [Suchen und Wiedergeben von Mediendateien mit anderen digital Media-Player oder Empfänger, die mit Windows Server Essentials kompatibel sind](../use/Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_Other)  
  
-   [Suchen und Wiedergeben von Mediendateien mit der Funktion für freigegebene Ordner im Launchpad](../use/Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_SharedFolders)  
  
-   [Suchen Sie und wiedergeben Sie freigegebener Medien mithilfe von Remotewebzugriff](../use/Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_RWA2)  

  
####  <a name="BKMK_WMC"></a> Suchen und Wiedergeben von Mediendateien auf einem Computer, auf der Windows Media Center ausgeführt wird  
  
1.  Klicken Sie auf **Start**, **Alle Programme** und dann auf **Windows Media Center**.  
  
2.  Führen Sie auf der Seite **Windows Media Center** einen Bildlauf zum gesuchten Medientyp durch, und klicken Sie auf die Medienbibliothek.  
  
3.  Suchen Sie manuell nach der gewünschten Datei, oder klicken Sie auf **Suchen** , und geben Sie den Namen der gesuchten Datei ein.  
  
4.  Klicken Sie auf das Bild der Mediendatei, um sie anzuzeigen oder wiederzugeben.  
  
####  <a name="BKMK_MWP"></a> Suchen und Wiedergeben von Mediendateien auf einem Computer, auf dem Windows ausgeführt wird, mithilfe von Windows Media Player  
  
-   Öffnen Sie auf dem Computer oder Mediengerät **Windows Media Player** , und suchen Sie die Medienbibliothek.  
  
    > [!NOTE]
    >  Die Schritte der Suche variieren je nach der verwendeten Version von Windows Media Player. Ausführliche Informationen finden Sie in der Hilfe zu Ihrer Version.  
  
####  <a name="BKMK_Xbox"></a> Suchen und Wiedergeben von Mediendateien mit der Xbox 360  
  
1.  Verbinden Sie die Xbox 360-Konsole über eine kabelgebundene oder kabellose Verbindung mit Ihrem Heimnetzwerk.  
  
2.  Aktivieren Sie auf dem Computer, auf der Windows Server Essentials ausgeführt wird, auf die Freigabe von Medien. Weitere Informationen finden Sie im Thema [aktiviert oder deaktiviert das Medienstreaming aktivieren](../manage/Manage-Digital-Media-in-Windows-Server-Essentials.md#BKMK_4).  
  
3.  So geben Sie digitale Mediendateien mit der Xbox 360-Konsole wieder:  
  
    1.  Wechseln Sie zu **Meine Xbox**, und wählen Sie dann abhängig vom Medientyp, den Sie anzeigen oder wiedergeben möchten, **Videobibliothek**, **Musikbibliothek**oder **Bildbibliothek**aus.  
  
    2.  Wählen Sie den Namen des Servers aus.  
  
        > [!NOTE]
        >  Wenn der Servername nicht aufgeführt ist, wählen Sie **Computer**, und klicken Sie dann auf **Verbindung testen**.  
  
    3.  Durchsuchen Sie die Dateiliste, und wählen Sie das Element aus, das Sie wiedergeben möchten.  
  
####  <a name="BKMK_Other"></a> Suchen und Wiedergeben von Mediendateien mit anderen digital Media-Player oder Empfänger, die mit Windows Server Essentials kompatibel sind  
  
1.  Wechseln Sie zum [Windows-Kompatibilitätscenter](https://www.microsoft.com/windows/compatibility/CompatCenter/Home) , und stellen Sie sicher, dass Ihr Digital Media-Player oder Empfänger für digitale Medien in der Liste kompatibler Geräte aufgeführt wird.  
  
2.  Die Suchschritte variieren abhängig vom verwendeten Digital Media-Player. Ausführliche Anweisungen finden Sie in der Hilfe zu Ihrem Gerät.  
  
####  <a name="BKMK_SharedFolders"></a> Suchen und Wiedergeben von Mediendateien mit der Funktion für freigegebene Ordner im Launchpad  
  
1.  Melden Sie sich beim Windows Server Essentials-LaunchPads.  
  
2.  Klicken Sie im Launchpad auf **Freigegebene Ordner**. Ein Windows-Explorer-Fenster wird geöffnet und zeigt die freigegebenen Ordner auf dem Server an.  
  
3.  Geben Sie im Feld **Suchen** den Namen einer Mediendatei ein. Die Ergebnisse Ihrer Suchabfrage werden angezeigt.  
  
    > [!NOTE]
    >  Optional können Sie auch auf einen freigegebenen Ordner doppelklicken, um den Ordnerinhalt zu durchsuchen.  
  
####  <a name="BKMK_RWA2"></a> Suchen Sie und wiedergeben Sie freigegebener Medien mithilfe von Remotewebzugriff  
  
1.  Melden Sie sich bei Remotewebzugriff an.  
  
2.  Klicken Sie auf **Freigegebene Ordner**. Im Abschnitt **Freigegebene Ordner** der Webseite wird eine Liste freigegebener Ordner auf dem Server angezeigt.  
  
3.  Doppelklicken Sie auf einen Ordner, um dessen Inhalt anzuzeigen.  
  
###  <a name="BKMK_SendToDevice"></a> Senden von Mediendateien in Windows Server Essentials an Windows Media Player, Xbox 360 oder einen digital Media-Player im Netzwerk  
 Verwenden Sie **Windows Media Player**, um die gewünschte Mediendatei zu suchen. Klicken Sie mit der rechten Maustaste auf die Mediendatei, und klicken Sie dann auf **Wiedergeben auf**, um die Mediendatei an ein Mediengerät im Netzwerk zu senden.  
  
##  <a name="BKMK_3"></a> Wiedergeben freigegebener digitaler Mediendateien von einem Remotestandort aus  
 Wenn Sie von Ihrem Windows Server Essentials-Netzwerk sind, mithilfe von Remotewebzugriff können Sie Ihre Mediendateien wiedergeben. Zum Suchen und Wiedergeben der auf Ihrem Server gespeicherten freigegebenen Mediendateien können Sie ein Mobiltelefon, einen Remotecomputer oder einen Digital Media-Player verwenden.  
  
#### <a name="to-play-shared-media-files-when-you-are-away-from-the-network"></a>So geben Sie freigegebene Mediendateien wieder, wenn Sie keinen Zugriff auf Ihr Netzwerk haben  
  
1. Öffnen Sie einen Internetbrowser.  
  
2. Wechseln Sie zur Website für Remotewebzugriff. Typ **https://<YourDomainName\>/remote** in der Adressleiste des Internet-Browser, und drücken Sie dann die EINGABETASTE.  
  
   > [!NOTE]
   >  *< IhrDomänenname\>*  ist ein Platzhalter. Sie werden ein Name, der auf dem Server eindeutig ist, damit die eingegebene Adresse aussieht **https://contoso.com/remote** . Wenn Sie den Namen der Domäne nicht kennen, erkundigen Sie sich beim Administrator, der den Domänennamen bei der Einrichtung der Remotezugriffsfunktion auf dem Server ausgewählt hat. Weitere Informationen finden Sie unter [Turn on Remote Web Access](../manage/Manage-Remote-Web-Access-in-Windows-Server-Essentials.md#BKMK_TurnOnRWA).  
  
3. Geben Sie auf der Anmeldeseite für den Remotewebzugriff Ihren Benutzernamen und Ihr Kennwort ein, und klicken Sie dann auf den Pfeil.  
  
4. Suchen Sie die wiederzugebende Mediendatei auf die für Sie geeignete Weise.  
  
   > [!NOTE]
   > 
   >  Informationen zu den verschiedenen Methoden zu suchen, finden Sie unter [suchen und Wiedergeben von Mediendateien in Windows Server Essentials auf einem Computer oder digital Media-Player im Netzwerk](Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_2.1).  
   > 
   >  Informationen zu den verschiedenen Methoden zu suchen, finden Sie unter [suchen und Wiedergeben von Mediendateien in Windows Server Essentials auf einem Computer oder digital Media-Player im Netzwerk](../use/Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_2.1).  

  
5. Sobald der Name der Mediendatei angezeigt wird, klicken Sie auf den Dateinamen, um das Medium wiederzugeben.  
  
##  <a name="BKMK_4"></a> Fügen Sie digitaler Mediendateien zum Server hinzu  

 Der Server-Administrator kann digitale Medien an freigegebene Ordner in der Medienbibliothek durch Zugriff auf den Server direkt oder mithilfe der Remotewebzugriff-Website für die Anmeldung auf dem Dashboard hinzufügen. Andere Benutzer können mit dem Server Mediendateien hinzufügen, indem Sie mit der **gemeinsam genutzten Ordnern** Verbindung auf dem Launchpad mithilfe der Remotewebzugriff-Website oder mithilfe der My Server-app für Windows Phone. Informationen zum Wiedergeben von Medien finden Sie unter [Wiedergeben und Freigeben digitaler Medien](Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_2).  

 Der Server-Administrator kann digitale Medien an freigegebene Ordner in der Medienbibliothek durch Zugriff auf den Server direkt oder mithilfe der Remotewebzugriff-Website für die Anmeldung auf dem Dashboard hinzufügen. Andere Benutzer können mit dem Server Mediendateien hinzufügen, indem Sie mit der **gemeinsam genutzten Ordnern** Verbindung auf dem Launchpad mithilfe der Remotewebzugriff-Website oder mithilfe der My Server-app für Windows Phone. Informationen zum Wiedergeben von Medien finden Sie unter [Wiedergeben und Freigeben digitaler Medien](../use/Play-Digital-Media-in-Windows-Server-Essentials.md#BKMK_2).  

  
> [!NOTE]
>  Sie können Mediendateien auch mit der My Server-App für Windows Phone auf den Server hochladen. Sie können die My Server-Apps aus dem [Windows Phone Store](http://www.windowsphone.com/store/app/my-server/6c2f98d5-6fcf-4e1d-b8b1-cde62ea1a94a)herunterladen. Weitere Informationen zur My Server-app für Windows Phone finden Sie im Blogbeitrag [My Server Phone-app für Windows Server Essentials](http://blogs.technet.com/b/sbs/archive/2012/09/18/my-server-phone-app-for-windows-server-2012-essentials.aspx).  
  
#### <a name="to-add-digital-media-files-to-shared-folders-on-the-server"></a>So fügen Sie digitale Mediendateien freigegebenen Ordnern auf dem Server hinzu  
  
1.  Verwenden Sie eine der folgenden Methoden für die Anmeldung beim Server:  
  

    1.  Weitere Informationen zur Anmeldung beim Remotewebzugriff finden Sie unter [Use Remote Web Access](Use-Remote-Web-Access-in-Windows-Server-Essentials.md).  

    1.  Weitere Informationen zur Anmeldung beim Remotewebzugriff finden Sie unter [Use Remote Web Access](../use/Use-Remote-Web-Access-in-Windows-Server-Essentials.md).  

  
    2.  Informationen zum Anmelden mit Launchpad finden Sie unter [Launchpad-Übersicht](../manage/Overview-of-the-Launchpad-in-Windows-Server-Essentials.md).  
  
2.  Suchen Sie den Ordner für das Medium, das Sie hinzufügen, und klicken Sie darauf.  
  
3.  Kopieren Sie die gewünschten Mediendateien, und fügen Sie sie in den entsprechenden freigegebenen Ordner auf dem Server ein. Sie können sie auch mit Drag & Drop verschieben.  
  
##  <a name="BKMK_5"></a> Formatoptionen für Downloads  
 Es gibt zwei Optionen zum Herunterladen von Dateien. Diese Optionen sind nur verfügbar, wenn Sie mehrere Dateien oder einen Ordner auf einen Windows-basierten Computer herunterladen.  
  
 Wählen Sie im Folgenden die Option, die Ihre Downloadanforderungen erfüllt:  
  
- **Komprimierte ZIP-Datei (.zip)**  
  
   Durch das Zippen einer Datei wird eine komprimierte Dateiversion erstellt, die kleiner als die Originaldatei ist. Die komprimierte Dateiversion verfügt über die Dateierweiterung ".zip". Dateitypen, die am meisten von der Komprimierung profitieren, sind textorientierte Dateitypen (z. B. TXT-, DOC- und XLS-Dateien) und Grafiken, die nicht komprimierte Dateitypen verwenden (z. B. ".bmp"). Einige Grafikdateien wie JPG- und GIF-Dateien nutzen bereits die Komprimierung, sodass sich die Dateigröße durch das Komprimieren nur geringfügig verkleinert. Darüber hinaus reduziert sich die Dateigröße eines Word-Dokuments mit vielen Grafiken nicht in dem Maße wie ein Dokument, das hauptsächlich Text enthält.  
  
  > [!NOTE]
  >  Diese Option bietet eingeschränkte Unterstützung für internationale Dateinamen.  
  
- **Selbstextrahierende ausführbare Datei (.exe)**  
  
   Eine selbstextrahierende ausführbare Datei ist eine herunterladbare Datei, die das Dekomprimierungsprogramm (ausführbare Datei) mit den komprimierten Dateien kombiniert. Beim Ausführen des Programms werden die komprimierten Dateien automatisch dekomprimiert. Mit diesem gängigen Verfahren können komprimierte Daten verteilt werden, ohne dass der Empfänger über das nötige Dekomprimierungshilfsprogramm verfügen muss.  
  
  > [!NOTE]
  >  Diese Option unterstützt Unicode-Zeichen.  
  
  Vor Beginn des eigentlichen Downloads wird die EXE- oder ZIP-Datei erstellt. Abhängig von der Anzahl der Dateien und der Gesamtgröße der Downloaddateien kann dies einige Minuten dauern. Nachdem die Downloaddatei erstellt wurde, erfolgt das Herunterladen der Datei im Hintergrund. Dadurch können Sie weiterarbeiten, während der Downloadvorgang ausgeführt wird.  
  
##  <a name="BKMK_6"></a> Einfache Tool "Dateiupload"  
 Die Tool "einfacher Dateiupload" optimiert das Hochladen von Dateien auf dem Windows Server Essentials-Server. Sie können beliebig viele Dateien, wie Sie das Tool einfacher Dateiupload möchten, und klicken Sie dann auf die freigegebenen Ordner auf dem Windows Server Essentials-Server in einem einzelnen Batch hochladen hinzufügen. Weitere Informationen finden Sie im Blogbeitrag [Grundlegendes zur Dateifreigabe mit Remotewebzugriff](http://blogs.technet.com/b/sbs/archive/2012/04/19/understanding-remote-web-access-file-sharing.aspx).  
  
##  <a name="BKMK_7"></a> Anzeigen und Durchsuchen von freigegebenen digitalen Medien  
 Sie können Ressourcen entweder über das Dashboard, das Launchpad, die Website für Remotewebzugriff oder die My Server-App für Windows Phone anzeigen oder durchsuchen.  
  
#### <a name="to-view-and-browse-shared-media-from-the-dashboard"></a>So können Sie freigegebene Medien über das Dashboard anzeigen und durchsuchen  
  
1.  Öffnen Sie das Server-Dashboard.  
  
2.  Klicken Sie auf der Navigationsleiste auf **SPEICHER**.  
  
3.  Klicken Sie auf die Registerkarte **Serverordner** . Eine Liste der Serverordner wird angezeigt.  
  
4.  Doppelklicken Sie auf einen Ordner, um dessen Inhalt anzuzeigen.  
  
#### <a name="to-view-and-browse-shared-media-using-the-launchpad-from-a-network-computer"></a>So können Sie freigegebene Medien über das Launchpad eines Netzwerkcomputers anzeigen und durchsuchen  
  
1.  Melden Sie sich beim Launchpad an.  
  
2.  Klicken Sie auf **Freigegebene Ordner**. Windows-Explorer wird geöffnet und zeigt eine Liste der freigegebenen Ordner auf dem Server an.  
  
3.  Doppelklicken Sie auf einen Ordner, um dessen Inhalt anzuzeigen.  
  
#### <a name="to-view-and-browse-shared-media-using-remote-web-access"></a>So können Sie freigegebene Medien über Remotewebzugriff anzeigen und durchsuchen  
  
1.  Melden Sie sich bei Remotewebzugriff an.  
  
2.  Klicken Sie auf **Freigegebene Ordner**. Im Abschnitt **Freigegebene Ordner** der Webseite wird eine Liste freigegebener Ordner auf dem Server angezeigt.  
  
3.  Doppelklicken Sie auf einen Ordner, um dessen Inhalt anzuzeigen.  
  
## <a name="see-also"></a>Siehe auch  
  
-   [Verwalten von digitalen Medien](../manage/Manage-Digital-Media-in-Windows-Server-Essentials.md)  
  

-   [Herstellen einer Verbindung](Get-Connected-in-Windows-Server-Essentials.md)  
  
-   [Verwenden von freigegebenen Ordnern](Use-Shared-Folders-in-Windows-Server-Essentials.md)  
  
-   [Arbeiten im Remotemodus](Work-Remotely-in-Windows-Server-Essentials.md)

-   [Herstellen einer Verbindung](../use/Get-Connected-in-Windows-Server-Essentials.md)  
  
-   [Verwenden von freigegebenen Ordnern](../use/Use-Shared-Folders-in-Windows-Server-Essentials.md)  
  
-   [Arbeiten im Remotemodus](../use/Work-Remotely-in-Windows-Server-Essentials.md)

