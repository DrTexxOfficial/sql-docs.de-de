---
title: fn_cdc_map_lsn_to_time (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-functions
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to: SQL Server (starting with 2008)
f1_keywords:
- sys.fn_cdc_map_lsn_to_time_TSQL
- sys.fn_cdc_map_lsn_to_time
- fn_cdc_map_lsn_to_time_TSQL
- fn_cdc_map_lsn_to_time
dev_langs: TSQL
helpviewer_keywords:
- sys.fn_cdc_map_lsn_to_time
- fn_cdc_map_lsn_to_time
ms.assetid: 405aa29c-8bd8-42d3-9f39-7494b643fc6f
caps.latest.revision: "15"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 3669075add94708fa90ca02181e805e0e7a36d32
ms.sourcegitcommit: 9fbe5403e902eb996bab0b1285cdade281c1cb16
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2017
---
# <a name="sysfncdcmaplsntotime-transact-sql"></a>sys.fn_cdc_map_lsn_to_time (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Gibt den Wert für Datum und Uhrzeit aus der **Tran_end_time** Spalte in der [lsn_time_mapping](../../relational-databases/system-tables/cdc-lsn-time-mapping-transact-sql.md) -Systemtabelle für die angegebene protokollfolgenummer (LSN). Sie können diese Funktion verwenden, um die LSN-Bereiche den Datumsbereichen in der Änderungstabelle systematisch zuzuordnen.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
sys.fn_cdc_map_lsn_to_time ( lsn_value )  
```  
  
## <a name="arguments"></a>Argumente  
 *lsn_value*  
 Der LSN-Wert, mit dem verglichen werden soll. *lsn_value* ist **binary(10)**  
  
## <a name="return-type"></a>Rückgabetyp  
 **datetime**  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion kann verwendet werden, um auf Basis des in der Änderungsdatenzeile zurückgegebenen **__$start_lsn** -Werts den Zeitpunkt zu bestimmen, zu dem für die Änderung ein Commit erfolgte.  
  
## <a name="permissions"></a>Berechtigungen  
 Erfordert die Mitgliedschaft in der **public** -Rolle.  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel wird mithilfe der `sys.fn_cdc_map_lsn_to_time` -Funktion die Commitzeit bestimmt, die mit der letzten Änderung verknüpft ist, die im angegebenen LSN-Intervall für die `HumanResources_Employee` -Aufzeichnungsinstanz verarbeitet wurde.  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @max_lsn binary(10);  
SELECT @max_lsn = MAX(__$start_lsn)  
FROM cdc.fn_cdc_get_all_changes_HumanResources_Employee(@from_lsn, @to_lsn, 'all');  
SELECT sys.fn_cdc_map_lsn_to_time(@max_lsn);  
GO   
```  
  
## <a name="see-also"></a>Siehe auch  
 [CDC. lsn_time_mapping &#40; Transact-SQL &#41;](../../relational-databases/system-tables/cdc-lsn-time-mapping-transact-sql.md)   
 [Sys. fn_cdc_map_time_to_lsn &#40; Transact-SQL &#41;](../../relational-databases/system-functions/sys-fn-cdc-map-time-to-lsn-transact-sql.md)   
 [CDC. fn_cdc_get_net_changes_ &#60; Capture_instance &#62; &#40; Transact-SQL &#41;](../../relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql.md)   
 [CDC. fn_cdc_get_all_changes_ &#60; Capture_instance &#62;  &#40; Transact-SQL &#41;](../../relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql.md)  
  
  