---
title: Aufrufen von gespeicherten Prozeduren (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [ODBC], calling
ms.assetid: 31176be8-d40e-4f93-8d44-a46e804a3e2d
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 6b6c57b37948110bca985994686e43f83de6e30b
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47595398"
---
# <a name="running-stored-procedures---call-stored-procedures"></a>Ausführen gespeicherter Prozeduren: Aufrufen gespeicherter Prozeduren
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-ODBC-Treiber unterstützt ausführende gespeicherte Prozeduren als remote gespeicherte Prozeduren. Das Ausführen einer gespeicherten Prozedur als remote gespeicherte Prozedur ermöglicht dem Treiber und dem Server das Optimieren der Leistung der Prozedurausführung.  
  
  Wenn eine SQL-Anweisung eine gespeicherte Prozedur mit der ODBC CALL-Escape-Klausel aufruft, sendet der Microsoft® SQL Server™-Treiber die Prozedur mit dem RPC (Remote Stored Procedure Call)-Mechanismus an SQL Server. RPC-Anforderungen umgehen größtenteils das Analysieren der Anwendungen und die Parameterverarbeitung in SQL Server und sind schneller als die Transact-SQL EXECUTE-Anweisung.  
  
 Eine beispielanwendung, die diese Funktion veranschaulicht wird, finden Sie unter [Prozess Rückgabecodes und Ausgabeparametern &#40;ODBC&#41;](../../relational-databases/native-client-odbc-how-to/running-stored-procedures-process-return-codes-and-output-parameters.md).  
  
### <a name="to-run-a-procedure-as-an-rpc"></a>So führen Sie eine Prozedur als RPC aus  
  
1.  Erstellen Sie eine SQL­Anweisung, die die ODBC CALL-Escapesequenz verwendet. Die Anweisung verwendet Parametermarkierungen für jeden Eingabe-, Eingabe/Ausgabe- und Ausgabeparameter sowie für den Prozedurrückgabewert (falls zutreffend):  
  
    ```  
    {? = CALL procname (?,?)}  
    ```  
  
2.  Rufen Sie [SQLBindParameter](../../relational-databases/native-client-odbc-api/sqlbindparameter.md) für jeden Eingabe-, Eingabe/Ausgabe- und Ausgabeparameter und für die Prozedur Rückgabewert (sofern vorhanden).  
  
3.  Führen Sie die Anweisung mit [SQLExecDirect](http://go.microsoft.com/fwlink/?LinkId=58399).  
  
> [!NOTE]  
>  Wenn eine Anwendung eine Prozedur mit der Transact-SQL EXECUTE-Syntax (statt mit der ODBC CALL-Escapesequenz) übermittelt, gibt der SQL Server ODBC-Treiber den Prozeduraufruf an SQL Server als SQL-Anweisung statt als RPC weiter. Darüber hinaus werden Ausgabeparameter nicht zurückgegeben, wenn die Transact SQL EXECUTE-Anweisung verwendet wird.  
  
## <a name="see-also"></a>Siehe auch  
  [Batchverarbeitung von gespeicherten Prozeduraufrufen](../../relational-databases/native-client-odbc-stored-procedures/batching-stored-procedure-calls.md)   
 [Ausführen gespeicherter Prozeduren](../../relational-databases/native-client-odbc-stored-procedures/running-stored-procedures.md)   
 [Aufrufen einer gespeicherten Prozedur](../../relational-databases/native-client-odbc-stored-procedures/calling-a-stored-procedure.md)   
 [Vorgehensweisen](../../relational-databases/native-client-odbc-queries/executing-statements/procedures.md)  
  
  
