---
title: Sys. fn_db_backup_file_snapshots (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 06/03/2015
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-functions
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: TSQL
ms.assetid: 45010ff2-219f-4086-9ea4-016a6c17cddd
caps.latest.revision: "10"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 30988d44e03a40ffcb8317a603b99633c21c8068
ms.sourcegitcommit: 9fbe5403e902eb996bab0b1285cdade281c1cb16
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2017
---
# <a name="sysfndbbackupfilesnapshots-transact-sql"></a>Sys. fn_db_backup_file_snapshots (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  Gibt die Datenbankdateien zugeordnete Azure-Momentaufnahmen zurück. Wenn die angegebene Datenbank nicht gefunden wird, oder wenn die Datenbankdateien nicht in Microsoft Azure Blob Storage Service gespeichert sind, werden keine Zeilen zurückgegeben. Verwenden von dieser Systemfunktion in Verbindung mit der **sp_delete_backup_file_snapshot** gespeicherte Systemprozedur, um zu identifizieren und löschen verwaiste Sicherungsdatei-Momentaufnahmen. Weitere Informationen finden Sie unter [Dateimomentaufnahme-Sicherungen für Datenbankdateien in Azure](../../relational-databases/backup-restore/file-snapshot-backups-for-database-files-in-azure.md).  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
sys.fn_db_backup_file_snapshots   
   [ ( database_name ) ]  
```  
  
## <a name="arguments"></a>Argumente  
 *Datenbankname*  
 Der Name der Datenbank, die abgefragt wird. Wenn der Wert NULL ist, ist diese Funktion im aktuellen Datenbankbereich ausgeführt.  
  
## <a name="table-returned"></a>Zurückgegebene Tabelle  
  
|Spaltenname|Datentyp|Description|  
|-----------------|---------------|-----------------|  
|file_id|**int**|Die Datei-ID für die Datenbank. Lässt keine NULL-Werte zu.|  
|snapshot_time|**nvarchar(260)**|Der Zeitstempel der Momentaufnahme, wie er wird von der REST-API zurückgegeben. Gibt NULL zurück, wenn keine Momentaufnahme vorhanden ist.|  
|snapshot_url|**nvarchar(360)**|Die vollständige URL der dateimomentaufnahme. Gibt NULL, wenn keine Momentaufnahme vorhanden sein.|  
  
## <a name="permissions"></a>Berechtigungen  
 Erfordert die VIEW DATABASE STATE-Berechtigung für die Datenbank.  
  
## <a name="see-also"></a>Siehe auch  
 [Sp_delete_backup_file_snapshot &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/snapshot-backup-sp-delete-backup-file-snapshot.md)   
 [sp_delete_backup &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/snapshot-backup-sp-delete-backup.md)  
  
  