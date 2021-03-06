---
title: Sp_dbmmonitorupdate (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_dbmmonitorupdate
- sp_dbmmonitorupdate_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_dbmmonitorupdate
- database mirroring [SQL Server], monitoring
ms.assetid: 9ceb9611-4929-44ee-a406-c39ba2720fd5
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: f8ee54383074e624d082d2ab782d6b038fd03d06
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47817060"
---
# <a name="spdbmmonitorupdate-transact-sql"></a>sp_dbmmonitorupdate (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Aktualisiert die Statustabelle des Datenbankspiegelungs-Monitors durch Einfügen einer neuen Tabellenzeile für jede gespiegelte Datenbank und schneidet Zeilen ab, die älter als die aktuelle Beibehaltungsdauer sind. Die Standardbeibehaltungsdauer beträgt 7 Tage (168 Stunden). Beim Aktualisieren der Tabelle **Sp_dbmmonitorupdate** die Leistungsmetriken ausgewertet.  
  
> [!NOTE]  
>  Beim ersten **Sp_dbmmonitorupdate** ausgeführt wird, erstellt den datenbankspiegelungs-Statustabelle und **Dbm_monitor** -Datenbankrolle in der **Msdb** Datenbank.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
sp_dbmmonitorupdate [ database_name ]  
```  
  
## <a name="arguments"></a>Argumente  
 *database_name*  
 Der Name der Datenbank, für die der Spiegelungsstatus aktualisiert wird. Wenn *Database_name* nicht angegeben ist, wird die Prozedur aktualisiert die Statustabelle für jede gespiegelte Datenbank auf der Serverinstanz.  
  
## <a name="return-code-values"></a>Rückgabecodewerte  
 None  
  
## <a name="result-sets"></a>Resultsets  
 None  
  
## <a name="remarks"></a>Hinweise  
 **Sp_dbmmonitorupdate** ausgeführt werden kann, nur im Rahmen der **Msdb** Datenbank.  
  
 Falls eine Spalte der Statustabelle für die Rolle eines Partners nicht gilt, ist der Wert für diesen Partner NULL. Eine Spalte hat auch den Wert NULL, wenn die relevanten Informationen nicht verfügbar sind, z. B. während eines Failovers oder eines Serverneustarts.  
  
 Nach **Sp_dbmmonitorupdate** erstellt die **Dbm_monitor** -Datenbankrolle in der **Msdb** -Datenbank Mitglied der **Sysadmin** feste Serverrolle kann allen Benutzern das Hinzufügen der **Dbm_monitor** festen Datenbankrolle. Die **Dbm_monitor** Rolle ermöglicht ihren Mitgliedern das Anzeigen von Datenbank-Spiegelungsstatus, aber nicht aktualisieren, aber nicht anzeigen oder Konfigurieren der datenbankspiegelung auftretende Ereignisse.  
  
 Beim Aktualisieren des Spiegelungsstatus einer Datenbank **Sp_dbmmonitorupdate** untersucht den aktuellen Wert der aller spiegelungsleistungsmetriken für die ein Schwellenwert für Warnung angegeben wurde. Wenn der Wert den Schwellenwert überschreitet, fügt die Prozedur dem Ereignisprotokoll ein Informationsereignis hinzu. Alle Raten sind seit dem letzten Update Durchschnittswerte. Weitere Informationen finden Sie unter [Verwenden von Warnungsschwellenwerten und Warnmeldungen für Spiegelungsleistungsmetriken &#40;SQL Server&#41;](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md).  
  
## <a name="permissions"></a>Berechtigungen  
 Erfordert die Mitgliedschaft in der festen Serverrolle **sysadmin** .  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel wird der Spiegelungsstatus nur für die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]-Datenbank aktualisiert.  
  
```  
USE msdb;  
EXEC sp_dbmmonitorupdate AdventureWorks2012 ;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Überwachen der Datenbankspiegelung &#40;SQL Server&#41;](../../database-engine/database-mirroring/monitoring-database-mirroring-sql-server.md)   
 [sp_dbmmonitorchangealert &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dbmmonitorchangealert-transact-sql.md)   
 [Sp_dbmmonitorchangemonitoring &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dbmmonitorchangemonitoring-transact-sql.md)   
 [sp_dbmmonitordropalert &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dbmmonitordropalert-transact-sql.md)   
 [sp_dbmmonitorhelpalert &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dbmmonitorhelpalert-transact-sql.md)   
 [Sp_dbmmonitorhelpmonitoring &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dbmmonitorhelpmonitoring-transact-sql.md)   
 [sp_dbmmonitorresults &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dbmmonitorresults-transact-sql.md)  
  
  
