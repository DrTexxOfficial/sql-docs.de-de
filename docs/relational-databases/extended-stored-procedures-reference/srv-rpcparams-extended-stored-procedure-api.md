---
title: srv_rpcparams (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: reference
apiname:
- srv_rpcparams
apilocation:
- opends60.dll
apitype: DLLExport
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcparams
ms.assetid: 96a5e6f6-d320-4623-b96e-0a856e3abebb
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: bb1ad7a17dcbf4c2bd5de11b87cccf0b3f84d3dd
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47803698"
---
# <a name="srvrpcparams-extended-stored-procedure-api"></a>srv_rpcparams (API für erweiterte gespeicherte Prozeduren)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Verwenden Sie stattdessen die CLR-Integration.  
  
 Gibt die Anzahl von Parametern für die derzeit remote gespeicherte Prozedur zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
int srv_rpcparams ( SRV_PROC *  
srvproc   
);  
```  
  
## <a name="arguments"></a>Argumente  
 *srvproc*   
 Ist ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist (in diesem Fall das Handle, das die remote gespeicherte Prozedur erhalten hat). Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Kommunikation und Daten zwischen der Anwendung und dem Client verwaltet.  
  
## <a name="returns"></a>Rückgabewert  
 Die Anzahl von Parametern in der remote gespeicherten Prozedur. Wenn die remote gespeicherte Prozedur keine Parameter enthält oder keine aktuelle remote gespeicherte Prozedur vorhanden ist, wird -1 zurückgegeben und ein Informationsfehler angezeigt.  
  
## <a name="remarks"></a>Remarks  
 Diese Funktion gibt die Anzahl von Parametern in der aktuellen remote gespeicherten Prozedur zurück. Sie wird normalerweise von der remote gespeicherten Prozedur aufgerufen.  
  
 Wenn eine remote gespeicherte Prozedur mit Parametern aufgerufen wird, werden die Parameter entweder mit ihrem Namen oder mit ihrer Position übergeben (unbenannt). Werden beim Aufruf einer remote gespeicherte Prozedur einige Parameter mit ihrem Namen und einige mit ihrer Position übergeben, so tritt ein Fehler auf. In diesem Fall wird der Handler der remote gespeicherten Prozedur aufgerufen, aber es werden keine remote gespeicherten Prozeduren empfangen, und **srv_rpcparams** gibt 0 zurück.  
  
> [!IMPORTANT]  
>  Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren. Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](http://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409http://msdn.microsoft.com/security/).  
  
  
