---
title: Sp_setsubscriptionxactseqno (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology:
- replication
ms.topic: language-reference
f1_keywords:
- sp_setsubscriptionxactseqno
- sp_setsubscriptionxactseqno_TSQL
helpviewer_keywords:
- sp_setsubscriptionxactseqno
ms.assetid: cdb4e0ba-5370-4905-b03f-0b0c6f080ca6
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 6b7bed35293d6bc766047d27e39e18661bfb5be2
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47650348"
---
# <a name="spsetsubscriptionxactseqno-transact-sql"></a>sp_setsubscriptionxactseqno (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Gibt bei der Problembehandlung die Protokollfolgenummer (LSN, Log Sequence Number) der nächsten vom Verteilungs-Agent auf dem Abonnenten anzuwendenden Transaktion an. Der Agent hat dadurch die Möglichkeit, eine Transaktion, die einen Fehler erzeugt hat, auszulassen. Diese gespeicherte Prozedur wird auf dem Abonnenten für die Abonnementdatenbank ausgeführt. Wird nicht für Nicht-SQL Server-Abonnenten unterstützt.  
  
> [!CAUTION]  
>  Eine falsche Verwendung dieser gespeicherten Prozedur oder die Angabe eines falschen LSN-Werts kann den Verteilungs-Agent dazu veranlassen, Änderungen, die bereits auf den Abonnenten angewendet wurden, rückgängig zu machen oder alle noch verbleibenden Änderungen auszulassen.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
sp_setsubscriptionxactseqno [ @publisher = ] 'publisher'  
        , [ @publisher_db = ] 'publisher_db'  
        , [ @publication = ] 'publication'  
        , [ @xact_seqno = ] xact_seqno   
```  
  
## <a name="arguments"></a>Argumente  
 [  **@publisher=** ] **"***Verleger***"**  
 Der Name des Verlegers. *Publisher* ist **Sysname**, hat keinen Standardwert.  
  
 [  **@publisher_db=** ] **"***Publisher_db***"**  
 Der Name der Veröffentlichungsdatenbank. *Publisher_db* ist **Sysname**, hat keinen Standardwert. Für einen nicht - SQL Server-Verleger, *Publisher_db* ist der Name der Verteilungsdatenbank.  
  
 [  **@publication=** ] **"***Veröffentlichung***"**  
 Der Name der Veröffentlichung. *Veröffentlichung* ist **Sysname**, hat keinen Standardwert. Wenn der Verteilungs-Agent von mehreren Veröffentlichungen gemeinsam verwendet wird, müssen Sie angeben, dass einen Wert, der alle für *Veröffentlichung*.  
  
 [  **@xact_seqno=** ] *Xact_seqno*  
 Die LSN der nächsten Transaktion auf dem Verteiler, die auf dem Abonnenten angewendet werden soll. *Xact_seqno* ist **varbinary(16)**, hat keinen Standardwert.  
  
## <a name="result-set"></a>Resultset  
  
|Spaltenname|Datentyp|Description|  
|-----------------|---------------|-----------------|  
|**URSPRÜNGLICHE XACT_SEQNO**|**varbinary(16)**|Die ursprüngliche LSN der nächsten Transaktion, die auf dem Abonnenten angewendet werden soll.|  
|**AKTUALISIERTE XACT_SEQNO**|**varbinary(16)**|Die aktualisierte LSN der nächsten Transaktion, die auf dem Abonnenten angewendet werden soll.|  
|**STREAM-ANZAHL FÜR ABONNEMENT**|**int**|Die Anzahl der bei der letzten Synchronisierung verwendeten Abonnementdatenströme.|  
  
## <a name="return-code-values"></a>Rückgabecodewerte  
 **0** (Erfolg) oder **1** (Fehler)  
  
## <a name="remarks"></a>Hinweise  
 **Sp_setsubscriptionxactseqno** wird in Transaktionsreplikationen verwendet.  
  
 **Sp_setsubscriptionxactseqno** kann nicht in einer Peer-zu-Peer-transaktionsreplikationstopologie verwendet werden.  
  
 **Sp_setsubscriptionxactseqno** können verwendet werden, um eine bestimmte Transaktion zu überspringen, die einen Fehler verursacht, wird beim Anwenden auf dem Abonnenten. Wenn ein Fehler auftritt und der Verteilungs-Agent wird beendet, rufen Sie [Sp_helpsubscriptionerrors &#40;Transact-SQL&#41; ](../../relational-databases/system-stored-procedures/sp-helpsubscriptionerrors-transact-sql.md) auf dem Verteiler, den Xact_seqno-Wert, der die fehlgeschlagene Transaktion abzurufen, und rufen dann **Sp_setsubscriptionxactseqno**, übergeben Sie diesen Wert für *Xact_seqno*. Dadurch wird sichergestellt, dass nur die Befehle nach dieser LSN verarbeitet werden.  
  
 Geben Sie den Wert **0** für *Xact_seqno* , alle ausstehenden Befehle in der Verteilungsdatenbank auf den Abonnenten übertragen.  
  
 **Sp_setsubscriptionxactseqno** kann fehlschlagen, wenn der Verteilungs-Agent Datenströme für mehrere Abonnements verwendet.  
  
 Wenn dieser Fehler auftritt, müssen Sie den Verteilungs-Agent mit einem Datenstrom für ein einzelnes Abonnement ausführen. Weitere Informationen finden Sie unter [Replication Distribution Agent](../../relational-databases/replication/agents/replication-distribution-agent.md).  
  
## <a name="permissions"></a>Berechtigungen  
 Nur Mitglieder der der **Sysadmin** -Serverrolle sein oder **Db_owner** feste Datenbankrolle können ausführen **Sp_setsubscriptionxactseqno**.  
  
  
