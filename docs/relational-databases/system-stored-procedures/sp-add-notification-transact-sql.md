---
title: Sp_add_notification (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/09/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_add_notification_TSQL
- sp_add_notification
dev_langs:
- TSQL
helpviewer_keywords:
- sp_add_notification
ms.assetid: 0525e0a2-ed0b-4e69-8a4c-a9e3e3622fbd
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: bb19049185ab79178213b1dc042a1c23f8978374
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47704598"
---
# <a name="spaddnotification-transact-sql"></a>sp_add_notification (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Richtet eine Benachrichtigung für eine Warnung ein.  
  
  
## <a name="syntax"></a>Syntax  
  
```  
  
sp_add_notification [ @alert_name = ] 'alert' ,   
    [ @operator_name = ] 'operator' ,   
    [ @notification_method = ] notification_method  
```  
  
## <a name="arguments"></a>Argumente  
 [ **@alert_name=** ] **'***alert***'**  
 Die Warnung für diese Benachrichtigung. *Warnung* ist **Sysname**, hat keinen Standardwert.  
  
 [ **@operator_name=** ] **'***operator***'**  
 Der Operator, der benachrichtigt werden soll, wenn die Warnung auftritt. *Operator* ist **Sysname**, hat keinen Standardwert.  
  
 [  **@notification_method=** ] *Notification_method*  
 Die Methode, durch die der Operator benachrichtigt wird. *Notification_method* ist **Tinyint**, hat keinen Standardwert. *Notification_method* einer oder mehrere der folgenden Werte, die in Kombination mit einem **OR** logischer Operator.  
  
|value|Description|  
|-----------|-----------------|  
|**1**|E-Mail|  
|**2**|Pager|  
|**4**|**net send**|  
  
## <a name="return-code-values"></a>Rückgabecodewerte  
 **0** (Erfolg) oder **1** (Fehler)  
  
## <a name="result-sets"></a>Resultsets  
 None  
  
## <a name="remarks"></a>Hinweise  
 **Sp_add_notification** muss ausgeführt werden, aus der **Msdb** Datenbank.  
  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] kann das gesamte Warnungssystem auf einfache Weise über eine grafische Oberfläche verwaltet werden. Für die Konfiguration einer Warnungsinfrastruktur sollte [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] verwendet werden.  
  
 Zum Senden einer Benachrichtigung als Reaktion auf eine Warnung müssen Sie zunächst den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent für das Senden von E-Mail konfigurieren.  
  
 Wenn beim Senden einer E-Mail- oder Pagerbenachrichtigung ein Fehler auftritt, wird der Fehler im Fehlerprotokoll des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Diensts aufgezeichnet.  
  
## <a name="permissions"></a>Berechtigungen  
 Nur Mitglieder der **Sysadmin** feste Serverrolle **Sp_add_notification**.  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel wird eine E-Mail-Benachrichtigung für die angegebene Warnung (`Test Alert`) hinzugefügt.  
  
> **Hinweis:** in diesem Beispiel wird vorausgesetzt, dass `Test Alert` bereits vorhanden ist und dass `François Ajenstat` ist ein gültiger Operatorname.  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_add_notification  
 @alert_name = N'Test Alert',  
 @operator_name = N'François Ajenstat',  
 @notification_method = 1 ;  
GO  
```  
  
## <a name="see-also"></a>Siehe auch  
 [sp_delete_notification &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-delete-notification-transact-sql.md)   
 [sp_help_notification &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-help-notification-transact-sql.md)   
 [sp_update_notification &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-update-notification-transact-sql.md)   
 [sp_add_operator &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-add-operator-transact-sql.md)   
 [Gespeicherte Systemprozeduren &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
