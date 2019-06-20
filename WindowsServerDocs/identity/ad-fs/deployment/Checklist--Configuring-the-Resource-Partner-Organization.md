---
ms.assetid: 80d50a9f-428e-40fe-b6b3-9837fd9a3efc
title: -Checkliste – Konfigurieren der Ressourcenpartnerorganisation
description: ''
author: billmath
manager: femila
ms.date: 05/31/2017
ms.topic: article
ms.prod: windows-server-threshold
ms.technology: identity-adfs
ms.author: billmath
ms.openlocfilehash: 41902de1253654eb3eac6176d6e8b7c50dc39663
ms.sourcegitcommit: 0b5fd4dc4148b92480db04e4dc22e139dcff8582
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2019
ms.locfileid: "66192397"
---
# <a name="checklist-configuring-the-resource-partner-organization"></a>Prüfliste: Konfigurieren der Ressourcenpartnerorganisation

Der Ressourcenpartnerorganisation enthält die Web-Server, die im Web hosten\--basierte Anwendungen, die von Benutzern in der Kontopartner zugegriffen werden. Administratoren in dieser Organisation müssen die AD FS-Verwaltungs-Snap verwenden\-in zum Erstellen von Anspruchsanbieter-Vertrauensstellungen ihre Vertrauensstellungen mit kontopartnerorganisationen darstellt. Wiederum muss der Kontoadministrator für Partner Vertrauensstellungen für jede Kontopartnerorganisation vertrauenden Seite erstellen, die zu vertrauen.  
  
Diese Prüfliste enthält die Aufgaben, die erforderlich sind, für die Bereitstellung von Active Directory Federation Services \(AD FS\) in der Ressourcenpartnerorganisation. Es enthält auch Aufgaben zum Konfigurieren von Komponenten, die erforderlich sind, um eine herstellen\-Teil einer verbundpartnerschaft.  
  
Bei der Bereitstellung einer [Web SSO Design](https://technet.microsoft.com/library/dd807033.aspx), Sie müssen keine dieser Checkliste suchen. Allerdings müssen Sie zum Ausführen der Aufgaben in dieser Prüfliste für die erfolgreiche Bereitstellung einer [Federated Web SSO Design](https://technet.microsoft.com/library/dd807050.aspx).  
  
> [!IMPORTANT]  
> Stellen Sie sicher, dass der Administrator der Kontopartnerorganisation die Anleitung im folgt [Prüfliste: Konfigurieren der Kontopartnerorganisation](Checklist--Configuring-the-Account-Partner-Organization.md) um sicherzustellen, dass alle erforderlichen Bereitstellungsaufgaben abgeschlossen werden, um erfolgreich zu der zweiten Hälfte des der verbundpartnerschaft erstellen  
  
> [!NOTE]  
> Führen Sie die Aufgaben in dieser Prüfliste in der angegebenen Reihenfolge aus. Wenn ein Link zu einer Prozedur gelangen, geben zu diesem Thema zurück, nachdem Sie die Schritte in diesem Verfahren abgeschlossen haben, damit Sie mit den übrigen Aufgaben in dieser Prüfliste fortfahren können.  
  
![Konfigurieren von Resource Partner Org](media/2b05dce3-938f-4168-9b8f-1f4398cbdb9b.gif)**Prüfliste: Konfigurieren der Ressourcenpartnerorganisation**  
  
||Aufgabe|Referenz|  
|-|--------|-------------|  
|![Konfigurieren der Partnerorganisation Ressource](media/icon_checkboxo.gif)|Wenn Sie noch heute eine vorhandene AD FS 1.0 oder 1.1-Bereitstellung in Ihrer produktionsumgebung verfügen, finden Sie unter den Link, um Informationen zum Migrieren von Einstellungen aus Ihrem aktuellen Verbunddienst zu einer neuen AD FS-Verbunddienst nach rechts. Wenn Sie AD FS in Ihrer Organisation zum ersten Mal bereitstellen mithilfe von AD FS, Sie können diesen Schritt überspringen und fahren Sie mit der nächsten Aufgabe in dieser Checkliste finden Sie Informationen zum Einrichten einer neuen Ressourcenpartnerorganisation übernehmen.|![Konfigurieren von Resource Partner Org](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[Planen einer Migration zu AD FS](https://technet.microsoft.com/library/ff678044.aspx)|  
|![Konfigurieren der Partnerorganisation Ressource](media/icon_checkboxo.gif)|Überprüfen Sie auf Grundlage der Bereitstellungsziele, Informationen zu den Komponenten, die erforderlich sind, um Benutzern Zugriff auf die verbundenen Anwendungen bereitzustellen.|![Konfigurieren von Resource Partner Org](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[Provide Your Active Directory Users Access auf Ihre Ansprüche unterstützenden Anwendungen und Dienste](https://technet.microsoft.com/library/dd807071.aspx)<br /><br />![Konfigurieren von Resource Partner Org](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[Provide Your Active Directory Users Access auf die Anwendungen und Dienste von anderen Organisationen](https://technet.microsoft.com/library/dd807123.aspx)<br /><br />![Konfigurieren von Resource Partner Org](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[bieten Benutzern in einer anderen Organisation den Zugriff auf Ihre Ansprüche unterstützenden Anwendungen und Dienste](https://technet.microsoft.com/library/dd807099.aspx)|  
|![Konfigurieren der Partnerorganisation Ressource](media/icon_checkboxo.gif)|Bestimmen Sie, welcher AD FS-Entwurfs diese Ressourcenpartnerorganisation zugeordnet werden soll.|![Konfigurieren von Resource Partner Org](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[Web SSO Design](https://technet.microsoft.com/library/dd807033.aspx)<br /><br />![Konfigurieren von Resource Partner Org](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[Federated Web SSO Design](https://technet.microsoft.com/library/dd807050.aspx)|  
|![Konfigurieren der Partnerorganisation Ressource](media/icon_checkboxo.gif)|Überprüfen Sie die unterschiedlichen Anwendungstypen, und entscheiden Sie, welche Anwendung bereitstellen.|![Konfigurieren von Resource Partner Org](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[Bestimmen der Verbund Anwendung Strategie beim Ressourcenpartner](https://technet.microsoft.com/library/dd807077.aspx)|  
|![Konfigurieren der Partnerorganisation Ressource](media/icon_checkboxo.gif)|Bevor Sie die Bereitstellung von AD FS-Server beginnen, überprüfen Sie das 1.\) vor- und Nachteilen bei der Wahl entweder Windows Internal Database \(WID\) oder SQL Server zum Speichern der AD FS-Konfigurationsdatenbank 2.\) AD FS-Topologie Bereitstellungstypen und ihre zugeordneten Server Platzierung und Netzwerk-Layout-Empfehlungen.|![Konfigurieren von Resource Partner Org](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[Bestimmen der AD FS-Bereitstellungstopologie](https://technet.microsoft.com/library/gg982491.aspx)<br /><br />![Konfigurieren von Resource Partner Org](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[Überlegungen zur Topologie der AD FS-Bereitstellung](https://technet.microsoft.com/library/gg982489.aspx)|  
|![Konfigurieren der Partnerorganisation Ressource](media/icon_checkboxo.gif)|Überprüfen Sie die AD FS-kapazitätsplanung Anleitungen zum Bestimmen der richtigen Anzahl von Verbundserver und Federation Server Proxy-Servern, die Sie in Ihrer produktionsumgebung verwenden sollten.|![Konfigurieren von Resource Partner Org](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[Planen der AD FS-Serverkapazität](https://technet.microsoft.com/library/gg749899.aspx)|  
|![Konfigurieren der Partnerorganisation Ressource](media/icon_checkboxo.gif)|Zur effektiven Planung und implementieren die physische Topologie für die Bereitstellung des Partners, bestimmen Sie, ob Ihre AD FS-Entwurfs für eine oder mehrere Verbundserver oder Verbundserverproxys erforderlich ist.|![Konfigurieren von Resource Partner Org](media/bc6cea1a-1c6c-4124-8c8f-1df5adfe8c88.gif)[Prüfliste: Einrichten eines Verbundservers](Checklist--Setting-Up-a-Federation-Server.md)<br /><br />![Konfigurieren von Resource Partner Org](media/bc6cea1a-1c6c-4124-8c8f-1df5adfe8c88.gif)[Prüfliste: Einrichten eines Verbundserverproxys](Checklist--Setting-Up-a-Federation-Server-Proxy.md)|  
|![Konfigurieren der Partnerorganisation Ressource](media/icon_checkboxo.gif)|Bestimmen Sie den Typ der Attributspeicher, die Sie mit AD FS hinzufügen möchten. Fügen Sie dann den Attributspeicher, die mit der AD FS-Verwaltungs-Snap\-in.|![Konfigurieren von Resource Partner Org](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[die Rolle des Attributspeichers](../../ad-fs/technical-reference/The-Role-of-Attribute-Stores.md)<br /><br />![Konfigurieren von Resource Partner Org](media/15dd35b6-6cc6-421f-93f8-7109920e7144.gif)[hinzufügen eine Store-Attribut](../../ad-fs/operations/Add-an-Attribute-Store.md)|  
|![Konfigurieren der Partnerorganisation Ressource](media/icon_checkboxo.gif)|Wenn Sie zum Senden von Ansprüchen oder nutzen Ansprüche eines Kontopartners, für die Verwendung einer AD FS 1.0 oder 1.1-Verbunddienst, finden Sie unter den Link, um das Recht für Informationen zur Verwendung von AD FS zu konfigurieren, die Interoperabilität mit früheren Versionen von AD FS benötigen. Wenn die Kontopartnerorganisation auch AD FS zum Senden oder Ansprüche für Ihre Organisation nutzen verwendet, können Sie diesen Schritt überspringen und mit der nächsten Aufgabe in dieser Prüfliste fortfahren.|![Konfigurieren von Resource Partner Org](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[Planen der Interoperabilität mit AD FS 1.x](https://technet.microsoft.com/library/ff678040.aspx)|  
|![Konfigurieren der Partnerorganisation Ressource](media/icon_checkboxo.gif)|Nach der Bereitstellung des ersten Verbundservers in der Ressourcenpartnerorganisation, erstellen Sie eine Vertrauensstellung für Anspruchsanbieter-Anbieter mithilfe der AD FS-Verwaltungs-Snap\-in. Sie können eine Anspruchsanbieter-Vertrauensstellung erstellen, durch Eingeben von Daten zum Kontopartner manuell oder mithilfe von eine Verbundmetadaten-URL, die der Administrator der Kontopartnerorganisation für Sie bereitstellt. Mithilfe der Verbundmetadaten können die Daten für den Ressourcenpartner automatisch abgerufen werden. **Hinweis**: Wenn der Kontopartner die Verbundmetadaten veröffentlicht oder bieten eine Dateikopie zur verwenden, empfehlen wir, dass Sie die Daten automatisch abgerufen werden, da dadurch Zeit gespart werden kann.|![Konfigurieren von Resource Partner Org](media/15dd35b6-6cc6-421f-93f8-7109920e7144.gif)[eine verlassen Partei vertrauen manuell erstellen](../operations/create-a-relying-party-trust.md#to-create-a-claims-aware-relying-party-trust-manually)<br /><br />![Konfigurieren von Resource Partner Org](media/15dd35b6-6cc6-421f-93f8-7109920e7144.gif)[erstellen Sie eine verlassen Partei Vertrauensstellung mithilfe von Verbundmetadaten](../operations/create-a-relying-party-trust.md#to-create-a-claims-aware-relying-party-trust-using-federation-metadata)|  
|![Konfigurieren der Partnerorganisation Ressource](media/icon_checkboxo.gif)|Je nach den Anforderungen Ihres Unternehmens, erstellen Sie eine oder mehrere Anspruchsregel legt fest, für jede Anspruchsanbieter-Vertrauensstellung, der angegeben wird im AD FS-Verwaltungs-Snap-\-im, damit eingehende Ansprüche durch übergeben werden, transformiert oder entsprechend zu zugeordnet entsprechende Ansprüche in den Ressourcenpartner.|![Konfigurieren von Resource Partner Org](media/bc6cea1a-1c6c-4124-8c8f-1df5adfe8c88.gif)[Prüfliste: Erstellen von Anspruchsregeln für eine Anspruchsanbieter-Vertrauensstellung](Checklist--Creating-Claim-Rules-for-a-Claims-Provider-Trust.md)|  
|![Konfigurieren der Partnerorganisation Ressource](media/icon_checkboxo.gif)|\(Optionale\) ein Anspruch Beschreibung möglicherweise erstellt werden, wenn Sie noch nicht, die vorhanden ist, wird die Anforderungen Ihrer Organisation erfüllen. AD FS enthält einen Standardsatz von anspruchsbeschreibungen, die verfügbar gemacht werden im AD FS-Verwaltungs-Snap-\-in.|![Konfigurieren von Resource Partner Org](media/15dd35b6-6cc6-421f-93f8-7109920e7144.gif)[Hinzufügen einer Anspruchsbeschreibung](../../ad-fs/operations/Add-a-Claim-Description.md)|  