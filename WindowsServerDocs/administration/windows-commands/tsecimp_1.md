---
title: tsecimp
description: 'Windows-Befehle Thema ****- '
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: d7488ec6-0eff-45ff-89ee-9cbe752416bf
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 85fea84ed9dcb0f85bfa80e56f0c2c04d2c8e85b
ms.sourcegitcommit: 1bc3c229e9688ac741838005ec4b88e8f9533e8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2019
ms.locfileid: "68314315"
---
# <a name="tsecimp"></a>tsecimp



Importiert Zuweisungs Informationen aus einer Extensible Markup Language-Datei (XML) in die TAPI-Server Sicherheits Datei (Tsec. ini). Sie können diesen Befehl auch verwenden, um die Liste der TAPI-Anbieter und der zugehörigen Geräte anzuzeigen, die Struktur der XML-Datei zu überprüfen, ohne den Inhalt zu importieren, und die Domänen Mitgliedschaft zu überprüfen.

## <a name="syntax"></a>Syntax

```
tsecimp /f <Filename> [{/v | /u}]
tsecimp /d
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------|-----------|
|/f \<filename->|Erforderlich. Gibt den Namen der XML-Datei an, die die Zuweisungs Informationen enthält, die Sie importieren möchten.|
|/v|Überprüft die Struktur der XML-Datei, ohne die Informationen in die Datei "tsec. ini" zu importieren.|
|/u|Überprüft, ob jeder Benutzer ein Mitglied der Domäne ist, die in der XML-Datei angegeben ist. Der Computer, auf dem Sie diesen Parameter verwenden, muss mit dem Netzwerk verbunden sein. Dieser Parameter kann die Leistung erheblich verlangsamen, wenn Sie eine große Menge an Benutzer Zuweisungs Informationen verarbeiten.|
|/d|Zeigt eine Liste installierter Telefonieanbieter an. Für jeden Telefonieanbieter werden die zugeordneten liniengeräte sowie die den einzelnen Zeilen Geräten zugeordneten Adressen und Benutzer aufgelistet.|
|/?|Zeigt die Hilfe an der Eingabeaufforderung an.|

## <a name="remarks"></a>Hinweise

-   Die XML-Datei, aus der Sie Zuweisungs Informationen importieren möchten, muss der unten beschriebenen Struktur folgen.  
    -   **Userlist** -Element

        Die **userlist** ist das oberste Element der XML-Datei.
    -   **User** -Element

        Jedes **User** -Element enthält Informationen zu einem Benutzer, der Mitglied einer Domäne ist. Jedem Benutzer wird möglicherweise ein oder mehrere Linien Geräte zugewiesen.

        Darüber hinaus kann jedes **User** -Element ein Attribut mit dem Namen " **nomerge**" aufweisen. Wenn dieses Attribut angegeben wird, werden alle Geräte Zuweisungen der aktuellen Zeile für den Benutzer entfernt, bevor neue erstellt werden. Sie können dieses Attribut verwenden, um unerwünschte Benutzer Zuweisungen auf einfache Weise zu entfernen. Standardmäßig ist dieses Attribut nicht festgelegt.

        Das **User** -Element muss ein einzelnes **Domainusername** -Element enthalten, das die Domäne und den Benutzernamen des Benutzers angibt. Das **User** -Element kann auch ein **FriendlyName** -Element enthalten, das einen benutzerfreundlichen Namen für den Benutzer angibt.

        Das **User** -Element kann ein **LineList** -Element enthalten. Wenn ein **LineList** -Element nicht vorhanden ist, werden alle Zeilen Geräte für diesen Benutzer entfernt.
    -   **LineList** -Element

        Das **LineList** -Element enthält Informationen zu den einzelnen Zeilen oder Geräten, die dem Benutzer zugewiesen werden können. Jedes **LineList** -Element kann mehr als ein **Line** -Element enthalten.
    -   **Line** -Element

        Jedes **Line** -Element gibt ein liniengerät an. Sie müssen jedes Zeilen Gerät identifizieren, indem Sie ein **Adress** Element oder ein **PermanentID-** Element unter dem **Line** -Element hinzufügen.

        Für jedes **Line** -Element können Sie das **Remove** -Attribut festlegen. Wenn Sie dieses Attribut festlegen, wird der Benutzer nicht mehr diesem Geräte Gerät zugewiesen. Wenn dieses Attribut nicht festgelegt ist, erhält der Benutzer Zugriff auf dieses liniengerät. Wenn das liniengerät für den Benutzer nicht verfügbar ist, wird kein Fehler ausgegeben.

## <a name="examples"></a>Beispiele
- Die folgenden XML-Beispielcode Segmente veranschaulichen die korrekte Verwendung der oben definierten Elemente.  
  - Mit dem folgenden Code werden alle Linien Geräte entfernt, die user1 zugewiesen sind.  
    ```
    <UserList>
      <User NoMerge="1">
        <DomainUser>domain1\user1</DomainUser>
      </User>
    </UserList>
    ```  
  - Mit dem folgenden Code werden alle Zeilen Geräte entfernt, die user1 zugewiesen sind, bevor eine Zeile mit der Adresse 99999 zugewiesen wird. User1 werden keine anderen Linien Geräte zugewiesen, unabhängig davon, ob zuvor Zeilen Geräte zugewiesen wurden.  
    ```
    <UserList>
      <User NoMerge="1">
        <DomainUser>domain1\user1</DomainUser>
        <FriendlyName>User1</FriendlyName>
        <LineList>
          <Line>
            <Address>99999</Address>
          </Line>
        </LineList>
      </User>
    </UserList>
    ```  
  - Mit dem folgenden Code wird ein Zeilen Gerät für User1 hinzugefügt, ohne zuvor zugewiesene Linien Geräte zu löschen.  
    ```
    <UserList>
      <User>
        <DomainUser>domain1\user1</DomainUser>
        <FriendlyName>User1</FriendlyName>
        <LineList>
          <Line>
            <Address>99999</Address>
          </Line>
        </LineList>
      </User>
    </UserList>
    ```  
  - Mit dem folgenden Code wird die Zeilen Adresse 99999 hinzugefügt und die Zeilen Adresse 88888 aus User1's Access entfernt.  
    ```
    <UserList>
      <User>
        <DomainUser>domain1\user1</DomainUser>
        <FriendlyName>User1</FriendlyName>
        <LineList>
          <Line>
            <Address>99999</Address>
          </Line>
          <Line Remove="1">
            <Address>88888</Address>
          </Line>
        </LineList>
      </User>
    </UserList>
    ```  
  - Mit dem folgenden Code wird das permanente Gerät 1000 hinzugefügt, und die Zeile 88888 wird aus User1's Access entfernt.  
    ```
    <UserList>
      <User>
        <DomainUser>domain1\user1</DomainUser>
        <FriendlyName>User1</FriendlyName>
        <LineList>
          <Line>
            <PermanentID>1000</PermanentID>
          </Line>
          <Line Remove="1">
            <Address>88888</Address>
          </Line>
        </LineList>
      </User>
    </UserList>
    ```

-   Die folgende Beispielausgabe wird angezeigt, nachdem die Befehlszeilenoption **/d** angegeben wurde, um die aktuelle TAPI-Konfiguration anzuzeigen. Für jeden Telefonieanbieter werden die zugeordneten liniengeräte sowie die den einzelnen Zeilen Geräten zugeordneten Adressen und Benutzer aufgelistet.  
    ```
    NDIS Proxy TAPI Service Provider
            Line: "WAN Miniport (L2TP)"
                    Permanent ID: 12345678910

    NDIS Proxy TAPI Service Provider
            Line: "LPT1DOMAIN1\User1"
                    Permanent ID: 12345678910

    Microsoft H.323 Telephony Service Provider
            Line: "H323 Line"
                    Permanent ID: 123456
                    Addresses:
                            BLDG1-TAPI32

    ```

#### <a name="additional-references"></a>Weitere Verweise

[Erläuterung zur Befehlszeilensyntax](command-line-syntax-key.md)

[Übersicht über Befehlsshell](https://technet.microsoft.com/library/cc737438(v=ws.10).aspx)
