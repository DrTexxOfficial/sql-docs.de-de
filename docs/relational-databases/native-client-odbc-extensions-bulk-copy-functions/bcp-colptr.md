---
title: Bcp_colptr | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
apiname:
- bcp_colptr
apilocation:
- sqlncli11.dll
apitype: DLLExport
helpviewer_keywords:
- bcp_colptr function
ms.assetid: 02ece13e-1da3-4f9d-b860-3177e43d2471
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 2bb66baa1cfefdeb857641daad0e454a1088d005
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47648278"
---
# <a name="bcpcolptr"></a>bcp_colptr
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  Legt die Datenadresse der Programmvariablen für die aktuelle Kopie in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
RETCODE bcp_colptr (  
        HDBC hdbc,  
        LPCBYTE pData,  
        INT idxServerCol);  
```  
  
## <a name="arguments"></a>Argumente  
 *HDBC*  
 Das für den Massenkopiervorgang aktivierte ODBC-Verbindungshandle.  
  
 *pData*  
 Ist ein Zeiger auf die zu kopierenden Daten. Wenn der gebundene Datentyp ein Typ mit umfangreichen Werten ist (beispielsweise SQLTEXT oder SQLIMAGE), dann kann *pData* NULL sein. Ein *pData* -Zeiger mit dem Wert NULL gibt an, dass lange Datenwerte mithilfe von [bcp_moretext](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-moretext.md)in Ausschnitten an SQL Server gesendet werden.  
  
 Wenn *pData* auf NULL festgelegt wird und die Spalte, die dem gebundenen Feld zugeordnet ist, keinen umfangreichen Datentyp enthält, dann schlägt **bcp_colptr** fehl.  
  
 Weitere Informationen zu Datentypen für umfangreiche Werte finden Sie unter [bcp_bind](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md)**.**  
  
 *idxServerCol*  
 Die Ordnungsposition der Spalte in der Datenbanktabelle, in die die Daten kopiert werden. Die erste Spalte einer Tabelle ist die Spalte 1. Die Ordnungsposition einer Spalte wird von [SQLColumns](../../relational-databases/native-client-odbc-api/sqlcolumns.md)ausgegeben.  
  
## <a name="returns"></a>Rückgabewert  
 SUCCEED oder FAIL.  
  
## <a name="remarks"></a>Hinweise  
 Die **Bcp_colptr** -Funktion können Sie die Adresse der Quelldaten für eine bestimmte Spalte ändern, wenn beim Kopieren von Daten zu SQL Server mit [Bcp_sendrow](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-sendrow.md).  
  
 Anfänglich wird der Zeiger auf Benutzerdaten durch einen Aufruf von **bcp_bind**festgelegt. Wenn sich die Datenadresse der Programmvariablen zwischen Aufrufen von **bcp_sendrow**ändert, können Sie den Zeiger mit einem Aufruf von **bcp_colptr** auf die Datenadresse zurücksetzen. Mit dem nächsten Aufruf von **bcp_sendrow** werden die Daten gesendet, die durch den Aufruf von **bcp_colptr**adressiert wurden.  
  
 Für jede Tabellenspalte, deren Datenadresse geändert werden soll, muss ein separater **bcp_colptr** -Aufruf angegeben werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Massenkopierfunktionen](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
