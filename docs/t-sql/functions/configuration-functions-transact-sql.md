---
title: Konfigurationsfunktionen (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 07/24/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- functions [SQL Server], configuration
- configuration options [SQL Server], functions
- current configuration information
- configuration functions [SQL Server]
ms.assetid: 066f15e7-3406-437e-93c4-3f247c529169
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 7f13582bee92fb2deac8765b6adbc717ad7fc67b
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47824178"
---
# <a name="configuration-functions-transact-sql"></a>Konfigurationsfunktionen (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

Diese skalaren Funktionen geben Informationen zu den aktuellen Einstellungen der Konfigurationsoptionen zurück:
  
|||  
|-|-|  
|[@@DATEFIRST](../../t-sql/functions/datefirst-transact-sql.md)|[@@OPTIONS](../../t-sql/functions/options-transact-sql.md)|  
|[@@DBTS](../../t-sql/functions/dbts-transact-sql.md)|[@@REMSERVER](../../t-sql/functions/remserver-transact-sql.md)|  
|[@@LANGID](../../t-sql/functions/langid-transact-sql.md)|[@@SERVERNAME](../../t-sql/functions/servername-transact-sql.md)|  
|[@@LANGUAGE](../../t-sql/functions/language-transact-sql.md)|[@@SERVICENAME](../../t-sql/functions/servicename-transact-sql.md)|  
|[@@LOCK_TIMEOUT](../../t-sql/functions/lock-timeout-transact-sql.md)|[@@SPID](../../t-sql/functions/spid-transact-sql.md)|  
|[@@MAX_CONNECTIONS](../../t-sql/functions/max-connections-transact-sql.md)|[@@TEXTSIZE](../../t-sql/functions/textsize-transact-sql.md)|  
|[@@MAX_PRECISION](../../t-sql/functions/max-precision-transact-sql.md)|[@@VERSION](../../t-sql/functions/version-transact-sql-configuration-functions.md)|  
|[@@NESTLEVEL](../../t-sql/functions/nestlevel-transact-sql.md)||  
  
Alle Konfigurationsfunktionen arbeiten in nicht deterministischer Weise. Das heißt, dass diese Funktionen nicht stets dasselbe Ergebnis zurückgeben, selbst wenn sie mit denselben Eingabewerten aufgerufen werden. Weitere Informationen zu Funktionsdeterminismus finden Sie unter [Deterministische und nicht deterministische Funktionen](../../relational-databases/user-defined-functions/deterministic-and-nondeterministic-functions.md).
  
## <a name="see-also"></a>Siehe auch
[Functions &#40;Transact-SQL&#41; (Funktionen (Transact-SQL))](../../t-sql/functions/functions.md)
  
  
