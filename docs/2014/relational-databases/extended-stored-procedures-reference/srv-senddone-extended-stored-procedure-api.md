---
title: srv_senddone (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.topic: reference
api_name:
- srv_senddone
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_senddone
ms.assetid: 1fc4f1d5-56d4-43f6-b5e4-0c0cc295cba3
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 51589cea0306f7a9fe3e4074c586c7c89892d9c9
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48157940"
---
# <a name="srvsenddone-extended-stored-procedure-api"></a>srv_senddone (API für erweiterte gespeicherte Prozeduren)
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Verwenden Sie stattdessen die CLR-Integration.  
  
 Sendet eine Meldung über die Beendigung des Ergebnisses an den Client.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
int srv_senddone (  
SRV_PROC *  
srvproc  
,  
DBUSMALLINT   
status  
,  
DBUSMALLINT  
info  
,  
DBINT  
count   
);  
  
```  
  
## <a name="arguments"></a>Argumente  
 *srvproc*   
 Ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist (in diesem Fall das Handle, das die Sprachanforderung erhalten hat). Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Kommunikation und Daten zwischen der Anwendung und dem Client verwaltet.  
  
 *status*  
 Ein 2-Byte-Feld für verschiedene *status* -Flags. Mehrere Flags können mit den logischen Operatoren AND und OR mit *status* -Flagwerten festgelegt werden. In der folgenden Tabelle sind die möglichen *status* -Flags aufgelistet.  
  
|Statusflag|Description|  
|-----------------|-----------------|  
|SRV_DONE_COUNT|Der *count* -Parameter enthält eine gültige Anzahl.|  
|SRV_DONE_ERROR|Der aktuelle Clientbefehl hat einen Fehler empfangen.|  
  
 *info*  
 Ist ein reserviertes 2-Byte-Feld. Legen Sie diesen Wert standardmäßig auf 0 fest.  
  
 *count*  
 Ein 4-Byte-Feld, das verwendet wird, um eine Anzahl für das aktuelle Resultset anzugeben. Wenn das SRV_DONE_COUNT-Flag im *status* -Feld festgelegt wird, enthält *count* eine gültige Anzahl.  
  
## <a name="returns"></a>Rückgabewert  
 SUCCEED oder FAIL  
  
## <a name="remarks"></a>Hinweise  
 Eine Clientanforderung kann bewirken, dass der Server eine Reihe von Befehlen ausführt und einige Resultsets zurückgibt. Für jedes Resultset muss **srv_senddone** dem Client eine Meldung über die Beendigung des Ergebnisses zurückgeben.  
  
 Das *count* -Feld gibt die Anzahl der Zeilen an, auf die sich ein Befehl auswirkt. Wenn das *count* -Feld eine Anzahl enthält, sollte das SRV_DONE_COUNT-Flag im *status* -Feld festgelegt werden. Anhand dieser Einstellung kann der Client zwischen einem *count* -Feld mit dem Wert 0 und einem nicht verwendeten *count* -Feld unterscheiden.  
  
 Rufen Sie **srv_senddone** nicht von der Behandlungsroutine für SRV_CONNECT aus auf.  
  
> [!IMPORTANT]  
>  Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren. Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](http://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409http://msdn.microsoft.com/security/).  
  
  
