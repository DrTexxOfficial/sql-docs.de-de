---
title: SQL Server-XTP-Cursor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
ms.assetid: 84bf4654-3ef7-4d7f-a269-c8bb4ed4acad
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 66973437f02bf2005b01531dea14c2f6d8d47771
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47595448"
---
# <a name="sql-server-xtp-cursors"></a>SQL Server-XTP-Cursor
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

  Das Leistungsobjekt für SQL Server-XTP-Cursor enthält Leistungsindikatoren für interne Cursor der In-Memory-OLTP-Engine. Cursor sind die Bausteine auf unterer Ebene, die die In-Memory-OLTP-Engine zur Verarbeitung von [!INCLUDE[tsql](../../includes/tsql-md.md)]-Abfragen verwendet. Daher können Sie diese in der Regel nicht direkt steuern.  
  
 In dieser Tabelle werden die Leistungsindikatoren für **SQL Server-XTP-Cursor** beschrieben.  
  
|Leistungsindikator|und Beschreibung|  
|-------------|-----------------|  
|**Cursorlöschvorgänge/s**|Die durchschnittliche Anzahl der pro Sekunde erfolgten Cursorlöschvorgänge.|  
|**Cursoreinfügevorgänge/s**|Die durchschnittliche Anzahl der pro Sekunde erfolgten Cursoreinfügevorgänge.|  
|**Gestartete Cursorscans/s**|Die durchschnittliche Anzahl der pro Sekunde gestarteten Cursorscans.|  
|**Cursor-UNIQUE-Verstöße/s**|Die durchschnittliche Anzahl der pro Sekunde erfolgten Verstöße gegen die UNIQUE-Einschränkung.|  
|**Cursorupdates/s**|Die durchschnittliche Anzahl der pro Sekunde erfolgten Cursorupdates.|  
|**Cursorschreibkonflikte/s**|Die durchschnittliche Anzahl der pro Sekunde erfolgten Write-Write-Konflikte in dieselbe Zeilenversion.|  
|**Dusty-Corner-Scanwiederholungen/s (durch den Benutzer ausgegeben)**|Die durchschnittliche Anzahl von Scanwiederholungen aufgrund von Schreibkonflikten während Dusty-Corner-Sweep-Vorgängen, die pro Sekunde durch vollständige Tabellenscans eines Benutzers ausgegeben werden. Dieser Leistungsindikator befindet sich auf einer sehr niedrigen Ebene und dient nicht der Verwendung durch Kunden.|  
|**Entfernte abgelaufene Zeilen/s**|Die durchschnittliche Anzahl abgelaufener Zeilen, die pro Sekunde von Cursorn entfernt werden.|  
|**Berührte abgelaufene Zeilen/s**|Die durchschnittliche Anzahl abgelaufener Zeilen, die pro Sekunde von Cursorn berührt werden.|  
|**Zurückgegebene Zeilen/s**|Die durchschnittliche Anzahl von Zeilen, die pro Sekunde von Cursorn zurückgegeben werden.|  
|**Berührte Zeilen/s**|Die durchschnittliche Anzahl von Zeilen, die pro Sekunde von Cursorn berührt werden.|  
|**Berührte vorläufig gelöschte Zeilen/s**|Die durchschnittliche Anzahl ablaufender Zeilen, die pro Sekunde von Cursorn berührt werden. Eine Zeile läuft ab, wenn die Transaktion, durch die sie gelöscht wurde, immer noch aktiv ist (d. h., es wurde noch kein Commit ausgeführt bzw. sie wurde nicht abgebrochen).|  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [Leistungsindikatoren für SQL Server XTP &#40;In-Memory OLTP&#41;](../../relational-databases/performance-monitor/sql-server-xtp-in-memory-oltp-performance-counters.md)  
  
  
